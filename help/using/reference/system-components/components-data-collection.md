---
description: Les composants de collecte de données comprennent les serveurs de collecte de données, l’API du DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Composants de collecte de données
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 3%

---

# Composants de collecte de données{#data-collection-components}

Les composants de collecte de données comprennent les serveurs de collecte de données, l’API du DIL, les transferts de données de serveur à serveur entrants et les fichiers journaux.

<!-- 

c_compcollect.xml

 -->

L’Audience Manager contient les composants de collecte de données suivants :

* [ Serveurs de collecte de données (DCS) et serveurs de cache de profils (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Bibliothèque d’intégration des données (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Serveur entrant vers serveur](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Fichiers journaux](../../reference/system-components/components-data-collection.md#log-files)

## Serveurs de collecte de données (DCS) et serveurs de cache de profils (PCS) {#dcs-pcs}

Le serveur de collecte de données et le système de collecte de données fonctionnent ensemble et fournissent séparément des services liés à la réalisation de caractéristiques, à la segmentation de l’audience et au stockage des données.

**[!UICONTROL Data Collection Servers (DCS)]Fonction**

Dans [!DNL Audience Manager], le DCS :

* Reçoit et évalue les données de caractéristique d’un appel d’événement. Cela inclut les informations utilisées pour la segmentation en temps réel et les données transmises à des intervalles planifiés par des transferts serveur à serveur.
* Segmente les utilisateurs en fonction de leurs caractéristiques réalisées et des règles de qualification que vous créez avec le [créateur de segments](../../features/segments/segment-builder.md).
* Crée et gère des identifiants d’appareil et des identifiants de profil authentifiés. Cela inclut les identifiants tels que les identifiants de fournisseur de données, les identifiants utilisateur, les identifiants déclarés, les codes d’intégration, etc.
* Vérifie le PCS pour détecter les caractéristiques supplémentaires qu’un utilisateur a déjà réalisées avant un appel d’événement en temps réel. Cela permet au serveur de collecte de données de qualifier les utilisateurs en fonction de données en temps réel et de données historiques.
* Écrit les fichiers journaux et les envoie aux systèmes d’analyse pour stockage et traitement.

**[!DNL DCS]Gère La Demande Par[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS] est un système géographiquement réparti et dont la charge est équilibrée. Cela signifie que [!DNL Audience Manager] peut diriger les requêtes vers et depuis un centre de données régional en fonction de l’emplacement géographique d’un visiteur du site. Cette stratégie permet d’améliorer les temps de réponse, car une réponse [!DNL DCS] est envoyée directement à un centre de données qui contient des informations sur ce visiteur. [!UICONTROL GSLB] rend notre système efficace, car les données pertinentes sont mises en cache dans les serveurs les plus proches de l’utilisateur.

>[!IMPORTANT]
>
>[!DNL DCS] ne détecte que le trafic web provenant d’appareils qui utilisent IPv4.

Dans un appel d’événement, la position géographique est capturée dans une paire clé-valeur renvoyée dans un plus grand ensemble de données JSON. Cette paire clé-valeur est le paramètre `"dcs_region": region ID` .

![](assets/dcs-map.png)

En tant que client, vous interagissez avec le [!DNL DCS] indirectement via notre code de collecte de données. Vous pouvez également travailler directement avec [!DNL DCS] par le biais d’un ensemble d’API. Voir [Méthodes et code de l’API du serveur de collecte de données (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS] est une base de données volumineuse (en gros, un énorme cookie côté serveur). Il stocke les données reçues pour les utilisateurs actifs provenant des transferts serveur à serveur et du [!DNL DCS]. Les données [!UICONTROL PCS] se composent d’identifiants d’appareil, d’identifiants de profil authentifiés et de leurs caractéristiques associées. Lorsque [!DNL DCS] reçoit un appel en temps réel, il recherche dans [!UICONTROL PCS] d’autres caractéristiques auxquelles un utilisateur peut appartenir ou auxquelles il peut se qualifier. Et, si une caractéristique est ajoutée ultérieurement à un segment, ces identifiants de caractéristique sont ajoutés au [!UICONTROL PCS] et les utilisateurs peuvent être qualifiés pour ce segment automatiquement, sans visite sur un site ou une application spécifique. [!UICONTROL PCS] contribue à approfondir la compréhension de vos utilisateurs par [!DNL Audience Manager], car il peut associer et segmenter les utilisateurs en temps réel ou en coulisses avec de nouvelles données de caractéristiques historiques. Ce comportement vous donne une image plus complète et plus précise de vos utilisateurs que des seules qualifications en temps réel.

Il n’existe aucun contrôle d’interface utilisateur qui permet à nos clients de travailler directement avec [!UICONTROL PCS]. L’accès du client à [!UICONTROL PCS] est indirect, par le biais de son rôle d’entrepôt de données et de transferts de données. Le [!UICONTROL PCS] s’exécute sur Apache Cassandra.

**Purge des identifiants inactifs à partir de[!UICONTROL PCS]**

Comme indiqué précédemment, le [!UICONTROL PCS] stocke les identifiants de caractéristique pour les utilisateurs actifs. Un utilisateur actif est un utilisateur qui a été vu par les [serveurs de données Edge](../../reference/system-components/components-edge.md) de n’importe quel domaine au cours des 14 derniers jours. Ces appels à [!UICONTROL PCS] maintiennent un utilisateur à l’état actif :

* [!DNL /event] appels
* [!DNL /ibs] appels (synchronisations des identifiants)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

Les caractéristiques [!UICONTROL PCS] sont vidées si elles sont inactives pendant 17 jours. Ces caractéristiques ne sont pas perdues cependant. Ils sont stockés dans un Hadoop. Si l’utilisateur est de nouveau consulté à un autre moment, Hadoop renvoie toutes ses caractéristiques à [!UICONTROL PCS], généralement dans un délai de 24 heures.

**Autres [!UICONTROL DCS/PCS] processus : Opt-out de la confidentialité**

Ces systèmes de serveur gèrent la confidentialité et les demandes d’exclusion des utilisateurs. Les informations des cookies utilisateur ne sont pas collectées dans le fichier journal si un utilisateur s’est désabonné de la collecte de données. Pour plus d’informations sur nos politiques de confidentialité, consultez le [Centre de confidentialité des Adobes](https://www.adobe.com/fr/privacy/experience-cloud.html).

## Bibliothèque d’intégration de données (DIL) {#dil}

[!UICONTROL DIL] est le code que vous placez sur la page pour la collecte de données. Pour plus d’informations sur les services et les méthodes disponibles, voir l’ [API DIL](../../dil/dil-overview.md) .

## Serveur entrant vers serveur {#inbound-outbound-server}

Il s’agit de systèmes qui reçoivent des données envoyées par diverses intégrations serveur à serveur avec nos clients. Pour plus d’informations, consultez la documentation sur l’ [envoi de données d’audience](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) .

## Fichiers journaux {#log-files}

Le [!UICONTROL PCS] crée et écrit des données dans les fichiers journaux. Ils sont envoyés à d’autres systèmes de base de données pour traitement, création de rapports et stockage.

>[!MORELIKETHIS]
>
>* [Centre de traitement des données personnelles Adobe](https://www.adobe.com/fr/privacy.html)
