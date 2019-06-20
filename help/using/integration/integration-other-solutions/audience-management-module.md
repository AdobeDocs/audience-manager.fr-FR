---
description: Ajoutez le module de gestion de l'audience à Adobe Analytics appmeasurement pour transférer les données Analytics à Audience Manager au lieu d'envoyer le code DIL (Audience Manager Library Integration Library) à un pixel de la page.
keywords: analyse de l'audience ; analytics ; ssf ; transfert côté serveur
seo-description: Ajoutez le module de gestion de l'audience à Adobe Analytics appmeasurement pour transférer les données Analytics à Audience Manager au lieu d'envoyer le code DIL (Audience Manager Library Integration Library) à un pixel de la page.
seo-title: Mise en œuvre du module de gestion de l'audience
solution: Audience Manager
title: Mise en œuvre du module de gestion de l'audience
uuid: 08846427-def 3-4 a 15-88 e 5-08882 d 8 d 57 ce
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Implement the Audience Management Module {#implement-the-audience-management-module}

Add the [!UICONTROL Audience Management Module] to [!DNL Adobe Analytics] [!UICONTROL AppMeasurement] to forward [!DNL Analytics] data to Audience Manager instead of having the Audience Manager [!UICONTROL Data Integration Library] ([!UICONTROL DIL]) code send a pixel from the page.

## Conditions préalables {#prereqs}

Outre la mise en œuvre du code décrit dans ce document, vous devez également :

* Implement the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Enable [!UICONTROL Server-Side Forwarding] for report suites in the [!UICONTROL Adobe Analytics Admin Console].

## Implémentation {#implementation}

To implement the [!UICONTROL Audience Management Module]:

1. Download [!UICONTROL AppMeasurement] using the [Analytics Code Manager](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html) (requires version 1.5 or later).
1. Update your [!UICONTROL AppMeasurement] code to the version included in the downloaded zip file.
1. Copy all of the code from `AppMeasurement_Module_AudienceManagement.js` from the zip file. Paste it into the `appMeasurement.js` file just above the text, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Add the code, `s.loadModule("AudienceManagement");`, just above the `AppMeasurement_Module_AudienceManagement.js` code you just added in the previous step.
1. Update and copy the code below and add it to the `doPlugins` function in your `AppMeasurement.js` file.

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
>`audienceManagement.setup` La fonction partage les paramètres avec la fonction Audience Manager `DIL.create` que vous pouvez configurer dans ce code. For more information about these parameters, see [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

## Code Elements Defined {#code-elements-defined}

Le tableau suivant définit les variables importantes dans l&#39;exemple de code.

| Paramètre | Description |
|--- |--- |
| `partner` | Requis. Nom de partenaire qui vous a été attribué par Adobe. Il est parfois appelé « ID de partenaire » ou « sous-domaine partenaire ».  » » Contact your Adobe consultant or [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if you don&#39;t know your partner name. |
| `containerNSID` | Requis. Most customers can just set  `"containerNSID":0` . Cependant, si votre société doit personnaliser les synchronisations avec un autre conteneur, vous pouvez spécifier cet identifiant de conteneur ici. |
| `uuidCookie` | Facultatif. Cette configuration vous permet de définir un cookie Adobe dans le domaine propriétaire. This cookie contains the [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Requis. `namespace` Le paramètre est requis si vous utilisez le module audiencemanagement fourni avec [!UICONTROL AppMeasurement] la version 2.10 ou ultérieure. This [!UICONTROL AudienceManagement] module requires that you use [!UICONTROL Experience Cloud ID Service] 3.3 or newer. <br>Il s&#39; [!UICONTROL Experience Cloud Organization ID] agit de l&#39;identifiant fourni par une société lors de la souscription à [!UICONTROL Experience Cloud]la demande. Find out your company&#39;s Organization ID in [Organizations and Account Linking](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html). |

## Results: Data Forwarding to Audience Manager {#results-data-forwarding}

Your [!DNL Analytics] implementation sends data to Audience Manager after you have:

* Enabled [!UICONTROL Server-Side Forwarding] (talk to your consultant about this feature);
* Mise en œuvre du service d&#39;ID ;
* Installed the [!UICONTROL Audience Management Module].

This process sends data to [!DNL Audience Manager]:

* Lors des appels de page vue ;
* À partir des liens suivis ;
* Des vidéos de jalon et de pulsation vidéo.

>[!NOTE]
>
>The variables sent to Audience Manager from [!DNL Analytics] use special prefixes. Vous devez comprendre et prendre en compte ces préfixes lors de la création des caractéristiques d&#39;Audience Manager. For more information on these prefixes, see [Prefix Requirements for Key Variables](../../features/traits/trait-variable-prefixes.md).