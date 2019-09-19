---
description: Exemples d’utilisation de certaines macros courantes pour créer des modèles de fichiers sortants.
seo-description: Exemples d’utilisation de certaines macros courantes pour créer des modèles de fichiers sortants.
seo-title: Exemples de macro sortante
solution: Audience Manager
title: Exemples de macro sortante
uuid: 823d85d4-d683-45cf-9e60-c12b7d52a498
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Exemples de macro sortante {#outbound-macro-examples}

Exemples d’utilisation de certaines macros courantes pour créer des modèles de fichiers sortants.

>[!NOTE]
>
>Dans les tableaux, le type **boldface** identifie chaque macro avec sa sortie associée. Pour les exemples de format, les `<` symboles `>` ont été ajoutés afin de séparer visuellement chaque macro.

## Macros de nom de fichier {#file-name-macros}

Pour obtenir la liste des macros et des définitions disponibles, voir Macros [](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)de modèles sortants.

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
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output : <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output : <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output : <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Output : </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Complet : <code> ftp_215_888_full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Incrémentiel : <code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ID_ORDRE&gt;_&lt;ID_DPID&gt;_&lt;MODE_SYNC&gt;_&lt;FICHIER&gt;_&lt;FICHIER&gt;.sync </code> </p> <p>Output : </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP : <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3 : <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>Output : <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Macros de rangée d’en-tête {#header-macros}

Pour obtenir la liste des macros et des définitions disponibles, voir Macros [](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)de modèles sortants.

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Exemples de format et de sortie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> TABULATION </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;ID_ORDRE&gt; &lt;TAB&gt;&lt;TYPE_SYNC&gt; </code> </p> <p>Output : <code> 888 full.sync </code> </p> <p>Dans la sortie, le caractère de tabulation non imprimable sépare chaque élément. </p> </td>
  </tr>
 </tbody>
</table>

## Macros de contenu de fichier {#file-content-macros}

Pour obtenir la liste des macros et des définitions disponibles, voir Macros [](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)de modèles sortants.

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
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output : <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output : <code> 123456 UUID1 UUID2 UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>Voir la section distincte ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output : <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Output : <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p><b>Format :</b> </p> <p> 
     <code>
       {"AdvertiserId":"&lt;PIDALIAS&gt;", "DataCenterId": 2,"TDID":"&lt;DP_UUID&gt;", "Data":[&lt;SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;"&lt;CLOSE_CURLY_BRACKET&gt;; separator=","&gt;&lt;if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)&gt;&lt;COMMA&gt;&lt;endif&gt; &lt;REMOVED_SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;", "TtlInMinutes":0&lt;CLOSE_CURator LY_BRACKET&gt;}; separator=","&gt;]} </code></p><p><b>Output :</b></p> <p>
     <code>//Premier exemple {"AdvertiserId":"12345", "DataCenterId": 2, "TDID":"dfd215e4-8d6b-4fdb-90b9-fab4456f2c9d","Data":[{"Name":"43 {"AdvertiserId":"12345", "DataCenterId": 2,"TDID":"9099e8fe-abab-5114-abaa-28bdaa0539ca","Data":["Name"{}}":"4321"},{"Name":"987","TtlInMinutes":0}, {"Name":"654","TtlInMinutes":0}]} </code></p> <p> <p>Remarque :  Dans le premier exemple, la macro renvoie uniquement des données pour <code> SEGMENT_LIST </code> car <code> REMOVED_SEGMENT_LIST </code> est vide. Le deuxième exemple renvoie des données pour les deux macros. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Format: </p> <p> <code> &lt;PID&gt;&lt;TAB&gt;&lt;UUID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt; &lt;SET_ATTRIBUTES&gt;&lt;TAB&gt;&lt;OPT_OUT&gt;&lt;TAB&gt;&lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.alias&gt;,&lt;OUTPUT_ATTRIBUTE_VALUE&gt;,&lt;seg.lastTime&gt;&amp;}&gt; </code> </p> <p>Output : </p> <p> <code> 1159 0008800857968365374151629750971735000 17t0aj01b120 hp 1 0 5 103 714,1 13 44 146 61 000&amp;5 103 713,1 1 134 325 066 1000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TABULATION </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Output : <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>Dans la sortie, le caractère de tabulation non imprimable sépare chaque élément. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format : <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>Output : <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` Exemples

Pour vous aider à comprendre comment la `DPUUID` macro génère des données, supposons que 2 `DPID`s sont mappés sur `DPUUID`des données, comme illustré ci-dessous :

* Le DPID `1111` établit une correspondance avec les DPUUID `AAAA` (horodatage = 1) et `BBBB` (horodatage = 2).
* Le DPID `2222` établit une correspondance avec le DPUUID `CCCC`.

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
   <td colname="col1"> <p>Renvoyer tous les mappages pour un seul DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111|maxMappings=0|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","AAAA"],["1111","BBBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Renvoie un maximum de 1 mappage pour tous les DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111,2222|maxMappings=1|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [[[1111","BBBB"],["2222","CCCC"]] </code> </p> <p>Pour le DPID <code> 1111 </code>, la macro est mappée sur le DPUUID <code> BBBB </code> uniquement parce que cet ID possède l’horodatage le plus grand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Renvoie un maximum de 2 mappages pour un seul DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=2222|maxMappings=2|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222","CCCC"]] </code> </p> <p>Même si <code> maxMappings=2 </code>, cette macro renvoie uniquement 1 DPID au mappage DPUUID, car le DPID spécifié n’a qu’un seul DPUUID. </p> </td> 
  </tr> 
 </tbody> 
</table>

[Macros de création de modèles sortants](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md) (en anglais)