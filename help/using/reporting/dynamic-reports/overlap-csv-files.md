---
description: Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport peut avoir atteint cette limite lorsque le message "Une erreur inattendue s'est produite" s'affiche. Contactez le service à la clientèle pour demander un fichier .csv compressé, que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.
seo-description: Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport peut avoir atteint cette limite lorsque le message "Une erreur inattendue s'est produite" s'affiche. Contactez le service à la clientèle pour demander un fichier .csv compressé, que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.
seo-title: Fichiers CSV pour les rapports de chevauchement
solution: Audience Manager
title: Fichiers CSV pour les rapports de chevauchement
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: overlap reports
translation-type: tm+mt
source-git-commit: a41f0beffba686f283a2933ad7066cb124e4d380
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 9%

---


# Fichiers CSV pour les rapports de chevauchement{#csv-files-for-overlap-reports}

Vous pouvez demander un fichier .csv pour un rapport de chevauchement lorsque le rapport en question atteint sa limite de 1-million de dossiers. Un rapport peut avoir atteint cette limite lorsque le message &quot;Une erreur inattendue s&#39;est produite&quot; s&#39;affiche. Contactez le service à la clientèle pour demander un fichier .csv compressé, que vous pouvez importer et utiliser dans votre propre système de base de données. Les fichiers sont disponibles pour les rapports de chevauchement segment à segment, segment à caractéristique et caractéristique à caractéristique.

## Métadonnées du nom de fichier {#file-name-metadata}

Le tableau suivant décrit les conventions d’attribution de noms de fichiers et les extensions de fichiers utilisées dans un fichier .csv de chevauchement. Dans les exemples, le texte en *italique* indique un espace réservé de variable.

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
   <td colname="col2"> <p>Les fichiers de rapport de chevauchement sont compressés par gzip et ont une extension de <code> .gz</code> fichier. Vous devez ajouter l’ <code> .csv</code> extension au fichier après la décompression. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom de fichier </p> </td> 
   <td colname="col2"> <p>Syntaxe du nom de fichier : </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Fichiers de segment à segment : <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Fichiers de segment à caractéristique : <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Fichiers de caractéristiques à caractéristiques : <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
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
   <td colname="col2"> <p>Nous incrémentons le dernier chiffre dans le nom de fichier si un rapport contient plusieurs fichiers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exemples </p> </td> 
   <td colname="col2"> <p>Exemples de noms de fichier pour un rapport unique : </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Fichier unique de 7 jours : <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Fichier unique de 30 jours : <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Exemples de noms de fichier pour un rapport contenant plusieurs fichiers : </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contenu du fichier {#file-contents}

Dans le fichier, les données de chaîne sont placées entre guillemets de doublon. Voir les données fictives ci-dessous. Ceci a été tronqué pour la brièveté et pour s&#39;adapter à l&#39;écran.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3","range_id", ...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765", ...
```

## Enregistrements de rapports de segment à segment {#segment-segment-records}

Un fichier de données pour votre rapport [Chevauchement de](segment-segment-overlap-report.md) segment à segment contient les enregistrements suivants.

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
   <td colname="col2"> <p>Nom du segment de base que vous comparez à d’autres segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de recherche en amont de 7 et 30 jours. Le <code> rangeid</code> correspond aux intervalles de temps indiqués ci-dessous. </p> <p> 
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
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques dans le segment que vous comparez au segment de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques dans le segment de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Nombre total de chevauchements d’utilisateurs uniques entre le segment de base et les autres segments sélectionnés pour la comparaison. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>Le pourcentage de chevauchement d’utilisateurs uniques entre le segment de base et les autres segments sélectionnés pour la comparaison. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Enregistrements de rapport Segment-à-Caractéristique {#segment-trait-records}

Un fichier de données pour votre rapport [](segment-trait-overlap-report.md) Chevauchement de segment à caractéristique contient les enregistrements suivants.

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
   <td colname="col2"> <p>ID de caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Nom de la caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. Les ID sont les suivants : </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nom du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de recherche en amont de 7 et 30 jours. Le <code> rangeid</code> correspond aux intervalles de temps indiqués ci-dessous. </p> <p> 
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
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques dans le segment sélectionné. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques d’une caractéristique. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques partagés entre les segments et caractéristiques sélectionnés. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent la caractéristique et le segment. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent le segment et la caractéristique. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Enregistrements de rapport caractéristiques-caractéristiques {#trait-trait-records}

Un fichier de données pour votre rapport [de chevauchement](trait-trait-overlap-report.md) caractéristiques-caractéristiques contient les enregistrements suivants.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Étiquette </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>ID de la caractéristique que vous comparez à la caractéristique de base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
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
   <td colname="col2"> <p>ID du fournisseur de données. Les ID sont les suivants : </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Nom du fournisseur de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>Vous pouvez obtenir des rapports pour des intervalles de recherche en amont de 7 et 30 jours. Le <code> rangeid</code> correspond aux intervalles de temps indiqués ci-dessous. </p> <p> 
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
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques partagés entre les caractéristiques sélectionnées. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques d’une caractéristique de base. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Nombre d’utilisateurs uniques partagés entre les caractéristiques sélectionnées. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent les caractéristiques sélectionnées. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% des utilisateurs uniques qui chevauchent les caractéristiques sélectionnées. Dans le rapport de l’interface utilisateur, ce nombre s’affiche dans la fenêtre contextuelle lorsque vous passez la souris sur une caractéristique des résultats de la carte thermique. </p> </td> 
  </tr> 
 </tbody> 
</table>
