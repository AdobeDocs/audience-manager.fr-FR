---
description: Configurez Open Ad Server comme destination et envoyez les données d’Audience Manager vers cette plateforme.
seo-description: Configurez Open Ad Server comme destination et envoyez les données d’Audience Manager vers cette plateforme.
seo-title: OAS comme destination d’Audience Manager
solution: Audience Manager
title: OAS comme destination d’Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# OAS comme destination d’Audience Manager {#oas-as-an-audience-manager-destination}

Configurez [!DNL Open Ad Server] comme destination et envoyez les données d’Audience Manager vers cette plateforme.

## Exigences de destination OAS {#oas-requirements}

Normes relatives au placement du code, aux formats de valeur clé pris en charge, aux rapports et au type de données de segment envoyées à [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Ce type de destination requiert les éléments suivants :

* **[!UICONTROL DIL]** : le [!UICONTROL Data Integration Library] code doit être déployé sur votre inventaire. [!UICONTROL DIL] évite d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page.
* **`get_aamCookie`** Fonction : Code qui capture l’ID utilisateur et les données de cookie d’Audience Manager. Placez [ce code](../../features/destinations/get-aam-cookie-code.md) en haut de la page ou à l’intérieur du `<head>` bloc de codes.
* **** Envoyer les journaux de remise à Audience Manager : Si vous souhaitez un rapport de diffusion de segments (facultatif), fournissez à Audience Manager un journal quotidien contenant des données de diffusion au niveau de l’impression. Les données peuvent être au format brut, mais chaque enregistrement doit contenir Audience Manager [!UICONTROL UUID]. Audience Manager peut les récupérer ou les recevoir via [!DNL FTP].

### Format du cookie et données de valeur clé

Audience Manager peut envoyer des données de segment à un cookie de navigateur comme suit :

* Clés uniques (`x=1&x=2`);
* Plusieurs clés (`x=1&x=2&y=3&y=4`);
* Valeurs sérialisées (`x=1,2,3`);
* Délimiteur de valeur standard utilisé pour séparer les paires clé-valeur individuelles.

### Seuls les segments qualifiés sont envoyés à l’OEA

La quantité de données transmises à [!DNL OAS] dépend du nombre de segments auxquels un utilisateur particulier est admissible. Supposons, par exemple, que vous configuriez 100 segments d’Audience Manager. Si un visiteur du site est admissible pour cinq d’entre eux, seuls ces cinq segments sont envoyés à l’OEA (pas tous les 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie Code](../../features/destinations/get-aam-cookie-code.md)
>* [Paires clé-valeur expliquées](../../reference/key-value-pairs-explained.md)


## Créer une destination OAS {#oas-dest-setup}

Créez une destination basée sur des cookies pour [!DNL OAS] dans Audience Manager.

<!-- aam-oas-destination-setup.xml -->

Dans Audience Manager, une *destination* correspond à tout autre système (serveur d’annonces, [!DNL DSP], réseau d’annonces, etc.) que vous souhaitez partager avec. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de remise des données. Les fonctionnalités de destination d’Audience Manager se trouvent dans *Audience Data &gt; Destinations*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

### Étape 1 :Informations de base

Pour compléter la [!UICONTROL Basic Information] section :

1. Nommez la destination.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Cliquez sur **[!UICONTROL Save]** puis passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] .

### Étape 2 : Informations de configuration

Pour compléter la [!UICONTROL Configuration] section :

1. **** Nom du cookie : Donnez un nom court et descriptif à votre cookie.
1. **** Domaine du cookie : Laissez ce champ vide pour définir un cookie dans le domaine de la page active de l’utilisateur. Si vous souhaitez spécifier un domaine, ajoutez un préfixe au nom avec un point de ce type `.mydomain.com`.
1. Choisissez une option clé dans la [!UICONTROL Data Format] section.
1. Si vos clés utilisent des données avec des valeurs sérialisées, sélectionnez le **[!UICONTROL Serialize]** contrôle et spécifiez le délimiteur série (le caractère qui sépare les valeurs sérialisées).
1. Cliquez sur **[!UICONTROL Save]** puis développez la [!UICONTROL Segment Mappings] section.

### Étape 3 :Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. **** Rechercher des segments : La [!UICONTROL Segment Mappings] section fournit deux outils de recherche pour faciliter la localisation des segments. Pour rechercher un segment :
   * Option 1 : Commencez à saisir le nom d’un segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte. Cliquez **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : Cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement de stockage. Click **[!UICONTROL Add Selected Segments]** when done.
1. **** Ajouter des mappages : Dans la fenêtre contextuelle Mappages, saisissez l’ID du segment dans le champ Mappages, puis cliquez sur **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Done]**.

## Configuration OAS {#oas-code-setup}

Modifiez [!DNL OAS] les paramètres pour qu’ils fonctionnent avec les données de segments d’Audience Manager.

<!-- aam-oas-code.xml -->

Pour configurer [!DNL OAS]

* Installez le [!UICONTROL DIL] code sur votre site.
* Créez OAS en tant que destination de cookie dans Audience Manager.
* Placez la `get_aamCookie` fonction en haut de la page, idéalement dans le `<head>` cadenas. Le `get_aamCookie` code est disponible [ici](../../features/destinations/get-aam-cookie-code.md).
* Modifiez la balise de votre publicité pour appeler la `get_aamCookie` fonction et inclure le nom du cookie que vous avez fourni lors de la configuration de la [!DNL OAS] destination. Par exemple, si vous avez nommé le cookie `test_cookie`, la balise publicitaire doit appeler `get_aamCookie` et référencer le nom du cookie.
* Votre balise publicitaire peut ressembler à l’exemple ci-dessous.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Pensez à inclure la `u=` variable. Il contient l’ID utilisateur unique ([!UICONTROL UUID]) réel transmis lors d’un appel publicitaire.
