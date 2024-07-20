---
description: Cet article présente un aperçu général de la classification des caractéristiques avec une taxonomie commune.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Classification de caractéristiques avec une taxonomie commune
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# Classification de caractéristiques avec une taxonomie commune {#classifying-traits-with-a-common-taxonomy}

Cet article présente un aperçu général de la classification des caractéristiques avec une taxonomie commune.

## La taxonomie des Audiences Manager

<!-- c_common_taxonomy_about.xml -->

La taxonomie [!DNL Audience Manager] est une fonction facultative qui classe les caractéristiques à l’aide de conventions d’affectation de noms uniformes, logiques et couramment comprises. Il fonctionne au niveau de la plateforme pour garantir la cohérence des noms dans tout l’écosystème [!DNL Audience Manager]. En fin de compte, la taxonomie commune est conçue pour amener notre produit à un plus grand alignement avec les normes de l’industrie concernant la confidentialité des consommateurs et les processus d’exclusion.

## Avantages de la classification des caractéristiques

Permettre à nos clients de créer des segments et des modèles de données personnalisés est essentiel au modèle [!DNL Audience Manager] et à votre capacité à capturer de la valeur à partir de notre plateforme. Toutefois, il est également nécessaire de disposer d’un moyen robuste et évolutif pour communiquer des informations sur les segments à vos clients et partenaires. En outre, cette communication exige que les informations sur les segments soient partagées dans un langage facile à comprendre et universellement compris, tout en protégeant vos caractéristiques propriétaires et vos noms de segment. La taxonomie commune [!DNL Audience Manager] fournit ce langage et cette fonctionnalité.

## La Taxonomie Utilise Les Catégories De Classification Standard Du Secteur.

La taxonomie commune est basée sur les classifications créées par [!DNL Interactive Advertising Bureau (IAB)]. Pour plus d’informations sur les consignes d’assurance qualité pour les réseaux et les exchanges, consultez le [site web](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) de [!DNL IAB].

## Organisation taxonomique

La taxonomie [!DNL Audience Manager] classe les données dans des catégories imbriquées appelées niveaux. Chaque catégorie peut contenir jusqu’à 3 niveaux distincts pour la classification des données. Au niveau le plus élevé, une catégorie de niveau 1 regroupe les données sous leur forme la plus générale (par exemple, la géographie). Les niveaux suivants fournissent une plus grande précision à la catégorie générale de niveau supérieur (par exemple, *géographie —> États-Unis —> New York*). Cependant, toutes les catégories n&#39;ont pas 3 niveaux, certaines n&#39;en utilisent que 2.

## Classification de caractéristiques dans les catégories de données

Vous attribuez des classifications taxonomiques lors de la création ou de la modification de caractéristiques dans le [!UICONTROL Add New Trait Wizard] (situé dans * **[!UICONTROL Audience Data > Traits]***). Pour plus d’informations, consultez la [documentation sur la création de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md) .

## Utilisation de la taxonomie : observations supplémentaires

Si vous décidez de classer les caractéristiques en fonction de notre taxonomie commune, il est important de vous souvenir :

* La classification est *optionnelle*.
* Les caractéristiques *ne sont pas* attribuées par défaut à une catégorie taxonomique (c’est-à-dire que les caractéristiques ne sont pas classées comme &quot;inconnues&quot; ou &quot;non classées&quot;, etc.).
* Les caractéristiques peuvent appartenir à la catégorie de taxonomie *un* uniquement (les classifications à plusieurs et à plusieurs catégories ne sont pas autorisées).
