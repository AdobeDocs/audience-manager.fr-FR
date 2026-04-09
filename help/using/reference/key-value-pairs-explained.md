---
description: Définit et décrit des paires clé-valeur standard et sérialisées.
keywords: code d'intégration
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Présentation Des Paires Clé-Valeur
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
TQID: https://experienceleague.adobe.com/6rXUarJT3GqTxNw6NuwivkSai1Rpf63sILAJ7oPJdXg
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 3%

---

# Présentation Des Paires Clé-Valeur{#key-value-pairs-explained}

Définit et décrit des paires clé-valeur standard et sérialisées.

<!-- 

c_key_value_explained.xml

 -->

Une paire clé-valeur se compose de deux éléments de données associés : une clé, qui est une constante définissant l’ensemble de données (par exemple, genre, couleur, prix), et une valeur, qui est une variable appartenant à l’ensemble (par exemple, homme/femme, vert, 100). Une paire clé-valeur entièrement formée pourrait ressembler à ceci :

* `gender = male`
* `color = green`
* `price > 100`

## Paires clé-valeur standard et sérialisées {#standard-serialized-pairs}

Les destinations acceptent les données clé-valeur au format *`standard`* ou *`serialized`*. La mise en forme standard organise les données en paires clé-valeur distinctes. Chaque clé est indiquée explicitement, même lorsqu’elle est utilisée à nouveau pour définir une valeur différente. En revanche, une mise en forme sérialisée condense plusieurs valeurs en un seul jeu défini par une seule clé. En outre, dans une paire sérialisée, un indicateur spécial est utilisé pour séparer les valeurs dans le jeu clé-valeur. Enfin, les valeurs-clés standard et sérialisées peuvent contenir des valeurs uniques ou multiples. Le tableau suivant fournit des exemples de formats de valeur de clé standard et série.

| Formatage | Clé unique | Paires Clé-Valeur |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Sérialisé** | `x=1;2` | `x=1;2&y=3;4` |



## Clés, délimiteurs et séparateurs {#keys-delimiters-separators}

Lorsque vous utilisez des données sérialisées, vous devez spécifier les caractères qui séparent les valeurs *dans* et *entre* les paires clé-valeur. Les éléments des paires clé-valeur sont définis comme suit :

* **Key :** identifiant unique dans la paire clé-valeur.
* **Délimiteur de valeur :** sépare les paires clé-valeur individuelles.
* **Séparateur clé-valeur :** sépare une clé des valeurs d’une paire clé-valeur.
* **Séparateur de série :** sépare les valeurs individuelles au sein de paires clé-valeur sérialisées.

## Éléments clé-valeur standard et sérialisés {#standard-serialized-key-value-elements}


| Type | Exemple | Clé | Séparateur Clé-Valeur | Délimiteur Clé-Valeur | Séparateur série |
|---------|----------|---------|---------|----------|---------|
| **Clé unique** (standard) | `x=1&x=2` | `x` | `=` | `&` | n/d |
| **Paires clé-valeur** (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/d |
| **Clé unique** (série) | `x=1;2;3` | `x` | `=` | n/d | `;` |
| **Paires clé-valeur** (série) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
