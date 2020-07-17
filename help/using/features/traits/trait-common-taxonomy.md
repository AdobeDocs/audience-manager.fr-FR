---
description: Cet article présente un aperçu général de la classification des caractéristiques avec une taxonomie commune.
keywords: DIL
seo-description: Cet article présente un aperçu général de la classification des caractéristiques avec une taxonomie commune.
seo-title: Classification de caractéristiques avec une taxonomie commune
solution: Audience Manager
title: Classification de caractéristiques avec une taxonomie commune
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 4%

---


# Classification de caractéristiques avec une taxonomie commune {#classifying-traits-with-a-common-taxonomy}

Cet article présente un aperçu général de la classification des caractéristiques avec une taxonomie commune.

## La taxonomie des Audiences Manager

<!-- c_common_taxonomy_about.xml -->

La [!DNL Audience Manager] taxonomie est une fonction facultative qui classe les caractéristiques en utilisant des conventions d&#39;attribution de noms uniformes, logiques et communément comprises. Il opère au niveau de la plate-forme pour assurer la cohérence des noms dans tout l&#39; [!DNL Audience Manager] écosystème. En fin de compte, la taxonomie commune est conçue pour aligner davantage notre produit sur les normes de l&#39;industrie en ce qui concerne la protection des renseignements personnels des consommateurs et les processus d&#39;exclusion.

## Avantages de la classification des caractéristiques

Permettre à nos clients de créer des segments et des modèles de données personnalisés est au coeur du [!DNL Audience Manager] modèle et de votre capacité à capturer de la valeur à partir de notre plateforme. Cependant, il est également nécessaire de disposer d’un moyen robuste et évolutif de communiquer des informations sur les segments à vos clients et partenaires. De plus, cette communication exige que les informations sur les segments soient partagées dans un langage compréhensible et universel tout en protégeant vos caractéristiques et noms de segment propriétaires. La taxonomie [!DNL Audience Manager] commune fournit ce langage et cette fonctionnalité.

## La taxonomie utilise les Catégories de classification standard du secteur

La taxonomie commune est basée sur les classifications créées par le [!DNL Interactive Advertising Bureau (IAB)]. Consultez le [!DNL IAB]site Web [de](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) l&#39;Office pour en savoir plus sur les lignes directrices d&#39;assurance de la qualité pour les réseaux et les échanges.

## Organisation taxonomique

La [!DNL Audience Manager] taxonomie organise les données en catégories imbriquées appelées niveaux. Chaque catégorie peut contenir jusqu’à 3 niveaux distincts pour la classification des données. Au niveau le plus élevé, une catégorie de niveau 1 regroupe les données sous sa forme la plus générale (par exemple, la géographie). Les niveaux suivants offrent une plus grande spécificité à la catégorie générale de niveau supérieur (par exemple, *géographie —> États-Unis —> New York*). Cependant, chaque catégorie n&#39;a pas 3 niveaux, certaines n&#39;en utilisent que 2.

## Classifier les caractéristiques dans les Catégories de données

Vous affectez des classifications taxonomiques lors de la création ou de la modification de caractéristiques dans le [!UICONTROL Add New Trait Wizard] (situé dans * **[!UICONTROL Audience Data > Traits]***). Pour plus d’informations, consultez la [documentation sur la création de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md) .

## Travailler avec la taxonomie : Considérations supplémentaires

Si vous décidez de classer les caractéristiques selon notre taxonomie commune, il est important de se souvenir :

* La classification est *facultative*.
* Par défaut, les caractéristiques ne *sont pas* attribuées à une catégorie taxonomique (c&#39;est-à-dire qu&#39;elles ne sont pas classées comme &quot;inconnues&quot; ou &quot;non catégorisées&quot;, etc.).
* Les caractéristiques peuvent appartenir à *une seule* catégorie taxonomique (les classifications multiples et entre catégories ne sont pas autorisées).