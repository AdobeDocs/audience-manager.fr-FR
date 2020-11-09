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
source-git-commit: 5d6983f5308f1dfd4560ee1b38bcaee3ca6e422f
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 6%

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


| Type | Exemple | Clé | Séparateur de valeur-clé | Délimiteur clé-valeur | Séparateur de série |
---------|----------|---------|---------|----------|---------
| **Clé** unique (standard) | `x=1&x=2` | `x` | `=` | `&` | n/d |
| **Paires** clé-valeur (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/d |
| **Clé** unique (série) | `x=1;2;3` | `x` | `=` | n/d | `;` |
| **Paires** clé-valeur (série) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
