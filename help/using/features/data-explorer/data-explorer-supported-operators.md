---
description: Utilisez des opérateurs logiques pour regrouper les paires clé-valeur et les caractéristiques de renvoi.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: Opérateurs logiques pris en charge
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 4%

---

# Opérateurs logiques pris en charge {#supported-logical-operators}

Utilisez des opérateurs logiques pour regrouper les paires clé-valeur et les caractéristiques de renvoi.

## Opérateurs pris en charge pour la recherche de signaux {#supported-operators-search}

Utilisez les opérateurs logiques pris en charge suivants pour rechercher des paires clé-valeur :

### Opérateurs de comparaison

| Opérateur | Définition |
|---|---|
| **==** | Égal à |
| **>** | Supérieur à |
| **&lt;** | Inférieur à |
| **=>** | Supérieur/égal à |
| **&lt;=** | Inférieur/égal à |

### Opérateurs nommés

| Opérateur | Est évalué sur [!DNL True] lorsque |
|---|---|
| **[!UICONTROL Contains]** | La valeur dans une paire clé-valeur *contient* caractères spécifiés par cet opérateur. |
| **[!UICONTROL Startswith]** | La valeur d’une paire clé-valeur *commence par* les caractères spécifiés par cet opérateur. |
| **[!UICONTROL Endswith]** | La valeur dans une paire clé-valeur *se termine par* les caractères spécifiés par cet opérateur. |

## Opérateurs pris en charge pour le remplissage et l’estimation des caractéristiques {#supported-operators-backfilling}

Vous pouvez renvoyer des caractéristiques qui incluent des expressions contenant l’un des opérateurs pris en charge par [!UICONTROL Signal Search]. Outre ces opérateurs, le remplissage et l’estimation des caractéristiques prennent également en charge les opérateurs logiques [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL AND NOT], utilisés pour combiner des paires clé-valeur dans les expressions de caractéristique renvoyées.
