---
description: Cet article décrit les opérateurs de comparaison utilisés par le créateur de caractéristiques.
seo-description: Cet article décrit les opérateurs de comparaison utilisés par le créateur de caractéristiques.
seo-title: Utilisation d’opérateurs de comparaison dans le générateur de caractéristiques
solution: Audience Manager
title: Utilisation d’opérateurs de comparaison dans le générateur de caractéristiques
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: 'Caractéristiques '
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 12%

---

# Utilisation d’opérateurs de comparaison dans le générateur de caractéristiques {#working-with-comparison-operators-in-trait-builder}

Cet article décrit les opérateurs de comparaison utilisés par [!UICONTROL Trait Builder].

## Objectif des opérateurs de comparaison

<!-- c_tb_comparison_operators.xml -->

Les opérateurs de comparaison (ou relationnels) sont utilisés pour comparer, tester ou évaluer la relation entre différentes valeurs. Dans [!UICONTROL Trait Builder], lors de la création de règles de signal, les opérateurs de comparaison vous permettent de tester la relation entre différentes paires clé-valeur. Par exemple, vous pouvez créer une règle de signal pour définir une audience pour les acheteurs d’appareils photo coûteux. Dans ce cas, vous pouvez créer une paire caméra/valeur-clé de prix et qualifier un utilisateur s’il a recherché une caméra dont le prix est égal ou supérieur à un montant donné.

## Avantages des opérateurs de comparaison

Les opérateurs de comparaison sont utiles lorsque vous devez évaluer et créer des caractéristiques basées sur plusieurs valeurs. Un examen des prix des biens et des services peut illustrer cette condition. Par exemple, votre entreprise peut vouloir identifier les visiteurs en fonction des prix des produits qu’ils consultent. Toutefois, il peut s’avérer inefficace sur le plan administratif de définir des segments individuels en fonction de valeurs spécifiques. Les opérateurs de comparaison permettent de surmonter cet obstacle en établissant des déclencheurs de segmentation en fonction des seuils de prix ou des plages.

## Opérateurs de comparaison

Vous pouvez créer des règles avec les opérateurs de comparaison suivants :

| Opérateur | Définition |
|---|---|
| **==** | Égal à |
| **!=** | Différent de |
| **>** | Supérieur à |
| **&lt;>** | Inférieur à |
| **=>** | Supérieur/égal à |
| **&lt;>** | Inférieur/égal à |

## Opérateurs nommés

Vous pouvez créer des règles avec les opérateurs nommés suivants :

| Opérateur | Évalue sur [!DNL True] Lorsque |
|---|---|
| **[!UICONTROL Contains]** | La valeur d’une paire clé-valeur *contient les caractères* spécifiés par cet opérateur. |
| **[!UICONTROL Matcheswords]** | La valeur d’une paire clé-valeur *correspond* au modèle spécifié par cet opérateur. |
| **[!UICONTROL Startswith]** | La valeur d’une paire clé-valeur *commence par les caractères* spécifiés par cet opérateur. |
| **[!UICONTROL Endswith]** | La valeur d’une paire clé-valeur *se termine par* les caractères spécifiés par cet opérateur. |
| **[!UICONTROL Matchesregex]** | La valeur d’une paire clé-valeur *correspond* au modèle spécifié par une expression régulière. [En savoir ](../../features/traits/trait-builder-regex.md) plus sur l’utilisation d’expressions régulières dans  [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Expressions booléennes dans le créateur de caractéristiques et de segments](../../reference/boolean-expressions-tsb.md)
* [Présentation des expressions booléennes dans TraitBuilder](../../reference/boolean-expressions-tsb.md)
* [Ordre des opérations dans les expressions TraitBuilder](../../features/traits/trait-operator-precedence.md)
* [Exemple d’expressions avec des opérateurs booléens et de comparaison](../../features/traits/trait-expression-samples.md)

