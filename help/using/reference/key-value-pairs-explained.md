---
description: Définit et décrit les paires clé-valeur standard et sérialisées.
keywords: integration code
seo-description: Définit et décrit les paires clé-valeur standard et sérialisées.
seo-title: Paires clé-valeur expliquées
solution: Audience Manager
title: Paires clé-valeur expliquées
uuid: f 1435742-81 ca -4964-8370-accf 2 f 1 c 47 a 5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Key-Value Pairs Explained{#key-value-pairs-explained}

Définit et décrit les paires clé-valeur standard et sérialisées.

<!-- 

c_key_value_explained.xml

 -->

Une paire clé-valeur comprend deux éléments de données connexes : Clé qui définit le jeu de données (par exemple, sexe, couleur, prix) et une valeur, qui est une variable qui appartient à la visionneuse (homme/femme, vert, 100, par exemple). Entièrement formé, une paire clé-valeur pourrait ressembler à celle-ci :

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinations accept key-value data in *`standard`* or *`serialized`* format. La mise en forme standard organise les données en paires clé-valeur distinctes. Chaque clé est explicitement spécifiée, même lorsqu'elle est réutilisée pour définir une valeur différente. En revanche, la mise en forme sérialisée condense plusieurs valeurs en un jeu défini par une clé unique. En outre, dans une paire sérialisée, un indicateur spécial est utilisé pour séparer les valeurs dans le jeu de valeurs clés. Enfin, les valeurs de clé standard et sérialisées peuvent contenir des valeurs uniques ou multiples. Le tableau suivant présente des exemples de formats standard et de valeurs de clé de série.

| Formatage | Clé unique | Paires clé-valeur |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Sérialisé** | `x=1;2` | `x=1;2&y=3;4` |



## Keys, Delimiters, and Separators {#keys-delimiters-separators}

When working with serialized data, you must specify the characters that separate values *within* and *between* the key-value pairs. Les éléments des paires clé-valeur sont définis comme suit :

* **Clé :** Identifiant unique dans la paire clé-valeur.
* **Délimiteur de valeurs :** Sépare les paires clé-valeur individuelles.
* **Séparateur de valeur clé :** Sépare une clé des valeurs d'une paire clé-valeur.
* **Séparateur de série :** Sépare les valeurs individuelles dans les paires clé-valeur sérialisées.

## Standard and Serialized Key-Value Elements {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Exemple </th> 
   <th colname="col3" class="entry"> Clé </th> 
   <th colname="col4" class="entry"> Séparateur de valeur clé </th> 
   <th colname="col5" class="entry"> Délimiteur de valeur clé </th> 
   <th colname="col6" class="entry"> Séparateur de série </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Clé unique</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/d </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Paires clé-valeur</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Clé unique</b> <p>(serial) </p> </td> 
   <td colname="col2"> <code> x = 1 ; 2 ; 3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/d </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Paires clé-valeur</b> (serial) </td> 
   <td colname="col2"> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

