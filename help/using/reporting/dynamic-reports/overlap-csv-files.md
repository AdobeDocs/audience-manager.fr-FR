---
description: Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport a peut-être atteint cette limite lorsqu’un message "Une erreur inattendue s’est produite" s’affiche. Contactez le service à la clientèle pour demander un fichier .csv compressé, que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.
seo-description: Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport a peut-être atteint cette limite lorsqu’un message "Une erreur inattendue s’est produite" s’affiche. Contactez le service à la clientèle pour demander un fichier .csv compressé, que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.
seo-title: Fichiers CSV pour les rapports de chevauchement
solution: Audience Manager
title: Fichiers CSV pour les rapports de chevauchement
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
translation-type: tm+mt
source-git-commit: d13b32999c5af4d20f33a92dfa805d7fe0babb2d

---


# Fichiers CSV pour les rapports de chevauchement{#csv-files-for-overlap-reports}

Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport a peut-être atteint cette limite lorsqu’un message "Une erreur inattendue s’est produite" s’affiche. Contactez le service à la clientèle pour demander un fichier .csv compressé, que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.

## Métadonnées du nom de fichier {#file-name-metadata}

Le tableau suivant répertorie et décrit les conventions d’appellation des fichiers et les extensions de fichiers utilisées dans un fichier .csv de chevauchement. In the examples, *italics* indicates a variable placeholder.

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
   <td colname="col2"> <p>Les fichiers de rapport de chevauchement sont compressés au format gzip et ont une extension de fichier <code> .gz</code> . Vous devez ajouter l’extension <code> .csv</code> au fichier après la décompression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom de fichier </p> </td> 
   <td colname="col2"> <p>Syntaxe du nom de fichier : </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Fichiers de segment à segment : <code>S2S_duplicate_<i>partenaire ID</i>_<i>aaaa-mm-jj</i>_plage de<i>dates</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Fichiers de segment à caractéristique : <code>S2T_duplicate_<i>partenaire ID</i>_<i>aaaa-mm-jj</i>_plage de<i>dates</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Fichiers de caractéristiques à caractéristiques : <code>T2T_duplicate_<i>partner ID</i>_<i>aaaa-mm-jj</i>_plage de<i>dates</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Période </p> </td> 
   <td colname="col2"> <p>La plage de dates d’un rapport est un identifiant à 5 chiffres qui comprend : </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> pour un rapport de 7 jours. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> pour un rapport de 30 jours. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fichiers multiples </p> </td> 
   <td colname="col2"> <p>Nous incrémentons le dernier chiffre dans le nom du fichier si un rapport contient plusieurs fichiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exemples </p> </td> 
   <td colname="col2"> <p>Exemples de noms de fichier pour un rapport unique : </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Fichier unique de 7 jours : <code> S2S_overview_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Fichier unique de 30 jours : <code> S2S_overview_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Exemples de noms de fichier pour un rapport avec plusieurs fichiers : </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overview_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overview_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overview_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contenu du fichier {#file-contents}

Dans le fichier, les données de chaîne sont entourées de guillemets doubles. Voir les données fictives ci-dessous. Ceci a été tronqué pour la brièveté et pour s'adapter à l'écran.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Enregistrements de rapports Segment à Segment {#segment-segment-records}

Un fichier de données pour votre rapport [de chevauchement](segment-segment-overlap-report.md) segment-à-segment contient les enregistrements suivants.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étiquette </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>ID du segment que vous comparez au segment de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>Nom du segment que vous comparez aux segments de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>ID de votre segment de base. Le segment de base est le segment que vous souhaitez comparer aux autres segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>Nom du segment de ligne de base que vous comparez à d’autres segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de 7 et 30 jours. Le <code> range</code> correspond aux intervalles de temps illustrés ci-dessous. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 jours </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Date de traitement d’un rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_unique1</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques dans le segment que vous comparez au segment de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_unique2</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques dans le segment de ligne de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_unique</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de chevauchements d’utilisateurs uniques entre le segment de base et les autres segments sélectionnés pour la comparaison. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>Le pourcentage de chevauchement des utilisateurs uniques entre le segment de base et les autres segments sélectionnés pour la comparaison. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Enregistrements de rapport Segment-à-Caractéristique {#segment-trait-records}

Un fichier de données pour votre rapport [de chevauchement](segment-trait-overlap-report.md) segment-à-caractéristique contient les enregistrements suivants.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étiquette </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p> ID de caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nom du trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. Les identifiants incluent : </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1re partie</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> tiers</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nom du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de 7 et 30 jours. Le <code> range</code> correspond aux intervalles de temps illustrés ci-dessous. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 jours </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Date de traitement d’un rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_unique</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques dans le segment sélectionné. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_unique</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques dans une caractéristique. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_unique</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques partagés entre les segments et caractéristiques sélectionnés. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_unique_duplicate_perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent la caractéristique et le segment. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_unique_duplicate_perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent le segment et la caractéristique. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Enregistrements de rapport Caractéristique-Caractéristique {#trait-trait-records}

Un fichier de données pour votre rapport [Chevauchement de](trait-trait-overlap-report.md) caractéristiques à caractéristiques contient les enregistrements suivants.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étiquette </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID de la caractéristique que vous comparez à la caractéristique de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nom de la caractéristique que vous comparez à la caractéristique de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID de votre caractéristique de base. La caractéristique de base est la caractéristique que vous souhaitez comparer à d’autres caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nom de la caractéristique de base que vous comparez à d'autres caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. Les identifiants incluent : </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1re partie</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> tiers</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nom du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de 7 et 30 jours. Le <code> range</code> correspond aux intervalles de temps illustrés ci-dessous. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 jours </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 jours </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>Date de traitement d’un rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_trait_unique</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques partagés entre les caractéristiques sélectionnées. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_unique</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques dans une caractéristique de base. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_unique</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques partagés entre les caractéristiques sélectionnées. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> duplicate_trait_unique_overl_perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent les caractéristiques sélectionnées. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_unique_duplicate_perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent les caractéristiques sélectionnées. Dans le rapport de l’interface utilisateur, ce nombre apparaît dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique dans les résultats de la carte thermique. </p> </td> 
  </tr> 
 </tbody> 
</table>
