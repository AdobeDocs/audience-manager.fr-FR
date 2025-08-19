---
description: Vous pouvez envoyer des segments qualifiés à Google Ad Manager par le biais d’une intégration côté client (côté navigateur) ou côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur des cookies pour les balises Google Publisher dans Audience Manager.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Créer une destination GPT
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 1%

---

# Créer une destination GPT {#create-a-gpt-destination}

Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] par le biais d’une intégration côté client (côté navigateur) ou côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur des cookies pour les [!DNL Google Publisher Tags] dans Audience Manager.

## Destinations

Dans Audience Manager, un *`destination`* correspond à tout autre système (serveur de publicités, [!DNL DSP], réseau de publicités, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion de données. Les fonctionnalités de destination d’Audience Manager se trouvent dans *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

## Informations fondamentales

Pour remplir la section [!UICONTROL Basic Information] :

1. Nommez la destination.
1. Sélectionnez **[!UICONTROL "Cookie"]** dans la liste déroulante [!UICONTROL Type] .
1. Cliquez sur **[!UICONTROL Next]** et passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] .

## Configuration des cookies

Fournissez les éléments suivants pour remplir la section [!UICONTROL Configuration] (les autres champs sont facultatifs) :

1. **Nom du cookie :** donnez un nom court et descriptif à votre cookie.
1. **Format des données :** sélectionnez l’option **[!UICONTROL "Single Key"]** .
1. **Clé :** indiquez un nom de clé.
1. **Sérialiser :** cochez la case **[!UICONTROL Enable]**.
1. **Délimiteur de série :** utilisez une virgule uniquement.

## Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. Rechercher des segments : la section [!UICONTROL Segment Mappings] fournit deux outils de recherche pour localiser les segments. Pour rechercher un segment :

   * Option 1 : commencez à saisir un nom de segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte saisi. Cliquez sur **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement de stockage. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous avez terminé.

1. **Ajouter des mappages :** dans la fenêtre contextuelle des mappages, saisissez l’identifiant du segment dans le champ Mappages et cliquez sur **[!UICONTROL Save]**.

1. Cliquez sur **[!UICONTROL Done]**.
