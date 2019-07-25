---
description: Cet article fournit une vue d'ensemble générale de la classification des caractéristiques avec une taxonomie commune.
keywords: DIL 
seo-description: Cet article fournit une vue d'ensemble générale de la classification des caractéristiques avec une taxonomie commune.
seo-title: Classification des caractéristiques avec une taxonomie commune
solution: Audience Manager
title: Classification des caractéristiques avec une taxonomie commune
uuid: 2 e 177344-07 d 9-40 a 7-8 c 99-c 6 c 6518 b 9 d 97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Classifying Traits with a Common Taxonomy {#classifying-traits-with-a-common-taxonomy}

Cet article fournit une vue d'ensemble générale de la classification des caractéristiques avec une taxonomie commune.

## Taxonomie d'Audience Manager

<!-- c_common_taxonomy_about.xml -->

[!DNL Audience Manager] La taxonomie est une fonctionnalité facultative qui classe les caractéristiques à l'aide de conventions d'affectation de nom uniformes, logiques et courantes. It operates at the platform level to help ensure naming consistency throughout the [!DNL Audience Manager] ecosystem. En fin de compte, la taxonomie commune est conçue pour renforcer l'alignement avec les normes du marché en ce qui concerne la confidentialité des utilisateurs et les processus d'exclusion.

## Avantages de la classification des caractéristiques

Enabling our customers to build custom segments and data models is core to the [!DNL Audience Manager] model and to your ability to capture value from our platform. Toutefois, ce qui est également requis, c'est un moyen puissant et évolutif de communiquer des informations sur les segments à vos clients et partenaires. De plus, cette communication requiert que les informations de segment soient partagées dans une langue compréhensible et universelle tout en protégeant vos noms de caractéristique et de segment propriétaires. The [!DNL Audience Manager] common taxonomy provides this language and capability.

## La Taxonomie utilise les catégories de classification standard du secteur

The common taxonomy is based on the classifications created by the [!DNL Interactive Advertising Bureau (IAB)]. Refer to the [!DNL IAB]'s [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) for more information about quality assurance guidelines for networks and exchanges.

## Organisation taxonomique

The [!DNL Audience Manager] taxonomy organizes data into nested categories called tiers. Chaque catégorie peut contenir jusqu'à trois niveaux distincts pour la classification des données. Au niveau supérieur, une catégorie de niveau 1 regroupe les données dans son formulaire le plus général (par exemple, géographie). Subsequent tiers provide greater specificity to the higher level, general category (e.g., *geography --&gt; United States --&gt; New York*). Toutefois, chaque catégorie n'a pas 3 niveaux, certains n'utilisent que 2.

## Classer les caractéristiques dans les catégories de données

You assign taxonomic classifications when creating or editing traits in the [!UICONTROL Add New Trait Wizard] (located in * **[!UICONTROL Audience Data > Traits]***). Refer to the [documentation on creating traits](../../features/traits/create-onboarded-rule-based-traits.md) for more information.

## Utilisation de la Taxonomie : Remarques supplémentaires

Si vous décidez de classer des caractéristiques selon notre taxonomie commune, il est important de se souvenir :

* Classification is *optional*.
* Traits *are not* assigned to a taxonomic category by default (i.e., traits are not classified as "unknown" or "uncategorized" etc.).
* Traits can belong to *one* taxonomic category only (multiple and cross-category classifications are not allowed).