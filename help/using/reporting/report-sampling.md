---
description: Résumé de la méthodologie d'échantillonnage utilisée pour certains rapports, taux d'erreurs d'échantillonnage et liste de rapports qui renvoient des informations basées sur des données échantillonnées.
seo-description: Résumé de la méthodologie d'échantillonnage utilisée pour certains rapports, taux d'erreurs d'échantillonnage et liste de rapports qui renvoient des informations basées sur des données échantillonnées.
seo-title: Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés
solution: Audience Manager
title: Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 397be3f44bf865633140bb45630a78be0a0d2219
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 7%

---


# Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Résumé de la méthodologie d&#39;échantillonnage utilisée pour certains rapports, taux d&#39;erreurs d&#39;échantillonnage et liste de rapports qui renvoient des informations basées sur des données échantillonnées.

## Taux d’échantillonnage des données {#data-sampling-ratio}

Certains [!DNL Audience Manager] rapports affichent les résultats en fonction d’un ensemble échantillonné de la quantité totale de données disponibles. Le rapport de données échantillonné est de 1:54. Pour les rapports qui utilisent des données échantillonnées, cela signifie que vos résultats sont basés sur un enregistrement sur chaque ensemble de 54 enregistrements.

Ces rapports utilisent des données statistiques échantillonnées parce qu&#39;ils ont besoin d&#39;une énorme puissance de calcul pour générer des résultats. L’échantillonnage permet d’équilibrer les exigences informatiques réduites, de maintenir les performances du système et de fournir des résultats précis.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Taux d&#39;erreur {#error-rates}

Des erreurs peuvent se produire dans les rapports qui génèrent des données de chevauchement. Une erreur est définie comme le pourcentage d&#39;enregistrements qui :

* N&#39;aurait pas dû être inclus dans un rapport, mais a été ajouté de toute façon.
* Aurait dû être inclus dans un rapport, mais il a été omis.

Il est important de noter que nos tests et modèles montrent que le taux d&#39;erreur *diminue* inversement proportionnellement au nombre d&#39;enregistrements dans votre jeu de données. Les ensembles de données contenant de nombreux enregistrements génèrent moins d’erreurs que les ensembles contenant un petit nombre d’enregistrements. Examinons cette affirmation de manière plus quantitative. Comme le montre le tableau suivant, pour un nombre défini d&#39;enregistrements, 95 % des résultats du rapport seront inférieurs à un taux d&#39;erreur spécifique.

| Nombre d&#39;enregistrements | Taux d’erreurs |
|--- |--- |
| 500 - 1,000 | 95 % ont un taux d’erreur de 42 %. |
| 1,000 - 1,500 | 95 % ont un taux d’erreur de 34 %. |
| 10,000 - 50,000 | 95 % ont un taux d’erreur de 14 %. |
| 50 000 | 95 % ont un taux d’erreur de 6 %. |
| 100,000 | 95 % ont un taux d’erreur de 4 %. |
| 500 000 (ou plus) | 95 % ont un taux d’erreur de 2 %. |

## Utilisation de la méthodologie d’échantillonnage de hachage {#minhash}

En se basant sur la méthodologie d&#39;échantillonnage [Minhash](https://en.wikipedia.org/wiki/MinHash) , l&#39;Audience Manager utilise une nouvelle méthode pour calculer les estimateurs de caractéristiques et de segments au-dessus d&#39;une esquisse de données de hachage d&#39;une permutation unique. Cette nouvelle méthode produit une variance plus faible que l&#39;estimateur standard pour la similarité de Jaccard. Reportez-vous à la section ci-dessous pour les rapports qui utilisent cette méthodologie.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Rapports utilisant des données échantillonnées {#reports-using-sampled-data}

Les [!DNL Audience Manager] rapports qui utilisent des données statistiques échantillonnées et la méthodologie d&#39;échantillonnage de Minhash comprennent :

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Échantillonnage statistique | Méthodologie d’échantillonnage au hachage |
|--- |--- |
| [Données d’Audience](../features/addressable-audiences.md) adressables (données au niveau du client et du segment). | [Rapports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) de chevauchement (trait à trait, segment à trait et segment à segment) |
| Mesure [Total des périphériques](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) pour un [!UICONTROL Profile Merge Rule]groupe. | [Recommandations de caractéristiques](/help/using/features/segments/trait-recommendations.md) |
| [Le Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) utilise des données échantillonnées dans l’ [!UICONTROL Search] onglet et les [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
