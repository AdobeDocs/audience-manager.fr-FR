---
description: Utilisez des opérateurs logiques pour regrouper les paires clé-valeur et les caractéristiques de renvoi.
seo-description: Utilisez des opérateurs logiques pour regrouper les paires clé-valeur et les caractéristiques de renvoi.
seo-title: Opérations logiques prises en charge
title: Opérations logiques prises en charge
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: 'Explorateur de données '
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 10%

---

# Opérations logiques prises en charge {#supported-logical-operators}

Utilisez des opérateurs logiques pour regrouper les paires clé-valeur et les caractéristiques de renvoi.

## Opérateurs pris en charge pour la recherche de signaux {#supported-operators-search}

Utilisez les opérateurs logiques pris en charge suivants pour rechercher des paires clé-valeur :

### Opérateurs de comparaison

| Opérateur | Définition |
|---|---|
| **==** | Égal à |
| **>** | Supérieur à |
| **&lt;>** | Inférieur à |
| **=>** | Supérieur/égal à |
| **&lt;>** | Inférieur/égal à |

### Opérateurs nommés

| Opérateur | Évalue sur [!DNL True] Lorsque |
|---|---|
| **[!UICONTROL Contains]** | La valeur d’une paire clé-valeur *contient les caractères* spécifiés par cet opérateur. |
| **[!UICONTROL Startswith]** | La valeur d’une paire clé-valeur *commence par les caractères* spécifiés par cet opérateur. |
| **[!UICONTROL Endswith]** | La valeur d’une paire clé-valeur *se termine par* les caractères spécifiés par cet opérateur. |

## Opérateurs pris en charge pour le renvoi et l’estimation des caractéristiques {#supported-operators-backfilling}

Vous pouvez renvoyer des caractéristiques qui incluent des expressions contenant l’un des opérateurs pris en charge par [!UICONTROL Signal Search]. Outre ces opérateurs, le renvoi et l’estimation des caractéristiques prennent également en charge les opérateurs logiques [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL AND NOT] utilisés pour combiner des paires clé-valeur dans les expressions de caractéristiques renvoyées.
