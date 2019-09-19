---
description: Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-description: Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-title: Rechercher des signaux par paires clé-valeur
title: Rechercher des signaux par paires clé-valeur
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Rechercher des signaux par paires clé-valeur {#search-signals-by-key-value-pairs}

Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
Pour rechercher plusieurs signaux, cliquez sur le bouton ![Ajouter](assets/icon_add.png) . Entrez les paires clé-valeur à rechercher, puis utilisez les filtres suivants pour affiner vos résultats.

* **État** du signal : rechercher les signaux inclus dans les caractéristiques, les signaux inutilisés ou les deux.
* **Afficher les enregistrements pour**: sélectionnez l’intervalle de temps dans lequel rechercher les signaux reçus.
* **Nombre** minimum : affiche uniquement les signaux avec le nombre total minimal spécifié dans l’intervalle sélectionné.

>[!IMPORTANT]
>
>Pour une expérience utilisateur simplifiée, les résultats de la recherche par paires clé-valeur reposent sur l’échantillonnage des données. Voir Echantillonnage de [données et Taux](/help/using/reporting/report-sampling.md) d’erreur pour en savoir plus sur la [!DNL Audience Manager] manière dont l’échantillonnage des données est utilisé et sur les raisons pour lesquelles de légères variations de résultats peuvent apparaître lors de la comparaison entre la recherche clé-valeur et les recherches générales.

Lors de la recherche de signaux utilisant plusieurs paires clé-valeur, [!DNL Audience Manager] lie les paires à l’aide de l’opérateur logique **ET** . Supposons, par exemple, que vous effectuiez une recherche avec les paires clé-valeur suivantes :

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Cette recherche renvoie uniquement les résultats qui répondent aux critères des trois filtres du même appel : `c_creative == "12345"` `AND` `c_product == "smartphone"``AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Insensibilité à la casse et exécution automatique de la recherche {#case-insensitivity}

Les champs de recherche de clé et de valeur ne sont pas sensibles à la casse. Le champ de recherche de clés contient des suggestions de saisie semi-automatique.

![](assets/signal-search-suggestions.png)

Disons que [!DNL Audience Manager] nous avons reçu les signaux suivants :

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Lorsque vous entrez `product` dans le champ de recherche de clés, vous recevez des suggestions de saisie semi-automatique `productCategory`, `newProduct`, `PRODUCT`et `product`.

De même, lorsque vous recherchez `product == phone`, [!UICONTROL Data Explorer] renvoie des résultats pour `PRODUCT == phone` et `product == PHONE`.
Les réalisations de caractéristiques avec renvoi sont insensibles à la casse. Un trait contenant le signal avec la paire clé-valeur `PRODUCT == SMARTPHONE` qualifie également le signal avec la paire clé-valeur `product == smartphone`.