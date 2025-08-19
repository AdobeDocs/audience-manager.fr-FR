---
description: Configurez OpenX en tant que destination et envoyez les données de segment Audience Manager à cette plateforme.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX comme destination Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# OpenX comme destination Audience Manager{#openx-as-an-audience-manager-destination}

Configurez [!DNL OpenX] en tant que destination et envoyez les données de segment Audience Manager à cette plateforme.

>[!NOTE]
>
>Pour le ciblage sur site et serveur d’annonces uniquement.

## Exigences de destination OpenX {#openx-requirements}

Normes relatives à l’emplacement du code, aux formats de valeur clé pris en charge, aux rapports et au type de données de segment envoyées à [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Consultez les éléments suivants avant de configurer [!DNL OpenX] en tant que destination Audience Manager :

* **[!UICONTROL DIL]:** le code [!UICONTROL Data Integration Library] doit être déployé sur votre site. [!UICONTROL DIL] permet d’éviter d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page.
* Fonction **`get_aamCookie`: code** capture l’ID utilisateur et les données de cookie d’Audience Manager. Placez [ce code](../../features/destinations/get-aam-cookie-code.md) en haut de la page ou à l’intérieur du bloc de code `<head>`.
* **Envoyer les journaux de diffusion à Audience Manager :** si vous souhaitez un rapport de diffusion de segment (facultatif), fournissez à Audience Manager un journal quotidien contenant les données de diffusion au niveau de l’impression. Les données peuvent être dans un format brut, mais chaque enregistrement doit contenir le `UUID` Audience Manager. Audience Manager peut les récupérer ou les recevoir via [!DNL FTP].

### Données Clé-Valeur : Exigences De Format

Audience Manager envoie des données sous la forme de paires clé-valeur. Créez des paires clé-valeur selon les spécifications suivantes :

* Clés de préface avec `c.` (par exemple, `c.color` ou `c.price`).
* Séparez les valeurs sérialisées associées à une seule clé par une virgule (par exemple, `c.color = red, green, blue`).
* Séparez plusieurs paires clé-valeur par une esperluette (par exemple, `c.color=red & c.price = 100 & c.condition = new`).
* Les noms de clé ne doivent pas contenir de caractères spéciaux tels que des accents, des signes de ponctuation ou d’autres symboles.

### Seuls les segments qualifiés sont envoyés à OpenX.

La quantité de données transmises à [!DNL OpenX] dépend du nombre de segments pour lesquels un utilisateur particulier est qualifié. Supposons, par exemple, que vous ayez configuré 100 segments Audience Manager. Si un visiteur ou une visiteuse du site remplit les conditions de cinq d’entre eux, seuls ces cinq segments sont envoyés à [!DNL OpenX] (pas les 100).

## Création d’une destination OpenX {#openx-destination}

Créez une destination de cookie pour les [!DNL OpenX] dans Audience Manager.

<!-- aam-openx-destination.xml -->

Dans Audience Manager, une *destination* désigne tout autre système (serveur publicitaire, [!DNL DSP], réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion de données. Les fonctionnalités de destination d’Audience Manager se trouvent dans *Données d’audience > Destinations*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

### Étape 1 : informations de base

Pour remplir la section [!UICONTROL Basic Information] :

1. Nommez la destination.
1. Sélectionnez **[!UICONTROL "Cookie"]** dans la liste déroulante [!UICONTROL Type] .
1. Cliquez sur **[!UICONTROL Next]** et passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] .

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

## Configuration d’OpenX {#openx-code-setup}

Modifiez [!DNL OpenX] paramètres pour utiliser les données de segment Audience Manager.

<!-- aam-openx-code.xml -->

Pour configurer [!DNL OpenX] :

* Installez le code [!UICONTROL DIL] sur l’ensemble de votre site.
* Créez [!DNL OpenX] comme destination de cookie dans Audience Manager.
* Placez la fonction `get_aamCookie` en haut de la page, idéalement dans le bloc de code `<head>`. Le code `get_aamCookie` est disponible [ici](../../features/destinations/get-aam-cookie-code.md).
* Modifiez la balise publicitaire pour appeler la fonction `get_aamCookie` et inclure le nom du cookie que vous avez fourni lors de la configuration de la destination [!DNL OpenX]. Par exemple, si vous avez nommé le cookie `test_cookie`, la balise d’annonce doit appeler `get_aamCookie` et référencer le nom du cookie.
* Votre balise publicitaire peut ressembler à l’exemple ci-dessous.

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

N’oubliez pas d’inclure `xid=` . Il contient l’ID d’utilisateur unique ([!UICONTROL UUID]) transmis lors d’un appel publicitaire.

L’appel publicitaire entièrement formé pourrait ressembler à ceci :

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
