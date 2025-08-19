---
description: Destination Builder vous permet de créer des destinations d’URL basées sur des cookies ou des DNL. Vous ne pouvez pas créer de destinations serveur à serveur (S2S) avec Destination Builder, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S2S. Le Créateur de destinations se trouve dans Données d’audience > Destinations.
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

[!UICONTROL Destination Builder] vous permet de créer des destinations basées sur des cookies ou des destinations [!DNL URL]. Vous ne pouvez pas créer de destinations serveur à serveur ([!DNL S2S]) avec [!UICONTROL Destination Builder], mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination [!DNL S2S]. [!UICONTROL Destination Builder] se trouve dans **[!UICONTROL Audience Data > Destinations]**.

## Paramètres de Destination Builder {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] comprend les sections et paramètres suivants :

| Section [!UICONTROL Destination Builder] | Rôle |
|--- |--- |
| Informations fondamentales | Utilisé pour nommer la destination, la décrire et sélectionner le type de destination ([!DNL URL] ou [!DNL cookie]) et la plateforme (tous, [!DNL Android], navigateur ou [!DNL iOS]). |
| Configuration | Comprend des commandes pour : <br/><ul><li>Transmettre des données clé-valeur à des destinations [!DNL URL]. Vous pouvez envoyer des données sous la forme de paires clé-valeur individuelles ou sérialisées. Pour plus d’informations, reportez-vous aux sections [Sérialisation de destination](../../features/destinations/key-value-pairs.md#destination-serialized) et [Paires clé-valeur standard et série](../../features/destinations/key-value-pairs.md). </li><li>Éléments d’une destination de cookie tels que le nom du cookie, le domaine, la taille, l’intervalle d’expiration, le format de données, etc.</li></ul> |
| Mappages de segments | Permet de : <br/><ul><li>Rechercher, ajouter et gérer des segments associés à tous les types de destination. </li><li>Définissez les priorités de diffusion sur des segments individuels (pour les segments basés sur des [!DNL cookie] uniquement).</li></ul> |

## Méthodes de diffusion des données {#data-delivery-methods}

Envoyez des informations à une destination en les transmettant par le biais d’une chaîne de [!DNL URL], en écrivant dans un [!DNL cookie] de navigateur ou par le biais de transferts de données hors ligne de serveur à serveur.

* Les destinations [!DNL URL] et basées sur des cookies transmettent les données de manière synchrone, lorsqu’un utilisateur ou une utilisatrice agit sur une page.
* La transmission de données de serveur à serveur est asynchrone et peut se produire longtemps après qu’un utilisateur a quitté la page. Le type de diffusion que vous sélectionnez dépend des besoins de votre entreprise et de la manière dont un partenaire de données spécifique souhaite ou peut recevoir des données.

Pour plus d’informations, consultez [Choix d’un type de destination](../../features/destinations/destinations.md) .
