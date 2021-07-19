---
description: Collectez les données envoyées à Analytics à partir de fichiers FLA et utilisez ces informations dans Audience Manager.
seo-description: Collectez les données envoyées à Analytics à partir de fichiers FLA et utilisez ces informations dans Audience Manager.
seo-title: DIL Flash
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: Mise en oeuvre du DIL
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 4%

---

# DIL Flash{#flash-dil}

Collectez les données envoyées à Analytics à partir de fichiers FLA et utilisez ces informations dans Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] est une bibliothèque de  [!DNL ActionScript] code qui vous permet d’utiliser les données de lecture vidéo en Audience Manager. [!DNL Flash DIL] fonctionne en capturant le contenu SWF que la  [!UICONTROL AppMeasurement] bibliothèque Adobe transmet à Analytics. [!DNL Flash DIL] envoie ces données à un module de collecte de données  [!UICONTROL DIL] JavaScript distinct, qui les transmet à l’Audience Manager. Données Analytics ( [!UICONTROL Props], [!UICONTROL eVars], événements, etc.) capturé à partir du fichier [!DNL FLA] est disponible en Audience Manager en tant que caractéristiques ou signaux inutilisés.

## Conditions requises pour la collecte de données de DIL Flash {#requirements}

Implémentation générale et exigences liées au code.

<!-- 

c_flash_dil_intro.xml

 -->

**Exigences d’implémentation**

[!UICONTROL Flash] la collecte de données requiert :

* Bibliothèque de classes [!UICONTROL DIL] ( `dil.swc`). Récupérez la bibliothèque de classes [!UICONTROL DIL] à partir de votre contact Partenaires en solutions .

* Code de collecte de données JavaScript [!UICONTROL DIL] sur la page.
* [](../dil/dil-flash.md#flash-dil-actionscript) Bibliothèque d’ActionScripts de DIL chargée dans l’objet de Flash à partir duquel vous souhaitez collecter des données.
* La bibliothèque [!DNL AppMeasurement] [!DNL AS] d’Adobe (version 3.5.2 ou ultérieure) a chargé l’objet [!DNL Flash] à partir duquel vous souhaitez collecter des données.

**Définissez AllowScriptAccess sur  `Always` ou`sameDomain`**

`AllowScriptAccess` dans le code HTML qui charge un fichier SWF contrôle la possibilité d’effectuer l’accès aux URL sortantes à partir du fichier SWF. Lorsque vous configurez une intégration de données [!UICONTROL Flash DIL], assurez-vous que le paramètre `AllowScriptAccess` Flash est défini sur `always` ou `sameDomain`. [!UICONTROL Flash DIL] la collecte de données ne fonctionnera pas si  `AllowScriptAccess` est défini sur  `never`. Voir [Contrôle de l’accès aux scripts ou Host Web Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Placement  [!UICONTROL DIL] du code JS**

Essayez de placer le module de collecte de données JS [!UICONTROL DIL] sur la page afin qu’il se charge avant le fichier [!DNL FLA] . Lorsque le fichier [!DNL FLA] se charge en premier, avant que la collecte de données [!UICONTROL DIL] ne soit prête, vous pouvez ignorer les signaux de données initiaux que [!UICONTROL Flash DIL] envoie à ce module. Cependant, une fois instancié, le module de collecte de données [!UICONTROL DIL] capture toutes les données de fichier SWF suivantes transmises par [!UICONTROL Flash DIL].

## Données collectées par le DIL de Flash {#data-collected}

[!UICONTROL Flash DIL] capture les pages vues, le suivi des liens, le suivi multimédia et d’autres événements d’affichage multimédia à partir de la  [!UICONTROL AppMeasurement] bibliothèque Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Événements de page vue**

Sauf indication contraire de `s.trackVars`, [!UICONTROL Flash DIL] collecte les données suivantes d’Adobe AppMeasurement :

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Événements de suivi des liens**

Sauf indication contraire de `s.linkTrackVars`, [!UICONTROL Flash DIL] collecte les données suivantes de l’Adobe [!UICONTROL AppMeasurement] :

* `pe` (Type de lien de suivi appelé)
* `pev1` (URL du lien)
* `pev2`(Texte du lien)

**Événements de suivi multimédia**

Sauf indication contraire de la part de `s.Media.trackVars`, [!UICONTROL Flash DIL] collecte toutes les données énumérées dans la section Événements de page vue .

**Autres points de données**

Les données de ces paramètres sont collectées par défaut :

* `mediaName` (Nom de l’élément média/vidéo)
* `mediaAdName` (Nom de la publicité)
* `mediaAdParentName` (Nom du contenu multimédia Principal sous lequel la publicité est imbriquée)
* `mediaAdParentPod` (coupure publicitaire ou de capsule dans le contenu Principal où la publicité est lue)
* `mediaAdParentPodPos` (Position numérique dans la capsule où la publicité est lue. Plusieurs publicités peuvent être lues dans une capsule.

## Flash des données DIL dans l’Audience Manager {#flash-dil-data}

Le module [!UICONTROL Flash DIL] transforme les données Adobe AppMeasurement en caractéristiques d’Audience Manager et en signaux inutilisés.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars] et les événements fonctionnent comme des caractéristiques en Audience Manager. Les caractéristiques sont des paires clé-valeur et sont utilisées pour créer des segments. Par exemple, dans une prop Analytics telle que `c30=foo`, `c30` est la clé (une constante) et `foo` est la valeur (une variable).

**Correspondance de caractéristiques d’Audience Manager avec les variables Analytics**

Pour utiliser les données Analytics transmises par [!UICONTROL Flash DIL], vous devez créer des caractéristiques d’Audience Manager dont la valeur de clé est précédée du préfixe `c_`.

Consultez le tableau pour obtenir des exemples :

| Élément de données Analytics | Exemple Analytics | En tant que caractéristique d’Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Données DIL/Analytics comme signaux inutilisés**

L’Audience Manager accepte les événements Analytics [!UICONTROL Props], [!UICONTROL eVars], et même sans caractéristique correspondante. Dans ce cas, les données ne sont pas disponibles pour la création de caractéristiques et apparaissent à la place dans le rapport [Signaux inutilisés](../reporting/dynamic-reports/unused-signals.md) . Pour tirer le meilleur parti de ces informations, créez des caractéristiques d’Audience Manager qui correspondent aux données Analytics transmises par la bibliothèque [!UICONTROL Flash DIL].

## Bibliothèque d’ActionScripts du DIL Flash {#flash-dil-actionscript}

Code de votre objet [!DNL Flash] pour envoyer des données Analytics à l’Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Pour chaque objet [!DNL Flash], le code prend uniquement en charge une instance de partenaire ( `d.partner`).
   >
   >
* Nécessite l’Adobe [!UICONTROL AppMeasurement] [!DNL AS] bibliothèque version 3.5.2 ou supérieure.


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [Caractéristiques ](../features/traits/trait-details-page.md)
* [Signaux, caractéristiques et segments](../reference/signal-trait-segment.md)
* [Explication des paires clé-valeur](../reference/key-value-pairs-explained.md)
* [Exigences de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)

