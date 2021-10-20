---
description: Ajoutez le module de gestion de l’audience à Adobe Analytics AppMeasurement pour transférer les données Analytics vers l’Audience Manager au lieu que le code du Data Integration Library d’Audience Manager (DIL) envoie un pixel depuis la page.
keywords: analytics de l’audience ; les analyses; ssf; transfert côté serveur
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Mise en oeuvre du module de gestion de l’audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 2%

---

# Comment transférer des données depuis [!DNL Adobe Analytics] to [!DNL Audience Manager] {#implement-the-audience-management-module}

Suivez les étapes de ce tutoriel pour transférer [!DNL Analytics] data to [!DNL Audience Manager] plutôt que d’avoir la variable [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) envoie un pixel à partir de la page.

>[!TIP]
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Tags] à transférer [!UICONTROL Analytics] données dans [!DNL Audience Manager]. En utilisant [!UICONTROL Tags], il n’est pas nécessaire de copier manuellement du code dans [!DNL AppMeasurement], comme illustré sur cette page.

## Conditions préalables {#prereqs}

Outre l’activation des extensions ou l’implémentation du code décrit dans ce document, vous devez également :

* Mettez en oeuvre le [Service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Activer [Transfert côté serveur](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) pour les suites de rapports dans le [!UICONTROL Adobe Analytics Admin Console].

## Mise en œuvre {#implementation}

Il existe deux méthodes pour mettre en oeuvre le transfert de données à partir de [!DNL Adobe Analytics] to [!DNL Audience Manager], selon la solution de gestion des balises que vous utilisez.

### Mise en oeuvre à l’aide de [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] recommande d’utiliser la variable [Balises](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) extension à instrument [!DNL Adobe Analytics] et [!DNL Audience Manager] sur vos propriétés. Dans ce cas, il n’est pas nécessaire de copier manuellement un code. Au lieu de cela, vous devez activer le partage de données dans la variable [!DNL Analytics] , comme illustré ci-dessous. Voir aussi [Extension Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) documentation.

>[!TIP]
>
>Si vous installez le [!DNL Adobe Analytics] extension, *ne pas* installez également la fonction [!DNL Audience Manager] extension . Transfert de données à partir du [!DNL Analytics] remplace l’extension [!DNL Audience Manager] fonctionnalité d’extension.

![Comment activer le partage de données de l’extension Adobe Analytics vers Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Éléments de code définis {#code-elements-defined}

Le tableau suivant définit des variables importantes dans l’exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Il s’agit du nom du partenaire qui vous est attribué par [!DNL Adobe]. Il est parfois appelé [!UICONTROL partner ID] ou sous-domaine du partenaire.  Contactez votre [!DNL Adobe] consultant ou [Assistance clientèle](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) si vous ne connaissez pas votre nom de partenaire. |
| `containerNSID` | Requis. La plupart des clients peuvent simplement définir  `"containerNSID":0` . Cependant, si votre entreprise doit personnaliser les synchronisations des identifiants avec un autre conteneur, vous pouvez spécifier cet identifiant de conteneur ici. |
| `uuidCookie` | Facultatif. Cette configuration vous permet de définir une [!DNL Adobe] dans le domaine propriétaire. Ceci [!DNL cookie] contient la variable [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requis. Le `namespace` est requis si vous utilisez la méthode [!DNL AudienceManagement] module fourni avec [!UICONTROL AppMeasurement] version 2.10 ou ultérieure. Ceci [!UICONTROL AudienceManagement] Le module requiert que vous utilisiez [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou version ultérieure. <br><br>Le [!UICONTROL Experience Cloud Organization ID] est l’identifiant fourni par une entreprise lorsqu’elle s’abonne au [!UICONTROL Experience Cloud]. Découvrez l’ID d’organisation de votre société dans [Organisations et liaison de comptes](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Résultats : Transfert de données vers [!DNL Audience Manager] {#results-data-forwarding}

Votre [!DNL Analytics] l’implémentation envoie des données à [!DNL Audience Manager] après avoir :

* Activé [!UICONTROL Server-Side Forwarding] (contactez votre consultant au sujet de cette fonctionnalité) ;
* Mise en oeuvre de la variable [!DNL Adobe Experience Platform Identity Service];
* Suivez les étapes de mise en oeuvre de ce tutoriel.

Ce processus envoie des données à [!DNL Audience Manager]:

* Lors des appels de page vue ;
* À partir des liens trackés ;
* À partir des visionneuses de jalons vidéo et de pulsation vidéo.

>[!NOTE]
>
>Les variables envoyées à [!DNL Audience Manager] de [!DNL Analytics] utilisez des préfixes spéciaux. Vous devez comprendre et prendre en compte ces préfixes lors de la création [!DNL Audience Manager] caractéristiques. Pour plus d’informations sur ces préfixes, voir [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md).
