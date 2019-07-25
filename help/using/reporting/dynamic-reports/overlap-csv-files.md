---
description: Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport a peut-être atteint cette limite lorsque le message « Erreur inattendue » s'est produit. Contactez le service d'assistance clientèle pour demander un fichier. csv compressé que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.
seo-description: Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport a peut-être atteint cette limite lorsque le message « Erreur inattendue » s'est produit. Contactez le service d'assistance clientèle pour demander un fichier. csv compressé que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.
seo-title: Fichiers CSV pour les rapports de chevauchement
solution: Audience Manager
title: Fichiers CSV pour les rapports de chevauchement
uuid: 047 e 440 e -00 c 5-4 d 06-a 809-51 d 776326 cd 6
translation-type: tm+mt
source-git-commit: d13b32999c5af4d20f33a92dfa805d7fe0babb2d

---


# Fichiers CSV pour les rapports de chevauchement{#csv-files-for-overlap-reports}

Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport a peut-être atteint cette limite lorsque le message « Erreur inattendue » s'est produit. Contactez le service d'assistance clientèle pour demander un fichier. csv compressé que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.

## File Name Metadata {#file-name-metadata}

Le tableau suivant répertorie et décrit les conventions de dénomination des fichiers et les extensions de fichier utilisées dans un fichier. csv chevauchement. In the examples, *italics* indicates a variable placeholder.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Métadonnées </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Fichier Extension </p> </td> 
   <td colname="col2"> <p>Overlap report files are gzip compressed and have a <code> .gz</code> file extension. You must add the <code> .csv</code> extension to the file after decompression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom de fichier </p> </td> 
   <td colname="col2"> <p>Fichier - syntaxe du nom : </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segment-to-segment files: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Segment-to-trait files: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Trait-to-trait files: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Période </p> </td> 
   <td colname="col2"> <p>La période d'un rapport est un identifiant de 5 chiffres qui comprend : </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> pour un rapport de 7 jours. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> pour un rapport de 30 jours. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs fichiers </p> </td> 
   <td colname="col2"> <p>Nous incrémentons le dernier chiffre du fichier - nom si un rapport contient plusieurs fichiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exemples </p> </td> 
   <td colname="col2"> <p>Fichier - exemples de nom pour un rapport unique : </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Single, 7-day file: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Single, 30-day file: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Fichier - exemples de noms pour un rapport contenant plusieurs fichiers : </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## File Contents {#file-contents}

Dans le fichier, les données de chaîne sont entourées de guillemets doubles. Voir les données mock ci-dessous. Elle a été tronquée pour être abrégée et ajustée à l'écran.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Segment-to-Segment Report Records {#segment-segment-records}

A data file for your [Segment-to-Segment Overlap Report](segment-segment-overlap-report.md) contains the following records.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étiquette </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id 1</code> </p> </td> 
   <td colname="col2"> <p>ID du segment que vous comparez au segment de ligne de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name 1</code> </p> </td> 
   <td colname="col2"> <p>Nom du segment que vous comparez aux segments de ligne de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ id 2</code> </p> </td> 
   <td colname="col2"> <p>ID de votre segment de ligne de base. Le segment de ligne de base est le segment que vous souhaitez comparer à d'autres segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ name 2</code> </p> </td> 
   <td colname="col2"> <p>Nom du segment de ligne de base que vous comparez à d'autres segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de consultation de 7 et 30 jours. <code> Le chemin d'accès</code> correspond aux intervalles de temps indiqués ci-dessous. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 jours </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Date de traitement d'un rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ separate 1</code> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs uniques dans le segment que vous comparez au segment de ligne de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ separate 2</code> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs uniques dans le segment de ligne de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overl_ separated</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de superpositions d'utilisateurs uniques entre le segment de ligne de base et les autres segments sélectionnés pour comparaison. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Chevauchement_ perc</code> </p> </td> 
   <td colname="col2"> <p>Pourcentage de chevauchement d'utilisateurs uniques entre le segment de ligne de base et les autres segments sélectionnés pour comparaison. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment-to-Trait Report Records {#segment-trait-records}

A data file for your [Segment-to-Trait Overlap Report](segment-trait-overlap-report.md) contains the following records.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étiquette </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> pattern_ id</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_ name</code> </p> </td> 
   <td colname="col2"> <p>Nom de la caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. Les ID incluent : </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1 er niveau</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> Tiers</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nom du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de consultation de 7 et 30 jours. <code> Le chemin d'accès</code> correspond aux intervalles de temps indiqués ci-dessous. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 jours </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Date de traitement d'un rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ separate</code> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs uniques dans le segment sélectionné. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> caractéristique_ uniqu</code> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs uniques d'une caractéristique. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overl_ separated</code> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs uniques partagés entre les segments et caractéristiques sélectionnés. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> pattern_ separate_ overl_ perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent la caractéristique et le segment. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_ separate_ overl_ perc</code> </p> </td> 
   <td colname="col2"> <p>% d'utilisateurs uniques qui chevauchent le segment et la caractéristique. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-to-Trait Report Records {#trait-trait-records}

A data file for your [Trait-to-Trait Overlap Report](trait-trait-overlap-report.md) contains the following records.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étiquette </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overl_ trait_ id</code> </p> </td> 
   <td colname="col2"> <p>ID de la caractéristique que vous comparez à la caractéristique de ligne de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overl_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>Nom de la caractéristique que vous comparez à la caractéristique de ligne de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ caractéristique_ id</code> </p> </td> 
   <td colname="col2"> <p>ID de la caractéristique de ligne de base. La caractéristique de ligne de base est la caractéristique que vous souhaitez comparer à d'autres caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ name</code> </p> </td> 
   <td colname="col2"> <p>Nom de la caractéristique de ligne de base que vous comparez à d'autres caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_ type</code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. Les ID incluent : </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1 er niveau</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> Tiers</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nom du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de consultation de 7 et 30 jours. <code> Le chemin d'accès</code> correspond aux intervalles de temps indiqués ci-dessous. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 jours </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Date de traitement d'un rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overl_ caractéristique_ commons</code> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs uniques partagés entre les caractéristiques sélectionnées. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ caractéristique_ commons</code> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs uniques dans une caractéristique de base. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overl_ separated</code> </p> </td> 
   <td colname="col2"> <p>Nombre d'utilisateurs uniques partagés entre les caractéristiques sélectionnées. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overl_ trait_ waves_ overl_ perc</code> </p> </td> 
   <td colname="col2"> <p>% d'utilisateurs uniques qui se chevauchent entre les caractéristiques sélectionnées. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_ trait_ waves_ overl_ perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui se chevauchent entre les caractéristiques sélectionnées. Dans le rapport IU, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte. </p> </td> 
  </tr> 
 </tbody> 
</table>
