---
description: Répertorie les macros que vous pouvez utiliser pour créer des modèles sortants. Il s’agit notamment des macros de nom de fichier, des macros d’en-tête et des macros de contenu.
seo-description: Répertorie les macros que vous pouvez utiliser pour créer des modèles sortants. Il s’agit notamment des macros de nom de fichier, des macros d’en-tête et des macros de contenu.
seo-title: Macros de création de modèles sortants (en anglais)
solution: Audience Manager
title: Macros de création de modèles sortants (en anglais)
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
translation-type: tm+mt
source-git-commit: 94984d14be6febf4de3ee3e0e79fba432e1cb15f

---


# Macros de création de modèles sortants{#outbound-template-macros} (en anglais)

Répertorie les macros que vous pouvez utiliser pour créer des modèles sortants. Il s’agit notamment des macros de nom de fichier, des macros d’en-tête et des macros de contenu.

## Macros Nom de fichier et En-tête de fichier {#file-name-header-macros}

Le tableau répertorie et décrit les macros que vous pouvez utiliser dans le nom de fichier et pour définir les champs d’en-tête. Pour consulter des exemples de code, reportez-vous à la page Exemples [](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)de macro sortante.

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>Caractère ASCII non imprimable. Il indique le début d’une ligne ou d’une section de contenu. Il peut également être utilisé pour séparer les colonnes de données dans un fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>ID utilisateur Identifiant du fournisseur de données de clé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Permet de créer des en-têtes multilignes pour les commandes sortantes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID de commande/destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>alias d’un ID de commande/destination. </p> <p>L’alias est défini dans l’interface utilisateur d’administration. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Indique le fractionnement de fichiers sortants en plusieurs parties. Remplacez la section SPLITNUM du nom de fichier par le numéro de pièce précédé de zéros, ce qui garantit un minimum de trois caractères pour la section SPLITNUM.</p>
   <p>La macro SPLITNUM ne doit pas nécessairement être entourée de caractères &lt;&gt;.</p><p>Exemple: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>Les trois derniers chiffres (001,002,003) dans les exemples ci-dessus sont les identifiants SPLITNUM.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indique le type de synchronisation et inclut : </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Synchronisation complète. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Synchronisation incrémentielle. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indique la méthode de transfert de données et inclut : </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilisée comme séparateur, cette macro insère un onglet entre les champs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Horodatage à 10 chiffres, UTC, Unix. </p> <p>Il peut également être formaté selon les règles de formatage de date et d’horodatage Java <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> suivantes. </p> </td> 
  </tr>

</tbody> 
</table>

## Macros de contenu {#content-macros}

Macros utilisées pour formater le contenu d’un fichier de données. Pour consulter des exemples de code, reportez-vous à la page Exemples [](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)de macro sortante.

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Insère un caractère d’accolade proche }. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Identifiant utilisateur unique du fournisseur de données </span>. </p> <p>Il s’agit de l’identifiant du partenaire de données auquel vous envoyez des données dans un fichier sortant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Renvoie une liste qui contient plusieurs ID pour un partenaire de données. Cela s’avère utile si vous disposez d’une grande organisation avec plusieurs subdivisions ou d’autres groupes d’organisation avec lesquels vous êtes autorisé à partager des données. Cette macro renvoie une liste des ID pour ces groupes subordonnés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>La sortie de cette macro mappe l’ID de fournisseur de données (DPID) aux ID d’utilisateur uniques associés (DPUUID). Cette macro doit avoir une chaîne de formatage pour contrôler sa sortie. L’exemple de sortie se présente comme suit : </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>Le <code> maxMappings </code> paramètre détermine le nombre de correspondances que vous souhaitez voir renvoyer la macro. Lorsque <code> maxMappings=0 </code>cette macro renvoie tous les mappages pour chaque DPID spécifié. Les données sont triées par horodatage (le plus récent en premier) et renvoient d’abord les résultats avec l’horodatage le plus grand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>Cette combinaison de macros crée une instruction conditionnelle qui répertorie les segments auxquels les utilisateurs appartiennent et dont ils ont été supprimés. Elle renvoie une chaîne vide si les deux conditions ne sont pas remplies ou s’il n’y a aucune donnée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud </span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Insère un caractère d’accolade ouvert {. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Obsolète. N’utilisez pas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>ID de commande ou de destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Obsolète. N’utilisez pas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Renvoie <code> 1 </code> une valeur statique codée en dur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>ID de partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>alias d’un ID de commande/destination. </p> <p>L’alias est défini dans l’interface utilisateur d’administration. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Renvoie une liste de segments, le cas échéant, qui ont été supprimés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Renvoie une liste de segments dans une liste. Accepte les arguments facultatifs suivants : </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>: ID de segment. Obsolète. Utilisez <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: ID de segment du client. Obsolète. Utilisez <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: ID de segment </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Renvoie <code> 5 </code>, une valeur statique codée en dur qui identifie les données comme des données de segment. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Obsolète. N’utilisez pas. </li> 
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: Horodatage Unix indiquant la dernière fois qu’un segment a été réalisé. </li> 
    </ul> <p>Placez ces variables entre accolades après la macro. Par exemple, ce code sépare les résultats par un caractère "|" de barre verticale : <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Renvoie <code> 1 </code>une valeur figée codée en dur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Indique le type de synchronisation et inclut : </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Synchronisation complète. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Synchronisation incrémentielle. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Indique la méthode de transfert de données et inclut : </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Utilisée comme séparateur, cette macro insère un onglet entre les champs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Renvoie une liste de caractéristiques. Accepte les arguments facultatifs suivants : </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifie les types de caractéristiques par ID numérique. Retours: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> qui identifie une caractéristique DPM (hors ligne, intégrée par une tâche entrante). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> qui identifie une caractéristique basée sur des règles (en temps réel, intégrée via le serveur de collecte de données). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: ID de caractéristique. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: La dernière fois que le trait a été réalisé. Horodatage Unix. </li> 
    </ul> <p>Placez ces variables entre accolades après la macro. Par exemple, ce code sépare les résultats par un caractère "|" en barre verticale : <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> ID </span> utilisateur d’Audience Manager. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Exemples de macro sortante](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

