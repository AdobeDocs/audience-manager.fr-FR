---
description: Collectez les données envoyées à Analytics à partir de fichiers FLA et utilisez ces informations dans Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: DIL Flash
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 3%

---

# DIL Flash{#flash-dil}

>[!WARNING]
>
>Depuis juillet 2023, l’Adobe a cessé de développer la [!DNL Data Integration Library (DIL)] et le [!DNL DIL] extension .
><br><br>
>Les clients existants peuvent continuer à utiliser leurs [!DNL DIL] implémentation. Cependant, l’Adobe ne se développera pas. [!DNL DIL] au-delà de ce point. Les clients sont encouragés à évaluer [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) pour leur stratégie de collecte de données à long terme.
><br><br>
>Les clients qui souhaitent mettre en oeuvre de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) au lieu de .

Collectez les données envoyées à Analytics à partir de fichiers FLA et utilisez ces informations dans Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] est un [!DNL ActionScript] bibliothèque de code qui vous permet d’utiliser les données de lecture vidéo en Audience Manager. [!DNL Flash DIL] fonctionne en capturant le contenu SWF de l’Adobe [!UICONTROL AppMeasurement] transmet à Analytics. [!DNL Flash DIL] envoie ces données à la [!UICONTROL DIL] Module de collecte de données JavaScript qui transmet ces informations à Audience Manager. Données Analytics ( [!UICONTROL Props], [!UICONTROL eVars], événements, etc.) capturé à partir de la propriété [!DNL FLA] est disponible en Audience Manager en tant que caractéristiques ou signaux inutilisés.

## Conditions requises pour la collecte de données de DIL Flash {#requirements}

Implémentation générale et exigences liées au code.

<!-- 

c_flash_dil_intro.xml

 -->

**Exigences d’implémentation**

[!UICONTROL Flash] la collecte de données requiert :

* Le [!UICONTROL DIL] bibliothèque de classes ( `dil.swc`). Obtenez la variable [!UICONTROL DIL] bibliothèque de classes de votre contact Partenaires en solutions .

* JavaScript [!UICONTROL DIL] code de collecte de données sur la page.
* [Bibliothèque d’ActionScripts DIL](../dil/dil-flash.md#flash-dil-actionscript) chargé dans l’objet de Flash à partir duquel vous souhaitez collecter des données.
* Adobe [!DNL AppMeasurement] [!DNL AS] La bibliothèque (version 3.5.2 ou ultérieure) a chargé la variable [!DNL Flash] à partir de laquelle vous souhaitez collecter des données.

**Définissez AllowScriptAccess sur `Always` ou`sameDomain`**

Le `AllowScriptAccess` dans le code de HTML qui charge un fichier de SWF contrôle la possibilité d’effectuer l’accès aux URL sortantes à partir du fichier de SWF. Lorsque vous configurez une [!UICONTROL Flash DIL] intégration des données, assurez-vous que le Flash `AllowScriptAccess` est défini sur `always` ou `sameDomain`. [!UICONTROL Flash DIL] la collecte de données ne fonctionne pas si `AllowScriptAccess` est défini sur `never`. Voir [Contrôle de l’accès aux scripts ou à la page web hôte](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Placement du code**

Essayez de placer le JS [!UICONTROL DIL] module de collecte de données sur la page afin qu’il se charge avant l’événement [!DNL FLA] fichier . Lorsque la variable [!DNL FLA] chargement des fichiers en premier, avant [!UICONTROL DIL] la collecte de données est prête, vous pouvez ignorer les signaux de données initiaux qui [!UICONTROL Flash DIL] envoie vers ce module. Cependant, une fois instanciée, la variable [!UICONTROL DIL] le module de collecte de données capture toutes les données de fichier de SWF suivantes transmises par [!UICONTROL Flash DIL].

## Données collectées par le DIL de Flash {#data-collected}

[!UICONTROL Flash DIL] capture les pages vues, le suivi des liens, le suivi multimédia et d’autres événements d’affichage multimédia de l’Adobe. [!UICONTROL AppMeasurement] bibliothèque .

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

Sauf indication contraire de `s.linkTrackVars`, [!UICONTROL Flash DIL] collecte les données suivantes d’Adobe [!UICONTROL AppMeasurement]:

* `pe` (Type de lien de suivi appelé)
* `pev1` (URL du lien)
* `pev2`(Texte du lien)

**Événements de suivi multimédia**

Sauf indication contraire de `s.Media.trackVars`, [!UICONTROL Flash DIL] collecte toutes les données énumérées dans la section Événements de page vue .

**Autres points de données**

Les données de ces paramètres sont collectées par défaut :

* `mediaName` (Nom de l’élément média/vidéo)
* `mediaAdName` (Nom de la publicité)
* `mediaAdParentName` (Nom du contenu multimédia Principal sous lequel la publicité est imbriquée)
* `mediaAdParentPod` (coupure publicitaire ou de capsule dans le contenu Principal où la publicité est lue)
* `mediaAdParentPodPos` (Position numérique dans la capsule où la publicité est lue. Plusieurs publicités peuvent être lues dans une capsule.

## Flash des données DIL dans l’Audience Manager {#flash-dil-data}

Le [!UICONTROL Flash DIL] transforme les données Adobe AppMeasurement en caractéristiques d’Audience Manager et en signaux inutilisés.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analytics [!UICONTROL Props], [!UICONTROL eVars], et les événements fonctionnent comme des caractéristiques en Audience Manager. Les caractéristiques sont des paires clé-valeur et sont utilisées pour créer des segments. Par exemple, dans une prop Analytics telle que `c30=foo`, `c30` est la clé (une constante) et `foo` est la valeur (une variable).

**Correspondance de caractéristiques d’Audience Manager avec les variables Analytics**

Pour utiliser les données Analytics transmises par [!UICONTROL Flash DIL], vous devez créer des caractéristiques d’Audience Manager dont la valeur de clé est précédée du préfixe `c_`.

Consultez le tableau pour obtenir des exemples :

| Élément de données Analytics | Exemple Analytics | En tant que caractéristique d’Audience Manager |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **events** | `events=event10` | `c_events=event10` |

**Données DIL/Analytics comme signaux inutilisés**

Audience Manager accepte Analytics [!UICONTROL Props], [!UICONTROL eVars], et les événements même sans caractéristique correspondante. Dans ce cas, les données ne sont pas disponibles pour la création de caractéristiques et s’affichent dans la variable [Rapport Signaux inutilisés](../reporting/dynamic-reports/unused-signals.md) au lieu de . Pour tirer le meilleur parti de ces informations, créez des caractéristiques d’Audience Manager qui correspondent aux données Analytics transmises par la variable [!UICONTROL Flash DIL] bibliothèque .

## Bibliothèque d’ActionScripts du DIL Flash {#flash-dil-actionscript}

Code pour votre [!DNL Flash] pour envoyer des données Analytics à l’Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* Pour chaque [!DNL Flash] , le code prend en charge une instance de partenaire ( `d.partner`) uniquement.
>
>* Nécessite l’Adobe [!UICONTROL AppMeasurement] [!DNL AS] bibliothèque version 3.5.2 ou ultérieure.

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
