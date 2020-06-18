---
description: Présentation du code DIL et de son fonctionnement.
seo-description: Présentation du code DIL et de son fonctionnement.
seo-title: Présentation de la bibliothèque d’intégration de données (DIL)
keywords: dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil,
solution: Audience Manager
title: Présentation de la bibliothèque d’intégration de données (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 2%

---


# Présentation du [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Présentation, prise en main et méthodes de code disponibles dans la bibliothèque de [!DNL Audience Manager DIL] code.

>[!IMPORTANT]
>
>A compter de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] dépend fortement du service [d&#39;identité de l&#39;](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform, version 3.3 ou ultérieure. Il s’appuie sur la fonction [!DNL ID Service] de déclenchement des synchronisations d’ID et des destinations URL. Une erreur se produit si la variable [!DNL ID Service] est manquante, ancienne ou non configurée.
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Launch] pour implémenter et gérer vos [!DNL DIL] et [!DNL Adobe Experience Platform Identity Service] bibliothèques.

Cependant, vous pouvez également télécharger les derniers Experience Cloud et [!DNL DIL] versions de notre page GitHub. Voir les liens de téléchargement ci-dessous :

* Téléchargement du service d&#39;identité [d&#39;Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Télécharger [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objet du DIL {#purpose-dil}

[!UICONTROL DIL] est une bibliothèque d’API. Vous pouvez le penser comme un corps de code d&#39;aide pour [!DNL Adobe Audience Manager]. Il n&#39;est pas nécessaire de l&#39;utiliser [!DNL Audience Manager], mais les méthodes et fonctions [!UICONTROL DIL] fournissent des moyens pour que vous n&#39;ayez pas à développer votre propre code pour envoyer des données à [!DNL Audience Manager]. En outre, [!UICONTROL DIL] est différent de l&#39;API fournie par le service [d&#39;identité](https://docs.adobe.com/content/help/en/id-service/using/home.html)d&#39;Adobe Experience Platform. Ce service est conçu pour gérer l&#39;identité des visiteurs dans différentes [!DNL Experience Cloud] solutions. En revanche, [!UICONTROL DIL] il est conçu pour :

* Effectuez des appels de événement et envoyez des données au serveur [de collecte de](../reference/system-components/components-data-collection.md)données.
* Envoyer des données vers [des destinations](../features/destinations/destinations.md).

## Obtention et mise en oeuvre du code DIL {#get-implement-dil-code}

[!UICONTROL DIL] est disponible en téléchargement **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Veuillez noter qu&#39;à partir de la version 8.0 (publiée en août 2018),[!UICONTROL DIL]il existe une dépendance stricte vis-à-vis du service[d&#39;identité de l&#39;](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform, version 3.3 ou ultérieure. Il s’appuie sur le[!DNL ID Service]pour déclencher les synchronisations d’identifiants et[!DNL URL destinations]. Une erreur se produit si la variable[!DNL ID Service]est manquante, ancienne ou non configurée.

Plutôt que de travailler avec [!UICONTROL DIL] et de configurer [!DNL Audience Manager] manuellement, nous vous recommandons d’utiliser le lancement [](https://docs.adobelaunch.com/) d’Adobe Experience Platform à la place. [!DNL Adobe Experience Platform Launch] est l’outil d’implémentation recommandé, car il simplifie le déploiement du code, l’emplacement et la gestion des versions. Pour en savoir plus sur l&#39;extension [](https://docs.adobelaunch.com/extension-reference/web/adobe-audience-manager-extension) d&#39;Audience Manager, consultez [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] est le successeur de [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Exemple d’appel {#sample-code}

[!UICONTROL DIL] envoie des données [!DNL Audience Manager] dans un appel de événement. Un appel de événement est une requête HTTP XML provenant de votre page. Il utilise une `POST` méthode pour envoyer des données dans le corps de la requête.

| Elément d’appel Événement | Description |
|--- |--- |
| URL | Les appels de événement DIL utilisent la syntaxe suivante : `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corps | Comme illustré dans l’exemple ci-dessous, DIL transmet les données sous forme de paires clé-valeur. Les caractères de préfixe spéciaux identifient les paires clé-valeur comme variables d’Audience Manager ou de partenaire.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Voir également :
* [Préfixe requis pour les variables clés](../features/traits/trait-variable-prefixes.md)
* [Attributs pris en charge pour les appels d’API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Liens connexes

* [Cas d’utilisation du code DIL et exemples de code](/help/using/dil/dil-use-cases.md)
* [Méthodes DIL de niveau classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Méthodes DIL au niveau de l’instance](/help/using/dil/dil-instance-methods.md)
* [Modules DIL](/help/using/dil/dil-modules.md)
* [Outils DIL](/help/using/dil/dil-tools.md)
* [DIL Flash](/help/using/dil/dil-flash.md)