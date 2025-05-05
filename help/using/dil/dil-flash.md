---
description: Collectez les données envoyées à Analytics à partir de fichiers FLA et utilisez ces informations dans Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 2%

---

# DIL Flash{#flash-dil}

>[!WARNING]
>
>Depuis juillet 2023, Adobe a arrêté le développement de l’extension [!DNL Data Integration Library (DIL)] et [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, l’Adobe ne développera pas [!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer le [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent mettre en oeuvre de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) à la place.

Collectez les données envoyées à Analytics à partir de fichiers FLA et utilisez ces informations dans Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] est une bibliothèque de code [!DNL ActionScript] qui vous permet de travailler avec les données de lecture vidéo en Audience Manager. [!DNL Flash DIL] fonctionne en capturant le contenu SWF que la bibliothèque [!UICONTROL AppMeasurement] d’Adobe transmet à Analytics. [!DNL Flash DIL] envoie ces données à un module de collecte de données JavaScript distinct [!UICONTROL DIL], qui transmet ces informations à l’Audience Manager. Données Analytics ( [!UICONTROL Props], [!UICONTROL eVars], événements, etc.) capturé à partir du fichier [!DNL FLA] est disponible en Audience Manager en tant que caractéristiques ou signaux inutilisés.

## Conditions requises pour la collecte de données de DIL Flash {#requirements}

Implémentation générale et exigences liées au code.

<!-- 

c_flash_dil_intro.xml

 -->

**Exigences d’implémentation**

La collecte de données [!UICONTROL Flash] requiert :

* Bibliothèque de classes [!UICONTROL DIL] ( `dil.swc`). Procurez-vous la bibliothèque de classes [!UICONTROL DIL] de votre contact Partenaires en solutions .

* Code de collecte de données JavaScript [!UICONTROL DIL] sur la page.
* [Bibliothèque d’ActionScripts DIL](../dil/dil-flash.md#flash-dil-actionscript) chargée dans l’objet de Flash à partir duquel vous souhaitez collecter des données.
* La bibliothèque [!DNL AppMeasurement] [!DNL AS] d&#39;Adobe (version 3.5.2 ou ultérieure) a chargé l&#39;objet [!DNL Flash] à partir duquel vous souhaitez collecter des données.

**Définissez AllowScriptAccess sur `Always` ou`sameDomain`**

Le `AllowScriptAccess` du code HTML qui charge un fichier de SWF contrôle la possibilité d’effectuer l’accès aux URL sortantes à partir du fichier de SWF. Lorsque vous configurez une intégration de données [!UICONTROL Flash DIL], assurez-vous que le paramètre de Flash `AllowScriptAccess` est défini sur `always` ou `sameDomain`. La collecte de données [!UICONTROL Flash DIL] ne fonctionnera pas si `AllowScriptAccess` est défini sur `never`. Voir [Contrôle de l’accès aux scripts ou Host Web Page](https://helpx.adobe.com/fr/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Placement du code**

Essayez de placer le module de collecte de données JS [!UICONTROL DIL] sur la page afin qu’il se charge avant le fichier [!DNL FLA]. Lorsque le fichier [!DNL FLA] se charge en premier, avant que la collecte de données [!UICONTROL DIL] ne soit prête, vous pouvez ignorer les signaux de données initiaux que [!UICONTROL Flash DIL] envoie à ce module. Cependant, une fois instancié, le module de collecte de données [!UICONTROL DIL] capture toutes les données de fichier de SWF suivantes transmises par [!UICONTROL Flash DIL].

## Données collectées par le DIL de Flash {#data-collected}

[!UICONTROL Flash DIL] capture les pages vues, le suivi des liens, le suivi des médias et d’autres événements d’affichage multimédia de la bibliothèque [!UICONTROL AppMeasurement] d’Adobe.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Événements de pages vues**

Sauf indication contraire de `s.trackVars`, [!UICONTROL Flash DIL] collecte les données suivantes auprès d’Adobe AppMeasurement :

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Événements de suivi de liens**

Sauf indication contraire de `s.linkTrackVars`, [!UICONTROL Flash DIL] collecte les données suivantes de l&#39;Adobe [!UICONTROL AppMeasurement] :

* `pe` (Type de lien de suivi appelé)
* `pev1` (URL du lien)
* `pev2`(texte du lien)

**Événements de suivi multimédia**

Sauf indication contraire de `s.Media.trackVars`, [!UICONTROL Flash DIL] collecte toutes les données énumérées dans la section Événements de page vue .

**Autres points de données**

Les données de ces paramètres sont collectées par défaut :

* `mediaName` (nom de l’élément média/vidéo)
* `mediaAdName` (Nom de la publicité)
* `mediaAdParentName` (nom du contenu multimédia principal sous lequel la publicité est imbriquée)
* `mediaAdParentPod` (coupure publicitaire ou de capsule dans le contenu principal où la publicité est lue)
* `mediaAdParentPodPos` (Position numérique dans la capsule où la publicité est lue. Plusieurs publicités peuvent être lues dans une capsule.

## Flash des données DIL dans l’Audience Manager {#flash-dil-data}

Le module [!UICONTROL Flash DIL] transforme les données Adobe AppMeasurement en caractéristiques d’Audience Manager et en signaux inutilisés.

<!-- 

c_flash_dil_in_aam.xml

 -->

Les événements Analytics [!UICONTROL Props], [!UICONTROL eVars] et fonctionnent comme des caractéristiques en Audience Manager. Les caractéristiques sont des paires clé-valeur et sont utilisées pour créer des segments. Par exemple, dans une prop Analytics telle que `c30=foo`, `c30` est la clé (une constante) et `foo` est la valeur (une variable).

**Faire correspondre les caractéristiques d’Audience Manager aux variables Analytics**

Pour utiliser les données Analytics transmises par [!UICONTROL Flash DIL], vous devez créer des caractéristiques d’Audience Manager dont la valeur de clé est précédée du préfixe `c_`.

Consultez le tableau pour obtenir des exemples :

| Élément de données Analytics | Exemple Analytics | En tant que caractéristique d’Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Données DIL/Analytics comme signaux inutilisés**

L’Audience Manager accepte les événements Analytics [!UICONTROL Props], [!UICONTROL eVars] et même sans caractéristique correspondante. Dans ce cas, les données ne sont pas disponibles pour la création de caractéristiques et apparaissent à la place dans le [rapport Signaux inutilisés](../reporting/dynamic-reports/unused-signals.md). Pour tirer le meilleur parti de ces informations, créez des caractéristiques d’Audience Manager qui correspondent aux données Analytics transmises par la bibliothèque [!UICONTROL Flash DIL].

## Bibliothèque d’ActionScripts du DIL Flash {#flash-dil-actionscript}

Code de votre objet [!DNL Flash] pour envoyer des données Analytics à l’Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Pour chaque objet [!DNL Flash], le code prend uniquement en charge une instance de partenaire ( `d.partner`).
>
>* Nécessite l’Adobe de bibliothèque [!UICONTROL AppMeasurement] [!DNL AS] version 3.5.2 ou supérieure.

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
>* [Explication des paires clé-valeur](../reference/key-value-pairs-explained.md)
>* [Exigences de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)
