---
description: Résumé de la méthodologie d'échantillonnage utilisée pour certains rapports, taux d'erreurs d'échantillonnage et liste des rapports renvoyant des informations sur la base de données échantillonnées.
seo-description: Résumé de la méthodologie d'échantillonnage utilisée pour certains rapports, taux d'erreurs d'échantillonnage et liste des rapports renvoyant des informations sur la base de données échantillonnées.
seo-title: Taux d'échantillonnage et d'erreur des données dans les rapports Audience Manager sélectionnés
solution: Audience Manager
title: Taux d'échantillonnage et d'erreur des données dans les rapports Audience Manager sélectionnés
uuid: 3 d 8 bd 764-a 9 da -40 f 1-8794-54304457 bb 9 a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Data Sampling and Error Rates in Selected Audience Manager Reports{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Résumé de la méthodologie d'échantillonnage utilisée pour certains rapports, taux d'erreurs d'échantillonnage et liste des rapports renvoyant des informations sur la base de données échantillonnées.

## Data Sampling Ratio and Minimum Requirements {#data-sampling-ratio}

Some [!DNL Audience Manager] reports display results based on a sampled set of the total amount of available data. Le taux de données échantillonné est 1:54. Dans le cas des rapports utilisant des données échantillonnées, cela signifie que vos résultats sont basés sur 1 enregistrement parmi chaque jeu de 54 enregistrements.

Ces rapports utilisent des données échantillonnées, car ils nécessitent une quantité importante de puissance informatique pour générer des résultats. L'échantillonnage permet d'équilibrer les exigences de calcul réduites, de conserver les performances du système et de fournir des résultats précis.

Les rapports qui utilisent un échantillonnage excluent les caractéristiques et les segments lorsqu'ils ne répondent pas aux exigences minimales des visiteurs uniques. Ces conditions minimales sont les suivantes :

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) over a 14-day period.
* Segments : 70 000 utilisateurs en temps réel sur une période de 14 jours.

## Error Rates {#error-rates}

Des erreurs peuvent se produire dans les rapports qui génèrent des données de chevauchement. Une erreur est définie sous forme d'un pourcentage d'enregistrements :

* N'auraient pas dû être inclus dans un rapport, mais ont toujours été ajoutés.
* Ils auraient dû être inclus dans un rapport, mais ils ont été omis.

It's important to note that our tests and models show that the error rate *decreases* in an inverse proportion to the number of records in your data set. Les jeux de données qui comportent beaucoup d'enregistrements génèrent moins d'erreurs que les ensembles avec un petit nombre d'enregistrements. Examinons cette affirmation de manière plus quantitative. Comme le montre le tableau suivant, pour un nombre d'enregistrements défini, 95 % des résultats du rapport seront inférieurs à un taux d'erreur spécifique.

| Nombre d'enregistrements | Taux d'erreur |
|--- |--- |
| 500 - 1,000 | 95 % d'erreurs se situent sous un taux d'erreur de 42 %. |
| 1,000 - 1,500 | 95 % se situent sous un taux d'erreur de 34 %. |
| 10,000 - 50,000 | 95 % se situent sous un taux d'erreur de 14 %. |
| 50 000 | 95 % se situent sous un taux d'erreur de 6 %. |
| 100,000 | 95 % se situent sous un taux d'erreur de 4 %. |
| 500 000 (ou plus) | 95 % se situent sous un taux d'erreur de 2 %. |

## Reports That Use Sampled Data {#reports-using-sampled-data}

The [!DNL Audience Manager] reports that use sampled data include:

* [Rapports de chevauchement](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (caractéristique-à-caractéristique, segment-à-caractéristique et segment-à-segmenter).
* [Données d'audience](../features/addressable-audiences.md) adressables (données au niveau des clients et des segments).
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
