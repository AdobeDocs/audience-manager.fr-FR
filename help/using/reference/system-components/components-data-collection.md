---
description: Les composants de collecte de données comprennent les serveurs de collecte de données, l'API DIL, les transferts de données serveur à serveur entrants et les fichiers journaux.
seo-description: Les composants de collecte de données comprennent les serveurs de collecte de données, l'API DIL, les transferts de données serveur à serveur entrants et les fichiers journaux.
seo-title: Composants de collecte de données
solution: Audience Manager
title: Composants de collecte de données
uuid: 51 bb 1719-5 ff 2-4 bc 7-8 eb 1-98795 e 05 d 08 f
translation-type: tm+mt
source-git-commit: 0b9da38fd8b999637bdf6c3fe6af8aa2426eb6ae

---


# Data Collection Components{#data-collection-components}

Les composants de collecte de données comprennent les serveurs de collecte de données, l'API DIL, les transferts de données serveur à serveur entrants et les fichiers journaux.

<!-- 

c_compcollect.xml

 -->

Audience Manager contient les composants de collecte de données suivants :

* [Serveurs de collecte de données et serveurs de cache de profil (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Bibliothèque d’intégration des données (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Serveur inbound-to-server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Fichiers journaux](../../reference/system-components/components-data-collection.md#log-files)

## Data Collection Servers (DCS) and Profile Cache Servers (PCS) {#dcs-pcs}

Le serveur de collecte de données et les PCS fonctionnent ensemble et fournissent séparément des services liés à la réalisation des caractéristiques, à la segmentation de l'audience et au stockage des données.

**[!UICONTROL Data Collection Servers (DCS)]Fonction**

In [!DNL Audience Manager], the DCS:

* Reçoit et évalue les données de caractéristiques d'un appel d'événement. Ceci inclut les informations utilisées pour la segmentation en temps réel et les données transmises à intervalles planifiés par transfert serveur/serveur.
* Segments users based on their realized traits and the qualification rules you create with [Segment Builder](../../features/segments/segment-builder.md#topic_E166819D26B94A868376BA54E10E4B74).
* Crée et gère les ID de périphérique et les ID de profil authentifiés. Cela inclut les identifiants tels que les identifiants de fournisseurs de données, l'utilisateur - id, les ID déclarés, les codes d'intégration, etc.
* Vérifie les caractéristiques d'autres caractéristiques qu'un utilisateur a déjà obtenues avant un appel d'événement en temps réel. Cela permet au serveur de collecte de données de qualifier les utilisateurs en fonction des données et des données historiques en temps réel.
* Ecrit les fichiers journaux et les envoie aux systèmes d'analyse pour le stockage et le traitement.

**[!UICONTROL DCS]Gère la demande par[!UICONTROL Global Server Load Balancing (GSLB)]**

The [!UICONTROL DCS] is a geographically distributed and load-balanced system. This means [!DNL Audience Manager] can direct requests to and from a regional data center based on the geographic location of a site visitor. This strategy helps improve response times because a [!UICONTROL DCS] response goes directly to a data center that contains information about that visitor. [!UICONTROL GSLB] rend notre système efficace car les données pertinentes sont mises en cache sur les serveurs le plus proche de l'utilisateur.

>[!IMPORTANT]
>
>The [!UICONTROL DCS] only detects web traffic originating from devices that use IPv4.

Dans un appel d'événement, l'emplacement géographique est capturé dans une paire clé-valeur renvoyée dans un corps de données JSON plus important. This key-value pair is the `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

As a customer, you engage with the [!UICONTROL DCS] indirectly through our data collection code. You can also work directly with the [!UICONTROL DCS] through a set of APIs. See [Data Collection Server (DCS) API Methods and Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

The [!UICONTROL PCS] is a large database (basically, a huge server-side cookie). It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] Les données sont constituées d'ID de périphérique, d'ID de profil authentifiés et de caractéristiques associées. When the [!UICONTROL DCS] receives a real time call, it checks the [!UICONTROL PCS] for other traits a user may belong to or qualify for. And, if a trait is added to a segment at a later time, those trait IDs are added to the [!UICONTROL PCS] and users can qualify for that segment automatically, without a visit to a particular site or app. The [!UICONTROL PCS] helps deepen [!DNL Audience Manager]'s understanding of your users because it can match and segment users in real time or behind the scenes with new and historic trait data. Ce comportement vous donne une image plus complète et plus précise de vos utilisateurs que des qualifications en temps réel.

There are no UI controls that lets our customers work directly with the [!UICONTROL PCS]. Customer access to the [!UICONTROL PCS] is indirect, through its role as a data store and data transfers. The [!UICONTROL PCS] runs on Apache Cassandra.

**Purge des identifiants inactifs de la variable[!UICONTROL PCS]**

As indicated previously, the [!UICONTROL PCS] stores trait IDs for active users. An active user is any user who has been seen by the [edge data servers](../../reference/system-components/components-edge.md) from any domain during the last 14-days. These calls to the [!UICONTROL PCS] keep a user in an active state:

* [!DNL /event] appels
* [!DNL /ibs] appels (synchronisation des identifiants)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

The [!UICONTROL PCS] flushes traits if they're inactive for 17-days. Ces caractéristiques ne sont toutefois pas perdues. Elles sont stockées dans Hadoop. If the user is seen again at another time, then Hadoop pushes all of their traits back to the [!UICONTROL PCS], typically within a 24-hour period.

**Autres[!UICONTROL DCS/PCS]processus : Exclusion de confidentialité**

Ces systèmes de serveur traitent les demandes de confidentialité et d'exclusion des utilisateurs. Les informations de cookie utilisateur ne sont pas collectées dans le fichier journal si un utilisateur a désactivé la collecte de données. For more information about our privacy policies see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

## Bibliothèque d’intégration des données (DIL){#dil} 

[!UICONTROL DIL] est le code que vous placez sur la page pour la collecte de données. See the [DIL API](../../dil/dil-overview.md) for more information about available services and methods.

## Inbound Server-to-Server {#inbound-outbound-server}

Il s'agit de systèmes qui reçoivent des données envoyées par diverses intégrations serveur à serveur avec nos clients. See the documentation on [sending audience data](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) for more information.

## Log Files {#log-files}

The [!UICONTROL PCS] creates and writes data to the log files. Elles sont envoyées à d'autres systèmes de base de données pour traitement, création de rapports et stockage.

>[!MORE_ LIKE_ THIS]
>
>* [Centre de traitement des données personnelles Adobe](https://www.adobe.com/privacy.html)

