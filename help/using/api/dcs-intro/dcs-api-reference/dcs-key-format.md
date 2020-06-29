---
description: Lors d’un appel, le serveur de collecte de données accepte les données de valeur de clé dans un format standard ou sérialisé. Consultez cette section pour savoir comment formater les données de valeur de clé standard et sérialisées.
seo-description: Lors d’un appel, le serveur de collecte de données accepte les données de valeur de clé dans un format standard ou sérialisé. Consultez cette section pour savoir comment formater les données de valeur de clé standard et sérialisées.
seo-title: Formatage des paires clé-valeur dans les appels DCS
solution: Audience Manager
title: Formatage des paires clé-valeur dans les appels DCS
uuid: af02f2a1-4388-4074-ab4e-66ee82023f1c
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 1%

---


# Formatage des paires clé-valeur dans les appels DCS {#formatting-key-value-pairs-in-dcs-calls}

Lors d’un appel, la fonction [!DNL DCS] accepte les données de valeur de clé dans un format standard ou sérialisé. Consultez cette section pour savoir comment formater les données de valeur de clé standard et sérialisées.

## Paires de valeurs clés standard et sérialisées {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type clé-valeur </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Une paire clé-valeur standard est composée d’une seule clé et d’une seule valeur. Cette structure organise les données en paires clé-valeur distinctes. Chaque clé est explicitement mentionnée, même lorsqu’elle est à nouveau utilisée pour définir une autre valeur. Il s’agit de la méthode la plus courante pour envoyer des données au serveur de collecte de données. </p> </td>
   <td colname="col3"> <code> key1=val1&amp;key2=val2&amp;key3=val3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Sérialisé</b> </td> 
   <td colname="col2"> <p>Une paire clé-valeur sérialisée se compose d’une seule clé et de plusieurs valeurs. Il peut s’agir d’un moyen efficace d’organiser les données, mais les paires clé-valeur sérialisées nécessitent des symboles spécifiques pour séparer chaque clé et chaque jeu clé-valeur. </p> </td> 
   <td colname="col3"> <code> key1=val1,val2,val3</code> </td> 
  </tr>
 </tbody>
</table>

## Délimiteurs et séparateurs pour les paires clé-valeur sérialisées {#delimiters-separators}

Avec les paires clé-valeur sérialisées, vous devez spécifier les marqueurs qui séparent les valeurs au sein de ces variables et entre elles. L’Audience Manager requiert les délimiteurs et séparateurs suivants :

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Conditions requises pour </th> 
   <th colname="col2" class="entry"> Symbole </th> 
   <th colname="col3" class="entry"> Sépare un individu </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Délimiteurs</b> </td> 
   <td colname="col2"> Esperluette &amp; </td> 
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
>* [Envoyer des données au serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Préfixes et variables de valeur de clé pris en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Paires clé-valeur expliquées](../../../reference/key-value-pairs-explained.md)

