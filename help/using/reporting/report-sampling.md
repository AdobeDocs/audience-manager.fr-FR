---
description: Un résumé de la méthodologie d’échantillonnage utilisée pour certains rapports, les taux d’erreur d’échantillonnage et une liste des rapports qui renvoient des informations basées sur des données échantillonnées.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: Échantillonnage des données et taux d’erreur dans les rapports Audience Manager sélectionnés
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Échantillonnage des données et taux d’erreur dans les rapports Audience Manager sélectionnés{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Un résumé de la méthodologie d’échantillonnage utilisée pour certains rapports, les taux d’erreur d’échantillonnage et une liste des rapports qui renvoient des informations basées sur des données échantillonnées.

## Rapport d’échantillonnage de données {#data-sampling-ratio}

Certains rapports [!DNL Audience Manager] affichent des résultats en fonction d’un ensemble échantillonné de la quantité totale de données disponibles. Le rapport de données échantillonné est de 1:54. Pour les rapports qui utilisent des données échantillonnées, cela signifie que vos résultats sont basés sur 1 enregistrement sur chaque ensemble de 54 enregistrements.

Ces rapports utilisent des données statistiques échantillonnées car ils ont besoin d’une énorme puissance de calcul pour générer des résultats. L’échantillonnage permet de trouver un équilibre entre la réduction des exigences de calcul, le maintien des performances du système et la fourniture de résultats précis.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Taux d’erreurs {#error-rates}

Des erreurs peuvent se produire dans les rapports qui génèrent des données de chevauchement. Une erreur est définie comme le pourcentage d’enregistrements qui :

* N’aurait pas dû être inclus dans un rapport, mais a été ajouté de toute façon.
* Ils auraient dû être inclus dans un rapport, mais ont été exclus.

Il est important de noter que nos tests et modèles montrent que le taux d’erreur *diminue* en proportion inverse du nombre d’enregistrements dans votre jeu de données. Les jeux de données contenant un grand nombre d’enregistrements génèrent moins d’erreurs que les jeux contenant un petit nombre d’enregistrements. Examinons cette assertion d&#39;une manière plus quantitative. Comme le montre le tableau suivant, pour un nombre défini d’enregistrements, 95 % des résultats de votre rapport seront inférieurs à un taux d’erreur spécifique.

| Nombre d’enregistrements | Taux d’erreurs |
|--- |--- |
| 500 - 1 000 | 95 % ont un taux d’erreur inférieur à 42 %. |
| 1 000 - 1 500 | 95 % ont un taux d’erreur inférieur à 34 %. |
| 10 000 - 50 000 | 95 % ont un taux d’erreur inférieur à 14 %. |
| 50 000 | 95 % ont un taux d’erreur inférieur à 6 %. |
| 100 000 | 95 % ont un taux d’erreur inférieur à 4 %. |
| 500 000 (ou plus) | 95 % ont un taux d’erreur inférieur à 2 %. |

## Utilisation de la méthodologie d’échantillonnage Minhash {#minhash}

Basée sur la méthodologie d’échantillonnage [Minhash](https://en.wikipedia.org/wiki/MinHash), Audience Manager utilise une nouvelle méthode pour calculer les estimateurs de caractéristiques et de segments en plus d’une esquisse de données de hachage à une permutation. Cette nouvelle méthode produit une variance inférieure à l&#39;estimateur standard pour la similarité de Jaccard. Voir la section ci-dessous pour connaître les rapports qui utilisent cette méthodologie.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Rapports Qui Utilisent Des Données Échantillonnées {#reports-using-sampled-data}

Les rapports [!DNL Audience Manager] qui utilisent des données statistiques échantillonnées et la méthodologie d’échantillonnage de Minhash incluent :

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Échantillonnage statistique | Méthodologie d’échantillonnage de Minhash |
|--- |--- |
| [&#x200B; Audience adressable &#x200B;](../features/addressable-audiences.md) données (données au niveau du client et du segment). | [&#x200B; Rapports de chevauchement &#x200B;](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait à trait, segment à trait et segment à segment) |
| La mesure [Nombre total d’appareils](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) pour un [!UICONTROL Profile Merge Rule]. | [Recommandations de caractéristiques](/help/using/features/segments/trait-recommendations.md) |
| [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) utilise des données échantillonnées dans l’onglet [!UICONTROL Search] et tout [!UICONTROL Saved Searches] | [Recommandations Audience Marketplace](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
