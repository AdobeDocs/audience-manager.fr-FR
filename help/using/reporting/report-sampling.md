---
description: Résumé de la méthodologie d’échantillonnage utilisée pour certains rapports, taux d’erreurs d’échantillonnage et liste des rapports qui renvoient des informations basées sur des données échantillonnées.
seo-description: Résumé de la méthodologie d’échantillonnage utilisée pour certains rapports, taux d’erreurs d’échantillonnage et liste des rapports qui renvoient des informations basées sur des données échantillonnées.
seo-title: Echantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés
solution: Audience Manager
title: Echantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
translation-type: tm+mt
source-git-commit: d96182b0741dd31cc5ec0ffb68182ed5f8445c03

---


# Echantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Résumé de la méthodologie d’échantillonnage utilisée pour certains rapports, taux d’erreurs d’échantillonnage et liste des rapports qui renvoient des informations basées sur des données échantillonnées.

## Rapport d’échantillonnage des données et configuration minimale requise {#data-sampling-ratio}

Certains [!DNL Audience Manager] rapports affichent des résultats en fonction d’un ensemble échantillonné de la quantité totale de données disponibles. Le rapport de données échantillonné est de 1:54. Pour les rapports qui utilisent des données échantillonnées, cela signifie que vos résultats reposent sur un enregistrement sur chaque ensemble de 54 enregistrements.

Ces rapports utilisent des données échantillonnées parce qu’ils ont besoin d’une énorme puissance de calcul pour générer des résultats. L’échantillonnage permet de trouver un équilibre entre la réduction des demandes de calcul, le maintien des performances du système et la précision des résultats.

Les rapports qui utilisent l’échantillonnage excluent les caractéristiques et les segments lorsqu’ils ne répondent pas aux exigences minimales des visiteurs uniques. Ces exigences minimales sont les suivantes :

* Caractéristiques : 28 000 réalisations [de caractéristiques](/help/using/features/traits/trait-qualification-reference.md#unique-trait-realizations) uniques sur une période de 14 jours.
* Segments : 70 000 utilisateurs en temps réel sur une période de 14 jours.

## Taux d'erreur {#error-rates}

Des erreurs peuvent se produire dans les rapports qui génèrent des données de chevauchement. Une erreur est définie comme le pourcentage d’enregistrements qui :

* N’aurait pas dû être inclus dans un rapport, mais il a été tout de même ajouté.
* Il aurait dû être inclus dans un rapport, mais il a été omis.

Il est important de noter que nos tests et modèles montrent que le taux d'erreur *diminue* inversement proportionnellement au nombre d'enregistrements dans votre jeu de données. Les ensembles de données contenant un grand nombre d’enregistrements génèrent moins d’erreurs que les ensembles contenant un petit nombre d’enregistrements. Regardons cette affirmation d'une manière plus quantitative. Comme le montre le tableau suivant, pour un nombre défini d’enregistrements, 95 % des résultats du rapport sont inférieurs à un taux d’erreur spécifique.

| Nombre d'enregistrements | Taux d’erreurs |
|--- |--- |
| 500 - 1,000 | 95 % ont un taux d’erreur de 42 %. |
| 1,000 - 1,500 | 95 % ont un taux d’erreur de 34 %. |
| 10,000 - 50,000 | 95 % ont un taux d’erreur de 14 %. |
| 50 000 | 95 % sont sous un taux d’erreur de 6 %. |
| 100,000 | 95 % sont sous un taux d’erreur de 4 %. |
| 500 000 (ou plus) | 95 % ont un taux d’erreur de 2 %. |

## Rapports utilisant des données échantillonnées {#reports-using-sampled-data}

Les [!DNL Audience Manager] rapports qui utilisent des données échantillonnées incluent :

* [Rapports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) de chevauchement (trait à trait, segment à trait et segment à segment).
* [Données d’audience](../features/addressable-audiences.md) adressables (données au niveau du client et du segment).
* Mesure [Total des périphériques](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) pour un [!UICONTROL Profile Merge Rule].
