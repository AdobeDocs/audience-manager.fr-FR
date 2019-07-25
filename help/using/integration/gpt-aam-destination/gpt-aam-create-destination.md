---
description: Vous pouvez envoyer des segments qualifiés au DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l'intégration côté client, vous devez créer une destination basée sur cookie pour les balises Google Publisher dans Audience Manager.
seo-description: Vous pouvez envoyer des segments qualifiés au DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l'intégration côté client, vous devez créer une destination basée sur cookie pour les balises Google Publisher dans Audience Manager.
seo-title: Création d'une destination GPT
solution: Audience Manager
title: Création d'une destination GPT
uuid: e 3 bbf 327-a 7 e 0-48 da-bc 84-8 f 531 b 7 f 6750
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Create a GPT Destination {#create-a-gpt-destination}

You can send qualified segments to [!DNL DFP] through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for [!DNL Google Publisher Tags] in Audience Manager.

## Destinations

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) dont vous souhaitez partager les données. [!UICONTROL Destination Builder] fournit les outils vous permettant de créer et de gérer ces processus de remise de données. Audience Manager destination features are located in *[!UICONTROL Audience Data]&gt;[!UICONTROL Destinations]*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

## Informations fondamentales

To complete the [!UICONTROL Basic Information] section:

1. Nommez la destination.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

## Configuration des cookies

Provide the following to complete the [!UICONTROL Configuration] section (other fields are optional):

1. **Nom du cookie :** Fournissez un nom court et descriptif pour votre cookie.
1. **Format des données :** Sélectionnez l' **[!UICONTROL "Single Key"]** option.
1. **Clé :** Fournissez un nom de clé.
1. **Sérialiser :** **[!UICONTROL Enable]** Cochez la case.
1. **Délimiteur de série :** Utilisez une virgule uniquement.

## Correspondances de segments

Pour ajouter un segment à une destination de cookie :

1. Find segments: The [!UICONTROL Segment Mappings] section provides two search tools to help locate segments. Pour trouver un segment :

   * Option 1 : Commencez à saisir un nom de segment dans le champ de recherche. Le champ se met automatiquement à jour en fonction du texte saisi. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.

1. **Ajouter des mappages :** Dans la fenêtre des correspondances, entrez l'identifiant du segment dans le champ des correspondances et cliquez **[!UICONTROL Save]** sur.

1. Cliquez sur **[!UICONTROL Done]**.