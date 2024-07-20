---
description: Configurez Open Ad Server comme destination et envoyez les données d’Audience Manager à cette plateforme.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS comme destination de l’Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# OAS comme destination de l’Audience Manager {#oas-as-an-audience-manager-destination}

Configurez [!DNL Open Ad Server] comme destination et envoyez les données d’Audience Manager à cette plateforme.

## Exigences de destination OAS {#oas-requirements}

Normes de placement du code, formats de valeur de clé pris en charge, rapports et type de données de segment envoyées à [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Ce type de destination requiert les éléments suivants :

* **[!UICONTROL DIL]: le code** [!UICONTROL Data Integration Library] doit être déployé sur votre inventaire. [!UICONTROL DIL] aide à éliminer la nécessité d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page.
* **`get_aamCookie`Fonction :** code qui capture l’identifiant utilisateur de l’Audience Manager et les données de cookie. Placez [ce code](../../features/destinations/get-aam-cookie-code.md) en haut de la page ou à l’intérieur du bloc de codes `<head>`.
* **Envoyer les logs de diffusion à l’Audience Manager :** Si vous souhaitez un rapport de diffusion de segment (facultatif), fournissez à l’Audience Manager un journal quotidien contenant des données de diffusion au niveau de l’impression. Les données peuvent être dans un format brut, mais chaque enregistrement doit contenir l’Audience Manager [!UICONTROL UUID]. L&#39;Audience Manager peut les récupérer ou les recevoir via [!DNL FTP].

### Format du cookie et données clé-valeur

L’Audience Manager peut envoyer des données de segment à un cookie de navigateur comme suit :

* Clés uniques (`x=1&x=2`);
* Plusieurs clés (`x=1&x=2&y=3&y=4`);
* Valeurs sérialisées (`x=1,2,3`);
* Délimiteur de valeur standard utilisé pour séparer les paires clé-valeur individuelles.

### Seuls les segments qualifiés sont envoyés à OAS

La quantité de données transmises à [!DNL OAS] dépend du nombre de segments pour lesquels un utilisateur particulier est admissible. Supposons, par exemple, que vous configuriez 100 segments d’Audience Manager. Si un visiteur du site est admissible pour cinq d’entre eux, seuls ces cinq segments sont envoyés à l’OAS (et non tous les 100).

>[!MORELIKETHIS]
>
>* [Code get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Explication des paires clé-valeur](../../reference/key-value-pairs-explained.md)

## Création d’une destination OAS {#oas-dest-setup}

Créez une destination basée sur des cookies pour [!DNL OAS] dans Audience Manager.

<!-- aam-oas-destination-setup.xml -->

En Audience Manager, une *destination* correspond à tout autre système (serveur de publicités, [!DNL DSP], réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et gérer ces processus de diffusion des données. Les fonctionnalités de destination des Audiences Manager se trouvent dans *Audience Data > Destinations*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et procédez comme suit.

### Étape 1 : informations de base

Pour terminer la section [!UICONTROL Basic Information] :

1. Nommez la destination.
1. Sélectionnez **[!UICONTROL "Cookie"]** dans la liste déroulante [!UICONTROL Type].
1. Cliquez sur **[!UICONTROL Save]** et passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] .

### Étape 2 : informations de configuration

Pour terminer la section [!UICONTROL Configuration] :

1. **Nom du cookie :** Attribuez un nom court et descriptif à votre cookie.
1. **Domaine du cookie :** Laissez vide pour définir un cookie dans le domaine de la page active de l’utilisateur. Si vous souhaitez spécifier un domaine, faites précéder le nom d’un point comme celui-ci, `.mydomain.com`.
1. Choisissez une option clé dans la section [!UICONTROL Data Format].
1. Si vos clés utilisent des données avec des valeurs sérialisées, sélectionnez le contrôle **[!UICONTROL Serialize]** et spécifiez le délimiteur série (le caractère qui sépare les valeurs sérialisées).
1. Cliquez sur **[!UICONTROL Save]** et développez la section [!UICONTROL Segment Mappings].

### Étape 3 : mappages de segments

Pour ajouter un segment à une destination de cookie :

1. **Rechercher des segments :** La section [!UICONTROL Segment Mappings] fournit deux outils de recherche pour aider à localiser les segments. Pour trouver un segment :
   * Option 1 : commencez à saisir un nom de segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte. Cliquez sur **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement de stockage. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous avez terminé.
1. **Ajouter des mappages :** Dans la fenêtre contextuelle des mappages, saisissez l’identifiant du segment dans le champ des mappages et cliquez sur **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Done]**.

## Configuration OAS {#oas-code-setup}

Modifiez les paramètres [!DNL OAS] pour qu’ils fonctionnent avec les données de segment d’Audience Manager.

<!-- aam-oas-code.xml -->

Pour configurer [!DNL OAS]

* Installez le code [!UICONTROL DIL] sur votre site.
* Créez OAS en tant que destination de cookie dans Audience Manager.
* Placez la fonction `get_aamCookie` en haut de la page, idéalement dans le bloc de code `<head>`. Le code `get_aamCookie` est disponible [ici](../../features/destinations/get-aam-cookie-code.md).
* Modifiez votre balise publicitaire pour appeler la fonction `get_aamCookie` et incluez le nom de cookie que vous avez fourni lors de la configuration de la destination [!DNL OAS]. Par exemple, si vous avez nommé le cookie `test_cookie`, la balise publicitaire doit appeler `get_aamCookie` et référencer le nom du cookie.
* Votre balise publicitaire pourrait ressembler à l’exemple ci-dessous.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

N’oubliez pas d’inclure la variable `u=`. Il contient l’identifiant utilisateur unique réel ([!UICONTROL UUID]) transmis lors d’un appel publicitaire.
