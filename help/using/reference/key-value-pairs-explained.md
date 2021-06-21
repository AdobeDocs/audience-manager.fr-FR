---
description: Définit et décrit des paires clé-valeur standard et sérialisées.
keywords: integration code
seo-description: Définit et décrit des paires clé-valeur standard et sérialisées.
seo-title: Explication des paires clé-valeur
solution: Audience Manager
title: Explication des paires clé-valeur
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: 'Référence '
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 7%

---

# Explication des paires clé-valeur{#key-value-pairs-explained}

Définit et décrit des paires clé-valeur standard et sérialisées.

<!-- 

c_key_value_explained.xml

 -->

Une paire clé-valeur se compose de deux éléments de données associés : Une clé, qui est une constante qui définit le jeu de données (par exemple, le sexe, la couleur, le prix), et une valeur, qui est une variable qui appartient à l’ensemble (par exemple, mâle/femelle, vert, 100). En forme complète, une paire clé-valeur peut se présenter comme suit :

* `gender = male`
* `color = green`
* `price > 100`

## Paires clé-valeur standard et sérialisées {#standard-serialized-pairs}

Les destinations acceptent les données clé-valeur au format *`standard`* ou *`serialized`*. La mise en forme standard classe les données en paires clé-valeur distinctes. Chaque clé est explicitement indiquée, même si elle est réutilisée pour définir une autre valeur. En revanche, la mise en forme sérialisée convertit plusieurs valeurs en un jeu défini par une seule clé. En outre, dans une paire sérialisée, un indicateur spécial est utilisé pour séparer les valeurs dans l’ensemble clé-valeur. Enfin, les valeurs de clé standard et sérialisées peuvent contenir une ou plusieurs valeurs. Le tableau suivant fournit des exemples de formats de valeur de clé standard et de série.

| Formatage | Clé unique | Paires clé-valeur |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Sérialisé** | `x=1;2` | `x=1;2&y=3;4` |



## Clés, délimiteurs et séparateurs {#keys-delimiters-separators}

Lorsque vous utilisez des données sérialisées, vous devez spécifier les caractères qui séparent les valeurs *dans* et *entre* les paires clé-valeur. Les éléments des paires clé-valeur sont définis comme suit :

* **Clé :** identifiant unique dans la paire clé-valeur.
* **Délimiteur de valeur :** sépare les paires clé-valeur individuelles.
* **Séparateur clé-valeur :** sépare une clé des valeurs dans une paire clé-valeur.
* **Séparateur de série :** sépare les valeurs individuelles dans des paires clé-valeur sérialisées.

## Éléments clé-valeur standard et sérialisés {#standard-serialized-key-value-elements}


| Type | Exemple | Clé | Séparateur clé-valeur | Délimiteur clé-valeur | Séparateur de série |
|---------|----------|---------|---------|----------|---------|
| **Clé unique**  (standard) | `x=1&x=2` | `x` | `=` | `&` | n/d |
| **Paires clé-valeur**  (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/d |
| **Clé unique**  (série) | `x=1;2;3` | `x` | `=` | n/d | `;` |
| **Paires clé-valeur**  (série) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
