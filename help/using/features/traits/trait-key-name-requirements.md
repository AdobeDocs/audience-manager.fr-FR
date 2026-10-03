---
description: Cet article décrit les conventions de dénomination utilisées par la variable clé dans une paire clé-valeur.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Exigences de nom pour les variables clés
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
TQID: 'https://experienceleague.adobe.com/OEw-vhgEQtUfiyA4FzKp7rnxeFOZh2nL3r1-YudPAhc'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b89b323a-1e91-40b1-8d20-96b5b726d55a
    internal-label: Audience management
subfeature_v2:
  - id: b1ecf375-97f8-4f5a-a937-6129552209be
    internal-label: Traits
topic_v2:
  - id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
    internal-label: Taxonomy
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%
---
# Exigences de nom pour les variables clés {#name-requirements-for-key-variables}

Cet article décrit les conventions de dénomination utilisées par la variable clé dans une paire clé-valeur.

## Exigences de dénomination pour les clés

<!-- c_tb_key_name_requirements.xml -->

En [!UICONTROL Expression Builder], le nom d’une variable clé dans une paire clé-valeur peut se composer d’un nombre illimité de chiffres suivis d’une ou de plusieurs lettres, d’un tiret, d’un trait de soulignement et de chiffres supplémentaires.

* Noms de clés valides : `price123`, `123price`, `price-123`, `c_price123`.

* Noms de clés non valides : `123`, `price!123`.

## Préfixe des variables clés avec `c_`

Le préfixe `c_` est *toujours* requis si les paramètres qui envoient des données sur une URL d’appel d’événement utilisent cette syntaxe.
