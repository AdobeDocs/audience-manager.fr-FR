---
description: Ajoutez le module de gestion des Audiences à Adobe Analytics AppMeasurement pour transférer les données Analytics à l’Audience Manager au lieu que le code du Data Integration Library d’Audience Manager (DIL) envoie un pixel de la page.
keywords: analyse des audiences ; analyse; ssf; transfert côté serveur
seo-description: Ajoutez le module de gestion des Audiences à Adobe Analytics AppMeasurement pour transférer les données Analytics à l’Audience Manager au lieu que le code du Data Integration Library d’Audience Manager (DIL) envoie un pixel de la page.
seo-title: Mise en oeuvre du module Gestion des Audiences
solution: Audience Manager
title: Mise en oeuvre du module Gestion des Audiences
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 5%

---

# Comment transférer des données de [!DNL Adobe Analytics] à [!DNL Audience Manager] {#implement-the-audience-management-module}

Suivez les étapes de ce didacticiel pour transférer les données [!DNL Analytics] à [!DNL Audience Manager] au lieu d’avoir le code [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) qui envoie un pixel de la page.

>[!TIP]
>
>Nous vous recommandons d&#39;utiliser [!DNL Adobe Experience Platform Launch] pour transférer les données [!UICONTROL Analytics] dans [!DNL Audience Manager]. En utilisant [!UICONTROL Launch], vous n&#39;avez pas à copier manuellement le code dans [!DNL AppMeasurement], comme indiqué sur cette page.

## Conditions préalables {#prereqs}

Outre l’activation des extensions ou la mise en oeuvre du code décrit dans ce document, vous devez également :

* Mettez en oeuvre le [service d’identité Adobe Experience Platform](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html).
* Activez [Transfert côté serveur](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) pour les suites de rapports dans [!UICONTROL Adobe Analytics Admin Console].

## Implémentation {#implementation}

Il existe deux méthodes pour implémenter le transfert de données de [!DNL Adobe Analytics] à [!DNL Audience Manager], selon la solution de gestion des balises que vous utilisez.

### Implémentation à l&#39;aide de [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] recommande d&#39;utiliser l&#39;extension  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launchextension pour instrumenter  [!DNL Adobe Analytics] et  [!DNL Audience Manager] sur vos propriétés. Dans ce cas, il n’est pas nécessaire de copier manuellement un code. Au lieu de cela, vous devez activer le partage de données dans l&#39;extension [!DNL Analytics Launch], comme illustré dans l&#39;image ci-dessous. Voir aussi la documentation [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager).

>[!TIP]
>
>Si vous installez l&#39;extension [!DNL Adobe Analytics], *n&#39;installez pas* également l&#39;extension [!DNL Audience Manager]. Le transfert de données à partir de l&#39;extension [!DNL Analytics] remplace la fonctionnalité d&#39;extension [!DNL Audience Manager].

![Comment activer le partage de données depuis l&#39;extension Adobe Analytics vers l&#39;Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implémentation à l’aide de [!DNL Adobe Digital Tag Management (DTM)] ou de toute autre solution de gestion des balises

>[!WARNING]
>
>[!DNL Adobe] a publié des plans de temporisation  [!DNL DTM] d&#39;ici la fin de 2020. Pour plus d&#39;informations et de planification, voir [!DNL DTM] Plans pour un coucher du soleil dans les [forums de la communauté des Adobes](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Pour implémenter [!UICONTROL Audience Management Module] à l’aide de [la gestion dynamique des balises ](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) Adobe ou d’une autre solution de gestion des balises :

1. Téléchargez [!UICONTROL AppMeasurement] à l’aide du [Gestionnaire de code Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/code-manager-admin.html) (nécessite la version 1.5 ou ultérieure).
1. Mettez à jour votre code [!UICONTROL AppMeasurement] vers la version incluse dans le fichier zip téléchargé.
1. Copiez tout le code de `AppMeasurement_Module_AudienceManagement.js` à partir du fichier zip. Collez-le dans le fichier `appMeasurement.js` juste au-dessus du texte, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Ajoutez le code `s.loadModule("AudienceManagement");` juste au-dessus du code `AppMeasurement_Module_AudienceManagement.js` que vous venez d’ajouter à l’étape précédente.
1. Mettez à jour et copiez le code ci-dessous et ajoutez-le à la fonction `doPlugins` de votre fichier `AppMeasurement.js`.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>La fonction `audienceManagement.setup` partage des paramètres avec la fonction [!DNL Audience Manager] `DIL.create`, que vous pouvez configurer dans ce code. Pour plus d’informations sur ces paramètres, voir [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Eléments de code définis {#code-elements-defined}

Le tableau suivant définit des variables importantes dans l’exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Il s&#39;agit d&#39;un nom de partenaire qui vous a été attribué par [!DNL Adobe]. Il est parfois appelé sous-domaine [!UICONTROL partner ID] ou partenaire.  Contactez votre [!DNL Adobe] consultant ou [Service à la clientèle](https://helpx.adobe.com/fr/marketing-cloud/contact-support.html) si vous ne connaissez pas le nom de votre partenaire. |
| `containerNSID` | Requis. La plupart des clients peuvent simplement définir `"containerNSID":0`. Cependant, si votre société doit personnaliser les synchronisations d’identifiants avec un conteneur différent, vous pouvez spécifier cet identifiant de conteneur ici. |
| `uuidCookie` | Facultatif. Cette configuration vous permet de définir un cookie [!DNL Adobe] dans le domaine propriétaire. [!DNL cookie] contient l&#39;[UUID](../../reference/ids-in-aam.md). |
| `visitorService` -  `namespace` | Requis. Le paramètre `namespace` est requis si vous utilisez le module [!DNL AudienceManagement] fourni avec [!UICONTROL AppMeasurement] version 2.10 ou ultérieure. Ce module [!UICONTROL AudienceManagement] requiert que vous utilisiez [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou version ultérieure. <br><br>Il  [!UICONTROL Experience Cloud Organization ID] s’agit de l’identifiant fourni par une société lors de sa connexion à la  [!UICONTROL Experience Cloud]société. Découvrez l’ID d’organisation de votre société dans [Organisations et liaison de compte](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Résultats : Transfert de données à [!DNL Audience Manager] {#results-data-forwarding}

Votre implémentation [!DNL Analytics] envoie les données à [!DNL Audience Manager] après avoir :

* Activé [!UICONTROL Server-Side Forwarding] (contactez votre consultant au sujet de cette fonctionnalité);
* Mise en oeuvre de [!DNL Adobe Experience Platform Identity Service];
* Suivez les étapes de mise en oeuvre de ce didacticiel.

Ce processus envoie des données à [!DNL Audience Manager] :

* Appels à la vue de la page ;
* à partir des liens suivis ;
* Du jalon vidéo et des vues vidéo de pulsation.

>[!NOTE]
>
>Les variables envoyées à [!DNL Audience Manager] à partir de [!DNL Analytics] utilisent des préfixes spéciaux. Vous devez comprendre et prendre en compte ces préfixes lors de la création de caractéristiques [!DNL Audience Manager]. Pour plus d’informations sur ces préfixes, voir [Préfixes requis pour les variables clés](../../features/traits/trait-variable-prefixes.md).
