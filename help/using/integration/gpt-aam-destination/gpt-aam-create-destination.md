---
description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager via une intégration côté client (côté navigateur) ou côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher en Audience Manager.
seo-description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager via une intégration côté client (côté navigateur) ou côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher en Audience Manager.
seo-title: Création d’une destination GPT
solution: Audience Manager
title: Création d’une destination GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---


# Création d’une destination GPT {#create-a-gpt-destination}

Vous pouvez envoyer des segments qualifiés vers [!DNL Google Ad Manager] via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour [!DNL Google Publisher Tags] en Audience Manager.

## Destinations 

In Audience Manager, a *`destination`* is any other system (ad server, [!DNL DSP], ad network, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion de données. Les fonctions de destination des Audiences Manager se trouvent dans *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]**et suivez les étapes ci-dessous.

## Informations fondamentales

Pour compléter la [!UICONTROL Basic Information] section :

1. Nommez la destination.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Cliquez sur **[!UICONTROL Next]** et passez aux [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] sections.

## Configuration des cookies

Fournissez les informations suivantes pour remplir la [!UICONTROL Configuration] section (les autres champs sont facultatifs) :

1. **Nom du cookie :** Donnez un nom court et descriptif à votre cookie.
1. **Format des données :** Sélectionnez l’ **[!UICONTROL "Single Key"]** option.
1. **Clé :** Indiquez un nom de clé.
1. **Sérialiser :** Cochez la **[!UICONTROL Enable]** case.
1. **Délimiteur série :** Utilisez une virgule uniquement.

## Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. Rechercher des segments : La [!UICONTROL Segment Mappings] section fournit deux outils de recherche pour aider à localiser les segments. Pour rechercher un segment :

   * Option 1 : Début de saisie du nom d’un segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte saisi. Cliquez sur **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : Cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement d’enregistrement. Cliquez **[!UICONTROL Add Selected Segments]** une fois terminé.

1. **Mappages des Ajoutes :** Dans la fenêtre Mappages, saisissez l’identifiant du segment dans le champ Mappages, puis cliquez sur **[!UICONTROL Save]**.

1. Cliquez sur **[!UICONTROL Done]**.