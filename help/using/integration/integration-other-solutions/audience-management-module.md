---
description: Ajoutez le module Gestion de l’audience à Adobe Analytics AppMeasurement pour transférer les données Analytics vers Audience Manager au lieu de laisser le code Audience Manager Data Integration Library (DIL) envoyer un pixel à partir de la page.
keywords: audience analytics;analytics;ssf;transfert côté serveur
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Mise en œuvre du module de gestion de l’audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 1%

---

# Comment transférer des données de [!DNL Adobe Analytics] vers [!DNL Audience Manager] {#implement-the-audience-management-module}

Suivez les étapes de ce tutoriel pour transférer des données [!DNL Analytics] vers [!DNL Audience Manager] au lieu de laisser le code [!DNL Audience Manager] ([!UICONTROL Data Integration Library]) [!DNL DIL] envoyer un pixel à partir de la page.

>[!TIP]
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Tags] pour transférer des données [!UICONTROL Analytics] dans [!DNL Audience Manager]. En utilisant [!UICONTROL Tags], vous n’avez pas à copier manuellement le code dans [!DNL AppMeasurement], comme illustré sur cette page.

## Conditions préalables {#prereqs}

Outre l’activation des extensions ou l’implémentation du code décrit dans ce document, vous devez également :

* Mettre en œuvre le service d’identités Adobe Experience Platform [&#128279;](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Activez le [transfert côté serveur](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) pour les suites de rapports dans le [!UICONTROL Adobe Analytics Admin Console].

## Mise en œuvre {#implementation}

Il existe deux méthodes pour implémenter le transfert de données de [!DNL Adobe Analytics] à [!DNL Audience Manager], selon la solution de gestion des balises que vous utilisez.

### Implémentation à l’aide de [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] vous recommande d’utiliser l’extension [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) pour instrumenter les [!DNL Adobe Analytics] et les [!DNL Audience Manager] sur vos propriétés. Dans ce cas, vous n’avez pas besoin de copier manuellement le code. Vous devez plutôt activer le partage de données dans l’extension [!DNL Analytics], comme illustré dans l’image ci-dessous. Consultez également la documentation de l’[extension Adobe Analytics](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager).

>[!TIP]
>
>Si vous installez l’extension [!DNL Adobe Analytics], n’installez *pas* également l’extension [!DNL Audience Manager]. Le transfert de données depuis l’extension [!DNL Analytics] remplace la fonctionnalité d’extension [!DNL Audience Manager].

![Comment activer le partage de données de l&#39;extension Adobe Analytics vers Audience Manager ](/help/using/integration/assets/analytics-to-aam.png)

## Éléments de code définis {#code-elements-defined}

Le tableau suivant définit des variables importantes dans l’exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Il s’agit d’un nom de partenaire qui vous est attribué par [!DNL Adobe]. Il est parfois appelé sous-domaine [!UICONTROL partner ID] ou partenaire.  Contactez votre consultant [!DNL Adobe] ou l’[assistance clientèle](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) si vous ne connaissez pas le nom de votre partenaire. |
| `containerNSID` | Requis. La plupart des clients peuvent simplement définir `"containerNSID":0` . Cependant, si votre entreprise doit personnaliser les synchronisations des identifiants avec un autre conteneur, vous pouvez spécifier cet identifiant de conteneur ici. |
| `uuidCookie` | Facultatif. Cette configuration vous permet de définir un cookie [!DNL Adobe] dans le domaine propriétaire. Ce [!DNL cookie] contient l’[ UUID ](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requis. Le paramètre `namespace` est requis si vous utilisez le module [!DNL AudienceManagement] fourni avec [!UICONTROL AppMeasurement] version 2.10 ou ultérieure. Ce module [!UICONTROL AudienceManagement] nécessite l’utilisation d’[!UICONTROL Adobe Experience Platform Identity Service] version 3.3 ou ultérieure. <br><br>Le [!UICONTROL Experience Cloud Organization ID] est l’identifiant fourni à une entreprise lors de son inscription au [!UICONTROL Experience Cloud]. Découvrez l’ID d’organisation de votre entreprise dans [Liaison d’organisations et de comptes](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Résultats : Transfert de données vers [!DNL Audience Manager] {#results-data-forwarding}

Votre implémentation [!DNL Analytics] envoie des données à [!DNL Audience Manager] après avoir :

* [!UICONTROL Server-Side Forwarding] activée (parlez de cette fonctionnalité à votre consultant) ;
* a mis en œuvre le [!DNL Adobe Experience Platform Identity Service] ;
* Vous avez suivi les étapes d’implémentation de ce tutoriel.

Ce processus envoie des données à [!DNL Audience Manager] :

* Appels sur la page vue ;
* À partir des liens suivis ;
* À partir des vues vidéo jalon et pulsation .

>[!NOTE]
>
>Les variables envoyées à [!DNL Audience Manager] depuis [!DNL Analytics] utilisent des préfixes spéciaux. Vous devez comprendre et prendre en compte ces préfixes lors de la création de caractéristiques [!DNL Audience Manager]. Pour plus d’informations sur ces préfixes, voir [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md).
