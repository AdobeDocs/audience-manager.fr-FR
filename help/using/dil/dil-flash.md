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
ht-degree: 1%

---


# DIL Flash{#flash-dil}

Collecte de données envoyées à Analytics à partir de fichiers FLA et utilisation de ces informations en Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] est une bibliothèque de [!DNL ActionScript] code qui vous permet de travailler avec les données de lecture vidéo en Audience Manager. [!DNL Flash DIL] fonctionne en capturant le contenu SWF que la bibliothèque Adobe [!UICONTROL AppMeasurement] transmet à Analytics. [!DNL Flash DIL] envoie ces données au module de collecte de données [!UICONTROL DIL] JavaScript distinct, qui les transmet à l’Audience Manager. Données Analytics ( [!UICONTROL Props], [!UICONTROL eVars]événements, etc.) capturé à partir du [!DNL FLA] fichier est disponible en Audience Manager en tant que caractéristiques ou signaux inutilisés.

## Conditions requises pour la collecte de données DIL Flash {#requirements}

Implémentation générale et exigences relatives au code.

<!-- 

c_flash_dil_intro.xml

 -->

**Exigences d’implémentation**

[!UICONTROL Flash] la collecte de données requiert :

* Bibliothèque de [!UICONTROL DIL] classes ( `dil.swc`). Récupérez la bibliothèque de [!UICONTROL DIL] classes à partir de votre contact Solutions partenaires.

* Code de collecte de données JavaScript [!UICONTROL DIL] sur la page.
* [Bibliothèque](../dil/dil-flash.md#flash-dil-actionscript) ActionScript DIL chargée dans l&#39;objet Flash à partir duquel vous souhaitez collecter des données.
* La [!DNL AppMeasurement] bibliothèque Adobe [!DNL AS] (version 3.5.2 ou ultérieure) a chargé l’ [!DNL Flash] objet à partir duquel vous souhaitez collecter des données.

**Définir AllowScriptAccess sur`Always`ou`sameDomain`**

Le code HTML `AllowScriptAccess` qui charge un fichier SWF contrôle la possibilité d’effectuer un accès URL sortant à partir du fichier SWF. Lorsque vous configurez une intégration de [!UICONTROL Flash DIL] données, assurez-vous que le paramètre Flash `AllowScriptAccess` est défini sur `always` ou `sameDomain`. [!UICONTROL Flash DIL] la collecte de données ne fonctionnera pas si `AllowScriptAccess` la valeur est définie sur `never`. Voir [Contrôle de l’accès aux scripts ou Page](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html)Web hôte.

**Placement du[!UICONTROL DIL]code JS**

Essayez de placer le module de collecte de données JS [!UICONTROL DIL] sur la page afin qu’il se charge avant le [!DNL FLA] fichier. Lorsque le [!DNL FLA] fichier est chargé en premier, avant que [!UICONTROL DIL] la collecte des données ne soit prête, vous pouvez rater les signaux de données initiaux qui [!UICONTROL Flash DIL] sont envoyés à ce module. Cependant, une fois instancié, le module de collecte de [!UICONTROL DIL] données capture toutes les données de fichier SWF suivantes transmises par [!UICONTROL Flash DIL].

## Données collectées par Flash DIL {#data-collected}

[!UICONTROL Flash DIL] capture la vue des pages, le suivi des liens, le suivi des médias et d’autres événements de vue des médias de la bibliothèque Adobe [!UICONTROL AppMeasurement] .

<!-- 

r_flash_dil_data_collected.xml

 -->

**Événements de Vue de page**

Sauf indication contraire `s.trackVars`, [!UICONTROL Flash DIL] collecte les données suivantes depuis Adobe AppMeasurement :

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Événements de suivi des liens**

Sauf indication contraire `s.linkTrackVars`, [!UICONTROL Flash DIL] collecte les données suivantes depuis Adobe [!UICONTROL AppMeasurement]:

* `pe` (Type de lien de suivi appelé)
* `pev1` (URL du lien)
* `pev2`(Texte du lien)

**Événements de suivi des médias**

Sauf indication contraire `s.Media.trackVars`, [!UICONTROL Flash DIL] collecte toutes les données énumérées dans la section Événements de Vues de page.

**Autres points de données**

Les données issues de ces paramètres sont collectées par défaut :

* `mediaName` (Nom de l’élément média/vidéo)
* `mediaAdName` (Nom de la publicité)
* `mediaAdParentName` (Nom du contenu multimédia principal sous lequel la publicité est imbriquée)
* `mediaAdParentPod` (Paquet ou coupure publicitaire dans le contenu principal où la publicité est lue)
* `mediaAdParentPodPos` (Position numérique dans la capsule où la publicité est lue. Plusieurs publicités peuvent être lues dans une capsule.

## Données DIL Flash en Audience Manager {#flash-dil-data}

Le [!UICONTROL Flash DIL] module transforme les données Adobe AppMeasurement en caractéristiques d’Audience Manager et en signaux inutilisés.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars]et les événements fonctionnent comme des traits en Audience Manager. Les caractéristiques sont des paires clé-valeur et sont utilisées pour créer des segments. Par exemple, dans une prop Analytics telle que `c30=foo`, `c30` est la clé (une constante) et `foo` la valeur (une variable).

**Correspondance des caractéristiques d’Audience Manager avec les variables Analytics**

Pour utiliser les données Analytics transmises par [!UICONTROL Flash DIL], vous devez créer des caractéristiques d’Audience Manager dont la valeur de clé est précédée `c_`.

Consultez le tableau pour obtenir des exemples :

| Élément de données Analytics | Exemple Analytics | En tant que trait d&#39;Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Données DIL/Analytics comme signaux inutilisés**

L&#39;Audience Manager accepte l&#39;Analytics [!UICONTROL Props], [!UICONTROL eVars]et les événements, même sans caractéristique correspondante. Dans ce cas, les données ne sont pas disponibles pour la création de caractéristiques et s’affichent dans le rapport [Signaux](../reporting/dynamic-reports/unused-signals.md) inutilisés à la place. Pour tirer le meilleur parti de ces informations, créez des caractéristiques d’Audience Manager qui correspondent aux données Analytics transmises par la [!UICONTROL Flash DIL] bibliothèque.

## Bibliothèque ActionScript DIL Flash {#flash-dil-actionscript}

Code de votre [!DNL Flash] objet pour l’envoi de données Analytics à l’Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Pour chaque [!DNL Flash] objet, le code ne prend en charge qu’une seule instance de partenaire ( `d.partner`).
   >
   >
* Requiert la version 3.5.2 ou ultérieure de la [!UICONTROL AppMeasurement] bibliothèque Adobe [!DNL AS] .


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
>* [Caractéristiques](../features/traits/trait-details-page.md)
>* [Signaux, caractéristiques et segments](../reference/signal-trait-segment.md)
>* [Paires clé-valeur expliquées](../reference/key-value-pairs-explained.md)
>* [Préfixe requis pour les variables clés](../features/traits/trait-variable-prefixes.md)

