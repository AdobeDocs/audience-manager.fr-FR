---
description: Présentation du DIL et de son fonctionnement.
seo-description: Présentation du DIL et de son fonctionnement.
seo-title: Présentation de Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Présentation de Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: Mise en oeuvre DIL
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 16%

---


# Présentation de [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Présentation, prise en main et méthodes de code disponibles dans la bibliothèque de code [!DNL Audience Manager DIL].

>[!IMPORTANT]
>
>À compter de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] dépend fortement de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html), version 3.3 ou supérieure. Il utilise [!DNL ID Service] pour déclencher les synchronisations d’ID et les destinations URL. Une erreur se produit si [!DNL ID Service] est manquant, ancien ou non configuré.
>
>Nous vous recommandons d&#39;utiliser [!DNL Adobe Experience Platform Launch] pour implémenter et gérer vos bibliothèques [!DNL DIL] et [!DNL Adobe Experience Platform Identity Service].

Cependant, vous pouvez également télécharger les dernières versions des Experience Cloud et [!DNL DIL] à partir de notre page GitHub. Voir les liens de téléchargement ci-dessous :

* Téléchargez le [service d’identité Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Télécharger [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objet du DIL {#purpose-dil}

[!UICONTROL DIL] est une bibliothèque d’API. Vous pouvez le considérer comme un corps de code d&#39;assistance pour [!DNL Adobe Audience Manager]. Il n&#39;est pas nécessaire d&#39;utiliser [!DNL Audience Manager], mais les méthodes et fonctions [!UICONTROL DIL] permettent de ne pas avoir à développer votre propre code pour envoyer des données à [!DNL Audience Manager]. En outre, [!UICONTROL DIL] est différent de l&#39;API fournie par le [Service d&#39;identité de Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html). Ce service est conçu pour gérer l&#39;identité des visiteurs dans différentes solutions [!DNL Experience Cloud]. Par contre, [!UICONTROL DIL] est conçu pour :

* Appelez le événement et envoyez les données au [serveur de collecte de données](../reference/system-components/components-data-collection.md).
* Envoyer des données vers [destinations](../features/destinations/destinations.md).

## Obtention et mise en oeuvre du code du DIL {#get-implement-dil-code}

[!UICONTROL DIL] est disponible en téléchargement  **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Veuillez noter qu&#39;à partir de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] dépend fortement du [service d&#39;identité Adobe Experience Platform](https://docs.adobe.com/content/help/en/id-service/using/home.html), de la version 3.3 ou supérieure. Il utilise [!DNL ID Service] pour déclencher les synchronisations d&#39;ID et [!DNL URL destinations]. Une erreur se produit si [!DNL ID Service] est manquant, ancien ou non configuré.

Plutôt que de travailler avec [!UICONTROL DIL] et de configurer [!DNL Audience Manager] manuellement, nous vous recommandons d&#39;utiliser [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) à la place. [!DNL Adobe Experience Platform Launch] est l’outil d’implémentation recommandé, car il simplifie le déploiement du code, l’emplacement et la gestion des versions. Pour en savoir plus sur l&#39;[extension d&#39;Audience Manager](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) dans [!DNL Adobe Experience Platform Launch].

[!DNL Adobe Experience Platform Launch] est le successeur de l’ [Adobe Dynamic Tag Manager](https://docs.adobe.com/content/help/en/dtm/using/c-overview.html) ([!DNL DTM]).

## Exemple d&#39;appel {#sample-code}

[!UICONTROL DIL] envoie des données  [!DNL Audience Manager] dans un appel de événement. Un appel de événement est une requête HTTP XML provenant de votre page. Il utilise une méthode `POST` pour envoyer des données dans le corps de la requête.

| Elément d’appel événement | Description |
|--- |--- |
| URL | Les appels de événement DIL utilisent la syntaxe suivante : `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corps | Comme illustré dans l’exemple ci-dessous, le DIL transmet les données sous forme de paires clé-valeur. Les caractères de préfixe spéciaux identifient les paires clé-valeur comme variables d&#39;Audience Manager ou de partenaire.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Voir également :
* [Exigences de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)
* [Attributs pris en charge pour les appels de l’API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Liens connexes

* [Cas d’utilisation DIL et exemples de code](/help/using/dil/dil-use-cases.md)
* [Méthodes DIL au niveau de la classe ](/help/using/dil/dil-class-overview/dil-start.md)
* [Méthodes DIL au niveau de l’instance](/help/using/dil/dil-instance-methods.md)
* [Modules DIL](/help/using/dil/dil-modules.md)
* [Outils DIL](/help/using/dil/dil-tools.md)
* [DIL Flash](/help/using/dil/dil-flash.md)