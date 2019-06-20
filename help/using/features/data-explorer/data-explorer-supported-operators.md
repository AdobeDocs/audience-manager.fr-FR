---
description: Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.
seo-description: Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.
seo-title: Opérateurs logiques pris en charge
title: Opérateurs logiques pris en charge
uuid: 645 fcb 6 f -50 ac -49 bc -8 df 9-c 699 c 749 cf 8 f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Supported Logical Operators {#supported-logical-operators}

Utilisez des opérateurs logiques pour regrouper des paires clé-valeur et des caractéristiques de renvoi.

## Supported Operators for Signal Search {#supported-operators-search}

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

| Opérateur | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |

## Supported Operators for Trait Backfilling and Estimation {#supported-operators-backfilling}

You can backfill traits that include expressions containing any of the operators supported by [!UICONTROL Signal Search]. In addition to these operators, trait backfilling and estimation also support the [!UICONTROL AND], [!UICONTROL OR], and [!UICONTROL AND NOT] logical operators, used to combine key-value pairs within the backfilled trait expressions.