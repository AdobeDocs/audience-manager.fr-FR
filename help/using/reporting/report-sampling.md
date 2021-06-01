---
description: Résumé de la méthodologie d’échantillonnage utilisée pour certains rapports, taux d’erreur d’échantillonnage et liste des rapports qui renvoient des informations sur la base de données échantillonnées.
seo-description: Résumé de la méthodologie d’échantillonnage utilisée pour certains rapports, taux d’erreur d’échantillonnage et liste des rapports qui renvoient des informations sur la base de données échantillonnées.
seo-title: Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés
solution: Audience Manager
title: Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Référence de création de rapports
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 7%

---

# Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Résumé de la méthodologie d’échantillonnage utilisée pour certains rapports, taux d’erreur d’échantillonnage et liste des rapports qui renvoient des informations sur la base de données échantillonnées.

## Rapport d’échantillonnage de données {#data-sampling-ratio}

Certains rapports [!DNL Audience Manager] affichent les résultats en fonction d’un échantillon de la quantité totale de données disponibles. Le rapport de données échantillonné est de 1:54. Pour les rapports qui utilisent des données échantillonnées, cela signifie que vos résultats sont basés sur 1 enregistrement sur chaque ensemble de 54 enregistrements.

Ces rapports utilisent des données échantillonnées statistiques, car ils ont besoin d’une puissance de calcul considérable pour générer des résultats. L’échantillonnage permet d’établir un équilibre entre la réduction des exigences de calcul, la conservation des performances du système et la fourniture de résultats précis.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Taux d’erreur {#error-rates}

Des erreurs peuvent se produire dans les rapports qui génèrent des données de chevauchement. Une erreur est définie en tant que pourcentage d&#39;enregistrements qui :

* N’aurait pas dû être inclus dans un rapport, mais a été ajouté de toute façon.
* Aurait dû être inclus dans un rapport, mais il a été exclu.

Il est important de noter que nos tests et modèles montrent que le taux d’erreur *diminue* dans une proportion inverse par rapport au nombre d’enregistrements dans votre jeu de données. Les jeux de données comportant de nombreux enregistrements génèrent moins d’erreurs que les jeux comportant un petit nombre d’enregistrements. Regardons cette assertion d&#39;une manière plus quantitative. Comme illustré dans le tableau suivant, pour un nombre d’enregistrements défini, 95 % des résultats du rapport seront inférieurs à un taux d’erreur spécifique.

| Nombre d’enregistrements | Taux d’erreur |
|--- |--- |
| 500 à 1 000 | 95 % sont sous un taux d’erreur de 42 %. |
| 1 000 à 1 500 | 95 % sont sous un taux d’erreur de 34 %. |
| 10 000 à 50 000 | 95 % sont sous un taux d’erreur de 14 %. |
| 50 000 | 95 % sont sous un taux d’erreur de 6 %. |
| 100 000 | 95 % sont sous un taux d’erreur de 4 %. |
| 500 000 (ou plus) | 95 % sont sous un taux d’erreur de 2 %. |

## Utilisation de la méthodologie d’échantillonnage de hachage {#minhash}

Sur la base de la [méthodologie d’échantillonnage Minhash](https://en.wikipedia.org/wiki/MinHash), l’Audience Manager utilise une nouvelle méthode pour calculer les estimateurs de caractéristiques et de segments au-dessus d’une esquisse de données de hachage à une permutation. Cette nouvelle méthode produit une variance inférieure à celle de l’estimateur standard pour la similarité de Jaccard. Consultez la section ci-dessous pour connaître les rapports qui utilisent cette méthodologie.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Rapports qui utilisent des données échantillonnées {#reports-using-sampled-data}

Les [!DNL Audience Manager] rapports qui utilisent des données échantillonnées statistiques et la méthodologie d’échantillonnage de l’empreinte digitale incluent :

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Tirage statistique | Méthodologie d’échantillonnage par hachage |
|--- |--- |
| [Données ](../features/addressable-audiences.md) d’audience adressables (données au niveau du client et du segment). | [Rapports de chevauchement](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)  (caractéristique à caractéristique, segment à caractéristique et segment à segment) |
| Mesure [Total des appareils](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) pour une [!UICONTROL Profile Merge Rule]. | [Recommandations de caractéristiques](/help/using/features/segments/trait-recommendations.md) |
| [Data ](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) Explorer utilise des données échantillonnées dans l’ [!UICONTROL Search] onglet et tout  [!UICONTROL Saved Searches] | [Audience Marketplace Recommendations](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
