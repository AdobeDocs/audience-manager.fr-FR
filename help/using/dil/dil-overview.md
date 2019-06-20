---
description: Une présentation de DIL et de son fonctionnement.
seo-description: Une présentation de DIL et de son fonctionnement.
seo-title: Présentation de la bibliothèque d'intégration des données (DIL)
solution: Audience Manager
title: Présentation de la bibliothèque d'intégration des données (DIL)
uuid: 77 b 12 f 35-81 e 4-4639-ada 6-bf 982 f 27 b 36 e
translation-type: tm+mt
source-git-commit: 8f2cbf8a31335762f03cad278114d9ab7c520763

---


# Understanding the Data Integration Library (DIL){#understanding-the-data-integration-library-dil}

Présentation, prise en main et méthodes de code disponibles dans la bibliothèque de code DIL Audience Manager.

>[!IMPORTANT]
>
>Starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Il repose sur le service d&#39;ID pour la synchronisation des identifiants et les destinations d&#39;URL. Une erreur se produit lorsque le service d&#39;ID est absent, ancien ou non configuré.
>
>Nous vous recommandons d&#39;utiliser Adobe Launch pour implémenter et gérer les bibliothèques du service DIL et Experience Cloud ID.

Vous pouvez toutefois télécharger les dernières versions d&#39;Experience Cloud et DIL depuis notre page github. Voir les liens de téléchargement ci-dessous :

* Download the [Experience Cloud ID Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Download [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Purpose of DIL {#purpose-dil}

[!UICONTROL DIL] est une bibliothèque API. You can think it as a body of helper code for [!DNL Adobe Audience Manager]. It is not required to use [!DNL Audience Manager], but the methods and functions [!UICONTROL DIL] provides means you don&#39;t have to develop your own code to send data to [!DNL Audience Manager]. Also, [!UICONTROL DIL] is different than the API provided by the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/). That service is designed to manage visitor identity across different [!DNL Experience Cloud] solutions. By contrast, [!UICONTROL DIL] is designed to:

* Make event calls and send data to the [Data Collection Server](../reference/system-components/components-data-collection.md).
* Send data to [destinations](../features/destinations/destinations.md).

## Getting and Implementing DIL Code {#get-implement-dil-code}

[!UICONTROL DIL] peut être téléchargé **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Please note that starting with version 8.0 (released August 2018), [!UICONTROL DIL] has a hard dependency on the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 or higher. Il repose sur le service d&#39;ID pour la synchronisation des identifiants et les destinations d&#39;URL. Une erreur se produit lorsque le service d&#39;ID est absent, ancien ou non configuré.

Rather than work with [!UICONTROL DIL] and set up [!DNL Audience Manager] manually, we recommend that you use [Adobe Launch](https://docs.adobelaunch.com/) instead. [!DNL Adobe Launch] est l&#39;outil d&#39;implémentation recommandé, car il simplifie le déploiement, le placement et la gestion des versions du code. Read more about the [Audience Manager extension](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) in Adobe Launch.

Adobe Launch is the successor to [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Sample Call {#sample-code}

[!UICONTROL DIL] envoie des données [!DNL Audience Manager] à un appel d&#39;événement. Un appel d&#39;événement est une requête HTTP HTTP de votre page. It uses a `POST` method to send data in the body of the request.

| Elément d&#39;appel d&#39;événement | Description |
|--- |--- |
| URL | DIL event calls use the following syntax: `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corps | Comme illustré dans l&#39;exemple ci-dessous, DIL transmet les données sous forme de paires clé-valeur. Special prefix characters identify the key-value pairs as Audience Manager or partner variables.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Voir également :
* [Exigences en matière de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)
* [Attributs pris en charge pour les appels d&#39;API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Liens associés

* [Cas d&#39;utilisation DIL et exemples de code](/help/using/dil/dil-use-cases.md)
* [Méthodes DIL de niveau classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Méthodes DIL au niveau de l&#39;instance](/help/using/dil/dil-instance-methods.md)
* [Modules DIL](/help/using/dil/dil-modules.md)
* [Outils DIL](/help/using/dil/dil-tools.md)
* [Flash DIL](/help/using/dil/dil-flash.md)