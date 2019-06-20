---
description: 'Répertorie les macros que vous pouvez utiliser pour créer des modèles sortants. Ces fichiers incluent le fichier : nom macros, macros d''en-tête et macros de contenu.'
seo-description: 'Répertorie les macros que vous pouvez utiliser pour créer des modèles sortants. Ces fichiers incluent le fichier : nom macros, macros d''en-tête et macros de contenu.'
seo-title: Macros de création de modèles sortants (en anglais)
solution: Audience Manager
title: Macros de création de modèles sortants (en anglais)
uuid: dec 082 d 3-306 b -4 ff 5-afb 2-418 bd 543 d 8 d 0
translation-type: tm+mt
source-git-commit: c5f9845a48d9d4432f38e9a0aaa256d89f9c1c11

---


# Macros de création de modèles sortants{#outbound-template-macros} (en anglais)

Répertorie les macros que vous pouvez utiliser pour créer des modèles sortants. Ces fichiers incluent le fichier : nom macros, macros d&#39;en-tête et macros de contenu.

## File Name and File Header Macros {#file-name-header-macros}

Le tableau répertorie et décrit les macros que vous pouvez utiliser dans le fichier - nom et pour définir les champs d&#39;en-tête. For code samples, see [Outbound Macro Examples](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_ SOH </code> </p> </td> 
   <td colname="col2"> <p>Caractère ASCII non imprimable. Il indique le début d'une ligne ou d'une section de contenu. Il peut également être utilisé pour séparer les colonnes de données d'un fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Identifiant du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_ DPID </code> </p> </td> 
   <td colname="col2"> <p>User - ID de fournisseur de données de clé d'ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>ID de commande/de destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Un alias pour un ID de commande/de destination. </p> <p>L'alias est défini dans l'interface utilisateur d'administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Indique le type de synchronisation et inclut : </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Synchronisation complète. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Synchronisation incrémentielle. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indique la méthode de transfert de données et inclut : </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilisé comme séparateur, cette macro insère un onglet entre les champs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Un horodatage de 10 chiffres, UTC, Unix. </p> <p>It can also be formatted as <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> following Java date/timestamp formatting rules. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Content Macros {#content-macros}

Macros utilisées pour formater le contenu d&#39;un fichier de données. For code samples, see [Outbound Macro Examples](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_ CURLY_ BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Insère un caractère de crochet fermant}. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Identifiant utilisateur unique du fournisseur de données </span>. </p> <p>Il s'agit de l'identifiant du partenaire de données que vous envoyez aux données dans un fichier sortant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_ UUID_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Renvoie une liste contenant plusieurs ID pour un partenaire de données. Cela s'avère utile si vous disposez d'une grande organisation comptant plusieurs sous-divisions ou d'autres groupes d'organisations auxquels vous êtes autorisé à partager des données. Cette macro renvoie la liste des identifiants de ces groupes subordonnés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Identifiant du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>La sortie de cette macro associe l'identifiant du fournisseur de données (DPID) à l'utilisateur unique associé - id (DPUUID). Cette macro doit disposer d'une chaîne de formatage pour contrôler sa sortie. L'exemple de sortie ressemble à ce qui suit : </p> <p> <code> « dpids = dpid 1, dpid 2,… dpid n | maxmappings = n | format = json » </code> </p> <p>The <code> maxMappings </code> setting determines how many mappings you want the macro to return. When <code> maxMappings=0 </code>, this macro returns all the mappings for each specified DPID. Les données sont triées par horodatage (le plus récent d'abord) et renvoie d'abord les résultats avec le plus grand horodatage. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if (SEGMENT_ LIST &amp; &amp; REMOVED_ SEGMENT_ LIST) endif </code> </p> </td> 
   <td colname="col2"> <p>Cette combinaison de macros crée une instruction conditionnelle qui répertorie les segments auxquels les utilisateurs appartiennent et qui ont été supprimés. Elle renvoie une chaîne vide si les deux conditions ne sont pas remplies ou qu'il n'y a aucune donnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_ CURLY_ BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Insère une accolade {caractère. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_ OUT </code> </p> </td> 
   <td colname="col2"> <p>Obsolète. N'utilisez pas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ ID </code> </p> </td> 
   <td colname="col2"> <p>ID de commande ou de destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ ATTRIBUTE_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Obsolète. N'utilisez pas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ ATTRIBUTE_ VALUE </code> </p> </td> 
   <td colname="col2"> <p>Returns <code> 1 </code> as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>ID du partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Un alias pour un ID de commande/de destination. </p> <p>L'alias est défini dans l'interface utilisateur d'administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_ SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Renvoie une liste de segments, le cas échéant, supprimés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Renvoie une liste de segments dans une liste. Accepte les arguments facultatifs suivants : </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> Segmentid </code>: Identifiant du segment. Obsolète. Use <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: Identifiant du segment client. Obsolète. Use <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: ID de segment </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Renvoie <code> 5 </code>, valeur figée et figée dans le code qui identifie les données comme données de segment. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Obsolète. N'utilisez pas. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> Lastupdatetime </code>: Horodatage Unix qui indique la dernière fois qu'un segment a été réalisé. </li> 
    </ul> <p>Placez ces variables entre accolades après la macro. For example, this code separates results with a pipe "|" character: <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Returns <code> 1 </code>, as a static, hardcoded value. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ MODE </code> </p> </td> 
   <td colname="col2"> <p>Indique le type de synchronisation et inclut : </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Synchronisation complète. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Synchronisation incrémentielle. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_ TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indique la méthode de transfert de données et inclut : </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s 3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilisé comme séparateur, cette macro insère un onglet entre les champs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_ LIST </code> </p> </td> 
   <td colname="col2"> <p>Renvoie une liste de caractéristiques. Accepte les arguments facultatifs suivants : </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifie les types de caractéristiques par identifiant numérique. Retours: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> qui identifie une caractéristique DPM (hors ligne, intégrée à une tâche inentrante). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> qui identifie une caractéristique basée sur des règles (en temps réel, intégrée via le serveur de collecte de données). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> Traitid </code>: identifiant de caractéristique. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> Lastrealized </code>: La dernière fois que la caractéristique a été réalisée. Horodatage Unix. </li> 
    </ul> <p>Placez ces variables entre accolades après la macro. For example, this code separates the results with a pipe "|" character: <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Utilisateur Audience Manager </span> - id. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Exemples de macro sortante](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

