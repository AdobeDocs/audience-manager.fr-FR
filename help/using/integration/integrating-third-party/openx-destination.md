---
description: Configurez openx comme destination et envoyez les données de segment Audience Manager à cette plateforme.
seo-description: Configurez openx comme destination et envoyez les données de segment Audience Manager à cette plateforme.
seo-title: Openx comme destination d'Audience Manager
solution: Audience Manager
title: Openx comme destination d'Audience Manager
uuid: 5 e 86 ba 73-281 c -403 b-af 06-64 a 1 d 427526 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# OpenX as an Audience Manager Destination{#openx-as-an-audience-manager-destination}

Set up [!DNL OpenX] as a destination and send Audience Manager segment data to that platform.

>[!NOTE]
>
>Pour le ciblage du serveur publicitaire sur site uniquement.

## OpenX Destination Requirements {#openx-requirements}

Standards for code placement, supported key-value formats, reports, and the type of segment data sent to [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Review the following before setting up [!DNL OpenX] as an Audience Manager destination:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library] le code doit être déployé sur votre site. [!UICONTROL DIL] aide à éliminer la nécessité d&#39;écrire du code spécial pour la collecte de données, l&#39;intégration, la lecture des valeurs de cookie et la récupération des données de la page.
* **`get_aamCookie`Fonction :** Code qui capture l&#39;utilisateur Audience Manager - id et données des cookies. Place [this code](../../features/destinations/get-aam-cookie-code.md) on the top of the page or inside the `<head>` codeblock.
* **Envoyer des journaux de diffusion à Audience Manager :** Si vous souhaitez un rapport de diffusion de segment (facultatif), fournissez à Audience Manager un journal quotidien contenant des données de diffusion au niveau d&#39;impression. The data can be in a raw format, but each record must contain the Audience Manager `UUID`. Audience Manager can pick up or receive these via [!DNL FTP].

### Données de clé-valeur : Configuration requise

Audience Manager envoie des données sous la forme de paires clé-valeur. Créez des paires clé-valeur conformément aux spécifications suivantes :

* Preface keys with `c.` (e.g., `c.color` or `c.price`).
* Separate serialized values attached to a single key with a comma (e.g., `c.color = red, green, blue`).
* Separate multiple key-value pairs with an ampersand (e.g., `c.color=red & c.price = 100 & c.condition = new`).
* Les noms de clés ne doivent pas contenir de caractères spéciaux, tels que des signes d&#39;accent et de ponctuation ou d&#39;autres symboles.

### Seuls les segments qualifiés sont envoyés à openx

The amount data passed in to [!DNL OpenX] depends on how many segments a particular user qualifies for. Par exemple, supposons que vous configurez 100 segments de gestion de l&#39;audience. If a site visitor qualifies for five of them, then only those five segments get sent to [!DNL OpenX] (not all 100).

## Create an OpenX Destination {#openx-destination}

Create a cookie destination for [!DNL OpenX] in Audience Management.

<!-- aam-openx-destination.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) dont vous souhaitez partager les données. [!UICONTROL Destination Builder] fournit les outils vous permettant de créer et de gérer ces processus de remise de données. Audience Manager destination features are located in *Audience Data &gt; Destinations*. To get started, click **[!UICONTROL Add New Destination]** and follow the steps below.

### Étape 1 : Informations de base

To complete the [!UICONTROL Basic Information] section:

1. Nommez la destination.
1. Select **[!UICONTROL "Cookie"]** from the [!UICONTROL Type] drop-down list.
1. Click **[!UICONTROL Next]** and move on to the [!UICONTROL Configuration] and [!UICONTROL Segment Mappings] sections.

### Étape 2 : Informations de configuration

To complete the [!UICONTROL Configuration] section:

1. **Nom du cookie :** Fournissez un nom court et descriptif pour votre cookie.
1. **Domaine du cookie :** Laissez vide pour définir un cookie dans le domaine de la page active de l&#39;utilisateur. If you want to specify a domain, prefix the name with a period like this, `.mydomain.com`.
1. Choose a key option in the [!UICONTROL Data Format] section.
1. If your keys use data with serialized values, select the **[!UICONTROL Serialize]** control and specify the serial delimiter (the character that separates the serialized values).
1. Click **[!UICONTROL Save]** and expand the [!UICONTROL Segment Mappings] section.

### Étape 3 : Correspondances de segments

Pour ajouter un segment à une destination de cookie :

1. **Rechercher des segments :** La [!UICONTROL Segment Mappings] section fournit deux outils de recherche pour faciliter la localisation des segments. Pour trouver un segment :
   * Option 1 : Commencez à saisir un nom de segment dans le champ de recherche. Le champ se met automatiquement à jour en fonction du texte. Click **[!UICONTROL Add]** once you find the segment you want to use.
   * Option 2: Click **[!UICONTROL Browse All Segments]** to open a window that lets you browse for segments by name or storage location. Click **[!UICONTROL Add Selected Segments]** when done.
1. **Ajouter des mappages :** Dans la fenêtre des correspondances, entrez l&#39;identifiant du segment dans le champ des correspondances et cliquez **[!UICONTROL Save]** sur.
1. Cliquez sur **[!UICONTROL Done]**.

## OpenX Setup {#openx-code-setup}

Modify [!DNL OpenX] settings to work with Audience Manager segment data.

<!-- aam-openx-code.xml -->

To set up [!DNL OpenX]:

* Install [!UICONTROL DIL] code across your site.
* Create [!DNL OpenX] as a cookie destination in Audience Manager.
* Place the `get_aamCookie` function at the top of the page, ideally within the `<head>` codeblock. `get_aamCookie` Le code est disponible [ici](../../features/destinations/get-aam-cookie-code.md).
* Modify your ad tag to call the `get_aamCookie` function and include the cookie name you provided when setting up the [!DNL OpenX] destination. For example, if you named the cookie `test_cookie`, then the ad tag should call `get_aamCookie` and reference the cookie name.
* La balise publicitaire peut ressembler à l&#39;exemple ci-dessous.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Remember to include `xid=` . It holds the actual unique user ID ([!UICONTROL UUID]) passed in during an ad call.

L&#39;appel publicitaire entièrement formé peut ressembler à ceci :

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
