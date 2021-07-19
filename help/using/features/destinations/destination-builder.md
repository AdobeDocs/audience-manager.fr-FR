---
description: Destination Builder vous permet de créer des destinations d’URL basées sur des cookies ou DNL. Vous ne pouvez pas créer de destinations serveur à serveur (S2S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S2S. Destination Builder se trouve sous Audience Data > Destinations.
seo-description: Destination Builder vous permet de créer des destinations d’URL basées sur des cookies ou DNL. Vous ne pouvez pas créer de destinations serveur à serveur (S2S) avec le créateur de destinations, mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination S2S. Destination Builder se trouve sous Audience Data > Destinations.
seo-title: Créateur de destinations
solution: Audience Manager
title: Créateur de destinations
feature: Concepts de base des destinations
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Créateur de destinations {#destination-builder}

[!UICONTROL Destination Builder] vous permet de créer des  [!DNL URL] destinations ou basées sur des cookies. Vous ne pouvez pas créer de destinations serveur à serveur ([!DNL S2S]) avec [!UICONTROL Destination Builder], mais vous pouvez gérer leurs mappages de segments. Contactez votre consultant pour configurer une destination [!DNL S2S]. [!UICONTROL Destination Builder] se trouve dans  **[!UICONTROL Audience Data > Destinations]**.

## Paramètres du créateur de destinations {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] se compose des sections et paramètres suivants :

| [!UICONTROL Destination Builder] Section | Rôle |
|--- |--- |
| Informations fondamentales | Utilisé pour nommer la destination, la décrire et sélectionner le type de destination ([!DNL URL] ou [!DNL cookie]), la plateforme (all, [!DNL Android], le navigateur ou [!DNL iOS]). |
| Configuration | Comprend des commandes pour : <br/><ul><li>Transmission de données clé-valeur aux destinations [!DNL URL]. Vous pouvez envoyer des données sous la forme de paires clé-valeur individuelles ou sérialisées. Pour plus d’informations, voir [Sérialisation de destination](../../features/destinations/key-value-pairs.md#destination-serialized) et [Paires clé-valeur standard et série](../../features/destinations/key-value-pairs.md). </li><li>Éléments d’une destination de cookie tels que le nom, le domaine, la taille, l’intervalle d’expiration, le format de données, etc.</li></ul> |
| Mappages de segments | Permet de: <br/><ul><li>Recherchez, ajoutez et gérez des segments associés à tous les types de destination. </li><li>Définissez les priorités de diffusion sur des segments individuels (pour les segments [!DNL cookie] uniquement).</li></ul> |

## Méthodes de diffusion des données {#data-delivery-methods}

Envoyez des informations à une destination en les transmettant par le biais d’une chaîne [!DNL URL], en écrivant sur un navigateur [!DNL cookie] ou par le biais de transferts de données serveur à serveur hors ligne.

* [!DNL URL] et les destinations basées sur des cookies transmettent les données de manière synchrone lorsqu’un utilisateur agit sur une page.
* La transmission des données serveur à serveur est asynchrone et peut survenir longtemps après que l’utilisateur a quitté la page. Le type de diffusion sélectionné dépend des besoins de votre entreprise et de la manière dont un partenaire de données spécifique souhaite ou peut recevoir des données.

Voir [Choix d’un type de destination](../../features/destinations/destinations.md) pour plus d’informations.
