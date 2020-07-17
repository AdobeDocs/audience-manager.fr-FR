---
description: Configurez OpenX en tant que destination et envoyez les données de segment d’Audience Manager à cette plateforme.
seo-description: Configurez OpenX en tant que destination et envoyez les données de segment d’Audience Manager à cette plateforme.
seo-title: OpenX en tant que destination d’Audience Manager
solution: Audience Manager
title: OpenX en tant que destination d’Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%

---


# OpenX en tant que destination d’Audience Manager{#openx-as-an-audience-manager-destination}

Configurez [!DNL OpenX] comme destination et envoyez des données de segment d’Audience Manager à cette plateforme.

>[!NOTE]
>
>Pour le ciblage sur site des serveurs d’annonces uniquement.

## Exigences de destination OpenX {#openx-requirements}

Normes relatives au placement du code, aux formats de valeur clé pris en charge, aux rapports et au type de données de segment envoyées à [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Examinez les éléments suivants avant de configurer [!DNL OpenX] une destination d’Audience Manager :

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library]doit être déployé sur votre site.[!UICONTROL DIL]aide à éliminer la nécessité d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page.
* **`get_aamCookie`Fonction :**Code qui capture l’ID utilisateur et les données de cookie de l’Audience Manager. Placez[ce code](../../features/destinations/get-aam-cookie-code.md)en haut de la page ou à l’intérieur du`<head>`bloc de codes.
* **Envoyer des Logs de diffusion à l&#39;Audience Manager :** Si vous souhaitez créer un rapport de diffusion de segments (facultatif), fournissez à l’Audience Manager un journal quotidien contenant des données de diffusion au niveau de l’impression. Les données peuvent être au format brut, mais chaque enregistrement doit contenir l’Audience Manager `UUID`. L&#39;Audience Manager peut les prendre ou les recevoir via [!DNL FTP].

### Données clés-valeurs : Format requis

L’Audience Manager envoie des données sous la forme de paires clé-valeur. Créez des paires clé-valeur selon les spécifications suivantes :

* Clés de préface avec `c.` (par ex. `c.color` ou `c.price`).
* Séparez les valeurs sérialisées associées à une seule clé par une virgule ( `c.color = red, green, blue`par exemple).
* Séparez plusieurs paires clé-valeur par une esperluette (par exemple `c.color=red & c.price = 100 & c.condition = new`).
* Les noms de clés ne doivent pas contenir de caractères spéciaux tels que des signes d’accentuation et de ponctuation ou d’autres symboles.

### Seuls les segments qualifiés sont envoyés à OpenX

Le montant des données transmises à [!DNL OpenX] dépend du nombre de segments pour lesquels un utilisateur particulier est admissible. Supposons, par exemple, que vous configuriez 100 segments d’Audience Manager. Si un visiteur de site est admissible pour cinq d&#39;entre eux, seuls ces cinq segments sont envoyés à [!DNL OpenX] (pas tous les 100).

## Création d’une destination OpenX {#openx-destination}

Créez une destination de cookie pour [!DNL OpenX] en Audience Manager.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion de données. Les fonctions de destination de l’Audience Manager se trouvent dans *Audience Data > Destinations*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

### Étape 1 : Informations de base

Pour compléter la [!UICONTROL Basic Information] section :

1. Nommez la destination.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Cliquez sur **[!UICONTROL Next]** et passez aux [!UICONTROL Configuration] et [!UICONTROL Segment Mappings] sections.

### Étape 2 : Informations de configuration

Pour compléter la [!UICONTROL Configuration] section :

1. **Nom du cookie :** Donnez un nom court et descriptif à votre cookie.
1. **Domaine du cookie :** Laissez ce champ vide pour définir un cookie dans le domaine de la page active de l’utilisateur. Si vous souhaitez spécifier un domaine, ajoutez un point au nom `.mydomain.com`.
1. Choisissez une option clé dans la [!UICONTROL Data Format] section.
1. Si vos clés utilisent des données avec des valeurs sérialisées, sélectionnez le **[!UICONTROL Serialize]** contrôle et spécifiez le délimiteur série (le caractère qui sépare les valeurs sérialisées).
1. Cliquez sur **[!UICONTROL Save]** et développez la [!UICONTROL Segment Mappings] section.

### Étape 3 : Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. **Rechercher des segments :** La [!UICONTROL Segment Mappings] section fournit deux outils de recherche pour aider à localiser les segments. Pour rechercher un segment :
   * Option 1 : Début de saisie du nom d’un segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte. Cliquez sur **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : Cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement d’enregistrement. Cliquez **[!UICONTROL Add Selected Segments]** une fois terminé.
1. **Mappages des Ajoutes :** Dans la fenêtre Mappages, saisissez l’identifiant du segment dans le champ Mappages, puis cliquez sur **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Done]**.

## Configuration d’OpenX {#openx-code-setup}

Modifiez [!DNL OpenX] les paramètres pour qu’ils fonctionnent avec les données des segments d’Audience Manager.

<!-- aam-openx-code.xml -->

Pour configurer [!DNL OpenX]:

* Installez le [!UICONTROL DIL] code sur votre site.
* Créez [!DNL OpenX] comme destination de cookie en Audience Manager.
* Placez la `get_aamCookie` fonction en haut de la page, idéalement dans le `<head>` cadenas. Le `get_aamCookie` code est disponible [ici](../../features/destinations/get-aam-cookie-code.md).
* Modifiez votre balise d&#39;annonce pour appeler la `get_aamCookie` fonction et inclure le nom de cookie que vous avez fourni lors de la configuration de la [!DNL OpenX] destination. Par exemple, si vous avez nommé le cookie `test_cookie`, la balise publicitaire doit appeler `get_aamCookie` et référencer le nom du cookie.
* Votre balise publicitaire peut ressembler à l’exemple ci-dessous.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

N’oubliez pas d’inclure `xid=` . Il contient l’ID utilisateur unique réel ([!UICONTROL UUID]) transmis au cours d’un appel publicitaire.

L’appel publicitaire entièrement formé peut ressembler à ceci :

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
