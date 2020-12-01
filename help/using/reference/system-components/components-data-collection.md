---
description: Les composants de collecte de données comprennent les serveurs de collecte de données, l’API du DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.
seo-description: Les composants de collecte de données comprennent les serveurs de collecte de données, l’API du DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.
seo-title: Composants de collecte de données
solution: Audience Manager
title: Composants de collecte de données
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 6%

---


# Composants de collecte de données{#data-collection-components}

Les composants de collecte de données comprennent les serveurs de collecte de données, l’API du DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.

<!-- 

c_compcollect.xml

 -->

L’Audience Manager contient les composants de collecte de données suivants :

* [Serveurs de collecte de données (DCS) et serveurs PCS (Profil Cache Server)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Bibliothèque d’intégration des données (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Serveur vers serveur entrant](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Fichiers journaux](../../reference/system-components/components-data-collection.md#log-files)

## Serveurs de collecte de données (DCS) et serveurs de mise en cache de Profil (PCS) {#dcs-pcs}

Le serveur de collecte de données et le système de collecte de données fonctionnent ensemble et fournissent séparément des services liés à la réalisation de caractéristiques, à la segmentation des audiences et à l’enregistrement des données.

**[!UICONTROL Data Collection Servers (DCS)]Fonction**

Dans [!DNL Audience Manager], le DCS :

* Récupère et évalue les données de caractéristiques d’un appel de événement. Ceci inclut les informations utilisées pour la segmentation en temps réel et les données transmises à intervalles planifiés par transferts de serveur à serveur.
* Segmente les utilisateurs en fonction de leurs caractéristiques réalisées et des règles de qualification que vous créez avec [Créateur de segments](../../features/segments/segment-builder.md).
* Crée et gère les ID de périphérique et les ID de profil authentifiés. Cela inclut les identifiants tels que les ID de fournisseurs de données, les ID d’utilisateur, les ID déclarés, les codes d’intégration, etc.
* Vérifie les caractéristiques supplémentaires qu&#39;un utilisateur a déjà réalisées avant un appel de événement en temps réel. Cela permet au serveur de collecte de données de qualifier les utilisateurs en fonction de données en temps réel et de données historiques.
* Ecrit des fichiers journaux et les envoie aux systèmes d’analyse pour enregistrement et traitement.

**[!DNL DCS]Gère la demande via[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS] est un système géographiquement réparti et équilibré en charge. Cela signifie que [!DNL Audience Manager] peut diriger les requêtes vers et depuis un centre de données régional en fonction de l&#39;emplacement géographique d&#39;un visiteur de site. Cette stratégie permet d&#39;améliorer les temps de réponse, car une réponse [!DNL DCS] va directement à un centre de données qui contient des informations sur ce visiteur. [!UICONTROL GSLB] rend notre système efficace, car les données pertinentes sont mises en cache sur les serveurs les plus proches de l&#39;utilisateur.

>[!IMPORTANT]
>
>[!DNL DCS] détecte uniquement le trafic Web provenant de périphériques qui utilisent IPv4.

Lors d’un appel de événement, l’emplacement géographique est capturé dans une paire clé-valeur renvoyée dans un ensemble plus important de données JSON. Cette paire clé-valeur est le paramètre `"dcs_region": region ID`.

![](assets/dcs-map.png)

En tant que client, vous interagissez avec [!DNL DCS] indirectement par l&#39;intermédiaire de notre code de collecte de données. Vous pouvez également travailler directement avec [!DNL DCS] via un ensemble d&#39;API. Voir [Méthodes et code d’API du serveur de collecte de données (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS] est une base de données volumineuse (en gros, un énorme cookie côté serveur). Il stocke les données reçues pour les utilisateurs actifs provenant des transferts serveur à serveur et du [!DNL DCS]. Les données [!UICONTROL PCS] se composent d’identifiants d’appareil, d’identifiants de profil authentifiés et de leurs caractéristiques associées. Lorsque [!DNL DCS] reçoit un appel en temps réel, il recherche dans [!UICONTROL PCS] d&#39;autres caractéristiques auxquelles un utilisateur peut appartenir ou pour lesquelles il peut être admissible. Et, si une caractéristique est ajoutée ultérieurement à un segment, ces identifiants de caractéristique sont ajoutés à [!UICONTROL PCS] et les utilisateurs peuvent être inclus automatiquement pour ce segment, sans visite sur un site ou une application spécifique. [!UICONTROL PCS] permet d&#39;approfondir la compréhension de [!DNL Audience Manager] de vos utilisateurs, car il peut associer et segmenter les utilisateurs en temps réel ou en arrière-plan à l&#39;aide de données de caractéristiques nouvelles et historiques. Ce comportement vous donne une image plus complète et plus précise de vos utilisateurs que des seules qualifications en temps réel.

Il n&#39;existe aucun contrôle d&#39;interface utilisateur permettant à nos clients de travailler directement avec [!UICONTROL PCS]. L&#39;accès du client à [!UICONTROL PCS] est indirect, grâce à son rôle de stockage de données et de transfert de données. Le [!UICONTROL PCS] s&#39;exécute sur Apache Cassandra.

**Purge des ID inactifs à partir de la variable[!UICONTROL PCS]**

Comme indiqué précédemment, [!UICONTROL PCS] stocke les ID de caractéristiques pour les utilisateurs principaux. Un utilisateur principal est un utilisateur qui a été vu par les [serveurs de données Edge](../../reference/system-components/components-edge.md) de n&#39;importe quel domaine au cours des 14 derniers jours. Ces appels à [!UICONTROL PCS] maintiennent un utilisateur à l’état principal :

* [!DNL /event] appels
* [!DNL /ibs] appels (synchronisation des identifiants)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

[!UICONTROL PCS] efface les caractéristiques si elles sont inactives pendant 17 jours. Ces caractéristiques ne sont pas perdues cependant. Ils sont stockés en Hadoop. Si l’utilisateur est de nouveau vu à un autre moment, Hadoop repousse toutes ses caractéristiques vers [!UICONTROL PCS], généralement dans un délai de 24 heures.

**Autres  [!UICONTROL DCS/PCS] processus : Exclusion de la confidentialité**

Ces systèmes de serveur gèrent la confidentialité et les demandes d’exclusion des utilisateurs. Les informations de cookie utilisateur ne sont pas collectées dans le fichier journal si un utilisateur a choisi de ne pas participer à la collecte de données. Pour plus d&#39;informations sur nos politiques de confidentialité, consultez le [Adobe Privacy Center](https://www.adobe.com/fr/privacy/experience-cloud.html).

##  Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] est le code que vous placez sur la page pour la collecte de données. Pour plus d&#39;informations sur les services et méthodes disponibles, consultez l&#39;[API du DIL](../../dil/dil-overview.md).

## Serveur entrant vers serveur {#inbound-outbound-server}

Il s&#39;agit de systèmes qui reçoivent des données envoyées par diverses intégrations serveur à serveur avec nos clients. Pour plus d&#39;informations, consultez la documentation sur [l&#39;envoi de données d&#39;audience](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md).

## Fichiers journaux {#log-files}

[!UICONTROL PCS] crée et écrit des données dans les fichiers journaux. Elles sont envoyées à d&#39;autres systèmes de base de données pour traitement, rapports et enregistrement.

>[!MORELIKETHIS]
>
>* [Centre de traitement des données personnelles Adobe](https://www.adobe.com/fr/privacy.html)

