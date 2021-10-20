---
description: Présentation du DIL et de son fonctionnement.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: 'dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil, dil l, '
solution: Audience Manager
title: Présentation de Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 11%

---

# Présentation de la fonction [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

Présentation, prise en main et méthodes de code disponibles dans [!DNL Audience Manager DIL] bibliothèque de code.

>[!IMPORTANT]
>
>à partir de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] dépend fortement de la variable [Service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 ou ultérieure. Elle repose sur la variable [!DNL ID Service] pour déclencher les synchronisations des identifiants et les destinations d’URL. Une erreur se produit si la variable [!DNL ID Service] est manquante, ancienne ou non configurée.
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Tags] pour mettre en oeuvre et gérer vos [!DNL DIL] et [!DNL Adobe Experience Platform Identity Service] bibliothèques.

Cependant, vous pouvez également télécharger le dernier Experience Cloud et [!DNL DIL] versions de notre page GitHub. Voir les liens de téléchargement ci-dessous :

* Téléchargez la [Service Adobe Experience Platform Identity](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Télécharger [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objectif du DIL {#purpose-dil}

[!UICONTROL DIL] est une bibliothèque d’API. Vous pouvez le penser comme un corps de code d’assistance pour [!DNL Adobe Audience Manager]. Il n’est pas nécessaire d’utiliser [!DNL Audience Manager], mais les méthodes et fonctions [!UICONTROL DIL] fournit signifie que vous n’avez pas à développer votre propre code pour envoyer des données à [!DNL Audience Manager]. En outre, [!UICONTROL DIL] est différent de l’API fournie par la variable [Service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html). Ce service est conçu pour gérer l’identité des visiteurs sur différents [!DNL Experience Cloud] solutions. En revanche, [!UICONTROL DIL] est conçu pour :

* Lancer des appels d’événement et envoyer des données à la variable [Serveur de collecte de données](../reference/system-components/components-data-collection.md).
* Envoi de données à [destinations](../features/destinations/destinations.md).

## Obtention et mise en oeuvre du code du DIL {#get-implement-dil-code}

[!UICONTROL DIL] code disponible en téléchargement **[here](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Veuillez noter qu’à partir de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] dépend fortement de la variable [Service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 ou ultérieure. Elle repose sur la variable [!DNL ID Service] pour déclencher les synchronisations des identifiants et [!DNL URL destinations]. Une erreur se produit si la variable [!DNL ID Service] est manquante, ancienne ou non configurée.

Plutôt que de travailler avec [!UICONTROL DIL] et configurer [!DNL Audience Manager] manuellement, nous vous recommandons d’utiliser [Balises Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) au lieu de . [!DNL Adobe Experience Platform Tags] est l’outil de mise en oeuvre recommandé, car il simplifie le déploiement du code, le placement et la gestion des versions. En savoir plus sur les [Extension Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) in [!DNL Adobe Experience Platform Tags].

## Exemple d’appel {#sample-code}

[!UICONTROL DIL] envoie des données à [!DNL Audience Manager] dans un appel d’événement. Un appel d’événement est une requête HTTP XML provenant de votre page. Elle utilise une `POST` pour envoyer des données dans le corps de la requête.

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
