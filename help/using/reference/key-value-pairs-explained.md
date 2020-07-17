---
description: Définit et décrit des paires clé-valeur standard et sérialisées.
keywords: integration code
seo-description: Définit et décrit des paires clé-valeur standard et sérialisées.
seo-title: Explication des paires clé-valeur
solution: Audience Manager
title: Explication des paires clé-valeur
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 7%

---


# Explication des paires clé-valeur{#key-value-pairs-explained}

Définit et décrit des paires clé-valeur standard et sérialisées.

<!-- 

c_key_value_explained.xml

 -->

Une paire clé-valeur se compose de deux éléments de données connexes : Une clé, qui est une constante qui définit l&#39;ensemble de données (par exemple, sexe, couleur, prix), et une valeur, qui est une variable qui appartient à l&#39;ensemble (par exemple, mâle/femelle, vert, 100). Entièrement formée, une paire clé-valeur peut se présenter comme suit :

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Les destinations acceptent les données de valeur clé dans *`standard`* ou *`serialized`* le format. La mise en forme standard organise les données en paires clé-valeur distinctes. Chaque clé est explicitement indiquée, même si elle est utilisée de nouveau pour définir une autre valeur. En revanche, la mise en forme sérialisée convertit plusieurs valeurs en un ensemble défini par une seule clé. En outre, dans une paire sérialisée, un indicateur spécial est utilisé pour séparer les valeurs dans le jeu de valeurs clés. Enfin, les valeurs de clé standard et sérialisées peuvent contenir une ou plusieurs valeurs. Le tableau suivant fournit des exemples de formats de valeur de clé standard et de série.

| Formatage | Clé unique | Paires clé-valeur |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Sérialisé** | `x=1;2` | `x=1;2&y=3;4` |



## Raccourcis clavier, délimiteurs et séparateurs {#keys-delimiters-separators}

Lorsque vous utilisez des données sérialisées, vous devez spécifier les caractères qui séparent les valeurs *au sein* et *entre* les paires clé-valeur. Les éléments des paires clé-valeur sont définis comme suit :

* **Clé :** Identificateur unique dans la paire clé-valeur.
* **Délimiteur de valeur :** Sépare les paires clé-valeur individuelles.
* **Séparateur de valeur de clé :** Sépare une clé des valeurs d’une paire clé-valeur.
* **Séparateur de série :** Sépare les valeurs individuelles dans des paires clé-valeur sérialisées.

## Éléments de valeur clé standard et sérialisés {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Exemple </th> 
   <th colname="col3" class="entry"> Clé </th> 
   <th colname="col4" class="entry"> Séparateur de valeur-clé </th> 
   <th colname="col5" class="entry"> Délimiteur clé-valeur </th> 
   <th colname="col6" class="entry"> Séparateur de série </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Clé unique</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col4" morerows="3"> = </td> 
   <td colname="col5" morerows="1"> &amp; </td> 
   <td colname="col6" morerows="1"> n/d </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Paires clé-valeur</b> <p>(standard) </p> </td> 
   <td colname="col2"> <code> x=1&amp;x=2&amp;y=3&amp;y=4 </code> </td> 
   <td colname="col3"> x, y </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Clé unique</b> <p>(série) </p> </td> 
   <td colname="col2"> <code> x=1;2;3 </code> </td> 
   <td colname="col3"> x </td> 
   <td colname="col5"> n/d </td> 
   <td colname="col6" morerows="1"> ; </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Paires</b> clé-valeur (série) </td> 
   <td colname="col2"> <code> x=1;2&amp;y=3;4 </code> </td> 
   <td colname="col3"> x, y </td> 
   <td colname="col5"> &amp; </td> 
  </tr> 
 </tbody> 
</table>

