---
description: Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.
seo-description: Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.
seo-title: Opérateurs logiques pris en charge
title: Opérateurs logiques pris en charge
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Opérateurs logiques pris en charge {#supported-logical-operators}

Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.

## Opérateurs pris en charge pour la recherche de signaux {#supported-operators-search}

Utilisez les opérateurs logiques pris en charge suivants pour rechercher des paires clé-valeur :

### Opérateurs de comparaison

| Opérateur | Définition |
|---|---|
| **==** | Égal à |
| **&gt;** | Supérieur à |
| **&lt;** | Inférieur à |
| **=&gt;** | Supérieur/égal à |
| **&lt;=** | Inférieur/égal à |

### Opérateurs nommés

| Opérateur | Evalue à [!DNL True] quel moment |
|---|---|
| **[!UICONTROL Contains]** | La valeur d’une paire clé-valeur *contient* des caractères spécifiés par cet opérateur. |
| **[!UICONTROL Startswith]** | La valeur d’une paire clé-valeur *commence par* des caractères spécifiés par cet opérateur. |
| **[!UICONTROL Endswith]** | La valeur d’une paire clé-valeur *se termine par* les caractères spécifiés par cet opérateur. |

## Opérateurs pris en charge pour le renvoi et l’estimation des caractéristiques {#supported-operators-backfilling}

Vous pouvez renvoyer des caractéristiques qui incluent des expressions contenant l’un des opérateurs pris en charge par [!UICONTROL Signal Search]. Outre ces opérateurs, le renvoi et l’estimation de caractéristiques prennent également en charge les opérateurs [!UICONTROL AND], [!UICONTROL OR]et [!UICONTROL AND NOT] logiques, utilisés pour combiner des paires clé-valeur dans les expressions de caractéristiques renvoyées.