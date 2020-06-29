---
description: Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-description: Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-title: Signaux de recherche par paires clé-valeur
title: Signaux de recherche par paires clé-valeur
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---


# Signaux de recherche par paires clé-valeur {#search-signals-by-key-value-pairs}

Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
Pour rechercher plusieurs signaux, cliquez sur le bouton ![Ajouter](assets/icon_add.png) . Entrez les paires clé-valeur à rechercher, puis utilisez les filtres suivants pour affiner vos résultats.

* **État** du signal : rechercher les signaux inclus dans les caractéristiques, les signaux inutilisés ou les deux.
* **Enregistrements de Vue pour**: sélectionnez l’intervalle de temps dans lequel rechercher les signaux reçus.
* **Nombre** minimum : afficher uniquement les signaux avec le nombre total minimal spécifié dans l’intervalle sélectionné.

>[!IMPORTANT]
>
>Pour une expérience utilisateur simplifiée, les résultats de la recherche par paires clé-valeur reposent sur l’échantillonnage des données. Voir Échantillonnage des [données et taux](/help/using/reporting/report-sampling.md) d’erreur pour en savoir plus sur l’ [!DNL Audience Manager] utilisation de l’échantillonnage des données et sur les raisons pour lesquelles de légères variations de résultats peuvent apparaître lors de la comparaison entre la recherche de valeur clé et les recherches générales.

Lors de la recherche de signaux utilisant plusieurs paires clé-valeur, [!DNL Audience Manager] lie les paires à l’aide de l’opérateur logique **ET** . Par exemple, supposons que vous effectuiez une recherche avec les paires clé-valeur suivantes :

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Cette recherche ne retournera que les résultats correspondant aux trois filtres du même appel : `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signaux exclus de la recherche de signaux {#excluded-signals}

Les variables clés utilisées par l’Audience Manager et préfixées par le `d_` préfixe et le préfixe `h_` ne sont pas mises en évidence par [!UICONTROL Signals Search]. Pour plus d’informations, voir [Préfixe requis pour les variables](../../traits/trait-variable-prefixes.md) clés.

## Insensibilité à la casse et auto-exécution de la recherche {#case-insensitivity}

Les champs de recherche de clé et de valeur ne tiennent pas compte de la casse. Le champ de recherche clé contient des suggestions remplies automatiquement.

![](assets/signal-search-suggestions.png)

Disons que [!DNL Audience Manager] nous avons reçu les signaux suivants :

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Lorsque vous entrez `product` dans le champ de recherche de clés, vous recevez des suggestions remplies automatiquement pour `productCategory`, `newProduct`, `PRODUCT`et `product`.

De même, lorsque vous recherchez `product == phone`, [!UICONTROL Data Explorer] renvoie des résultats pour les deux `PRODUCT == phone` et `product == PHONE`.
Les réalisations de caractéristiques renvoyées ne tiennent pas compte de la casse. Un trait contenant le signal avec la paire clé-valeur `PRODUCT == SMARTPHONE` qualifie également le signal avec la paire clé-valeur `product == smartphone`.