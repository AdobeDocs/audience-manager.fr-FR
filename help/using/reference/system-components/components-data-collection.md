---
description: Les composants de collecte de données comprennent les serveurs de collecte de données, l’API DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.
seo-description: Les composants de collecte de données comprennent les serveurs de collecte de données, l’API DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.
seo-title: Composants de collecte de données
solution: Audience Manager
title: Composants de collecte de données
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Composants de collecte de données{#data-collection-components}

Les composants de collecte de données comprennent les serveurs de collecte de données, l’API DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.

<!-- 

c_compcollect.xml

 -->

Audience Manager contient les composants de collecte de données suivants :

* [Serveurs de collecte de données (DCS) et serveurs PCS (Profile Cache Servers)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Bibliothèque d’intégration des données (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Serveur à serveur entrant](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Fichiers journaux](../../reference/system-components/components-data-collection.md#log-files)

## Serveurs de collecte de données (DCS) et serveurs PCS (Profile Cache Servers) {#dcs-pcs}

Le serveur de collecte de données et le système PCS fonctionnent ensemble et fournissent séparément des services liés à la réalisation de caractéristiques, à la segmentation de l’audience et au stockage des données.

**[!UICONTROL Data Collection Servers (DCS)]Fonction**

Dans [!DNL Audience Manager]le DCS :

* Reçoit et évalue les données de caractéristiques d’un appel d’événement. Cela inclut les informations utilisées pour la segmentation en temps réel et les données transmises à intervalles planifiés par transferts de serveur à serveur.
* Segmente les utilisateurs en fonction de leurs caractéristiques réalisées et des règles de qualification que vous créez avec le créateur de [segments](../../features/segments/segment-builder.md).
* Crée et gère les ID de périphérique et les ID de profil authentifiés. Cela inclut les identifiants tels que les ID de fournisseur de données, les ID d’utilisateur, les ID déclarés, les codes d’intégration, etc.
* Vérifie le serveur PCS pour déterminer les caractéristiques supplémentaires qu’un utilisateur a déjà réalisées avant un appel d’événement en temps réel. Cela permet au serveur de collecte de données de classer les utilisateurs en fonction des données en temps réel et des données historiques.
* Ecrit des fichiers journaux et les envoie aux systèmes d’analyse pour stockage et traitement.

**[!UICONTROL DCS]Gère la demande par[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!UICONTROL DCS] is a geographically distributed and load-balanced system. Cela signifie que [!DNL Audience Manager] les requêtes peuvent être dirigées vers et depuis un centre de données régional en fonction de l’emplacement géographique du visiteur du site. Cette stratégie permet d’améliorer les temps de réponse, car une [!UICONTROL DCS] réponse est envoyée directement à un centre de données contenant des informations sur ce visiteur. [!UICONTROL GSLB] rend notre système efficace, car les données pertinentes sont mises en cache dans les serveurs les plus proches de l’utilisateur.

>[!IMPORTANT]
>
>Le [!UICONTROL DCS] système détecte uniquement le trafic Web provenant de périphériques qui utilisent IPv4.

Dans un appel d’événement, l’emplacement géographique est capturé dans une paire clé-valeur renvoyée dans un plus grand nombre de données JSON. Cette paire clé-valeur est le `"dcs_region": region ID` paramètre.

![](assets/dcs-map.png)

En tant que client, vous interagissez avec le [!UICONTROL DCS] indirectement par le biais de notre code de collecte de données. Vous pouvez également travailler directement avec l’application [!UICONTROL DCS] via un ensemble d’API. Voir Méthodes et code [API du serveur de collecte de](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)données (DCS).

**[!UICONTROL Profile Cache Servers (PCS)]**

La [!UICONTROL PCS] base de données est volumineuse (un énorme cookie côté serveur). Il stocke les données reçues pour les utilisateurs actifs à partir des transferts serveur à serveur et du [!UICONTROL DCS]. [!UICONTROL PCS] les données sont constituées d’ID de périphérique, d’ID de profil authentifiés et des caractéristiques associées. Lorsqu’un [!UICONTROL DCS] utilisateur reçoit un appel en temps réel, il vérifie la [!UICONTROL PCS] présence d’autres caractéristiques auxquelles il peut appartenir ou auxquelles il peut être admissible. Et, si une caractéristique est ajoutée à un segment ultérieurement, ces identifiants de caractéristique sont ajoutés au [!UICONTROL PCS] et les utilisateurs peuvent être inclus automatiquement pour ce segment, sans visite sur un site ou une application spécifique. Le [!UICONTROL PCS] guide [!DNL Audience Manager]aide à mieux comprendre vos utilisateurs, car il peut associer et segmenter les utilisateurs en temps réel ou en arrière-plan avec des données de caractéristiques nouvelles et historiques. Ce comportement vous donne une image plus complète et plus précise de vos utilisateurs que des seules qualifications en temps réel.

Il n’existe aucun contrôle d’interface utilisateur qui permet à nos clients de travailler directement avec le [!UICONTROL PCS]. L’accès du client à la [!UICONTROL PCS] est indirect, par le biais de son rôle de stockage de données et de transferts de données. Le [!UICONTROL PCS] programme fonctionne sur Apache Cassandra.

**Purge des ID inactifs à partir de la variable[!UICONTROL PCS]**

Comme indiqué précédemment, les identifiants de caractéristiques [!UICONTROL PCS] sont stockés pour les utilisateurs actifs. Un utilisateur actif est un utilisateur qui a été vu par les serveurs [de données](../../reference/system-components/components-edge.md) Edge depuis n’importe quel domaine au cours des 14 derniers jours. Ces appels permettent de [!UICONTROL PCS] garder un utilisateur actif :

* [!DNL /event] appels
* [!DNL /ibs] appels (synchronisation des identifiants)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Les [!UICONTROL PCS] traits se vident s'ils sont inactifs pendant 17 jours. Ces traits ne sont pas perdus, cependant. Ils sont stockés dans Hadoop. Si l’utilisateur est de nouveau vu à un autre moment, Hadoop repousse toutes ses caractéristiques vers le [!UICONTROL PCS], généralement dans un délai de 24 heures.

**Autres[!UICONTROL DCS/PCS]processus : Exclusion de la confidentialité**

Ces systèmes de serveur traitent les demandes de confidentialité et d’exclusion des utilisateurs. Les informations de cookie utilisateur ne sont pas collectées dans le fichier journal si un utilisateur a choisi de ne pas participer à la collecte de données. Pour plus d’informations sur nos règles de confidentialité, consultez le Centre [de confidentialité](https://www.adobe.com/privacy/advertising-services.html)Adobe.

## Bibliothèque d’intégration des données (DIL){#dil} 

[!UICONTROL DIL] est le code que vous placez sur la page pour la collecte de données. Voir l’API [](../../dil/dil-overview.md) DIL pour plus d’informations sur les services et méthodes disponibles.

## Serveur à serveur entrant {#inbound-outbound-server}

Ce sont des systèmes qui reçoivent des données envoyées par diverses intégrations serveur à serveur avec nos clients. Pour plus d’informations, consultez la documentation sur l’ [envoi des données](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) d’audience.

## Fichiers journaux {#log-files}

Le [!UICONTROL PCS] programme crée et écrit des données dans les fichiers journaux. Elles sont envoyées à d’autres systèmes de base de données pour traitement, création de rapports et stockage.

>[!MORELIKETHIS]
>
>* [Centre de traitement des données personnelles Adobe](https://www.adobe.com/privacy.html)

