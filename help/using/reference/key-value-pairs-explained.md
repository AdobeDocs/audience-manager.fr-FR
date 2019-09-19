---
description: Définit et décrit des paires clé-valeur standard et sérialisées.
keywords: integration code
seo-description: Définit et décrit des paires clé-valeur standard et sérialisées.
seo-title: Paires clé-valeur expliquées
solution: Audience Manager
title: Paires clé-valeur expliquées
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# Paires clé-valeur expliquées{#key-value-pairs-explained}

Définit et décrit des paires clé-valeur standard et sérialisées.

<!-- 

c_key_value_explained.xml

 -->

Une paire clé-valeur se compose de deux éléments de données connexes : Une clé, qui est une constante qui définit l’ensemble de données (par exemple, sexe, couleur, prix), et une valeur, qui est une variable qui appartient à l’ensemble (par exemple, mâle/femelle, vert, 100). Entièrement formée, une paire clé-valeur peut se présenter comme suit :

* `gender = male`
* `color = green`
* `price > 100`

## Paires de valeurs clés standard et sérialisées {#standard-serialized-pairs}

Les destinations acceptent les données clé-valeur dans *`standard`* ou *`serialized`* le format. Le formatage standard classe les données en paires clé-valeur distinctes. Chaque clé est explicitement mentionnée, même si elle est utilisée de nouveau pour définir une autre valeur. En revanche, la mise en forme sérialisée convertit plusieurs valeurs en un jeu défini par une seule clé. En outre, dans une paire sérialisée, un indicateur spécial est utilisé pour séparer les valeurs dans l’ensemble clé-valeur. Enfin, les valeurs de clé standard et sérialisées peuvent contenir une ou plusieurs valeurs. Le tableau suivant fournit des exemples de formats de valeur de clé standard et de série.

| Formatage | Clé unique | Paires clé-valeur |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Sérialisé** | `x=1;2` | `x=1;2&y=3;4` |



## Touches, délimiteurs et séparateurs {#keys-delimiters-separators}

Lorsque vous utilisez des données sérialisées, vous devez spécifier les caractères qui séparent les valeurs *au sein* et *entre* les paires clé-valeur. Les éléments des paires clé-valeur sont définis comme suit :

* **** Clé : Identifiant unique dans la paire clé-valeur.
* **** Délimiteur de valeur : Sépare les paires clé-valeur individuelles.
* **** Séparateur clé-valeur : Sépare une clé des valeurs d’une paire clé-valeur.
* **** Séparateur de série : Sépare les valeurs individuelles dans des paires clé-valeur sérialisées.

## Eléments de valeur clé standard et sérialisés {#standard-serialized-key-value-elements}

<table id="table_62B0498441034A719C9DB57276777D40"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type </th> 
   <th colname="col2" class="entry"> Exemple </th> 
   <th colname="col3" class="entry"> Clé </th> 
   <th colname="col4" class="entry"> Séparateur clé-valeur </th> 
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

