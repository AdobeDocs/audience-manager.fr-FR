---
description: Cet article décrit les opérateurs de comparaison utilisés par le créateur de caractéristiques.
seo-description: Cet article décrit les opérateurs de comparaison utilisés par le créateur de caractéristiques.
seo-title: Utilisation d’opérateurs de comparaison dans le générateur de caractéristiques
solution: Audience Manager
title: Utilisation d’opérateurs de comparaison dans le générateur de caractéristiques
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 11%

---


# Utilisation d’opérateurs de comparaison dans le générateur de caractéristiques {#working-with-comparison-operators-in-trait-builder}

Cet article décrit les opérateurs de comparaison utilisés par [!UICONTROL Trait Builder].

## Objectif des opérateurs de comparaison

<!-- c_tb_comparison_operators.xml -->

Les opérateurs de comparaison (ou opérateurs relationnels) sont utilisés pour comparer, tester ou évaluer la relation entre différentes valeurs. Dans [!UICONTROL Trait Builder]le cas de la création de règles de signal, les opérateurs de comparaison vous permettent de tester la relation entre les différentes paires clé-valeur. Par exemple, vous pouvez créer une règle de signal pour définir une audience pour les acheteurs d’appareils photo coûteux. Dans ce cas, vous pouvez créer une paire caméra/prix-clé-valeur et qualifier un utilisateur s’il a recherché une caméra dont le prix est égal ou supérieur à un montant défini.

## Avantages des opérateurs de comparaison

Les opérateurs de comparaison sont utiles lorsque vous devez évaluer et créer des caractéristiques basées sur plusieurs valeurs. L&#39;examen des prix des biens et des services peut illustrer cette situation. Par exemple, votre entreprise peut vouloir identifier les visiteurs en fonction des prix des produits qu’elle vue. Cependant, il peut s’avérer inefficace sur le plan administratif de définir des segments individuels en fonction de valeurs spécifiques. Les opérateurs de comparaison aident à surmonter cet obstacle en établissant des déclencheurs de segmentation en fonction de seuils ou de plages de prix.

## Opérateurs de comparaison

Vous pouvez créer des règles à l’aide des opérateurs de comparaison suivants :

| Opérateur | Définition |
|---|---|
| **==** | Égal à |
| **!=** | N’est pas égal à |
| **>** | Supérieur à |
| **&lt;** | Inférieur à |
| **=>** | Supérieur/égal à |
| **&lt;=** | Inférieur/égal à |

## Opérateurs nommés

Vous pouvez créer des règles avec les opérateurs nommés suivants :

| Opérateur | Évaluer à [!DNL True] quel moment |
|---|---|
| **[!UICONTROL Contains]** | La valeur d’une paire clé-valeur *contient* des caractères spécifiés par cet opérateur. |
| **[!UICONTROL Matcheswords]** | La valeur d’une paire clé-valeur *correspond* au modèle spécifié par cet opérateur. |
| **[!UICONTROL Startswith]** | Valeur d’une paire clé-valeur *débuts avec* des caractères spécifiés par cet opérateur. |
| **[!UICONTROL Endswith]** | La valeur d’une paire clé-valeur *se termine par* les caractères spécifiés par cet opérateur. |
| **[!UICONTROL Matchesregex]** | La valeur d’une paire clé-valeur *correspond* au modèle spécifié par une expression régulière. [En savoir plus](../../features/traits/trait-builder-regex.md) sur l&#39;utilisation des expressions régulières dans [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Expressions booléennes dans le créateur de caractéristiques et de segments](../../reference/boolean-expressions-tsb.md)
>* [Présentation des Expressions booléennes dans TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Ordre des opérations dans les Expressions TraitBuilder](../../features/traits/trait-operator-precedence.md)
>* [Exemple d’expressions avec des opérateurs booléens et de comparaison](../../features/traits/trait-expression-samples.md)

