---
description: Configurez le serveur d'annonces Open comme destination et envoyez les données Audience Manager à cette plateforme.
seo-description: Configurez le serveur d'annonces Open comme destination et envoyez les données Audience Manager à cette plateforme.
seo-title: OAS en tant que destination d'Audience Manager
solution: Audience Manager
title: OAS en tant que destination d'Audience Manager
uuid: 5891 a 063-5 a 4 b -4 ea 7-865 f-b 24 e 17 ca 735 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OAS as an Audience Manager Destination {#oas-as-an-audience-manager-destination}

Set up [!DNL Open Ad Server] as a destination and send Audience Manager data to that platform.

## OAS Destination Requirements {#oas-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Ce type de destination requiert les éléments suivants :

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] le code doit être déployé sur votre inventaire. [!UICONTROL DIL] aide à éliminer la nécessité d'écrire du code spécial pour la collecte de données, l'intégration, la lecture des valeurs de cookie et la récupération des données de la page.
* **`get_aamCookie`Fonction :** Code qui capture l'utilisateur Audience Manager - id et données des cookies. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Envoyer des journaux de diffusion à Audience Manager :** Si vous souhaitez un rapport de diffusion de segment (facultatif), fournissez à Audience Manager un journal quotidien contenant des données de diffusion au niveau d'impression. The data can be in a raw format, but each record must contain the Audience Manager [!UICONTROL UUID]. Audience Manager can pick up or receive these via [!DNL FTP].

### Format du cookie et données de clé-valeur

Audience Manager peut envoyer des données de segmentation à un cookie de navigateur comme suit :

* Single keys (`x=1&x=2`);
* Multiple keys (`x=1&x=2&y=3&y=4`);
* Serialized values (`x=1,2,3`);
* Séparateur de valeur standard servant à séparer les paires clé-valeur individuelles.

### Seuls les segments qualifiés sont envoyés à OAS

The amount data passed in to [!DNL OAS] depends on how many segments a particular user qualifies for. Par exemple, supposons que vous configurez 100 segments de gestion de l'audience. Si un visiteur de site est admissible pour cinq d'entre eux, seuls ces cinq segments sont envoyés à OAS (pas tous les 100).

>[!MORE_ LIKE_ THIS]
>
>* [get_ aamcookie Code](../../features/destinations/get-aam-cookie-code.md)
>* [Paires clé-valeur expliquées](../../reference/key-value-pairs-explained.md)


## Create an OAS Destination {#oas-dest-setup}

Create a cookie-based destination for [!DNL OAS] in Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) dont vous souhaitez partager les données. [!UICONTROL Destination Builder] fournit les outils vous permettant de créer et de gérer ces processus de remise de données. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Étape 1 : Informations de base

To complete the [!UICONTROL Basic Information] section:

1. Nommez la destination.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Save]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### Étape 2 : Informations de configuration

To complete the [!UICONTROL Configuration] section:

1. **Nom du cookie :** Fournissez un nom court et descriptif pour votre cookie.
1. **Domaine du cookie :** Laissez vide pour définir un cookie dans le domaine de la page active de l'utilisateur. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### Étape 3 : Correspondances de segments

Pour ajouter un segment à une destination de cookie :

1. **Rechercher des segments :** La [!UICONTROL Segment Mappings] section fournit deux outils de recherche pour faciliter la localisation des segments. Pour trouver un segment :
   * Option 1 : Commencez à saisir un nom de segment dans le champ de recherche. Le champ se met automatiquement à jour en fonction du texte. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **Ajouter des mappages :** Dans la fenêtre des correspondances, entrez l'identifiant du segment dans le champ des correspondances et cliquez **[!UICONTROL Save]** sur.
1. Cliquez sur **[!UICONTROL Done]**.

## OAS Setup {#oas-code-setup}

Modify [!DNL OAS] settings to work with Audience Manager segment data.

<!-- aam-oas-code.xml -->

To set up [!DNL OAS]

* Install [!UICONTROL DIL] code across your site.
* Créez l'OAS en tant que destination de cookie dans Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` Le code est disponible [ici](../../features/destinations/get-aam-cookie-code.md).
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OAS] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* La balise publicitaire peut ressembler à l'exemple ci-dessous.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Remember to include the `u=` variable. It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.
