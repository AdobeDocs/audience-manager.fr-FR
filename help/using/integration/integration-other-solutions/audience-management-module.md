---
description: Ajouter le module de gestion des  à Adobe Analytics AppMeasurement pour transférer les données Analytics au Gestionnaire deau lieu que le code de la bibliothèque d’intégration de données (DIL) du Gestionnaire de de l’envoie un pixel de la page.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Ajouter le module de gestion des  à Adobe Analytics AppMeasurement pour transférer les données Analytics au Gestionnaire deau lieu que le code de la bibliothèque d’intégration de données (DIL) du Gestionnaire de de l’envoie un pixel de la page.
seo-title: Mise en oeuvre du module   Management
solution: Audience Manager
title: Mise en oeuvre du module   Management
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Comment transférer des données d’Adobe Analytics vers  Gestionnaire de  de {#implement-the-audience-management-module}

Suivez les étapes de ce didacticiel pour transférer [!DNL Analytics] des données vers  Gestionnaire de  de au lieu d’envoyer un pixel de la page au code du Gestionnaire de de la  [!UICONTROL Data Integration Library] ([!UICONTROL DIL]).

>[!TIP]
>
>Nous vous recommandons [!DNL Adobe Experience Platform Launch] de transférer [!UICONTROL Analytics] des données dans  Gestionnaire de  de. En utilisant [!UICONTROL Launch], vous n’avez pas à copier manuellement le code dans [!UICONTROL AppMeasurement], comme illustré sur cette page.

## Conditions préalables {#prereqs}

Outre l’activation des extensions ou l’implémentation du code décrit dans ce  de, vous devez également :

* Mettez en oeuvre le service [d’identité](https://marketing.adobe.com/resources/help/en_US/mcvid/)Adobe Experience Platform.
* Activez le transfert côté [serveur](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) pour les suites de rapports dans le [!UICONTROL Adobe Analytics Admin Console].

## Implémentation {#implementation}

Il existe deux méthodes pour implémenter le transfert de données d’Adobe Analytics vers  Gestionnaire de  de, selon la solution de gestion des balises que vous utilisez.

### Implémentation à l’aide d’Adobe Experience Platform Launch

Adobe vous recommande d’utiliser l’extension [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) pour instrumenter Adobe Analytics et  Gestionnaire de  de sur vos propriétés. Dans ce cas, vous n’avez pas besoin de copier manuellement un code. Vous devez plutôt activer le partage des données dans l’extension de lancement d’Analytics, comme illustré dans l’image ci-dessous. Voir aussi la documentation d’ [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Si vous installez l’extension Adobe Analytics, *n’installez pas* également l’extension  Gestionnaire de . Le transfert de données à partir de l’extension Analytics remplace la fonctionnalité  de l’extension  Manager.

![Comment activer le partage de données depuis l’extension Adobe Analytics vers  Gestionnaire de  de](/help/using/integration/assets/analytics-to-aam.png)

### Implémentation à l’aide d’Adobe Digital Tag Management (DTM) ou de toute autre solution de gestion des balises


>[!WARNING]
>
>Adobe a publié des plans pour mettre fin à la gestion dynamique des balises d’ici la fin de 2020. Pour plus d’informations et de planification, voir Plans de gestion dynamique des balises pour un coucher de soleil dans les forums [de la communauté](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe.

Pour mettre en oeuvre l’ [!UICONTROL Audience Management Module] utilisation d’ [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) ou d’une autre solution de gestion des balises :

1. Téléchargez [!UICONTROL AppMeasurement] à l’aide du gestionnaire [de code](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) Analytics (nécessite la version 1.5 ou ultérieure).
1. Mettez à jour votre [!UICONTROL AppMeasurement] code vers la version incluse dans le fichier zip téléchargé.
1. Copiez tout le code `AppMeasurement_Module_AudienceManagement.js` du fichier zip. Collez-le dans le `appMeasurement.js` fichier situé juste au-dessus du texte, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Ajouter le code, `s.loadModule("AudienceManagement");`, juste au-dessus du `AppMeasurement_Module_AudienceManagement.js` code que vous venez d’ajouter à l’étape précédente.
1. Mettez à jour et copiez le code ci-dessous et ajoutez-le à la `doPlugins` fonction dans votre `AppMeasurement.js` fichier.

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
>La `audienceManagement.setup` fonction partage les paramètres avec la fonction   Manager `DIL.create` que vous pouvez configurer dans ce code. Pour plus d’informations sur ces paramètres, voir Création [de](../../dil/dil-class-overview/dil-create.md#dil-create)code DIL.

## Définition des éléments de code {#code-elements-defined}

Le tableau suivant définit des variables importantes dans l’exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Il s’agit d’un nom de partenaire qui vous a été attribué par Adobe. Il est parfois appelé votre &quot;ID partenaire&quot; ou &quot;sous-domaine partenaire&quot;.  Contactez votre conseiller Adobe ou le service à la [clientèle](https://helpx.adobe.com/marketing-cloud/contact-support.html) si vous ne connaissez pas le nom de votre partenaire. |
| `containerNSID` | Requis. La plupart des clients peuvent simplement définir `"containerNSID":0` . Cependant, si votre  de doit personnaliser l’ID se synchronise avec un autre  de, vous pouvez spécifier cet ID de  de l’ici. |
| `uuidCookie` | Facultatif. Cette configuration vous permet de définir un cookie Adobe dans le domaine propriétaire. Ce cookie contient l’ [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requis. Le `namespace` paramètre est requis si vous utilisez le module AudienceManagement fourni avec [!UICONTROL AppMeasurement] la version 2.10 ou ultérieure. Ce [!UICONTROL AudienceManagement] module nécessite l&#39;utilisation de [!UICONTROL Adobe Experience Platform Identity Service] 3.3 ou plus récent. <br> Il [!UICONTROL Experience Cloud Organization ID] s’agit de l’ID fourni à un lors de son inscription [!UICONTROL Experience Cloud]. Découvrez votre ID d’organisation  dans [Organisations et liaison](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)de compte. |

## Résultats : Transfert de données vers  Gestionnaire de  de {#results-data-forwarding}

Votre [!DNL Analytics] implémentation envoie les données à  Gestionnaire de  de après que vous avez :

* Activé [!UICONTROL Server-Side Forwarding] (contactez votre consultant au sujet de cette fonctionnalité) ;
* Mise en oeuvre d’Adobe Experience Platform Identity Service ;
* Suivez les étapes de mise en oeuvre de ce didacticiel.

Ce processus envoie les données à [!DNL Audience Manager]:

* Sur la page,  les appels ;
* À partir des liens suivis ;
* À partir du jalon vidéo et du  vidéo de pulsation.

>[!NOTE]
>
>Les variables envoyées à   Manager à partir de [!DNL Analytics] préfixes spéciaux. Vous devez comprendre et prendre en compte ces préfixes lors de la création  caractéristiques  Manager. Pour plus d’informations sur ces préfixes, voir [Préfixe requis pour les variables](../../features/traits/trait-variable-prefixes.md)clés.