---
description: Exemples d’utilisation de macros courantes pour créer des modèles de fichiers sortants.
seo-description: Examples of how some of the common macros are used to create outbound file templates.
seo-title: Outbound Macro Examples
solution: Audience Manager
title: Exemples de macro sortante
uuid: 823d85d4-d683-45cf-9e60-c12b7d52a498
feature: Outbound Data Transfers
exl-id: 7e3f2b25-7b7c-47fe-aa62-7ebd4e25f9ba
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Exemples de macro sortante {#outbound-macro-examples}

Exemples d’utilisation de macros courantes pour créer des modèles de fichiers sortants.

>[!NOTE]
>
>Dans les tableaux, le type **boldface** identifie chaque macro avec sa sortie associée. Pour les exemples de format, les symboles `<` `>` ont été ajoutés afin de séparer visuellement chaque macro.

## Macros de nom de fichier {#file-name-macros}

Pour obtenir la liste des macros et des définitions disponibles, voir [Macros de modèles sortants](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Exemples de format et de sortie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Sortie : <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Sortie : <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Sortie : <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Sortie : </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Complet : <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Incrémentiel : <code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Sortie : </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP : <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3 : <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>Sortie : <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Macros Rangée d’en-tête {#header-macros}

Pour obtenir la liste des macros et des définitions disponibles, voir [Macros de modèles sortants](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Exemples de format et de sortie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>Sortie : <code> 888 full.sync </code> </p> <p>Dans la sortie, le caractère de tabulation non imprimable sépare chaque élément. </p> </td>
  </tr>
 </tbody>
</table>

## Macros de contenu de fichier {#file-content-macros}

Pour obtenir la liste des macros et des définitions disponibles, voir [Macros de modèles sortants](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Exemples de format et de sortie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;UUID&gt; </code> </p> <p>Sortie : <code> 123456 07955261652886032950143702505894272138 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Sortie : <code> 07955261652886032950143702505894272138 DP_UUID1 DP_UUID2 DP_UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>Consultez la section distincte ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Sortie : <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Sortie : <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p><b>Format :</b> </p> <p> 
     <code>
       {"AdvertiserId":"&lt;PIDALIAS&gt;",&nbsp;"DataCenterId":&nbsp;2,"TDID":"&lt;DP_UUID&gt;", "Data":[&lt;SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;"&lt;CLOSE_CURLY_BRACKET&gt;}; separator=","&gt;&lt;if(SEGMENT_LIST&nbsp;&amp;&amp;&nbsp;REMOVED_SEGMENT_LIST)&gt;&lt;COMMA&gt;&lt;endif&gt; &lt;REMOVED_SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;", "TtlInMinutes":0&lt;CLOSE_CURLY_BRACKET&gt;};&nbsp;separator=","&gt;]}
     </code></p><p><b>Sortie :</b></p> <p>
     <code>//First&nbsp;example {"AdvertiserId":"12345",&nbsp;"DataCenterId":&nbsp;2, "TDID":"dfd215e4-8d6b-4fdb-90b9-fab4456f2c9d","Data":[{"Name":"4321"}]} //Second&nbsp;example {"AdvertiserId":"12345",&nbsp;"DataCenterId":&nbsp;2,"TDID":"9099e8fe-abab-5114-abaa-28bdaa0539ca","Data":[{"Name":"4321"},{"Name":"987","TtlInMinutes":0}, {"Name":"654","TtlInMinutes":0}]} 
     </code></p> <p> <p>Remarque : Dans le premier exemple, la macro renvoie uniquement des données pour <code> SEGMENT_LIST </code>, car <code> REMOVED_SEGMENT_LIST </code> est vide. Le deuxième exemple renvoie des données pour les deux macros. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Format : </p> <p> <code> &lt;PID&gt;&lt;TAB&gt;&lt;UUID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt; &lt;SET_ATTRIBUTES&gt;&lt;TAB&gt;&lt;OPT_OUT&gt;&lt;TAB&gt;&lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.alias&gt;,&lt;OUTPUT_ATTRIBUTE_VALUE&gt;,&lt;seg.lastUpdateTime&gt;&amp;}&gt; </code> </p> <p>Sortie : </p> <p> <code> 1159 00088008579683653741516297509717335000 17t0aj01b120hp 1 0 5,103714,1,1344114661000&amp;5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Sortie : <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>Dans la sortie, le caractère de tabulation non imprimable sépare chaque élément. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>Sortie : <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` Exemples

Pour vous aider à comprendre comment la macro `DPUUID` génère des données, supposons que nous avons 2 `DPID`s mappés à `DPUUID` comme illustré ci-dessous :

* Le DPID `1111` correspond aux DPUUID `AAAA` (horodatage = 1) et `BBBB` (horodatage = 2).
* Le DPID `2222` correspond au DPUUID `CCCC`.

Dans ces conditions, le tableau suivant énumère certaines chaînes de format possibles et leur sortie.

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Condition de mappage </th> 
   <th colname="col2" class="entry"> Format de macro </th> 
   <th colname="col3" class="entry"> Sortie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Renvoie tous les mappages pour un seul DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111|maxMappings=0|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","AAAA"],["1111","BBBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Renvoie un mappage maximal de 1 pour tous les DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111,2222|maxMappings=1|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","BBBB"],["2222","CCCC"]] </code> </p> <p>Pour le DPID <code> 1111 </code>, la macro correspond uniquement au DPUUID <code> BBBB </code>, car cet ID possède un horodatage plus grand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Renvoie un maximum de 2 mappages pour un seul DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=2222|maxMappings=2|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222","CCCC"]] </code> </p> <p>Même si <code> maxMappings=2 </code>, cette macro renvoie uniquement 1 mapping DPID vers DPUUID, car le DPID spécifié n’a qu’un seul DPUUID. </p> </td> 
  </tr> 
 </tbody> 
</table>

[Macros de modèles sortants](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)
