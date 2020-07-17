---
description: Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.
seo-description: Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.
seo-title: Opérations logiques prises en charge
title: Opérations logiques prises en charge
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 9%

---


# Opérations logiques prises en charge {#supported-logical-operators}

Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.

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

| Opérateur | Évaluer à [!DNL True] quel moment |
|---|---|
| **[!UICONTROL Contains]** | La valeur d’une paire clé-valeur *contient* des caractères spécifiés par cet opérateur. |
| **[!UICONTROL Startswith]** | Valeur d’une paire clé-valeur *débuts avec* des caractères spécifiés par cet opérateur. |
| **[!UICONTROL Endswith]** | La valeur d’une paire clé-valeur *se termine par* les caractères spécifiés par cet opérateur. |

## Opérateurs pris en charge pour le renvoi et l&#39;estimation des caractéristiques {#supported-operators-backfilling}

Vous pouvez renvoyer les caractéristiques qui incluent des expressions contenant l’un des opérateurs pris en charge par [!UICONTROL Signal Search]. Outre ces opérateurs, le renvoi et l&#39;estimation des caractéristiques prennent également en charge les opérateurs [!UICONTROL AND], [!UICONTROL OR]et [!UICONTROL AND NOT] logiques, utilisés pour combiner des paires clé-valeur dans les expressions de caractéristiques renvoyées.