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

Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] via une intégration côté client (côté navigateur) ou côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur un cookie pour [!DNL Google Publisher Tags] en Audience Manager.

## Destinations 

En Audience Manager, un *`destination`* correspond à tout autre système (serveur publicitaire, [!DNL DSP], réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion de données. Les fonctions de destination de l&#39;Audience Manager se trouvent dans *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

## Informations fondamentales

Pour compléter la section [!UICONTROL Basic Information] :

1. Nommez la destination.
1. Sélectionnez **[!UICONTROL "Cookie"]** dans la liste déroulante [!UICONTROL Type].
1. Cliquez sur **[!UICONTROL Next]** et passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings].

## Configuration des cookies

Fournissez les informations suivantes pour compléter la section [!UICONTROL Configuration] (les autres champs sont facultatifs) :

1. **Nom du cookie :** attribuez un nom court et descriptif à votre cookie.
1. **Format des données :** sélectionnez l’ **[!UICONTROL "Single Key"]** option.
1. **Clé :** indiquez un nom de clé.
1. **Sérialiser :** cochez la  **[!UICONTROL Enable]** case.
1. **Délimiteur de série :** utilisez une virgule uniquement.

## Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. Rechercher des segments : La section [!UICONTROL Segment Mappings] fournit deux outils de recherche pour aider à localiser les segments. Pour rechercher un segment :

   * Option 1 : Début de saisie du nom d’un segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte saisi. Cliquez sur **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : Cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement d’enregistrement. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous avez terminé.

1. **Mappages des Ajoutes :** dans la fenêtre Mappages, saisissez l’identifiant du segment dans le champ Mappages, puis cliquez sur  **[!UICONTROL Save]** Mappages.

1. Cliquez sur **[!UICONTROL Done]**.