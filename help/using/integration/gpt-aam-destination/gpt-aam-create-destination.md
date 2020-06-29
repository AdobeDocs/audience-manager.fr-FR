---
description: Vous pouvez envoyer des segments qualifiés à DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher en Audience Manager.
seo-description: Vous pouvez envoyer des segments qualifiés à DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher en Audience Manager.
seo-title: Créer une destination GPT
solution: Audience Manager
title: Créer une destination GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 1%

---


# Créer une destination GPT {#create-a-gpt-destination}

Vous pouvez envoyer des segments qualifiés vers [!DNL DFP] via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour [!DNL Google Publisher Tags] en Audience Manager.

## Destinations 

En Audience Manager, un *`destination`* est tout autre système (serveur publicitaire, [!DNL DSP]réseau publicitaire, etc.) que vous souhaitez partager avec. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion de données. Les fonctions de destination des Audiences Manager se trouvent dans *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]**et suivez les étapes ci-dessous.

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