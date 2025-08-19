---
description: Cet article fournit une présentation générale sur la classification des caractéristiques avec une taxonomie commune.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Classification des caractéristiques avec une taxonomie commune
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 0%

---

# Classification des caractéristiques avec une taxonomie commune {#classifying-traits-with-a-common-taxonomy}

Cet article fournit une présentation générale sur la classification des caractéristiques avec une taxonomie commune.

## Taxonomie Audience Manager

<!-- c_common_taxonomy_about.xml -->

La taxonomie [!DNL Audience Manager] est une fonctionnalité facultative qui classe les caractéristiques à l’aide de conventions de nommage uniformes, logiques et communément comprises. Il fonctionne au niveau de la plateforme pour aider à assurer la cohérence des noms dans tout l’écosystème [!DNL Audience Manager]. En fin de compte, la taxonomie commune est conçue pour aligner davantage notre produit sur les normes du secteur en ce qui concerne la vie privée des consommateurs et les processus de désinscription.

## Avantages de la classification des caractéristiques

Permettre à nos clients de créer des segments et des modèles de données personnalisés est essentiel au modèle de [!DNL Audience Manager] et à votre capacité à capturer de la valeur à partir de notre plateforme. Toutefois, il est également nécessaire de disposer d’un moyen robuste et évolutif de communiquer des informations sur les segments à vos clients et partenaires. En outre, cette communication nécessite que les informations sur les segments soient partagées dans un langage facile à comprendre et universellement compris, tout en protégeant vos caractéristiques et noms de segment propriétaires. La taxonomie commune [!DNL Audience Manager] fournit ce langage et cette fonctionnalité.

## La Taxonomie Utilise Les Catégories De Classification Standard Du Secteur

La taxonomie commune est basée sur les classifications créées par le [!DNL Interactive Advertising Bureau (IAB)]. Pour plus d&#39;informations sur les lignes directrices relatives à l&#39;assurance de la qualité pour les réseaux et les échanges[!DNL IAB] consultez le [site Web du ](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines).

## Organisation taxonomique

La taxonomie [!DNL Audience Manager] organise les données en catégories imbriquées appelées niveaux. Chaque catégorie peut contenir jusqu’à 3 niveaux distincts pour la classification des données. Au niveau le plus élevé, une catégorie de niveau 1 regroupe les données sous leur forme la plus générale (p. ex. géographie). Les niveaux suivants fournissent une plus grande spécificité au niveau supérieur, catégorie générale (par exemple, *géographie —> États-Unis —> New York*). Cependant, toutes les catégories n’ont pas 3 niveaux, certaines n’en utilisent que 2.

## Classer les caractéristiques dans des catégories de données

Vous attribuez des classifications taxonomiques lors de la création ou de la modification de caractéristiques dans le [!UICONTROL Add New Trait Wizard] (situé dans * **[!UICONTROL Audience Data > Traits]***). Reportez-vous à la [documentation sur la création de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md) pour plus d’informations.

## Utilisation de la taxonomie : considérations supplémentaires

Si vous décidez de classer les caractéristiques selon notre taxonomie commune, il est important de se rappeler :

* La classification est *facultative*.
* Les caractéristiques *ne sont pas* affectées par défaut à une catégorie taxonomique (c’est-à-dire que les caractéristiques ne sont pas classées comme « inconnues » ou « non classées », etc.).
* Les caractéristiques ne peuvent appartenir qu’à *une seule* catégorie taxonomique (les classifications multiples et intercatégories ne sont pas autorisées).
