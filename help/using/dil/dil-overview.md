---
description: Présentation du DIL et de son fonctionnement.
seo-description: Présentation du DIL et de son fonctionnement.
seo-title: Présentation de Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Présentation de Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: Mise en oeuvre du DIL
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 16%

---

# Comprendre le [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Présentation, prise en main et méthodes de code disponibles dans la bibliothèque de code [!DNL Audience Manager DIL].

>[!IMPORTANT]
>
>À compter de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] dépend fortement de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html), version 3.3 ou supérieure. Il s’appuie sur [!DNL ID Service] pour déclencher les synchronisations des identifiants et les destinations d’URL. Une erreur se produit si [!DNL ID Service] est manquant, ancien ou non configuré.
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Launch] pour implémenter et gérer vos bibliothèques [!DNL DIL] et [!DNL Adobe Experience Platform Identity Service].

Cependant, vous pouvez également télécharger les dernières versions de l’Experience Cloud et de [!DNL DIL] à partir de notre page GitHub. Voir les liens de téléchargement ci-dessous :

* Téléchargez le [service Adobe Experience Platform Identity](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Télécharger [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objectif du DIL {#purpose-dil}

[!UICONTROL DIL] est une bibliothèque d’API. Vous pouvez le considérer comme un corps de code d’assistance pour [!DNL Adobe Audience Manager]. Il n’est pas nécessaire d’utiliser [!DNL Audience Manager], mais les méthodes et fonctions [!UICONTROL DIL] fournies vous évitent d’avoir à développer votre propre code pour envoyer des données à [!DNL Audience Manager]. En outre, [!UICONTROL DIL] est différent de l’API fournie par le [service Adobe Experience Platform Identity](https://docs.adobe.com/content/help/en/id-service/using/home.html). Ce service est conçu pour gérer l’identité des visiteurs dans différentes solutions [!DNL Experience Cloud]. En revanche, [!UICONTROL DIL] est conçu pour :

* Effectuez des appels d’événement et envoyez des données au [serveur de collecte de données](../reference/system-components/components-data-collection.md).
* Envoyez des données à [destinations](../features/destinations/destinations.md).

## Obtention et mise en oeuvre du code du DIL {#get-implement-dil-code}

[!UICONTROL DIL] Vous pouvez télécharger le code  **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Notez qu’à partir de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] dépend fortement de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html), version 3.3 ou supérieure. Il s’appuie sur [!DNL ID Service] pour déclencher les synchronisations des identifiants et [!DNL URL destinations]. Une erreur se produit si [!DNL ID Service] est manquant, ancien ou non configuré.

Au lieu de travailler avec [!UICONTROL DIL] et de configurer [!DNL Audience Manager] manuellement, nous vous recommandons d’utiliser [Adobe Experience Platform Launch](https://experienceleague.adobe.com/docs/launch/using/home.html) à la place. [!DNL Adobe Experience Platform Launch] est l’outil de mise en oeuvre recommandé, car il simplifie le déploiement du code, le placement et la gestion des versions. Pour en savoir plus sur l’ [extension de l’Audience Manager](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/audience-manager/overview.html) dans [!DNL Adobe Experience Platform Launch].

## Exemple d’appel {#sample-code}

[!UICONTROL DIL] envoie des données à  [!DNL Audience Manager] dans un appel d’événement. Un appel d’événement est une requête HTTP XML provenant de votre page. Il utilise une méthode `POST` pour envoyer des données dans le corps de la requête.

| Elément d’appel d’événement | Description |
|--- |--- |
| URL | Les appels d’événement de DIL utilisent la syntaxe suivante : `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corps | Comme illustré dans l’exemple ci-dessous, DIL transmet les données sous la forme de paires clé-valeur. Les caractères de préfixe spéciaux identifient les paires clé-valeur comme variables d’Audience Manager ou de partenaire.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

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
