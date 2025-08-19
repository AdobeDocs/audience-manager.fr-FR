---
description: Configurez Open Ad Server comme destination et envoyez les données Audience Manager à cette plateforme.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: Destination OAS as a Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 0%

---

# Destination OAS as a Audience Manager {#oas-as-an-audience-manager-destination}

Configurez [!DNL Open Ad Server] en tant que destination et envoyez les données Audience Manager à cette plateforme.

## Exigences de destination OAS {#oas-requirements}

Normes relatives à l’emplacement du code, aux formats de valeur clé pris en charge, aux rapports et au type de données de segment envoyées à [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Ce type de destination nécessite les éléments suivants :

* **[!UICONTROL DIL]:** le code [!UICONTROL Data Integration Library] doit être déployé sur votre inventaire. [!UICONTROL DIL] permet d’éviter d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page.
* Fonction **`get_aamCookie`: code** capture l’ID utilisateur et les données de cookie d’Audience Manager. Placez [ce code](../../features/destinations/get-aam-cookie-code.md) en haut de la page ou à l’intérieur du bloc de code `<head>`.
* **Envoyer les journaux de diffusion à Audience Manager :** si vous souhaitez un rapport de diffusion de segment (facultatif), fournissez à Audience Manager un journal quotidien contenant les données de diffusion au niveau de l’impression. Les données peuvent être dans un format brut, mais chaque enregistrement doit contenir le [!UICONTROL UUID] Audience Manager. Audience Manager peut les récupérer ou les recevoir via [!DNL FTP].

### Format de cookie et données clé-valeur

Audience Manager peut envoyer des données de segment à un cookie de navigateur comme suit :

* Clés uniques (`x=1&x=2`);
* Clés multiples (`x=1&x=2&y=3&y=4`);
* Valeurs sérialisées (`x=1,2,3`) ;
* Délimiteur de valeur standard utilisé pour séparer les paires clé-valeur individuelles.

### Seuls les segments qualifiés sont envoyés à OAS

La quantité de données transmises à [!DNL OAS] dépend du nombre de segments pour lesquels un utilisateur particulier est qualifié. Supposons, par exemple, que vous ayez configuré 100 segments Audience Manager. Si un visiteur du site remplit les conditions de cinq d’entre eux, seuls ces cinq segments sont envoyés à OAS (pas les 100).

>[!MORELIKETHIS]
>
>* [Code get_aamCookie](../../features/destinations/get-aam-cookie-code.md)
>* [Explication des paires clé-valeur](../../reference/key-value-pairs-explained.md)

## Création d’une destination OAS {#oas-dest-setup}

Créez une destination basée sur des cookies pour les [!DNL OAS] dans Audience Manager.

<!-- aam-oas-destination-setup.xml -->

Dans Audience Manager, une *destination* désigne tout autre système (serveur publicitaire, [!DNL DSP], réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion de données. Les fonctionnalités de destination d’Audience Manager se trouvent dans *Données d’audience > Destinations*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

### Étape 1 : informations de base

Pour remplir la section [!UICONTROL Basic Information] :

1. Nommez la destination.
1. Sélectionnez **[!UICONTROL "Cookie"]** dans la liste déroulante [!UICONTROL Type] .
1. Cliquez sur **[!UICONTROL Save]** et passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] .

### Étape 2 : informations de configuration

Pour remplir la section [!UICONTROL Configuration] :

1. **Nom du cookie :** donnez un nom court et descriptif à votre cookie.
1. **Domaine du cookie :** laissez ce champ vide pour définir un cookie dans le domaine de la page active de l’utilisateur. Si vous souhaitez spécifier un domaine, ajoutez un préfixe au nom avec un point comme celui-ci, `.mydomain.com`.
1. Choisissez une option de clé dans la section [!UICONTROL Data Format].
1. Si vos clés utilisent des données avec des valeurs sérialisées, sélectionnez le contrôle **[!UICONTROL Serialize]** et spécifiez le délimiteur de série (caractère qui sépare les valeurs sérialisées).
1. Cliquez sur **[!UICONTROL Save]** et développez la section [!UICONTROL Segment Mappings] .

### Étape 3 : Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. **Rechercher des segments :** la section [!UICONTROL Segment Mappings] propose deux outils de recherche pour localiser les segments. Pour rechercher un segment :
   * Option 1 : commencez à saisir un nom de segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte. Cliquez sur **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement de stockage. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous avez terminé.
1. **Ajouter des mappages :** dans la fenêtre contextuelle des mappages, saisissez l’identifiant du segment dans le champ Mappages et cliquez sur **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Done]**.

## Configuration OAS {#oas-code-setup}

Modifiez [!DNL OAS] paramètres pour utiliser les données de segment Audience Manager.

<!-- aam-oas-code.xml -->

Pour configurer [!DNL OAS]

* Installez le code [!UICONTROL DIL] sur l’ensemble de votre site.
* Créez OAS comme destination de cookie dans Audience Manager.
* Placez la fonction `get_aamCookie` en haut de la page, idéalement dans le bloc de code `<head>`. Le code `get_aamCookie` est disponible [ici](../../features/destinations/get-aam-cookie-code.md).
* Modifiez la balise publicitaire pour appeler la fonction `get_aamCookie` et inclure le nom du cookie que vous avez fourni lors de la configuration de la destination [!DNL OAS]. Par exemple, si vous avez nommé le cookie `test_cookie`, la balise d’annonce doit appeler `get_aamCookie` et référencer le nom du cookie.
* Votre balise publicitaire peut ressembler à l’exemple ci-dessous.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

N’oubliez pas d’inclure la variable `u=` . Il contient l’ID d’utilisateur unique ([!UICONTROL UUID]) transmis lors d’un appel publicitaire.
