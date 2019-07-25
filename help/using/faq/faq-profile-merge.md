---
description: Réponses aux questions courantes sur la règle de fusion des profils et le graphique des dispositifs.
keywords: ID d’organisation
seo-description: Réponses aux questions courantes sur la règle de fusion des profils et le graphique des dispositifs.
seo-title: FAQ sur la fusion des profils et le graphique des périphériques
solution: Audience Manager
title: FAQ sur la fusion des profils et le graphique des périphériques
uuid: ba 7986 f 1-078 f -4162-aef 3-b 5 c 8740 cebf 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Merge Rules and Device Graph FAQ{#profile-merge-rules-and-device-graph-faq}

Réponses aux questions courantes sur la règle de fusion des profils et le graphique des dispositifs.

<!-- 

profile-merge-faq.xml

 -->

## Device Graph Basics {#device-graph-basics}

**Qu'est-ce qu'un graphique de périphérique ?**

Un graphique de périphérique est un ensemble de mappages d'ID définissant des groupes de périphériques anonymes. Il associe ces périphériques à une personne ou un foyer en fonction des éléments communs des signaux collectés à partir de chaque périphérique. Ces signaux permettent d'identifier les périphériques au niveau individuel ou du foyer.

<br> 

**Qu'est-ce qu'un graphique de périphérique externe ?**

An external device graph is any device graph in [!DNL Audience Manager] that has not been created exclusively from your own cross-device data sources. For example, when you create a [Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md) and choose the [!UICONTROL Co-op Device Graph] or third-party device graph options, you're working with an external device graph. See [Device Options](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

<br> 

**Quels sont les cas d'utilisation courants d'utilisation d'un graphique de périphérique externe dans[!UICONTROL Profile Merge Rule]une ?**

The main objective of using a device graph in a [!UICONTROL Profile Merge Rule] is to evaluate and qualify multiple devices belonging to a single person or household for a specific segment. Le segment lui-même peut comporter plusieurs utilisations, par exemple cibler une audience de prospects avec et de publicité diffusée par un DSP ou personnaliser l'expérience sur site d'un client via une plateforme de personnalisation sur site. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

<br> 

**Audience Manager fournit-il une prise en charge internationale des graphiques de périphériques externes ?**

Non. Les graphiques de périphériques externes sont disponibles aux États-Unis et au Canada uniquement.

<br> 

**À quelle fréquence[!DNL Audience Manager]les données des graphiques externes de périphériques externes sont-elles mises à jour ?**

Une fois par semaine.

<br> 

## Device Graphs and Profile Merge Rules {#device-graph-profile-merge-rules}

**Comment[!DNL Audience Manager]utiliser un graphique de périphérique ?**

In [!DNL Audience Manager], device graphs appear as configuration options when you [create a Profile Merge Rule](../features/profile-merge-rules/merge-rules-start.md). Through your [!UICONTROL Profile Merge Rules], these device graphs help [!DNL Audience Manager]:

* Fusionnez plusieurs profils de périphérique. Cela crée un seul ensemble de caractéristiques.
* Evaluez le recouvrement de caractéristiques pour la qualification des segments (plutôt que d'évaluer individuellement chaque profil de périphérique).
* Ajoutez des périphériques qualifiés aux segments disponibles.

<br> 

**Combien[!UICONTROL Profile Merge Rules]puis-je créer ?**

Currently, you can create a maximum of 3 [!UICONTROL Profile Merge Rules].

<br> 

**Combien de profils de périphérique[!DNL Audience Manager]fusionnent et lu lors de l'utilisation d'un graphique de périphérique dans[!UICONTROL Profile Merge Rule]un ?**

When qualifying a device for a segment using a [!UICONTROL Profile Merge Rule], Audience Manager merges and reads the current device profile and a maximum of 3 additional device profiles linked by your selected device graph option.

<br> 

**Quels sont les périphériques qui remplissent les critères d'un segment lors de l'utilisation d'un graphique de périphérique dans[!UICONTROL Profile Merge Rule]?**

The devices [!DNL Audience Manager] merges and reads are the same devices that are qualified for a segment.

>[!NOTE]
>
>For external device graphs, [!DNL Audience Manager] stores the mapping between devices at the platform level and selects 3 without evaluating their relationship to the devices seen in your instance of [!DNL Audience Manager].

<br> 

**Quels appareils **peuvent remplir un segment à l'aide d'un[!UICONTROL Profile Merge Rule]graphique de périphérique ?**

To qualify for a segment, devices must have been seen by Audience Manager on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created. En outre, les serveurs Edge :

* Stocker les données de profil pendant 14 jours au maximum.
* Supprimez un profil de périphérique s'il a été inactif pendant plus de 14 jours. Remarque : Cette action supprime uniquement les données du bord. D'autres systèmes conservent les enregistrements pendant des intervalles plus longs. See the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).
* Reset the 14-day interval if [!DNL Audience Manager] records any activity for that profile across the entire platform.

See also, [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**Où[!DNL Audience Manager]peut envoyer les segments qui ont été qualifiés par un[!UICONTROL Profile Merge Rule]graphique de périphérique ?**

[!DNL Audience Manager] peut envoyer des segments à une destination dans des fichiers de traitement par lots ou en temps réel. And, as noted in the FAQ entry above, To qualify for a segment, devices must have been seen by [!DNL Audience Manager] on our [edge data servers](../reference/system-components/components-edge.md) after the segment was created.

<br> 

## Segments, Device Graphs, and Profile Merge Rules {#segments-device-graphs-rules}

**Comment[!DNL Audience Manager]dissocier un périphérique lorsqu'il n'est plus qualifié pour un segment avec un[!UICONTROL Profile Merge Rule]graphique de périphérique ?**

Audience Manager merges up to four devices when evaluating segments with a [!UICONTROL Profile Merge Rule] that uses a device graph. Si le signal de dissociation est émis, le périphérique actuel et trois périphériques supplémentaires vus en temps réel sont supprimés du segment dans la destination. Par exemple, dans une grappe de six périphériques, quatre périphériques au maximum sont fusionnés, évalués et qualifiés pour un segment. De même, jusqu'à quatre périphériques sont fusionnés, évalués et non segmentés.

<br> 

**Si une destination peut ne pas segmenter les périphériques, les périphériques seront-ils supprimés des segments par[!UICONTROL Profile Merge Rules]le biais d'un graphique de périphérique ?**

Oui. Reportez-vous à l'explication ci-dessus.

<br> 

**Si je construise un segment avec un[!UICONTROL Profile Merge Rule]graphique de périphérique et que le segment utilise des données en temps réel et en ligne, mon segment sera-t-il mis à jour lorsque les modifications de données intégrées ?**

Non. Currently, [!DNL Audience Manager] evaluates segments with a [!UICONTROL Profile Merge Rule] that uses a device graph in real-time only. Updates made to on-boarded traits after the segment has been evaluated will be used to qualify the segment when the device is next seen by our [edge data servers](../reference/system-components/components-edge.md). Cela suppose que le profil de périphérique reste actif sur les serveurs Edge et que les données intégrées ont été mises à la disposition de ces systèmes. See also, the [Privacy and Data Retention FAQ](../faq/faq-privacy.md).

<br> 

**Les estimations de taille de segment incluent-elles des périphériques qui remplissent les critères d'un segment selon les connexions fournies par un[!UICONTROL Profile Merge Rule]utilisateur utilisant une option graphique de périphérique ?**

Non. See the definitions for the [!UICONTROL Estimated Real-Time Population] and [!UICONTROL Estimated Total Population] in [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

**[!UICONTROL Addressable Audiences]Les périphériques sont-ils inclus dans un segment selon les connexions fournies par un[!UICONTROL Profile Merge Rule]utilisateur utilisant une option graphique de périphérique ?**

Oui.

<br> 

**Si un segment utilise une[!UICONTROL Profile Merge Rule]variable avec[!UICONTROL No Authenticated Profile]et que les caractéristiques qui qualifient les périphériques pour le segment sont stockées uniquement sur le profil authentifié, la population totale du segment sera-t-elle 0 ?**

Non. Aujourd'hui, Audience Manager compte les périphériques associés au profil authentifié comme étant qualifiés pour le segment.

<br> 

## Trait Frequency, Device Graphs, and Profile Merge Rules {#trait-freq-device-rules}

**Comment[!DNL Audience Manager]calculer la fréquence de caractéristiques avec un[!UICONTROL Profile Merge Rule]graphique de périphérique ?**

La fréquence de caractéristiques est définie par la somme du nombre de qualifications pour une caractéristique spécifique sur plusieurs périphériques. Pour vous aider à comprendre ce problème, observez le cas d'utilisation suivant.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Le périphérique A et le périphérique B sont liés par un graphique de périphérique. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">You have a <span class="wintitle"> Profile Merge Rule</span> that uses a device graph option. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Un segment unique (Segment 1) composé d'une caractéristique unique (Caractéristique 1), où Caractéristique 1 a une fréquence de 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Actions</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> lit et fusionne les profils de périphérique pour le périphérique A et le périphérique B. Voici ce qui suit : </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Le périphérique A est qualifié trois fois pour Caractéristique. Elle a la fréquence 3 pour la caractéristique 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Le périphérique B est qualifié pour la caractéristique 1 fois. Elle a une fréquence de 5 pour Caractéristique 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> additionne la fréquence de Caractéristique 1 et utilise 8 (3 + 5 = 8) pour déterminer la qualification des segments. Le périphérique A et le périphérique B sont admissibles pour le segment 1 parce qu'il a une fréquence de 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

## Reports, Device Graphs, and Profile Merge Rules {#reports-device-graphs-rules}

**Puis-je afficher le nombre de périphériques pouvant être atteints par un[!UICONTROL Profile Merge Rule]graphique utilisant un graphique de périphérique ?**

Oui. Reports return data at the [!UICONTROL Profile Merge Rule] level. Les données du rapport sont mises à jour quotidiennement. Les données sont basées sur les dispositifs affichés dans votre compte et non sur ceux liés par un graphique de périphérique. See [Report Metrics for Profile Merge Rules](../features/profile-merge-rules/profile-link-metrics.md).

<br> 

**Puis-je voir le nombre de périphériques qualifiés pour un segment spécifique en *temps réel*avec[!UICONTROL Profile Merge Rules]un graphique de périphérique ?**

Oui. La mesure de population en temps réel capture les qualifications des segments pour l'appareil actuel (le périphérique affiché en temps réel) à l'aide des profils de tous les dispositifs liés par un graphique de périphérique.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément du cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p>Supposons que nous ayons : </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 basé sur ces caractéristiques et la logique de qualification : Segment 1 = Caractéristique A et Caractéristique B et Caractéristique C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 profils de périphérique : Périphérique 1 (périphérique actuel), Périphérique 2 (graphique de périphérique), Périphérique 3 (graphique de périphérique). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Actions</b> </p> </td> 
   <td colname="col2"> <p>Chaque caractéristique disponible est associée à un périphérique : </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Périphérique 1 : Caractéristique A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Périphérique 2 : Caractéristique B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Périphérique 3 : Caractéristique C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Étant donné les éléments précédents, la population totale du segment 1 est une. </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Cela signifie que les périphériques 1, 2 et 3 sont admissibles pour le segment 1 mais, comme indiqué ci-dessus, seul le périphérique 1 est inclus dans la population de segments en temps réel. Cela est dû au fait que : </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Device 1 is the current device interacting with the Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) in real-time. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Les périphériques 2 et 3 sont associés à Device 1 par un graphique de périphérique, mais ils n'interagissent pas avec le serveur de collecte de données en même temps que le périphérique 1. </li> 
     </ul> </p> <p>Par conséquent, les périphériques 2 et 3 ne sont pas inclus dans la mesure de population de segments en temps réel. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Puis-je voir le nombre total de périphériques qualifiés pour un segment spécifique avec[!UICONTROL Profile Merge Rule]un graphique de périphérique ?**

Oui. La mesure totale de population de segments inclut les périphériques supplémentaires qui sont qualifiés pour un segment en fonction des connexions issues d'un graphique de périphérique.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément du cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p>Supposons que nous ayons : </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 basé sur ces caractéristiques et la logique de qualification : Segment 1 = Caractéristique A et Caractéristique B et Caractéristique C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 profils de périphérique : Périphérique 1 (périphérique actuel), Périphérique 2 (graphique de périphérique), Périphérique 3 (graphique de périphérique). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associations</b> </p> </td> 
   <td colname="col2"> <p>Chaque caractéristique disponible est associée à un périphérique : </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Périphérique 1 : Caractéristique A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Périphérique 2 : Caractéristique B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Périphérique 3 : Caractéristique C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Selon les éléments précédents, la population totale pour Segment 1 est trois (3). </p> <p>In this case, the <span class="wintitle"> Profile Merge Rule</span> uses all the devices and their traits to decide segment qualification. Cela signifie que les périphériques 1, 2 et 3 sont admissibles pour le segment 1 et que les trois sont inclus dans la population totale. </p> </td> 
  </tr> 
 </tbody> 
</table>

<br> 

**Les périphériques qui remplissent les critères d'un segment utilisent-ils[!UICONTROL Profile Merge Rule]un graphique de périphérique inclus dans[!UICONTROL Interactive]les rapports,[!UICONTROL Overlap]rapports et[!UICONTROL Audience Optimization]rapports ?**

Non

>[!MORE_ LIKE_ THIS]
>
>* [Profile Link](../features/profile-merge-rules/merge-rules-overview.md)

