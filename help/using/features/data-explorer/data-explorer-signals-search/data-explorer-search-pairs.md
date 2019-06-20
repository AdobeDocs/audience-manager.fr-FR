---
description: Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-description: Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-title: Rechercher des signaux par paires clé-valeur
title: Rechercher des signaux par paires clé-valeur
uuid: 2 a 38 d 0 d 4-4 a 2 e -4 ca 5-b 9 ec-af 9 d 4963 d 876
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

---


# Search Signals by Key-Value Pairs {#search-signals-by-key-value-pairs}

Recherchez un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
To search for more than one signal, click the ![Add](assets/icon_add.png) button. Entrez les paires clé-valeur à rechercher, puis utilisez les filtres suivants pour réduire vos résultats.

* **État du signal**: rechercher des signaux inclus dans des caractéristiques, des signaux inutilisés ou les deux.
* **Afficher les enregistrements pour**: sélectionnez l&#39;intervalle dans lequel rechercher les signaux reçus.
* **Nombre minimum**: n&#39;affiche que les signaux avec le nombre total minimal spécifié dans l&#39;intervalle sélectionné.

>[!IMPORTANT]
>
>Pour une expérience utilisateur simplifiée, les résultats de recherche de paire clé-valeur sont basés sur l&#39;échantillonnage des données. See [Data Sampling and Error Rates](/help/using/reporting/report-sampling.md) for details on how [!DNL Audience Manager] uses data sampling and why slight result variations may appear when comparing key-value search to general searches.

When searching for signals using multiple key-value pairs, [!DNL Audience Manager] links the pairs using the logical **AND** operator. Par exemple, supposons que vous réalisiez une recherche avec les paires clé-valeur suivantes :

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

This search will return only results that qualify for all three filters on the same call: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Case Insensitivity and Search Auto-Completion {#case-insensitivity}

Les champs de recherche de clé et de valeur ne sont pas sensibles à la casse. Le champ de recherche clé inclut les suggestions semi-complétées.

![](assets/signal-search-suggestions.png)

Let&#39;s say [!DNL Audience Manager] received the following signals:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

When you enter `product` in the key search field, you receive auto-completed suggestions for `productCategory`, `newProduct`, `PRODUCT`, and `product`.

Similarly, when you search for `product == phone`, [!UICONTROL Data Explorer] returns results for both `PRODUCT == phone` and `product == PHONE`.
Les realizations de caractéristiques renvoyées ne sont pas sensibles à la casse. A trait containing the signal with the key-value pair `PRODUCT == SMARTPHONE` also qualifies the signal with the key-value pair `product == smartphone`.