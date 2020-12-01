---
description: Le créateur de destinations vous permet de créer des destinations URL basées sur des cookies ou DNL. Vous ne pouvez pas créer de destinations de serveur à serveur (S2S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S2S. Le créateur de destinations se trouve sous Données d’Audience > Destinations.
seo-description: Le créateur de destinations vous permet de créer des destinations URL basées sur des cookies ou DNL. Vous ne pouvez pas créer de destinations de serveur à serveur (S2S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S2S. Le créateur de destinations se trouve sous Données d’Audience > Destinations.
seo-title: Créateur de destinations
solution: Audience Manager
title: Créateur de destinations
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 4%

---


# Créateur de destinations {#destination-builder}

[!UICONTROL Destination Builder] vous permet de créer des  [!DNL URL] destinations ou basées sur des cookies. Vous ne pouvez pas créer de destinations serveur à serveur ([!DNL S2S]) avec [!UICONTROL Destination Builder], mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination [!DNL S2S]. [!UICONTROL Destination Builder] se trouve dans  **[!UICONTROL Audience Data > Destinations]**.

## Paramètres du créateur de destinations {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] se compose des sections et paramètres suivants :

| [!UICONTROL Destination Builder] Section | Rôle |
|--- |--- |
| Informations fondamentales | Utilisé pour nommer la destination, la décrire et sélectionner le type de destination ([!DNL URL] ou [!DNL cookie]) et la plateforme (all, [!DNL Android], browser ou [!DNL iOS]). |
| Configuration | Comprend des contrôles pour : <br/><ul><li>Transmission de données de valeur de clé aux destinations [!DNL URL]. Vous pouvez envoyer des données sous la forme de paires clé-valeur individuelles ou sérialisées. Pour plus d’informations, voir [Sérialisation de destination](../../features/destinations/key-value-pairs.md#destination-serialized) et [Paires de valeurs de clé standard et série](../../features/destinations/key-value-pairs.md). </li><li>Éléments d’une destination de cookie tels que le nom du cookie, le domaine, la taille, l’intervalle d’expiration, le format de données, etc.</li></ul> |
| Mappages de segments | Permet de: <br/><ul><li>Recherchez, ajoutez et gérez des segments associés à tous les types de destination. </li><li>Définissez des priorités de diffusion sur des segments individuels (pour les segments basés sur [!DNL cookie] uniquement).</li></ul> |

## Méthodes de Diffusion de données {#data-delivery-methods}

Envoyez des informations à une destination en les transmettant par le biais d&#39;une chaîne [!DNL URL], en les écrivant à un navigateur [!DNL cookie] ou par le biais de transferts de données de serveur à serveur hors ligne.

* [!DNL URL] et les destinations basées sur des cookies transmettent les données de manière synchrone, lorsqu’un utilisateur agit sur une page.
* La transmission des données serveur à serveur est asynchrone et peut survenir longtemps après que l’utilisateur a quitté la page. Le type de diffusion que vous sélectionnez dépend des besoins de votre entreprise et de la manière dont un partenaire de données spécifique souhaite ou peut recevoir des données.

Voir [Comment choisir un type de destination](../../features/destinations/destinations.md) pour plus d&#39;informations.