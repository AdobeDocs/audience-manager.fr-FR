---
description: Lors d’un appel, le serveur de collecte de données accepte les données clé-valeur au format standard ou sérialisé. Consultez cette section pour plus d’informations sur le format des données clé-valeur standard et sérialisées.
seo-description: When making a call, the DCS accepts key-value data in standard or serialized format. Review this section for information about how to format standard and serialized key-value data.
seo-title: Formatting Key-Value Pairs in DCS Calls
solution: Audience Manager
title: Formatage des paires clé-valeur dans les appels DCS
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
exl-id: ff2d9ff6-7d5b-4a0d-b831-5d9bc79b32a1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Formatage des paires clé-valeur dans les appels DCS {#formatting-key-value-pairs-in-dcs-calls}

Lors d’un appel , le [!DNL DCS] accepte les données clé-valeur au format standard ou sérialisé. Consultez cette section pour plus d’informations sur le format des données clé-valeur standard et sérialisées.

## Paires clé-valeur standard et sérialisées {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de valeur-clé </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Une paire clé-valeur standard se compose d’une seule clé et d’une seule valeur. Cette structure organise les données en paires clé-valeur distinctes. Chaque clé est indiquée explicitement, même lorsqu’elle est utilisée à nouveau pour définir une valeur différente. Il s’agit de la méthode la plus courante pour envoyer des données au serveur de collecte de données. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Sérialisé</b> </td> 
   <td colname="col2"> <p>Une paire clé-valeur sérialisée se compose d’une seule clé et de plusieurs valeurs. Cela peut être un moyen efficace d’organiser les données, mais les paires clé-valeur sérialisées nécessitent des symboles spécifiques pour séparer chaque clé et chaque jeu clé-valeur. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Délimiteurs et séparateurs pour les paires clé-valeur sérialisées {#delimiters-separators}

Avec des paires clé-valeur sérialisées, vous devez spécifier les marqueurs qui séparent les valeurs au sein de ces variables et entre elles. Audience Manager requiert les délimiteurs et séparateurs suivants :

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Conditions requises pour </th> 
   <th colname="col2" class="entry"> Symbole </th> 
   <th colname="col3" class="entry"> Separates Individual </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b> Délimiteurs </b> </td> 
   <td colname="col2"> Esperluette et </td> 
   <td colname="col3"> <p>Paires clé-valeur : </p> <p><code> key1=val1&amp;key2=val2,val3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Séparateurs</b> </td> 
   <td colname="col2"> Virgule , </td> 
   <td colname="col3"> <p>Valeurs dans les paires clé-valeur : </p> <p><code> key1=val1,val2,val3&amp;key2=valA,valB,valC</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Envoi de données au DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Préfixes et variables clé-valeur pris en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Explication des paires clé-valeur](../../../reference/key-value-pairs-explained.md)
