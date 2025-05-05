---
description: Ajoutez le module de gestion de l’audience à l’AppMeasurement Adobe Analytics pour transférer les données Analytics vers l’Audience Manager au lieu que le code du Data Integration Library d’Audience Manager (DIL) envoie un pixel depuis la page.
keywords: audience analytics ; analytics ; ssf ; transfert côté serveur
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Mise en oeuvre du module de gestion de l’audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# Comment transférer des données de [!DNL Adobe Analytics] vers [!DNL Audience Manager] {#implement-the-audience-management-module}

Suivez les étapes de ce tutoriel pour transférer des données [!DNL Analytics] vers [!DNL Audience Manager] au lieu que le code [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) envoie un pixel depuis la page.

>[!TIP]
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Tags] pour transférer des données [!UICONTROL Analytics] vers [!DNL Audience Manager]. En utilisant [!UICONTROL Tags], vous n&#39;avez pas à copier manuellement du code dans [!DNL AppMeasurement], comme indiqué sur cette page.

## Conditions préalables {#prereqs}

Outre l’activation des extensions ou l’implémentation du code décrit dans ce document, vous devez également :

* Mettez en oeuvre le [service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).
* Activez le [transfert côté serveur](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=fr) pour les suites de rapports dans [!UICONTROL Adobe Analytics Admin Console].

## Mise en œuvre {#implementation}

Il existe deux méthodes pour mettre en oeuvre le transfert de données de [!DNL Adobe Analytics] vers [!DNL Audience Manager], selon la solution de gestion des balises que vous utilisez.

### Mise en oeuvre avec [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] vous recommande d&#39;utiliser l&#39;extension [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr) pour instrumenter [!DNL Adobe Analytics] et [!DNL Audience Manager] sur vos propriétés. Dans ce cas, il n’est pas nécessaire de copier manuellement un code. Vous devez plutôt activer le partage de données dans l’extension [!DNL Analytics], comme illustré dans l’image ci-dessous. Consultez également la documentation [Extension Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=fr#adobe-audience-manager) .

>[!TIP]
>
>Si vous installez l&#39;extension [!DNL Adobe Analytics], *ne pas* installez également l&#39;extension [!DNL Audience Manager]. Le transfert de données à partir de l’extension [!DNL Analytics] remplace la fonctionnalité d’extension [!DNL Audience Manager].

![Comment activer le partage de données de l’extension Adobe Analytics vers l’Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Éléments de code définis {#code-elements-defined}

Le tableau suivant définit des variables importantes dans l’exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Il s’agit d’un nom de partenaire qui vous a été attribué par [!DNL Adobe]. Il est parfois appelé sous-domaine [!UICONTROL partner ID] ou partenaire.  Contactez votre consultant [!DNL Adobe] ou l&#39;[assistance clientèle](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) si vous ne connaissez pas le nom de votre partenaire. |
| `containerNSID` | Requis. La plupart des clients peuvent simplement définir `"containerNSID":0` . Cependant, si votre entreprise doit personnaliser les synchronisations des identifiants avec un autre conteneur, vous pouvez spécifier cet identifiant de conteneur ici. |
| `uuidCookie` | Facultatif. Cette configuration vous permet de définir un cookie [!DNL Adobe] dans le domaine propriétaire. Ce [!DNL cookie] contient l’ [UID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requis. Le paramètre `namespace` est requis si vous utilisez le module [!DNL AudienceManagement] fourni avec [!UICONTROL AppMeasurement] version 2.10 ou ultérieure. Ce module [!UICONTROL AudienceManagement] nécessite l&#39;utilisation de [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou version ultérieure. <br><br>L’ [!UICONTROL Experience Cloud Organization ID] est l’identifiant fourni par une société lorsqu’elle s’abonne à [!UICONTROL Experience Cloud]. Découvrez l’ID d’organisation de votre société dans [Organisations et liaison de comptes](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=fr). |

## Résultats : transfert des données vers [!DNL Audience Manager] {#results-data-forwarding}

Votre implémentation [!DNL Analytics] envoie des données à [!DNL Audience Manager] après avoir :

* Activé [!UICONTROL Server-Side Forwarding] (contactez votre consultant au sujet de cette fonctionnalité) ;
* Mise en oeuvre de [!DNL Adobe Experience Platform Identity Service] ;
* Suivez les étapes de mise en oeuvre de ce tutoriel.

Ce processus envoie des données à [!DNL Audience Manager] :

* Lors des appels de page vue ;
* À partir des liens suivis ;
* À partir des visionneuses de jalons vidéo et de pulsation vidéo.

>[!NOTE]
>
>Les variables envoyées à [!DNL Audience Manager] à partir de [!DNL Analytics] utilisent des préfixes spéciaux. Vous devez comprendre et prendre en compte ces préfixes lors de la création de caractéristiques [!DNL Audience Manager]. Pour plus d’informations sur ces préfixes, voir [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md).
