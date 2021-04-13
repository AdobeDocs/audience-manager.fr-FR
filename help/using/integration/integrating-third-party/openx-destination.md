---
description: Configurez OpenX en tant que destination et envoyez les données de segment d’Audience Manager à cette plateforme.
seo-description: Configurez OpenX en tant que destination et envoyez les données de segment d’Audience Manager à cette plateforme.
seo-title: OpenX en tant que destination d’Audience Manager
solution: Audience Manager
title: OpenX en tant que destination d’Audience Manager
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Intégration tierce
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '697'
ht-degree: 3%

---

# OpenX en tant que destination d’Audience Manager{#openx-as-an-audience-manager-destination}

Configurez [!DNL OpenX] en tant que destination et envoyez les données de segment d’Audience Manager à cette plateforme.

>[!NOTE]
>
>Pour le ciblage sur site des serveurs d’annonces uniquement.

## Exigences de destination d&#39;OpenX {#openx-requirements}

Normes relatives au placement du code, aux formats de valeur de clé pris en charge, aux rapports et au type de données de segment envoyées à [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Examinez les éléments suivants avant de configurer [!DNL OpenX] en tant que destination d’Audience Manager :

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] code doit être déployé sur votre site. [!UICONTROL DIL] aide à éliminer la nécessité d’écrire du code spécial pour la collecte de données, l’intégration, la lecture des valeurs de cookie et la récupération des données de page.
* **`get_aamCookie`Fonction :** code qui capture l’ID utilisateur et les données de cookie de l’Audience Manager. Placez [ce code](../../features/destinations/get-aam-cookie-code.md) en haut de la page ou à l’intérieur du bloc de codes `<head>`.
* **Envoyer des Logs de diffusion à l’Audience Manager :** si vous souhaitez un rapport de diffusion de segments (facultatif), fournissez à l’Audience Manager un journal quotidien contenant des données de diffusion au niveau de l’impression. Les données peuvent être au format brut, mais chaque enregistrement doit contenir l’Audience Manager `UUID`. L&#39;Audience Manager peut les récupérer ou les recevoir par [!DNL FTP].

### Données clés-valeurs : Format requis

L’Audience Manager envoie des données sous la forme de paires clé-valeur. Créez des paires clé-valeur selon les spécifications suivantes :

* Clés de préface avec `c.` (par exemple, `c.color` ou `c.price`).
* Séparez les valeurs sérialisées associées à une seule clé par une virgule (par exemple, `c.color = red, green, blue`).
* Séparez plusieurs paires clé-valeur par une esperluette (par exemple, `c.color=red & c.price = 100 & c.condition = new`).
* Les noms de clés ne doivent pas contenir de caractères spéciaux tels que des signes d’accentuation et de ponctuation ou d’autres symboles.

### Seuls les segments qualifiés sont envoyés à OpenX

La quantité de données transmises à [!DNL OpenX] dépend du nombre de segments pour lesquels un utilisateur particulier est admissible. Supposons, par exemple, que vous configuriez 100 segments d’Audience Manager. Si un visiteur de site est admissible pour cinq d&#39;entre eux, seuls ces cinq segments sont envoyés à [!DNL OpenX] (pas tous les 100).

## Créer une destination OpenX {#openx-destination}

Créez une destination de cookie pour [!DNL OpenX] en Audience Manager.

<!-- aam-openx-destination.xml -->

En Audience Manager, une *destination* correspond à tout autre système (serveur publicitaire, [!DNL DSP], réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion de données. Les fonctions de destination de l&#39;Audience Manager se trouvent dans *Données d&#39;Audience > Destinations*. Pour commencer, cliquez sur **[!UICONTROL Add New Destination]** et suivez les étapes ci-dessous.

### Étape 1 : Informations de base

Pour compléter la section [!UICONTROL Basic Information] :

1. Nommez la destination.
1. Sélectionnez **[!UICONTROL "Cookie"]** dans la liste déroulante [!UICONTROL Type].
1. Cliquez sur **[!UICONTROL Next]** et passez aux sections [!UICONTROL Configuration] et [!UICONTROL Segment Mappings].

### Étape 2 : Informations de configuration

Pour compléter la section [!UICONTROL Configuration] :

1. **Nom du cookie :** attribuez un nom court et descriptif à votre cookie.
1. **Domaine du cookie :** laissez vide pour définir un cookie dans le domaine de la page active de l’utilisateur. Si vous souhaitez spécifier un domaine, ajoutez un préfixe au nom avec un point de ce type, `.mydomain.com`.
1. Choisissez une option clé dans la section [!UICONTROL Data Format].
1. Si vos clés utilisent des données avec des valeurs sérialisées, sélectionnez le contrôle **[!UICONTROL Serialize]** et spécifiez le délimiteur série (le caractère qui sépare les valeurs sérialisées).
1. Cliquez sur **[!UICONTROL Save]** et développez la section [!UICONTROL Segment Mappings].

### Étape 3 : Mappages de segments

Pour ajouter un segment à une destination de cookie :

1. **Rechercher des segments :** la  [!UICONTROL Segment Mappings] section fournit deux outils de recherche pour aider à localiser les segments. Pour rechercher un segment :
   * Option 1 : Début de saisie du nom d’un segment dans le champ de recherche. Le champ est automatiquement mis à jour en fonction du texte. Cliquez sur **[!UICONTROL Add]** une fois que vous avez trouvé le segment à utiliser.
   * Option 2 : Cliquez sur **[!UICONTROL Browse All Segments]** pour ouvrir une fenêtre qui vous permet de rechercher des segments par nom ou emplacement d’enregistrement. Cliquez sur **[!UICONTROL Add Selected Segments]** lorsque vous avez terminé.
1. **Mappages des Ajoutes :** dans la fenêtre Mappages, saisissez l’identifiant du segment dans le champ Mappages, puis cliquez sur  **[!UICONTROL Save]** Mappages.
1. Cliquez sur **[!UICONTROL Done]**.

## Configuration d’OpenX {#openx-code-setup}

Modifiez les paramètres [!DNL OpenX] pour qu’ils fonctionnent avec les données de segment d’Audience Manager.

<!-- aam-openx-code.xml -->

Pour configurer [!DNL OpenX] :

* Installez le code [!UICONTROL DIL] sur votre site.
* Créez [!DNL OpenX] comme destination de cookie en Audience Manager.
* Placez la fonction `get_aamCookie` en haut de la page, idéalement dans le bloc de codes `<head>`. Le code `get_aamCookie` est disponible [ici](../../features/destinations/get-aam-cookie-code.md).
* Modifiez votre balise publicitaire pour appeler la fonction `get_aamCookie` et ajoutez le nom de cookie que vous avez fourni lors de la configuration de la destination [!DNL OpenX]. Par exemple, si vous avez nommé le cookie `test_cookie`, la balise publicitaire doit appeler `get_aamCookie` et référencer le nom du cookie.
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
