---
description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager par le biais d’une intégration côté client (côté navigateur) ou d’une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour Google Publisher Tags dans Audience Manager.
seo-description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager par le biais d’une intégration côté client (côté navigateur) ou d’une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour Google Publisher Tags dans Audience Manager.
seo-title: Création d’une destination GPT
solution: Audience Manager
title: Création d’une destination GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Intégration tierce
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 7%

---

# Création d’une destination GPT {#create-a-gpt-destination}

Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] par le biais d’une intégration côté client (côté navigateur) ou d’une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour [!DNL Google Publisher Tags] en Audience Manager.

## Destinations 

En Audience Manager, un *`destination`* correspond à tout autre système (serveur publicitaire, [!DNL DSP], réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et gérer ces processus de diffusion des données. Les fonctions de destination de l’Audience Manager se trouvent dans *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

## Informations fondamentales

Pour terminer la section [!UICONTROL Basic Information] :

1. Nommez la destination.
1. Sélectionnez **[!UICONTROL "Cookie"]** dans la liste déroulante [!UICONTROL Type].
1. Cliquez sur **[!UICONTROL Next]** et passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] .

## Configuration des cookies

Indiquez les informations suivantes pour remplir la section [!UICONTROL Configuration] (les autres champs sont facultatifs) :

1. **Nom du cookie :** attribuez un nom court et descriptif à votre cookie.
1. **Format des données :** sélectionnez l’ **[!UICONTROL "Single Key"]** option .
1. **Clé :** indiquez un nom de clé.
1. **Sérialiser :** cochez la  **[!UICONTROL Enable]** case.
1. **Délimiteur série :** utilisez une virgule uniquement.

## Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. Rechercher des segments : La section [!UICONTROL Segment Mappings] fournit deux outils de recherche pour aider à localiser les segments. Pour trouver un segment :

   * Option 1 : Commencez à saisir un nom de segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte saisi. Cliquez sur **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : Cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement de stockage. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous avez terminé.

1. **Ajouter des mappages :** dans la fenêtre contextuelle Mappings, saisissez l’identifiant du segment dans le champ mappings et cliquez sur  **[!UICONTROL Save]**.

1. Cliquez sur **[!UICONTROL Done]**.
