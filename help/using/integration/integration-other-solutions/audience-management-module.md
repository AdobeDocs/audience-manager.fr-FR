---
description: Ajoutez le module de gestion de l’audience à Adobe Analytics AppMeasurement pour transférer les données Analytics vers l’Audience Manager au lieu que le code du Data Integration Library d’Audience Manager (DIL) envoie un pixel depuis la page.
keywords: analytics de l’audience ; les analyses; ssf; transfert côté serveur
seo-description: Ajoutez le module de gestion de l’audience à Adobe Analytics AppMeasurement pour transférer les données Analytics vers l’Audience Manager au lieu que le code du Data Integration Library d’Audience Manager (DIL) envoie un pixel depuis la page.
seo-title: Mise en oeuvre du module de gestion de l’audience
solution: Audience Manager
title: Mise en oeuvre du module de gestion de l’audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Intégration d’Adobe Analytics
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: 8fc6c96bf9e8216ef4458989c87f1f93ea9f0347
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 4%

---

# Comment transférer les données de [!DNL Adobe Analytics] à [!DNL Audience Manager] {#implement-the-audience-management-module}

Suivez les étapes de ce tutoriel pour transférer des données [!DNL Analytics] vers [!DNL Audience Manager] au lieu d’avoir le code [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) qui envoie un pixel à partir de la page.

>[!TIP]
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Launch] pour transférer les données [!UICONTROL Analytics] dans [!DNL Audience Manager]. En utilisant [!UICONTROL Launch], vous n’avez pas à copier manuellement le code dans [!DNL AppMeasurement], comme indiqué sur cette page.

## Conditions préalables {#prereqs}

Outre l’activation des extensions ou l’implémentation du code décrit dans ce document, vous devez également :

* Mettez en oeuvre le [service Adobe Experience Platform Identity](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html).
* Activez [Transfert côté serveur](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) pour les suites de rapports dans la balise [!UICONTROL Adobe Analytics Admin Console].

## Mise en œuvre {#implementation}

Il existe deux méthodes pour mettre en oeuvre le transfert de données de [!DNL Adobe Analytics] vers [!DNL Audience Manager], selon la solution de gestion des balises que vous utilisez.

### Mise en oeuvre à l’aide de [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] vous recommande d’utiliser l’extension  [](https://experienceleague.adobe.com/docs/launch/using/home.html?lang=en) Launch pour instrumenter  [!DNL Adobe Analytics] et  [!DNL Audience Manager] sur vos propriétés. Dans ce cas, il n’est pas nécessaire de copier manuellement un code. Vous devez plutôt activer le partage de données dans l’extension [!DNL Analytics Launch], comme illustré dans l’image ci-dessous. Voir également la documentation [Extension Adobe Analytics](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Si vous installez l’extension [!DNL Adobe Analytics], *ne pas* installez également l’extension [!DNL Audience Manager]. Le transfert de données à partir de l’extension [!DNL Analytics] remplace la fonctionnalité d’extension [!DNL Audience Manager].

![Comment activer le partage de données de l’extension Adobe Analytics vers Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Éléments de code définis {#code-elements-defined}

Le tableau suivant définit des variables importantes dans l’exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Il s’agit d’un nom de partenaire qui vous est attribué par [!DNL Adobe]. Il est parfois appelé sous-domaine [!UICONTROL partner ID] ou partenaire.  Contactez votre [!DNL Adobe] consultant ou [Assistance clientèle](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) si vous ne connaissez pas le nom de votre partenaire. |
| `containerNSID` | Requis. La plupart des clients peuvent simplement définir `"containerNSID":0` . Cependant, si votre entreprise doit personnaliser les synchronisations des identifiants avec un autre conteneur, vous pouvez spécifier cet identifiant de conteneur ici. |
| `uuidCookie` | Facultatif. Cette configuration permet de définir un cookie [!DNL Adobe] dans le domaine propriétaire. Ce [!DNL cookie] contient [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` -  `namespace` | Requis. Le paramètre `namespace` est requis si vous utilisez le module [!DNL AudienceManagement] fourni avec [!UICONTROL AppMeasurement] version 2.10 ou ultérieure. Ce module [!UICONTROL AudienceManagement] requiert que vous utilisiez [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou une version ultérieure. <br><br>L’  [!UICONTROL Experience Cloud Organization ID] est l’identifiant fourni à une entreprise lorsqu’elle s’inscrit pour le  [!UICONTROL Experience Cloud]. Découvrez l’ID d’organisation de votre société dans [Organisations et liaison de comptes](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Résultats : Transfert de données vers [!DNL Audience Manager] {#results-data-forwarding}

Votre mise en oeuvre [!DNL Analytics] envoie des données à [!DNL Audience Manager] après avoir :

* Activé [!UICONTROL Server-Side Forwarding] (contactez votre consultant au sujet de cette fonctionnalité) ;
* Mise en oeuvre de [!DNL Adobe Experience Platform Identity Service] ;
* Suivez les étapes de mise en oeuvre de ce tutoriel.

Ce processus envoie des données à [!DNL Audience Manager] :

* Lors des appels de page vue ;
* À partir des liens trackés ;
* À partir des visionneuses de jalons vidéo et de pulsation vidéo.

>[!NOTE]
>
>Les variables envoyées à [!DNL Audience Manager] à partir de [!DNL Analytics] utilisent des préfixes spéciaux. Vous devez comprendre et prendre en compte ces préfixes lors de la création de caractéristiques [!DNL Audience Manager]. Pour plus d’informations sur ces préfixes, voir [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md).
