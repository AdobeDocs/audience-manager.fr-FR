---
description: Les composants de collecte de données comprennent les serveurs de collecte de données, l’API DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.
seo-description: Les composants de collecte de données comprennent les serveurs de collecte de données, l’API DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.
seo-title: Composants de collecte de données
solution: Audience Manager
title: Composants de collecte de données
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 1%

---


# Composants de collecte de données{#data-collection-components}

Les composants de collecte de données comprennent les serveurs de collecte de données, l’API DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.

<!-- 

c_compcollect.xml

 -->

L’Audience Manager contient les composants de collecte de données suivants :

* [Serveurs de collecte de données (DCS) et serveurs de mise en cache de Profil (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Bibliothèque d’intégration des données (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Serveur vers serveur entrant](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Fichiers journaux](../../reference/system-components/components-data-collection.md#log-files)

## Serveurs de collecte de données (DCS) et serveurs de mise en cache de Profil (PCS) {#dcs-pcs}

Le serveur de collecte de données et le système de collecte de données fonctionnent ensemble et fournissent séparément des services liés à la réalisation de caractéristiques, à la segmentation des audiences et à l’enregistrement des données.

**[!UICONTROL Data Collection Servers (DCS)]Fonction **

Dans [!DNL Audience Manager]le DCS :

* Récupère et évalue les données de caractéristiques d’un appel de événement. Ceci inclut les informations utilisées pour la segmentation en temps réel et les données transmises à intervalles planifiés par transferts de serveur à serveur.
* Segmente les utilisateurs en fonction de leurs caractéristiques réalisées et des règles de qualification que vous créez avec le créateur de [segments](../../features/segments/segment-builder.md).
* Crée et gère les ID de périphérique et les ID de profil authentifiés. Cela inclut les identifiants tels que les ID de fournisseurs de données, les ID d’utilisateur, les ID déclarés, les codes d’intégration, etc.
* Recherche les caractéristiques supplémentaires qu&#39;un utilisateur a déjà réalisées sur le système PCS avant un appel de événement en temps réel. Cela permet au serveur de collecte de données de qualifier les utilisateurs en fonction de données en temps réel et de données historiques.
* Ecrit des fichiers journaux et les envoie aux systèmes d’analyse pour enregistrement et traitement.

**[!DNL DCS]Gère la demande via[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!DNL DCS] is a geographically distributed and load-balanced system. Cela signifie que [!DNL Audience Manager] les requêtes peuvent être dirigées vers et depuis un centre de données régional en fonction de l’emplacement géographique d’un visiteur de site. Cette stratégie permet d’améliorer les temps de réponse, car une [!DNL DCS] réponse est envoyée directement à un centre de données contenant des informations sur ce visiteur. [!UICONTROL GSLB] rend notre système efficace, car les données pertinentes sont mises en cache sur les serveurs les plus proches de l&#39;utilisateur.

>[!IMPORTANT]
>
>Le [!DNL DCS] filtre détecte uniquement le trafic Web provenant de périphériques qui utilisent IPv4.

Lors d’un appel de événement, l’emplacement géographique est capturé dans une paire clé-valeur renvoyée dans un ensemble plus important de données JSON. Cette paire clé-valeur est le `"dcs_region": region ID` paramètre.

![](assets/dcs-map.png)

En tant que client, vous vous engagez [!DNL DCS] indirectement avec les données par le biais de notre code de collecte de données. Vous pouvez également travailler directement avec les [!DNL DCS] utilisateurs par le biais d’un ensemble d’API. Voir Méthodes et code [API du serveur de collecte de](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)données (DCS).

**[!UICONTROL Profile Cache Servers (PCS)]**

La base de données [!UICONTROL PCS] est volumineuse (en gros, un énorme cookie côté serveur). Il stocke les données reçues pour les utilisateurs actifs à partir des transferts serveur à serveur et du [!DNL DCS]. [!UICONTROL PCS] les données se composent d’ID de périphérique, d’ID de profil authentifiés et de leurs caractéristiques associées. Lorsque l’ [!DNL DCS] utilisateur reçoit un appel en temps réel, il vérifie la [!UICONTROL PCS] présence d’autres caractéristiques auxquelles il peut appartenir ou pour lesquelles il peut être admissible. Et, si une caractéristique est ajoutée ultérieurement à un segment, ces identifiants de caractéristique sont ajoutés au [!UICONTROL PCS] et les utilisateurs peuvent être inclus automatiquement pour ce segment, sans avoir à se rendre sur un site ou une application spécifique. Il [!UICONTROL PCS] permet d’approfondir [!DNL Audience Manager]la compréhension de vos utilisateurs, car il peut associer et segmenter les utilisateurs en temps réel ou en arrière-plan à l’aide de données de caractéristiques nouvelles et historiques. Ce comportement vous donne une image plus complète et plus précise de vos utilisateurs que des seules qualifications en temps réel.

Il n&#39;existe pas de contrôle d&#39;interface utilisateur qui permette à nos clients de travailler directement avec le [!UICONTROL PCS]serveur. L’accès du client à la [!UICONTROL PCS] est indirect, grâce à son rôle de stockage de données et de transfert de données. Le [!UICONTROL PCS] programme fonctionne sur Apache Cassandra.

**Purge des ID inactifs à partir de la variable[!UICONTROL PCS]**

Comme indiqué précédemment, les identifiants de caractéristiques [!UICONTROL PCS] sont stockés pour les utilisateurs actifs. Un utilisateur actif est un utilisateur qui a été vu par les serveurs [de données](../../reference/system-components/components-edge.md) Edge de n’importe quel domaine au cours des 14 derniers jours. Ces appels permettent de [!UICONTROL PCS] garder un utilisateur à l’état actif :

* [!DNL /event] appels
* [!DNL /ibs] appels (synchronisation des identifiants)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Les [!UICONTROL PCS] traits vident s&#39;ils sont inactifs pendant 17 jours. Ces caractéristiques ne sont pas perdues cependant. Ils sont stockés dans Hadoop. Si l’utilisateur est de nouveau vu à un autre moment, Hadoop repousse toutes ses caractéristiques vers le [!UICONTROL PCS]site, généralement dans un délai de 24 heures.

**Autres[!UICONTROL DCS/PCS]processus : Exclusion de la confidentialité**

Ces systèmes de serveur gèrent la confidentialité et les demandes d’exclusion des utilisateurs. Les informations de cookie utilisateur ne sont pas collectées dans le fichier journal si un utilisateur a choisi de ne pas participer à la collecte de données. Pour plus d&#39;informations sur nos politiques de confidentialité, consultez le Centre [de confidentialité](https://www.adobe.com/privacy/advertising-services.html)Adobe.

## Bibliothèque d’intégration des données (DIL){#dil} 

[!UICONTROL DIL] est le code que vous placez sur la page pour la collecte de données. Consultez l’API [](../../dil/dil-overview.md) DIL pour plus d’informations sur les services et méthodes disponibles.

## Serveur vers serveur entrant {#inbound-outbound-server}

Il s&#39;agit de systèmes qui reçoivent des données envoyées par diverses intégrations serveur à serveur avec nos clients. Pour plus d’informations, consultez la documentation sur l’ [envoi de données](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) d’audience.

## Fichiers journaux {#log-files}

L’ [!UICONTROL PCS] utilisateur crée et écrit des données dans les fichiers journaux. Elles sont envoyées à d&#39;autres systèmes de base de données pour traitement, rapports et enregistrement.

>[!MORELIKETHIS]
>
>* [Centre de traitement des données personnelles Adobe](https://www.adobe.com/privacy.html)

