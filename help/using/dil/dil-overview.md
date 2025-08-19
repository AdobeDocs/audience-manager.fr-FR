---
description: Présentation de DIL et de son fonctionnement.
seo-description: An overview of DIL and how it works.
seo-title: Understanding the Data Integration Library (DIL)
keywords: dil
solution: Audience Manager
title: Présentation de Data Integration Library (DIL)
uuid: 77b12f35-81e4-4639-ada6-bf982f27b36e
feature: DIL Implementation
exl-id: f194a422-27ed-4a74-9583-8de3b6786caf
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 1%

---

# Comprendre le [!DNL Data Integration Library] (DIL){#understanding-the-data-integration-library-dil}

>[!WARNING]
>
>Depuis juillet 2023, Adobe a interrompu le développement du [!DNL Data Integration Library (DIL)] et de l’extension [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, Adobe ne développera pas d’[!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent implémenter de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) à la place.

Présentation, prise en main et méthodes de code disponibles dans la bibliothèque de code [!DNL Audience Manager DIL].

>[!IMPORTANT]
>
>À compter de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] a une dépendance forte sur [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 ou ultérieure. Il repose sur la [!DNL ID Service] pour déclencher les synchronisations d’identifiants et les destinations d’URL. Une erreur se produit si le [!DNL ID Service] est manquant, ancien ou non configuré.
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Tags] pour implémenter et gérer vos bibliothèques [!DNL DIL] et [!DNL Adobe Experience Platform Identity Service].

Cependant, vous pouvez également télécharger les dernières versions d’Experience Cloud et de [!DNL DIL] à partir de notre page GitHub. Voir les liens de téléchargement ci-dessous :

* Télécharger le service d’identités Adobe Experience Platform [](https://github.com/Adobe-Marketing-Cloud/id-service/releases)
* Télécharger [DIL](https://github.com/Adobe-Marketing-Cloud/dil/releases)

## Objectif de DIL {#purpose-dil}

[!UICONTROL DIL] est une bibliothèque d’API. Vous pouvez le considérer comme un corps de code d’assistance pour [!DNL Adobe Audience Manager]. Il n’est pas nécessaire d’utiliser [!DNL Audience Manager], mais les méthodes et fonctions fournies par [!UICONTROL DIL] vous permettent de ne pas avoir à développer votre propre code pour envoyer des données à [!DNL Audience Manager]. En outre, [!UICONTROL DIL] est différent de l’API fournie par le service d’identités Adobe Experience Platform [](https://experienceleague.adobe.com/docs/id-service/using/home.html). Ce service est conçu pour gérer l’identité des visiteurs dans différentes solutions [!DNL Experience Cloud]. En revanche, [!UICONTROL DIL] est conçu pour :

* Effectuer des appels d’événement et envoyer des données au [serveur de collecte de données](../reference/system-components/components-data-collection.md).
* Envoyez les données aux [destinations](../features/destinations/destinations.md).

## Obtention et implémentation du code DIL {#get-implement-dil-code}

[!UICONTROL DIL] code peut être téléchargé **[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Veuillez noter qu’à partir de la version 8.0 (publiée en août 2018), [!UICONTROL DIL] a une dépendance stricte sur [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html), version 3.3 ou ultérieure. Il repose sur l’[!DNL ID Service] de déclencher les synchronisations et les [!DNL URL destinations] des identifiants. Une erreur se produit si le [!DNL ID Service] est manquant, ancien ou non configuré.

Plutôt que de travailler avec [!UICONTROL DIL] et de configurer [!DNL Audience Manager] manuellement, nous vous recommandons d’utiliser [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html) à la place. [!DNL Adobe Experience Platform Tags] est l’outil d’implémentation recommandé, car il simplifie le déploiement, l’emplacement et la gestion des versions du code. En savoir plus sur l’extension [Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) dans [!DNL Adobe Experience Platform Tags].

## Exemple d’appel {#sample-code}

[!UICONTROL DIL] envoie des données aux [!DNL Audience Manager] dans un appel d’événement. Un appel d’événement est une requête HTTP XML provenant de votre page. Elle utilise une méthode `POST` pour envoyer des données dans le corps de la requête.

| Élément d’appel d’événement | Description |
|--- |--- |
| URL | Les appels d’événement DIL utilisent la syntaxe suivante : `https://adobe.demdex.net/event?_ts =` *`UNIX UTC timestamp`* |
| Corps | Comme le montre l’exemple ci-dessous, DIL transmet les données sous forme de paires clé-valeur. Les caractères de préfixe spéciaux identifient les paires clé-valeur en tant que variables Audience Manager ou variables partenaires.<br>`d_dst=1`<br>`d_jsonv=1`<br>`d_ld=_ts=1473693143821`<br>`d_mid=54192285857942994142875423154873503351`<br>`d_nsid=0`<br>`d_rtbd=json`<br> |

Voir également :
* [Exigences de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)
* [Attributs pris en charge pour les appels API DCS](../api/dcs-intro/dcs-api-reference/dcs-keys.md)

## Liens connexes

* [Cas d’utilisation et exemples de code DIL](/help/using/dil/dil-use-cases.md)
* [Méthodes DIL au niveau de la classe](/help/using/dil/dil-class-overview/dil-start.md)
* [Méthodes DIL au niveau de l’instance](/help/using/dil/dil-instance-methods.md)
* [Modules DIL](/help/using/dil/dil-modules.md)
* [Outils DIL](/help/using/dil/dil-tools.md)
* [DIL Flash](/help/using/dil/dil-flash.md)
