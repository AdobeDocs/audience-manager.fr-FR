---
description: Résumé de la méthodologie d'échantillonnage utilisée pour certains rapports, taux d'erreurs d'échantillonnage et liste de rapports qui renvoient des informations basées sur des données échantillonnées.
seo-description: Résumé de la méthodologie d'échantillonnage utilisée pour certains rapports, taux d'erreurs d'échantillonnage et liste de rapports qui renvoient des informations basées sur des données échantillonnées.
seo-title: Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés
solution: Audience Manager
title: Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 8%

---


# Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Résumé de la méthodologie d&#39;échantillonnage utilisée pour certains rapports, taux d&#39;erreurs d&#39;échantillonnage et liste de rapports qui renvoient des informations basées sur des données échantillonnées.

## Ratio d’échantillonnage des données et exigences minimales {#data-sampling-ratio}

Certains [!DNL Audience Manager] rapports affichent les résultats en fonction d’un ensemble échantillonné de la quantité totale de données disponibles. Le rapport de données échantillonné est de 1:54. Pour les rapports qui utilisent des données échantillonnées, cela signifie que vos résultats sont basés sur un enregistrement sur chaque ensemble de 54 enregistrements.

Ces rapports utilisent des données échantillonnées car ils ont besoin d&#39;une puissance de calcul énorme pour générer des résultats. L’échantillonnage permet d’équilibrer les exigences informatiques réduites, de maintenir les performances du système et de fournir des résultats précis.

Les rapports qui utilisent l’échantillonnage excluent les caractéristiques et les segments lorsqu’ils ne répondent pas aux exigences minimales du visiteur unique. Ces exigences minimales sont les suivantes :

* Caractéristiques : 28 000 réalisations [de caractéristiques](/help/using/features/traits/trait-and-segment-qualification-reference.md#unique-trait-realizations) uniques sur une période de 14 jours.
* Segments : 70 000 utilisateurs en temps réel sur une période de 14 jours.

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

## Rapports utilisant des données échantillonnées {#reports-using-sampled-data}

Les [!DNL Audience Manager] rapports qui utilisent des données échantillonnées incluent :

* [Chevauchement des rapports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (de caractéristique à caractéristique, de segment à caractéristique et de segment à segment).
* [Données d’Audience](../features/addressable-audiences.md) adressables (données au niveau du client et du segment).
* Mesure [Total des périphériques](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) pour un [!UICONTROL Profile Merge Rule]groupe.
* [L’Explorateur](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) de données utilise des données échantillonnées dans l’ [!UICONTROL Search] onglet et dans tout [!UICONTROL Saved Searches]onglet.