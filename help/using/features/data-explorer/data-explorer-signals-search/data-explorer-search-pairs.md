---
description: Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-description: Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-title: Recherche de signaux par paires clé-valeur
title: Recherche de signaux par paires clé-valeur
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: 'Explorateur de données '
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 5%

---

# Recherche de signaux par paires clé-valeur {#search-signals-by-key-value-pairs}

Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
Pour rechercher plusieurs signaux, cliquez sur le bouton ![Ajouter](assets/icon_add.png) . Entrez les paires clé-valeur que vous souhaitez rechercher, puis utilisez les filtres suivants pour réduire vos résultats.

* **État du signal** : rechercher des signaux inclus dans les caractéristiques, des signaux inutilisés ou les deux.
* **Afficher les enregistrements pour** : sélectionnez l’intervalle dans lequel rechercher les signaux reçus.
* **Nombre** minimum : afficher uniquement les signaux avec le nombre total minimal spécifié dans l’intervalle sélectionné.

>[!IMPORTANT]
>
>Pour une expérience utilisateur rationalisée, les résultats de la recherche par paires clé-valeur reposent sur l’échantillonnage de données. Voir [Échantillonnage de données et taux d’erreur](/help/using/reporting/report-sampling.md) pour plus d’informations sur la façon dont [!DNL Audience Manager] utilise l’échantillonnage de données et sur les raisons pour lesquelles de légères variations de résultats peuvent apparaître lors de la comparaison entre la recherche de valeur clé et les recherches générales.

Lors de la recherche de signaux utilisant plusieurs paires clé-valeur, [!DNL Audience Manager] lie les paires à l’aide de l’opérateur logique **AND** . Supposons, par exemple, que vous effectuiez une recherche avec les paires clé-valeur suivantes :

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Cette recherche ne renverra que les résultats qui remplissent les critères des trois filtres du même appel : `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signaux exclus de la recherche de signaux {#excluded-signals}

Les variables clés utilisées par l’Audience Manager et affectées du préfixe `d_` et `h_` ne sont pas affichées par [!UICONTROL Signals Search]. Voir [Exigences de préfixe pour les variables clés](../../traits/trait-variable-prefixes.md) pour plus d’informations.

## Insensibilité à la casse et auto-complétion de recherche {#case-insensitivity}

Les champs de recherche de clé et de valeur ne sont pas sensibles à la casse. Le champ de recherche de clés comprend des suggestions complétées automatiquement.

![](assets/signal-search-suggestions.png)

Supposons que [!DNL Audience Manager] ait reçu les signaux suivants :

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Lorsque vous saisissez `product` dans le champ de recherche de clé, vous recevez des suggestions remplies automatiquement pour `productCategory`, `newProduct`, `PRODUCT` et `product`.

De même, lorsque vous recherchez `product == phone`, [!UICONTROL Data Explorer] renvoie des résultats pour `PRODUCT == phone` et `product == PHONE`.
Les réalisations de caractéristiques renvoyées ne sont pas sensibles à la casse. Une caractéristique contenant le signal avec la paire clé-valeur `PRODUCT == SMARTPHONE` qualifie également le signal avec la paire clé-valeur `product == smartphone`.
