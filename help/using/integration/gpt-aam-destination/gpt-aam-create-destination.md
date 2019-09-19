---
description: Vous pouvez envoyer des segments qualifiés au DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher dans Audience Manager.
seo-description: Vous pouvez envoyer des segments qualifiés au DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher dans Audience Manager.
seo-title: Création d’une destination GPT
solution: Audience Manager
title: Création d’une destination GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Création d’une destination GPT {#create-a-gpt-destination}

Vous pouvez envoyer des segments qualifiés vers [!DNL DFP] une intégration côté client (côté navigateur) ou côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour [!DNL Google Publisher Tags] dans Audience Manager.

## Destinations

Dans Audience Manager, un *`destination`* est tout autre système (serveur d’annonces, [!DNL DSP]réseau d’annonces, etc.) que vous souhaitez partager avec. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de remise des données. Les fonctions de destination d’Audience Manager se trouvent dans *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

## Informations fondamentales

Pour compléter la [!UICONTROL Basic Information] section :

1. Nommez la destination.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Cliquez sur **[!UICONTROL Next]** puis passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] .

## Configuration du cookie

Fournissez les informations suivantes pour compléter la [!UICONTROL Configuration] section (les autres champs sont facultatifs) :

1. **** Nom du cookie : Donnez un nom court et descriptif à votre cookie.
1. **** Format des données : Sélectionnez l’ **[!UICONTROL "Single Key"]** option.
1. **** Clé : Attribuez un nom de clé.
1. **** Sérialiser : Cochez la **[!UICONTROL Enable]** case.
1. **** Délimiteur série : Utilisez une virgule uniquement.

##  Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. Rechercher des segments : La [!UICONTROL Segment Mappings] section fournit deux outils de recherche pour faciliter la localisation des segments. Pour rechercher un segment :

   * Option 1 : Commencez à saisir le nom d’un segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte saisi. Cliquez **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : Cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement de stockage. Click **[!UICONTROL Add Selected Segments]** when done.

1. **** Ajouter des mappages : Dans la fenêtre contextuelle Mappages, saisissez l’ID du segment dans le champ Mappages, puis cliquez sur **[!UICONTROL Save]**.

1. Cliquez sur **[!UICONTROL Done]**.