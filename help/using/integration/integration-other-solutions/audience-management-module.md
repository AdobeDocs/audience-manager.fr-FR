---
description: Ajouter le module de gestion des Audiences à Adobe Analytics AppMeasurement pour transférer les données Analytics à Audience Manager au lieu que le code de la bibliothèque d’intégration de données (DIL) d’Audience Manager envoie un pixel de la page.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Ajouter le module de gestion des Audiences à Adobe Analytics AppMeasurement pour transférer les données Analytics à Audience Manager au lieu que le code de la bibliothèque d’intégration de données (DIL) d’Audience Manager envoie un pixel de la page.
seo-title: Mise en oeuvre du module Gestion des Audiences
solution: Audience Manager
title: Mise en oeuvre du module Gestion des Audiences
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Transfert de données d’Adobe Analytics vers Audience Manager {#implement-the-audience-management-module}

Suivez les étapes de ce didacticiel pour transférer [!DNL Analytics] des données à Audience Manager au lieu que le code Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) envoie un pixel de la page.

>[!TIP]
>
>Nous vous recommandons d’utiliser [!DNL Adobe Experience Platform Launch] pour transférer [!UICONTROL Analytics] des données dans Audience Manager. En utilisant [!UICONTROL Launch], vous n&#39;avez pas à copier manuellement le code dans [!UICONTROL AppMeasurement], comme indiqué sur cette page.

## Conditions préalables {#prereqs}

Outre l’activation des extensions ou la mise en oeuvre du code décrit dans ce document, vous devez également :

* Mettez en oeuvre le service [d’identité](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform.
* Activez le transfert [côté](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) serveur pour les suites de rapports dans le [!UICONTROL Adobe Analytics Admin Console].

## Implémentation {#implementation}

Il existe deux méthodes pour implémenter le transfert de données d’Adobe Analytics vers Audience Manager, selon la solution de gestion des balises que vous utilisez.

### Mise en oeuvre à l’aide d’Adobe Experience Platform Launch

Adobe vous recommande d’utiliser l’extension [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) pour instrumenter Adobe Analytics et Audience Manager sur vos propriétés. Dans ce cas, il n’est pas nécessaire de copier manuellement un code. Au lieu de cela, vous devez activer le partage de données dans l’extension de lancement d’Analytics, comme illustré dans l’image ci-dessous. Voir aussi la documentation d’ [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Si vous installez l’extension Adobe Analytics, *n’installez pas* également l’extension Audience Manager. Le transfert de données à partir de l’extension Analytics remplace la fonctionnalité de l’extension Audience Manager.

![Comment activer le partage de données à partir de l’extension Adobe Analytics vers Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Mise en oeuvre à l’aide d’Adobe Digital Tag Management (DTM) ou de toute autre solution de gestion des balises


>[!WARNING]
>
>Adobe a publié des plans pour lever la gestion dynamique des balises d’ici la fin de 2020. Pour plus d’informations et de planification, voir Plans de gestion dynamique des balises pour un Sunset dans les forums [de la communauté](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset)Adobe.

Pour mettre en oeuvre l’ [!UICONTROL Audience Management Module] utilisation d’ [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) ou d’une autre solution de gestion des balises :

1. Téléchargez [!UICONTROL AppMeasurement] à l’aide du Gestionnaire [de code](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) Analytics (nécessite la version 1.5 ou ultérieure).
1. Mettez à jour votre [!UICONTROL AppMeasurement] code vers la version incluse dans le fichier zip téléchargé.
1. Copiez tout le code `AppMeasurement_Module_AudienceManagement.js` du fichier zip. Collez-le dans le `appMeasurement.js` fichier juste au-dessus du texte, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Ajouter le code, `s.loadModule("AudienceManagement");`, juste au-dessus du `AppMeasurement_Module_AudienceManagement.js` code que vous venez d’ajouter à l’étape précédente.
1. Mettez à jour et copiez le code ci-dessous et ajoutez-le à la `doPlugins` fonction de votre `AppMeasurement.js` fichier.

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
>La `audienceManagement.setup` fonction partage des paramètres avec la `DIL.create` fonction Audience Manager, que vous pouvez configurer dans ce code. Pour plus d’informations sur ces paramètres, voir Création [](../../dil/dil-class-overview/dil-create.md#dil-create)DIL.

## Définition des éléments de code {#code-elements-defined}

Le tableau suivant définit des variables importantes dans l’exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Il s’agit du nom du partenaire qui vous a été attribué par Adobe. Il est parfois appelé votre &quot;identifiant partenaire&quot; ou &quot;sous-domaine partenaire&quot;.  Si vous ne connaissez pas le nom de votre partenaire, contactez votre consultant Adobe ou le service à la [clientèle](https://helpx.adobe.com/marketing-cloud/contact-support.html) . |
| `containerNSID` | Requis. La plupart des clients peuvent simplement définir `"containerNSID":0` . Cependant, si votre société doit personnaliser les synchronisations d’identifiants avec un conteneur différent, vous pouvez spécifier cet identifiant de conteneur ici. |
| `uuidCookie` | Facultatif. Cette configuration vous permet de définir un cookie Adobe dans le domaine propriétaire. Ce cookie contient l’ [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requis. Le `namespace` paramètre est requis si vous utilisez le module AudienceManagement fourni avec [!UICONTROL AppMeasurement] la version 2.10 ou ultérieure. Ce [!UICONTROL AudienceManagement] module nécessite l&#39;utilisation de [!UICONTROL Adobe Experience Platform Identity Service] la version 3.3 ou ultérieure. <br> Il [!UICONTROL Experience Cloud Organization ID] s’agit de l’identifiant fourni par une société lors de sa connexion au [!UICONTROL Experience Cloud]service. Découvrez l’ID d’organisation de votre société dans [Organisations et Liaison de compte](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Résultats : Transfert de données vers Audience Manager {#results-data-forwarding}

Votre [!DNL Analytics] implémentation envoie des données à Audience Manager après avoir :

* Activé [!UICONTROL Server-Side Forwarding] (contactez votre consultant au sujet de cette fonctionnalité);
* Mise en oeuvre d’Adobe Experience Platform Identity Service ;
* Suivez les étapes de mise en oeuvre de ce didacticiel.

Ce processus envoie des données à [!DNL Audience Manager]:

* Appels à la vue de la page ;
* à partir des liens suivis ;
* Du jalon vidéo et des vues vidéo de pulsation.

>[!NOTE]
>
>Les variables envoyées à Audience Manager à partir de [!DNL Analytics] préfixes spéciaux. Vous devez comprendre et prendre en compte ces préfixes lors de la création des caractéristiques d’Audience Manager. Pour plus d’informations sur ces préfixes, voir [Préfixes requis pour les variables](../../features/traits/trait-variable-prefixes.md)clés.