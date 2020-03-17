---
description: Présentation de DIL et de son fonctionnement.
seo-description: Présentation de DIL et de son fonctionnement.
seo-title: Présentation de la bibliothèque d’intégration de données (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Présentation de la bibliothèque d’intégration de données (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Présentation de la bibliothèque d’intégration de données (DIL){#understanding-the-data-integration-library-dil}

Présentation, prise en main et méthodes de code disponibles dans la bibliothèque de code DIL  Gestionnaire de .

>[!IMPORTANT]
>
>Depuis la version 8.0 (publiée en août 2018), [!UICONTROL DIL] dépend fortement d’Adobe Experience Platform Identity Service [](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 ou ultérieure. Il s’appuie sur le service d’ID pour déclencher les synchronisations d’ID et les destinations URL. Une erreur se produit si le service d’ID est manquant, ancien ou non configuré.
>
>Nous vous recommandons d’utiliser Adobe Experience Platform Launch pour implémenter et gérer vos bibliothèques DIL et Adobe Experience Platform Identity Service.

Cependant, vous pouvez également télécharger les dernières versions d’Experience Cloud et de DIL à partir de notre page GitHub. Voir les liens de téléchargement ci-dessous :

* Téléchargement d’ [Adobe Experience Platform Identity Service](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Télécharger [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objet de la DIL {#purpose-dil}

[!UICONTROL DIL] est une bibliothèque d’API. Vous pouvez le penser comme un corps de code d&#39;aide pour [!DNL Adobe Audience Manager]. Il n&#39;est pas nécessaire de l&#39;utiliser [!DNL Audience Manager], mais les méthodes et fonctions [!UICONTROL DIL] fournissent des moyens pour que vous n&#39;ayez pas à développer votre propre code pour envoyer des données à [!DNL Audience Manager]. En outre, [!UICONTROL DIL] est différent de l’API fournie par le service [d’identité](https://marketing.adobe.com/resources/help/en_US/mcvid/)Adobe Experience Platform. Ce service est conçu pour gérer l’identité des dans différentes [!DNL Experience Cloud] solutions. En revanche, [!UICONTROL DIL] il est conçu pour :

* Appelez  et envoyez des données au serveur [de collecte de](../reference/system-components/components-data-collection.md)données.
* Envoyer des données vers [des destinations](../features/destinations/destinations.md).

## Obtention et implémentation du code DIL {#get-implement-dil-code}

[!UICONTROL DIL] est disponible en téléchargement **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Veuillez noter que depuis la version 8.0 (publiée en août 2018),[!UICONTROL DIL]Adobe Experience Platform Identity Service[](https://marketing.adobe.com/resources/help/en_US/mcvid/), version 3.3 ou ultérieure, dépend fortement d’Adobe Experience Platform Identity Service. Il s’appuie sur le service d’ID pour déclencher les synchronisations d’ID et les destinations URL. Une erreur se produit si le service d’ID est manquant, ancien ou non configuré.

Plutôt que de travailler avec [!UICONTROL DIL] et de configurer [!DNL Audience Manager] manuellement, nous vous recommandons d’utiliser plutôt le lancement [d’](https://docs.adobelaunch.com/) Adobe Experience Platform. [!DNL Adobe Experience Platform Launch] est l’outil d’implémentation recommandé, car il simplifie le déploiement du code, l’emplacement et la gestion des versions. Pour en savoir plus sur l’extension [](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) Gestionnaire de  dans le lancement d’Adobe Experience Platform.

Le lancement d’Adobe Experience Platform succède à [Adobe Dynamic Tag Manager](https://marketing.adobe.com/resources/help/en_US/dtm/c_overview.html) ([!DNL DTM]).

## Exemple d’appel {#sample-code}

[!UICONTROL DIL] envoie des données [!DNL Audience Manager] dans un appel  de. Un appel  est une requête HTTP XML provenant de votre page. Il utilise une `POST` méthode pour envoyer des données dans le corps de la requête.

| Elément d’appel  | Description |
|--- |--- |
| URL | Les appels de DIL utilisent la syntaxe suivante : `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corps | Comme illustré dans l’exemple ci-dessous, DIL transmet les données sous forme de paires clé-valeur. Les caractères de préfixe spéciaux identifient les paires clé-valeur comme Gestionnaire de  de ou comme variables de partenaire.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Voir également :
* [Préfixe requis pour les variables clés](../features/traits/trait-variable-prefixes.md)
* [Attributs pris en charge pour les appels d’API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Liens connexes

* [Cas d’utilisation DIL et exemples de code](/help/using/dil/dil-use-cases.md)
* [Méthodes DIL de niveau classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Méthodes DIL au niveau de l’instance](/help/using/dil/dil-instance-methods.md)
* [Modules DIL](/help/using/dil/dil-modules.md)
* [Outils DIL](/help/using/dil/dil-tools.md)
* [DIL Flash](/help/using/dil/dil-flash.md)