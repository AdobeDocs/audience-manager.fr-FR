---
description: Lors d'un appel, le serveur de collecte de données accepte les données clé-valeur au format standard ou sérialisé. Consultez cette section pour plus d'informations sur la mise en forme des données standard et sérialisées de valeurs de clé.
seo-description: Lors d'un appel, le serveur de collecte de données accepte les données clé-valeur au format standard ou sérialisé. Consultez cette section pour plus d'informations sur la mise en forme des données standard et sérialisées de valeurs de clé.
seo-title: Mise en forme des paires clé-valeur dans les appels DCS
solution: Audience Manager
title: Mise en forme des paires clé-valeur dans les appels DCS
uuid: af 02 f 2 a 1-4388-4074-ab 4 e -66 ee 82023 f 1 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Formatting Key-Value Pairs in DCS Calls {#formatting-key-value-pairs-in-dcs-calls}

When making a call, the [!UICONTROL DCS] accepts key-value data in standard or serialized format. Consultez cette section pour plus d'informations sur la mise en forme des données standard et sérialisées de valeurs de clé.

## Standard and Serialized Key-Value Pairs {#standard-serialized}

<table id="table_A220F9B359F34C6EA7B83618FC22EE3A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de valeur clé </th> 
   <th colname="col2" class="entry"> Description </th> 
   <th colname="col3" class="entry"> Exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Standard</b> </td> 
   <td colname="col2"> <p>Une paire clé-valeur standard se compose d'une clé et d'une valeur uniques. Cette structure classe les données en paires clé-valeur distinctes. Chaque clé est explicitement spécifiée, même lorsqu'elle est réutilisée pour définir une valeur différente. Il s'agit de la méthode la plus courante pour envoyer des données au serveur de collecte de données. </p> </td>
   <td colname="col3"> <code> key 1 = val 1 &amp; key 2 = val 2 &amp; key 3 = val 3</code> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Sérialisé</b> </td> 
   <td colname="col2"> <p>Une paire clé-valeur sérialisée consiste en une clé unique et plusieurs valeurs. Cela peut être un moyen efficace d'organiser les données, mais les paires clé-valeur sérialisées nécessitent des symboles spécifiques pour séparer chaque clé et chaque jeu de valeurs de clé. </p> </td> 
   <td colname="col3"> <code> key 1 = val 1, val 2, val 3</code> </td> 
  </tr>
 </tbody>
</table>

## Delimiters and Separators for Serialized Key-Value Pairs {#delimiters-separators}

Avec les paires clé-valeur sérialisées, vous devez spécifier les marqueurs qui séparent les valeurs dans et entre ces variables. Audience Manager requiert les délimiteurs et les séparateurs suivants :

<table id="table_8FD4E6B9506943AEA619D4089913ECBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Conditions requises pour </th> 
   <th colname="col2" class="entry"> Symbole </th> 
   <th colname="col3" class="entry"> Sépare individuellement </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Délimiteurs</b> </td> 
   <td colname="col2"> Esperluette &amp; </td> 
   <td colname="col3"> <p>Paires clé-valeur : </p> <p><code> key 1 = val 1 &amp; key 2 = val 2, val 3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Séparateurs</b> </td> 
   <td colname="col2"> Virgule , </td> 
   <td colname="col3"> <p>Valeurs dans les paires clé-valeur : </p> <p><code> key 1 = val 1, val 2, val 3 &amp; key 2 = vala, valb, valc</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Envoi de données au serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)
>* [Préfixes de valeurs clés et variables prises en charge par le serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-keys.md)
>* [Paires clé-valeur expliquées](../../../reference/key-value-pairs-explained.md)

