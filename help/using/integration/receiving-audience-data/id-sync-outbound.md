---
description: Décrit la syntaxe et les paramètres utilisés dans l'appel HTTP initial pour synchroniser l'utilisateur - id entre Audience Manager et un fournisseur de données tiers. Contactez votre consultant Adobe Audience Manager avant de lancer votre première synchronisation des identifiants.
seo-description: Décrit la syntaxe et les paramètres utilisés dans l'appel HTTP initial pour synchroniser l'utilisateur - id entre Audience Manager et un fournisseur de données tiers. Contactez votre consultant Adobe Audience Manager avant de lancer votre première synchronisation des identifiants.
seo-title: Synchronisation des identifiants pour les transferts de données sortants
solution: Audience Manager
title: Synchronisation des identifiants pour les transferts de données sortants
uuid: f 3849 be 8-1094-47 db -9296-7482 f 020 af 18
translation-type: tm+mt
source-git-commit: e206d3a3cba259dc215f2f4190c9b4e03264f080

---


# ID Synchronization for Outbound Data Transfers{#id-synchronization-for-outbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between Audience Manager and a third-party data provider. Contactez votre consultant Adobe Audience Manager avant de lancer votre première synchronisation des identifiants.

<!-- c_id_sync_out.xml -->

## Objectif de la synchronisation des identifiants

La synchronisation des identifiants est la première étape du processus de transfert des données asynchrones. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. For example, an [!DNL Audience Manager] customer may know a user by ID 123. Cependant, votre partenaire de données peut identifier cet utilisateur avec l'identifiant 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and the third-party data provider should have corresponding IDs for each unique user seen on our networks.

## Syntaxe d'URL

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Paramètres d’URL

The [!DNL URL] for your inbound ID synchronization call should contain variables described in the table below.

>[!NOTE]
>
>Remplacez le contenu en italique par les valeurs de paramètre réelles.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; PROVIDER_ ID &gt;</i></code> </td> 
   <td colname="col2">Unique ID for the data provider (assigned by <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; PROVIDER_ UUID &gt;</i></code> </td> 
   <td colname="col2"> Utilisateur unique - id. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2">An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. <p><b>Remarque :</b> Ajouté uniquement lorsque le fournisseur de données initie l'appel. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p><code>gdpr</code> peut être 0 (GDPR ne s'applique pas) ou 1 (GDPR s'applique).</p><p><b>Remarque :</b> <ul><li>The <code>gdpr</code> and <code>gdpr_consent</code> parameters are being gradually rolled out in ID sync URLs with activation partners. See Activation partners that support IAB TCF in <a href="../../overview/aam-gdpr/aam-iab-plugin.md#aam-activation-partners">Audience Manager Plug-in for IAB TCF.</a></li><li>This parameter can only be used together with <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_ permission = &lt; CHAÎNE CODÉE &gt;</i></code> </td> 
   <td colname="col2"><p><code>gdpr_ permission</code> est la chaîne de consentement GDPR 64 codées sans URL (voir <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> Spécifications IAB</a>).</p><p><b>Remarque :</b> Ce paramètre ne peut être utilisé qu'avec <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Méthodes et code d'API de serveur de collecte de données](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Composants de collecte de données](../../reference/system-components/components-data-collection.md)

