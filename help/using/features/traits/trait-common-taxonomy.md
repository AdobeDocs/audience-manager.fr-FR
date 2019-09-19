---
description: Cet article présente un aperçu général de la classification des caractéristiques avec une taxonomie commune.
keywords: DIL 
seo-description: Cet article présente un aperçu général de la classification des caractéristiques avec une taxonomie commune.
seo-title: Classification des caractéristiques avec une taxonomie commune
solution: Audience Manager
title: Classification des caractéristiques avec une taxonomie commune
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
translation-type: tm+mt
source-git-commit: 44bb4d511215a7bbc8889cc9518b3b5ffcb79a2a

---


# Classification des caractéristiques avec une taxonomie commune {#classifying-traits-with-a-common-taxonomy}

Cet article présente un aperçu général de la classification des caractéristiques avec une taxonomie commune.

## La taxonomie d'Audience Manager

<!-- c_common_taxonomy_about.xml -->

La [!DNL Audience Manager] taxonomie est une fonction facultative qui classe les caractéristiques en utilisant des conventions d’affectation de nom uniformes, logiques et communément comprises. Il fonctionne au niveau de la plate-forme pour assurer la cohérence des noms dans tout l' [!DNL Audience Manager] écosystème. En fin de compte, la taxonomie commune est conçue pour aligner davantage notre produit sur les normes de l'industrie en ce qui concerne la protection de la vie privée des consommateurs et les processus d'exclusion.

## Avantages de la classification des caractéristiques

Permettre à nos clients de créer des segments et des modèles de données personnalisés est essentiel au [!DNL Audience Manager] modèle et à votre capacité à capturer de la valeur à partir de notre plateforme. Toutefois, il est également nécessaire de disposer d’un moyen robuste et évolutif de communiquer des informations sur les segments à vos clients et partenaires. De plus, cette communication exige que les informations sur les segments soient partagées dans un langage facile à comprendre et universellement compris, tout en protégeant vos caractéristiques et noms de segments propriétaires. La taxonomie [!DNL Audience Manager] commune fournit ce langage et cette capacité.

## La Taxonomie Utilise Les Catégories De Classification Standard De L'Industrie

La taxonomie commune est basée sur les classifications créées par le [!DNL Interactive Advertising Bureau (IAB)]. Consultez le [!DNL IAB]site Web du [](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) Ministère pour en savoir plus sur les lignes directrices d'assurance de la qualité pour les réseaux et les échanges.

## Organisation taxonomique

La [!DNL Audience Manager] taxonomie classe les données en catégories imbriquées appelées niveaux. Chaque catégorie peut contenir jusqu’à 3 niveaux distincts pour la classification des données. Au niveau le plus élevé, une catégorie de niveau 1 regroupe les données dans leur forme la plus générale (par exemple, la géographie). Les niveaux suivants fournissent une plus grande spécificité au niveau supérieur, catégorie générale (par exemple, *géographie —&gt; États-Unis —&gt; New York*). Cependant, chaque catégorie n'a pas 3 niveaux, certains n'utilisent que 2.

## Classification des caractéristiques dans les catégories de données

Vous affectez des classifications taxonomiques lors de la création ou de la modification de caractéristiques dans [!UICONTROL Add New Trait Wizard] (situé dans * **[!UICONTROL Audience Data > Traits]***). Pour plus d’informations, consultez la [documentation sur la création de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md) .

## Travailler avec la taxonomie : Remarques supplémentaires

Si vous décidez de classer les caractéristiques selon notre taxonomie commune, il est important de se souvenir :

* La classification est *facultative*.
* Les caractéristiques ne *sont pas* attribuées par défaut à une catégorie taxonomique (c.-à-d. que les caractéristiques ne sont pas classées comme "inconnues" ou "non classées", etc.).
* Les caractéristiques peuvent appartenir à *une seule* catégorie taxonomique (les classifications multiples et intercatégories ne sont pas autorisées).