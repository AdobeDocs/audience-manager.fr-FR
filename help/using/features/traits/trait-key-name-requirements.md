---
description: Cet article décrit les conventions de dénomination utilisées par la variable clé dans une paire clé-valeur.
seo-description: Cet article décrit les conventions de dénomination utilisées par la variable clé dans une paire clé-valeur.
seo-title: Exigences de nom pour les variables clés
solution: Audience Manager
title: Exigences de nom pour les variables clés
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: 'Caractéristiques '
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 12%

---

# Exigences de nom pour les variables clés {#name-requirements-for-key-variables}

Cet article décrit les conventions de dénomination utilisées par la variable clé dans une paire clé-valeur.

## Exigences d’attribution de noms pour les clés

<!-- c_tb_key_name_requirements.xml -->

Dans [!UICONTROL Expression Builder], le nom d’une variable clé d’une paire clé-valeur peut être composé de n’importe quel nombre de chiffres suivis par 1 (ou plus) lettres, un tiret, un trait de soulignement et des chiffres supplémentaires.

* Noms de clés valides : `price123`, `123price`, `price-123`, `c_price123`.

* Noms de clés non valides : `123`, `price!123`.

## Ajout d’un préfixe aux variables clés avec `c_`

Le préfixe `c_` est *always* requis si les paramètres qui envoient des données sur une URL d’appel d’événement utilisent cette syntaxe.
