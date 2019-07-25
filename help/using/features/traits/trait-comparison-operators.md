---
description: Cet article décrit les opérateurs de comparaison utilisés par le créateur de caractéristiques.
seo-description: Cet article décrit les opérateurs de comparaison utilisés par le créateur de caractéristiques.
seo-title: Utilisation des opérateurs de comparaison dans le créateur de caractéristiques
solution: Audience Manager
title: Utilisation des opérateurs de comparaison dans le créateur de caractéristiques
uuid: 41 bec 3 b 3-e 5 df -4 a 6 f-abb 0-80 ce 4 c 75 f 5 e 7
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Working with Comparison Operators in Trait Builder {#working-with-comparison-operators-in-trait-builder}

This article describes the comparison operators used by [!UICONTROL Trait Builder].

## Objectif des opérateurs de comparaison

<!-- c_tb_comparison_operators.xml -->

Les opérateurs de comparaison (ou opérateurs relationnels) servent à comparer, tester ou évaluer la relation entre les différentes valeurs. In [!UICONTROL Trait Builder], when building signal rules, comparison operators let you test the relationship between different key-value pairs. Par exemple, vous pouvez créer une règle de signal pour définir une audience pour les acheteurs de caméra coûteux. Dans ce cas, vous pouvez créer une paire clé-valeur de prix/appareil photo et qualifier un utilisateur s'il a recherché une caméra dont le prix est égal ou supérieur à un montant défini.

## Avantages des opérateurs de comparaison

Les opérateurs de comparaison sont utiles lorsque vous devez évaluer et créer des caractéristiques basées sur plusieurs valeurs. La consultation des prix sur les produits et les services peut illustrer cette condition. Par exemple, votre entreprise peut vouloir identifier les visiteurs en fonction des prix des produits qu'ils consultent. Cependant, il peut être administrativement inefficace de définir des segments individuels en fonction de valeurs spécifiques. Les opérateurs de comparaison permettent de résoudre ce problème en créant des triggers de segmentation basés sur des seuils ou plages de prix.

## Opérateurs de comparaison

Vous pouvez créer des règles avec les opérateurs de comparaison suivants :

| Opérateur | Définition |
|---|---|
| **==** | Égal à |
| **!=** | Différent de |
| **&gt;** | Supérieur à |
| **&lt;** | Inférieur à |
| **=&gt;** | Supérieur/égal à |
| **&lt;=** | Inférieur/égal à |

## Opérateurs nommés

Vous pouvez créer des règles avec les opérateurs nommés suivants :

| Opérateur | Evaluates to [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | The value in a key-value pair *contains* characters specified by this operator. |
| **[!UICONTROL Matcheswords]** | The value in a key-value pair *matches* the pattern specified by this operator. |
| **[!UICONTROL Startswith]** | The value in a key-value pair *starts with* characters specified by this operator. |
| **[!UICONTROL Endswith]** | The value in a key-value pair *ends with* the characters specified by this operator. |
| **[!UICONTROL Matchesregex]** | The value in a key-value pair *matches* the pattern specified by a regular expression. [En savoir plus](../../features/traits/trait-builder-regex.md) sur l'utilisation d'expressions régulières dans [!UICONTROL Trait Builder]. |

>[!MORE_ LIKE_ THIS]
>
>* [Expressions booléennes dans le créateur de caractéristiques et le créateur de segment](../../reference/boolean-expressions-tsb.md)
>* [Présentation des expressions booléennes dans traitbuilder](../../reference/boolean-expressions-tsb.md)
>* [Ordre des opérations dans les expressions traitbuilder](../../features/traits/trait-operator-precedence.md)
>* [Exemples d'expressions avec opérateurs booléens et de comparaison](../../features/traits/trait-expression-samples.md)

