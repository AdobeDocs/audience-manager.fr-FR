---
description: Rechercher un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Rechercher des signaux par paires clé-valeur
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Recherche de signaux par paires clé-valeur {#search-signals-by-key-value-pairs}

Rechercher un ou plusieurs signaux, en fonction de leurs paires clé-valeur respectives.
Pour rechercher plusieurs signaux, cliquez sur le bouton ![Ajouter](assets/icon_add.png). Saisissez les paires clé-valeur à rechercher, puis utilisez les filtres suivants pour affiner vos résultats.

* **État du signal** : recherchez les signaux inclus dans les caractéristiques, les signaux inutilisés, ou les deux.
* **Afficher les enregistrements pour** : sélectionnez l’intervalle de temps dans lequel rechercher les signaux reçus.
* **Nombres minimaux** : affichez uniquement les signaux dont le nombre total minimal est spécifié dans l’intervalle sélectionné.

>[!IMPORTANT]
>
>Pour une expérience utilisateur rationalisée, les résultats de la recherche par paire clé-valeur sont basés sur l’échantillonnage de données. Consultez la section [Échantillonnage de données et taux d’erreur](/help/using/reporting/report-sampling.md) [!DNL Audience Manager] pour plus d’informations sur l’utilisation de l’échantillonnage de données et sur les raisons pour lesquelles de légères variations de résultats peuvent apparaître lorsque vous comparez une recherche clé-valeur à des recherches générales.

Lors de la recherche de signaux à l&#39;aide de plusieurs paires clé-valeur, [!DNL Audience Manager] relie les paires à l&#39;aide de l&#39;opérateur logique **AND**. Supposons, par exemple, que vous exécutiez une recherche avec les paires clé-valeur suivantes :

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Cette recherche renvoie uniquement les résultats qui remplissent les critères pour les trois filtres sur le même appel : `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signaux exclus de la recherche de signaux {#excluded-signals}

Les variables clés utilisées par Audience Manager et précédées des préfixes `d_` et `h_` ne sont pas affichées par [!UICONTROL Signals Search]. Pour plus d’informations, voir [Exigences de préfixe pour les variables clés](../../traits/trait-variable-prefixes.md).

## Respect de la casse et saisie semi-automatique des recherches {#case-insensitivity}

Les champs de recherche de clé et de valeur sont sensibles à la casse. Le champ de recherche clé inclut des suggestions auto-renseignées.

![](assets/signal-search-suggestions.png)

Supposons que [!DNL Audience Manager] ayez reçu les signaux suivants :

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

Lorsque vous saisissez `product` dans le champ de recherche de clé, vous recevez des suggestions remplies automatiquement pour `productCategory` et `product`.

De même, lorsque vous recherchez des `product == PHONE`, [!UICONTROL Data Explorer] renvoie des résultats uniquement pour les `product == PHONE`.

Les réalisations de caractéristiques renvoyées sont également sensibles à la casse. Une caractéristique contenant le signal avec la paire clé-valeur `PRODUCT == SMARTPHONE` ne qualifie pas le signal avec la paire clé-valeur `product == smartphone`.
