---
description: Destination Builder vous permet de créer des destinations d’URL basées sur des cookies ou DNL. Vous ne pouvez pas créer de destinations serveur à serveur (S2S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S2S. Destination Builder se trouve sous Audience Data > Destinations.
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Créateur de destinations
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Créateur de destinations {#destination-builder}

[!UICONTROL Destination Builder] vous permet de créer des destinations basées sur des cookies ou [!DNL URL]. Vous ne pouvez pas créer de destinations serveur à serveur ([!DNL S2S]) avec [!UICONTROL Destination Builder], mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination [!DNL S2S]. [!UICONTROL Destination Builder] se trouve dans **[!UICONTROL Audience Data > Destinations]**.

## Paramètres du créateur de destinations {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] se compose des sections et paramètres suivants :

| Section [!UICONTROL Destination Builder] | Rôle |
|--- |--- |
| Informations fondamentales | Utilisé pour nommer la destination, la décrire et sélectionner le type de destination ([!DNL URL] ou [!DNL cookie]) et la plateforme (all, [!DNL Android], browser ou [!DNL iOS]). |
| Configuration | Inclut des contrôles pour : <br/><ul><li>Transmission de données clé-valeur vers des destinations [!DNL URL]. Vous pouvez envoyer des données sous la forme de paires clé-valeur individuelles ou sérialisées. Pour plus d’informations, voir [Sérialisation de destination](../../features/destinations/key-value-pairs.md#destination-serialized) et [Paires clé-valeur standard et série](../../features/destinations/key-value-pairs.md). </li><li>Éléments d’une destination de cookie tels que le nom, le domaine, la taille, l’intervalle d’expiration, le format de données, etc.</li></ul> |
| Mappages de segments | Permet : <br/><ul><li>Recherchez, ajoutez et gérez des segments associés à tous les types de destination. </li><li>Définissez les priorités de diffusion sur des segments individuels (pour les segments basés sur [!DNL cookie] uniquement).</li></ul> |

## Méthodes de diffusion des données {#data-delivery-methods}

Envoyez des informations à une destination en les transmettant par le biais d’une chaîne [!DNL URL], en écrivant sur un navigateur [!DNL cookie] ou par le biais de transferts de données serveur à serveur hors ligne.

* [!DNL URL] et les destinations basées sur des cookies transmettent les données de manière synchrone, lorsqu’un utilisateur agit sur une page.
* La transmission des données serveur à serveur est asynchrone et peut survenir longtemps après que l’utilisateur a quitté la page. Le type de diffusion sélectionné dépend des besoins de votre entreprise et de la manière dont un partenaire de données spécifique souhaite ou peut recevoir des données.

Pour plus d’informations, voir [Choix d’un type de destination](../../features/destinations/destinations.md) .
