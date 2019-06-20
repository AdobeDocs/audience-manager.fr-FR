---
description: Collecte de données envoyées à partir de fichiers FLA vers Analytics et utilisation de ces informations dans Audience Manager
seo-description: Collecte de données envoyées à partir de fichiers FLA vers Analytics et utilisation de ces informations dans Audience Manager
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833 cfd -768 e -4 b 16-95 c 5-debd 8411 df 38
translation-type: tm+mt
source-git-commit: 49fff90fa1330c59360e16f2a56e8fba7d4c43dc

---


# Flash DIL{#flash-dil}

Collecte de données envoyées à partir de fichiers FLA vers Analytics et utilisation de ces informations dans Audience Manager

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] est une bibliothèque [!DNL ActionScript] de code qui vous permet de manipuler les données de lecture vidéo dans Audience Manager. [!DNL Flash DIL] fonctionne en capturant le contenu SWF que la [!UICONTROL AppMeasurement] bibliothèque Adobe transmet à Analytics. [!DNL Flash DIL] envoie ces données au module de collecte de données [!UICONTROL DIL] JavaScript distinct, qui transmet ces informations à Audience Manager. Analytics data ( [!UICONTROL Props], [!UICONTROL eVars], events, etc.) captured from the [!DNL FLA] file is available in Audience Manager as traits or unused signals.

## Requirements for Flash DIL Data Collection {#requirements}

Implémentation générale et exigences liées au code.

<!-- 

c_flash_dil_intro.xml

 -->

**Exigences d’implémentation**

[!UICONTROL Flash] la collecte de données requiert :

* The [!UICONTROL DIL] class library ( `dil.swc`). Obtain the [!UICONTROL DIL] class library from your Partner Solutions contact.

* JavaScript [!UICONTROL DIL] data collection code on the page.
* [Bibliothèque actionscript DIL](../dil/dil-flash.md#flash-dil-actionscript) chargée dans l&#39;objet Flash dont vous souhaitez collecter les données.
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2, or later) loaded the [!DNL Flash] object you want to collect data from.

**Définissez allowscriptaccess sur`Always`ou`sameDomain`**

The `AllowScriptAccess` in HTML code that loads a SWF file controls the ability to perform outbound URL access from within the SWF file. When you configure a [!UICONTROL Flash DIL] data integration, make sure the Flash `AllowScriptAccess` parameter is set to `always` or `sameDomain`. [!UICONTROL Flash DIL] la collecte de données ne fonctionne pas si `AllowScriptAccess` elle est définie `never`sur. See [Control Access to Scripts or Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Emplacement[!UICONTROL DIL]du code JS**

Try to place the JS [!UICONTROL DIL] data collection module on the page so it loads before the [!DNL FLA] file. When the [!DNL FLA] file loads first, before [!UICONTROL DIL] data collection is ready, you can miss the initial data signals that [!UICONTROL Flash DIL] sends to that module. However, once instantiated, the [!UICONTROL DIL] data collection module will capture all subsequent SWF file data passed in by [!UICONTROL Flash DIL].

## Data Collected by Flash DIL {#data-collected}

[!UICONTROL Flash DIL] capture la page vue, le suivi des liens, le suivi des médias et d&#39;autres événements de vue média depuis [!UICONTROL AppMeasurement] la bibliothèque Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Evénements Page vue**

Unless specified otherwise by `s.trackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Evénements de suivi de liens**

Unless specified otherwise by `s.linkTrackVars`, [!UICONTROL Flash DIL] collects the following data from Adobe [!UICONTROL AppMeasurement]:

* `pe` (Type de lien de suivi appelé)
* `pev1` (URL du lien)
* `pev2`(Texte du lien)

**Événements de suivi multimédia**

Unless specified otherwise by `s.Media.trackVars`, [!UICONTROL Flash DIL] collects all the data enumerated in the Page View Events section.

**Autres points de données**

Les données de ces paramètres sont collectées par défaut :

* `mediaName` (Nom de l&#39;élément Média/vidéo)
* `mediaAdName` (Nom de la publicité)
* `mediaAdParentName` (Le nom du contenu multimédia principal est imbriqué sous).
* `mediaAdParentPod` (Capsule ou coupure publicitaire dans le contenu principal où la publicité est lue)
* `mediaAdParentPodPos` (Position numérique dans la capsule où la publicité est lue). Plusieurs publicités peuvent être lues dans un conteneur.

>[!MORE_ LIKE_ THIS]
>
>* [Guide de mise en œuvre appmeasurement Flash, Flex et OSMF](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)


## Flash DIL Data in Audience Manager {#flash-dil-data}

[!UICONTROL Flash DIL] Le module convertit les données Adobe appmeasurement dans les caractéristiques Audience Manager et les signaux inutilisés.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], and events work like traits in Audience Manager. Les caractéristiques sont des paires clé-valeur et servent à créer des segments. For example, in an Analytics prop like `c30=foo`, `c30` is the key (a constant) and `foo` is the value (a variable).

**Correspondance des caractéristiques Audience Manager et des variables Analytics**

To use the Analytics data passed by [!UICONTROL Flash DIL], you should create Audience Manager traits that have the key value prefixed with `c_`.

Pour obtenir des exemples, reportez-vous au tableau suivant :

| Elément de données Analytics | Exemple Analytics | Comme caractéristique d&#39;Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Données DIL/Analytics comme signaux inutilisés**

Audience Manager accepts Analytics [!UICONTROL Props], [!UICONTROL eVars], and events even without a corresponding trait. In this case, the data is unavailable for trait creation and appears in the [Unused Signals report](../reporting/dynamic-reports/unused-signals.md) instead. To make the most of this information, create Audience Manager traits that match the Analytics data passed in by the [!UICONTROL Flash DIL] library.

>[!MORE_ LIKE_ THIS]
>
>* [Caractéristiques](../features/traits/trait-details-page.md)
>* [Signaux, caractéristiques et segments](../reference/signal-trait-segment.md)
>* [Paires clé-valeur expliquées](../reference/key-value-pairs-explained.md)
>* [Exigences en matière de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)


## Flash DIL ActionScript Library {#flash-dil-actionscript}

Code for your [!DNL Flash] object to send Analytics data to Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* For each [!DNL Flash] object, the code supports one partner instance ( `d.partner`) only.
   >
   >
* Requires the Adobe [!UICONTROL AppMeasurement] [!DNL AS] library version 3.5.2 or higher.
>



```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

