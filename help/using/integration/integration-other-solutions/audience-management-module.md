---
description: Ajoutez le module Gestion de l’audience à Adobe Analytics AppMeasurement pour transférer les données Analytics à Audience Manager au lieu que le code DIL (Audience Manager Data Integration Library) envoie un pixel de la page.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Ajoutez le module Gestion de l’audience à Adobe Analytics AppMeasurement pour transférer les données Analytics à Audience Manager au lieu que le code DIL (Audience Manager Data Integration Library) envoie un pixel de la page.
seo-title: Mise en oeuvre du module Gestion de l’audience
solution: Audience Manager
title: Mise en oeuvre du module Gestion de l’audience
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 1b7c29c0637432a320b2a7573a3f5a7fb4cdcb81

---


# Mise en oeuvre du module Gestion de l’audience {#implement-the-audience-management-module}

Ajoutez la [!UICONTROL Audience Management Module] pour [!DNL Adobe Analytics] transférer [!UICONTROL AppMeasurement] des données à Audience Manager au lieu que le code Audience Manager [!DNL Analytics] ( [!UICONTROL Data Integration Library][!UICONTROL DIL]) envoie un pixel de la page.

>[!NOTE]
>
>Les instructions de cette page se rapportent aux implémentations à l’aide d’ [Adobe Digital Tag Manager (DTM)](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) ou de toute autre solution de gestion des balises, *à l’exception* d’ [Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html). Nous vous recommandons d’utiliser Adobe Launch. En utilisant [!DNL Launch], vous n’avez pas à copier manuellement le code dans [!UICONTROL AppMeasurement], comme illustré sur cette page.

## Conditions préalables {#prereqs}

Outre la mise en oeuvre du code décrit dans ce document, vous devez également :

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Activez [!UICONTROL Server-Side Forwarding] les suites de rapports dans le [!UICONTROL Adobe Analytics Admin Console].

## Implémentation {#implementation}

Pour implémenter [!UICONTROL Audience Management Module]:

1. Téléchargez [!UICONTROL AppMeasurement] à l’aide du gestionnaire [de code](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) Analytics (nécessite la version 1.5 ou ultérieure).
1. Mettez à jour votre [!UICONTROL AppMeasurement] code vers la version incluse dans le fichier zip téléchargé.
1. Copiez tout le code `AppMeasurement_Module_AudienceManagement.js` du fichier zip. Collez-le dans le `appMeasurement.js` fichier situé juste au-dessus du texte, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Ajoutez le code `s.loadModule("AudienceManagement");`, juste au-dessus du `AppMeasurement_Module_AudienceManagement.js` code que vous venez d’ajouter à l’étape précédente.
1. Mettez à jour et copiez le code ci-dessous et ajoutez-le à la `doPlugins` fonction dans votre `AppMeasurement.js` fichier.

```js
s.AudienceManagement.setup({ 
     "partner":"partner name", 
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
>La `audienceManagement.setup` fonction partage des paramètres avec la `DIL.create` fonction Audience Manager, que vous pouvez configurer dans ce code. Pour plus d’informations sur ces paramètres, voir Création [de](../../dil/dil-class-overview/dil-create.md#dil-create)code DIL.

## Définition des éléments de code {#code-elements-defined}

Le tableau suivant définit des variables importantes dans l’exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Il s’agit d’un nom de partenaire qui vous a été attribué par Adobe. Il est parfois appelé votre "ID partenaire" ou "sous-domaine partenaire".  Contactez votre conseiller Adobe ou le service à la [clientèle](https://helpx.adobe.com/marketing-cloud/contact-support.html) si vous ne connaissez pas le nom de votre partenaire. |
| `containerNSID` | Requis. La plupart des clients peuvent simplement définir `"containerNSID":0` . Cependant, si votre entreprise doit personnaliser les synchronisations d’ID avec un autre conteneur, vous pouvez spécifier cet ID de conteneur ici. |
| `uuidCookie` | Facultatif. Cette configuration vous permet de définir un cookie Adobe dans le domaine propriétaire. Ce cookie contient l’ [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requis. Le `namespace` paramètre est requis si vous utilisez le module AudienceManagement fourni avec [!UICONTROL AppMeasurement] la version 2.10 ou ultérieure. Ce [!UICONTROL AudienceManagement] module nécessite l'utilisation de [!UICONTROL Experience Cloud ID Service] 3.3 ou plus récent. <br> Il [!UICONTROL Experience Cloud Organization ID] s’agit de l’ID fourni à une entreprise lors de son inscription à la [!UICONTROL Experience Cloud]. Découvrez l’ID d’organisation de votre entreprise dans [Organisations et Liaison de compte](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Résultats : Transfert de données vers Audience Manager {#results-data-forwarding}

Votre [!DNL Analytics] implémentation envoie les données à Audience Manager une fois que vous avez :

* Activé [!UICONTROL Server-Side Forwarding] (contactez votre consultant au sujet de cette fonctionnalité) ;
* Mise en oeuvre du service d’ID ;
* Installation du [!UICONTROL Audience Management Module].

Ce processus envoie les données à [!DNL Audience Manager]:

* Appels à la page vue ;
* À partir des liens suivis ;
* A partir des affichages de jalon vidéo et de pulsation vidéo.

>[!NOTE]
>
>Les variables envoyées à Audience Manager à partir de [!DNL Analytics] préfixes spéciaux. Vous devez comprendre et prendre en compte ces préfixes lors de la création de caractéristiques d’Audience Manager. Pour plus d’informations sur ces préfixes, voir [Préfixe requis pour les variables](../../features/traits/trait-variable-prefixes.md)clés.