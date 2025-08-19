---
description: Collectez les données envoyées des fichiers FLA à Analytics et utilisez-les dans Audience Manager.
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
>Depuis juillet 2023, Adobe a interrompu le développement du [!DNL Data Integration Library (DIL)] et de l’extension [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, Adobe ne développera pas d’[!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent implémenter de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) à la place.

Collectez les données envoyées des fichiers FLA à Analytics et utilisez-les dans Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] est une bibliothèque de code [!DNL ActionScript] qui vous permet d’utiliser les données de lecture vidéo dans Audience Manager. [!DNL Flash DIL] fonctionne en capturant le contenu SWF que la bibliothèque Adobe [!UICONTROL AppMeasurement] transmet à Analytics. [!DNL Flash DIL] envoie ces données au module de collecte de données [!UICONTROL DIL] JavaScript, qui transmet ces informations à Audience Manager. Les données Analytics ( [!UICONTROL Props], [!UICONTROL eVars], événements, etc.) capturées à partir du fichier [!DNL FLA] sont disponibles dans Audience Manager sous la forme de caractéristiques ou de signaux inutilisés.

## Conditions requises pour la collecte de données Flash DIL {#requirements}

Mise en œuvre générale et exigences liées au code.

<!-- 

c_flash_dil_intro.xml

 -->

**Exigences d’implémentation**

[!UICONTROL Flash] collecte de données nécessite :

* Bibliothèque de classes [!UICONTROL DIL] (`dil.swc`). Obtenez la bibliothèque de classes [!UICONTROL DIL] auprès de votre contact Partner Solutions.

* JavaScript [!UICONTROL DIL] le code de collecte de données sur la page.
* [Bibliothèque ActionScript de DIL](../dil/dil-flash.md#flash-dil-actionscript) chargée dans l&#39;objet Flash à partir duquel vous souhaitez collecter des données.
* La bibliothèque [!DNL AppMeasurement] Adobe [!DNL AS] (version 3.5.2 ou ultérieure) a chargé l’objet [!DNL Flash] à partir duquel vous souhaitez collecter des données.

**Définir AllowScriptAccess sur `Always` ou`sameDomain`**

Le code `AllowScriptAccess` dans HTML qui charge un fichier SWF contrôle la possibilité d’effectuer l’accès aux URL sortantes à partir du fichier SWF. Lorsque vous configurez une intégration de données [!UICONTROL Flash DIL], assurez-vous que le paramètre `AllowScriptAccess` Flash est défini sur `always` ou `sameDomain`. [!UICONTROL Flash DIL] collecte de données ne fonctionnera pas si `AllowScriptAccess` est définie sur `never`. Voir [Contrôler l’accès aux scripts ou à la page web hôte](https://helpx.adobe.com/fr/flash/kb/control-access-scripts-host-web.html).

**Emplacement du code [!UICONTROL DIL] JS**

Essayez de placer le module de collecte de données JS [!UICONTROL DIL] sur la page afin qu’il se charge avant le fichier [!DNL FLA]. Lorsque le fichier [!DNL FLA] se charge en premier, avant que [!UICONTROL DIL] collecte de données ne soit prête, vous pouvez ignorer les signaux de données initiaux que [!UICONTROL Flash DIL] envoie à ce module. Cependant, une fois instancié, le module de collecte de données [!UICONTROL DIL] capture toutes les données de fichier SWF suivantes transmises par [!UICONTROL Flash DIL].

## Données collectées par Flash DIL {#data-collected}

[!UICONTROL Flash DIL] capture les événements de page vue, de suivi des liens, de suivi multimédia et d’autres événements de vue multimédia à partir de la bibliothèque [!UICONTROL AppMeasurement] d’Adobe.

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

Sauf indication contraire de `s.linkTrackVars`, [!UICONTROL Flash DIL] collecte les données suivantes auprès des [!UICONTROL AppMeasurement] Adobe :

* `pe` (Type de lien de suivi appelé)
* `pev1` (URL du lien)
* `pev2`(Texte du lien)

**Événements de suivi multimédia**

Sauf indication contraire de `s.Media.trackVars`, [!UICONTROL Flash DIL] collecte toutes les données énumérées dans la section Événements de page vue .

**Autres points de données**

Les données issues de ces paramètres sont collectées par défaut :

* `mediaName` (nom de l’élément média/vidéo)
* `mediaAdName` (Nom de l’annonce publicitaire)
* `mediaAdParentName` (nom du contenu du média principal sous lequel l’annonce publicitaire est imbriquée)
* `mediaAdParentPod` (la coupure publicitaire dans le contenu principal où la publicité est lue)
* `mediaAdParentPodPos` (position numérique dans la capsule où la publicité est lue. Plusieurs publicités peuvent être lues dans une capsule.

## Données Flash DIL dans Audience Manager {#flash-dil-data}

Le module [!UICONTROL Flash DIL] transforme les données Adobe AppMeasurement en caractéristiques Audience Manager et en signaux inutilisés.

<!-- 

c_flash_dil_in_aam.xml

 -->

Les [!UICONTROL Props], [!UICONTROL eVars] et événements Analytics fonctionnent comme des caractéristiques dans Audience Manager. Les caractéristiques sont des paires clé-valeur et sont utilisées pour créer des segments. Par exemple, dans une prop Analytics telle que `c30=foo`, `c30` est la clé (une constante) et `foo` est la valeur (une variable).

**Correspondance des caractéristiques Audience Manager aux variables Analytics**

Pour utiliser les données Analytics transmises par [!UICONTROL Flash DIL], vous devez créer des caractéristiques Audience Manager dont la valeur de clé comporte le préfixe `c_`.

Consultez le tableau pour obtenir des exemples :

| Élément de données Analytics | Exemple pour Analytics | En tant que caractéristique Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Les données DIL/Analytics sont des signaux inutilisés**

Audience Manager accepte les [!UICONTROL Props], [!UICONTROL eVars] et événements Analytics même sans caractéristique correspondante. Dans ce cas, les données ne sont pas disponibles pour la création de caractéristique et apparaissent à la place dans le rapport [ Signaux inutilisés ](../reporting/dynamic-reports/unused-signals.md). Pour tirer le meilleur parti de ces informations, créez des caractéristiques Audience Manager correspondant aux données Analytics transmises par la bibliothèque [!UICONTROL Flash DIL].

## Bibliothèque Flash DIL ActionScript {#flash-dil-actionscript}

Code de votre objet [!DNL Flash] pour envoyer des données Analytics à Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Pour chaque objet [!DNL Flash], le code ne prend en charge qu’une seule instance partenaire ( `d.partner`).
>
>* Nécessite la bibliothèque [!UICONTROL AppMeasurement] Adobe [!DNL AS] version 3.5.2 ou ultérieure.

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
