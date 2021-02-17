---
description: Collecte de données envoyées à Analytics à partir de fichiers FLA et utilisation de ces informations en Audience Manager.
seo-description: Collecte de données envoyées à Analytics à partir de fichiers FLA et utilisation de ces informations en Audience Manager.
seo-title: DIL Flash
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 4%

---


# DIL Flash{#flash-dil}

Collecte de données envoyées à Analytics à partir de fichiers FLA et utilisation de ces informations en Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] est une bibliothèque de  [!DNL ActionScript] code qui vous permet de travailler avec les données de lecture vidéo en Audience Manager. [!DNL Flash DIL] fonctionne en capturant le contenu SWF que la  [!UICONTROL AppMeasurement] bibliothèque d’Adobes transmet à Analytics. [!DNL Flash DIL] envoie ces données au module de collecte de données  [!UICONTROL DIL] JavaScript distinct, qui les transmet à l’Audience Manager. Données Analytics ( [!UICONTROL Props], [!UICONTROL eVars], événements, etc.) capturé à partir du fichier [!DNL FLA] est disponible en Audience Manager en tant que caractéristiques ou signaux inutilisés.

## Conditions requises pour la collecte de données des DIL de Flash {#requirements}

Implémentation générale et exigences relatives au code.

<!-- 

c_flash_dil_intro.xml

 -->

**Exigences d’implémentation**

[!UICONTROL Flash] la collecte de données requiert :

* Bibliothèque de classes [!UICONTROL DIL] ( `dil.swc`). Récupérez la bibliothèque de classes [!UICONTROL DIL] à partir de votre contact Solutions partenaires.

* Code de collecte de données JavaScript [!UICONTROL DIL] sur la page.
* [ActionScript DIL ](../dil/dil-flash.md#flash-dil-actionscript) chargé dans l&#39;objet Flash à partir duquel vous souhaitez collecter des données.
* L’Adobe de la bibliothèque [!DNL AppMeasurement] [!DNL AS] (version 3.5.2 ou ultérieure) a chargé l’objet [!DNL Flash] à partir duquel vous souhaitez collecter des données.

**Définir AllowScriptAccess sur  `Always` ou`sameDomain`**

Le fichier `AllowScriptAccess` dans le code HTML qui charge un fichier SWF contrôle la capacité d’effectuer l’accès URL sortant à partir du fichier SWF. Lorsque vous configurez une intégration de données [!UICONTROL Flash DIL], assurez-vous que le paramètre Flash `AllowScriptAccess` est défini sur `always` ou `sameDomain`. [!UICONTROL Flash DIL] la collecte de données ne fonctionnera pas si  `AllowScriptAccess` elle est définie sur  `never`. Voir [Contrôle de l&#39;accès aux scripts ou Page Web hôte](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**Emplacement du  [!UICONTROL DIL] code JS**

Essayez de placer le module de collecte de données JS [!UICONTROL DIL] sur la page afin qu&#39;il se charge avant le fichier [!DNL FLA]. Lorsque le fichier [!DNL FLA] se charge en premier, avant que la collecte de données [!UICONTROL DIL] ne soit prête, vous pouvez ignorer les signaux de données initiaux que [!UICONTROL Flash DIL] envoie à ce module. Cependant, une fois instancié, le module de collecte de données [!UICONTROL DIL] capture toutes les données de fichier SWF suivantes transmises par [!UICONTROL Flash DIL].

## Données collectées par le DIL de Flash {#data-collected}

[!UICONTROL Flash DIL] capture la vue de page, le suivi des liens, le suivi des médias et d’autres événements de vue des médias à partir de la  [!UICONTROL AppMeasurement] bibliothèque d’Adobes.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Événements de Vue de page**

Sauf indication contraire de `s.trackVars`, [!UICONTROL Flash DIL] collecte les données suivantes à partir de Adobe AppMeasurement :

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Événements de suivi des liens**

Sauf indication contraire de `s.linkTrackVars`, [!UICONTROL Flash DIL] collecte les données suivantes de l&#39;Adobe [!UICONTROL AppMeasurement] :

* `pe` (Type de lien de suivi appelé)
* `pev1` (URL du lien)
* `pev2`(Texte du lien)

**Événements de suivi des médias**

Sauf indication contraire de `s.Media.trackVars`, [!UICONTROL Flash DIL] collecte toutes les données énumérées dans la section Événements de Vue de page.

**Autres points de données**

Les données issues de ces paramètres sont collectées par défaut :

* `mediaName` (Nom de l’élément média/vidéo)
* `mediaAdName` (Nom de la publicité)
* `mediaAdParentName` (Nom du contenu multimédia Principal sous lequel la publicité est imbriquée)
* `mediaAdParentPod` (Paquet ou coupure publicitaire dans le contenu Principal où la publicité est lue)
* `mediaAdParentPodPos` (Position numérique dans la capsule où la publicité est lue. Plusieurs publicités peuvent être lues dans une capsule.

## Flash de données DIL dans l&#39;Audience Manager {#flash-dil-data}

Le module [!UICONTROL Flash DIL] transforme les données Adobe AppMeasurement en caractéristiques d&#39;Audience Manager et en signaux inutilisés.

<!-- 

c_flash_dil_in_aam.xml

 -->

Les analyses [!UICONTROL Props], [!UICONTROL eVars] et les événements fonctionnent comme des caractéristiques en Audience Manager. Les caractéristiques sont des paires clé-valeur et sont utilisées pour créer des segments. Par exemple, dans une prop Analytics telle que `c30=foo`, `c30` est la clé (une constante) et `foo` est la valeur (une variable).

**Correspondance des caractéristiques d’Audience Manager avec les variables Analytics**

Pour utiliser les données Analytics transmises par [!UICONTROL Flash DIL], vous devez créer des caractéristiques d’Audience Manager dont la valeur de clé est précédée de `c_`.

Consultez le tableau pour obtenir des exemples :

| Elément de données Analytics | Exemple d’Analytics | En tant que trait d&#39;Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Données DIL/Analytics comme signaux inutilisés**

L’Audience Manager accepte Analytics [!UICONTROL Props], [!UICONTROL eVars] et les événements même sans caractéristique correspondante. Dans ce cas, les données ne sont pas disponibles pour la création de caractéristiques et s’affichent à la place dans le rapport [Signaux inutilisés](../reporting/dynamic-reports/unused-signals.md). Pour tirer le meilleur parti de ces informations, créez des caractéristiques d’Audience Manager qui correspondent aux données Analytics transmises par la bibliothèque [!UICONTROL Flash DIL].

## Bibliothèque d&#39;ActionScripts DIL de Flash {#flash-dil-actionscript}

Code de votre objet [!DNL Flash] pour envoyer les données Analytics à l’Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Pour chaque objet [!DNL Flash], le code ne prend en charge qu&#39;une seule instance de partenaire ( `d.partner`).
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
>* [Signaux, caractéristiques et segments](../reference/signal-trait-segment.md)
>* [Explication des paires clé-valeur](../reference/key-value-pairs-explained.md)
>* [Exigences de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)

