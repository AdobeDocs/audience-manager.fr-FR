---
description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les ID utilisateur entre Audience Manager et un fournisseur de données tiers. Contactez votre consultant Adobe Audience Manager avant de tenter votre première synchronisation d’identifiants.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: Synchronisation des identifiants pour les transferts de données sortants
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 2%

---

# Synchronisation des identifiants pour les transferts de données sortants{#id-synchronization-for-outbound-data-transfers}

Décrit la syntaxe et les paramètres utilisés dans l’appel `HTTP` initial pour synchroniser les ID utilisateur entre Audience Manager et un fournisseur de données tiers. Contactez votre consultant Adobe Audience Manager avant de tenter votre première synchronisation d’identifiants.

<!-- c_id_sync_out.xml -->

## Objectif de la synchronisation des identifiants

La synchronisation des identifiants est la première étape du processus de transfert de données asynchrone sortant. Au cours de cette étape, [!DNL Audience Manager] et le fournisseur comparent les identifiants des visiteurs de leur site respectifs et les font correspondre. Par exemple, un client [!DNL Audience Manager] peut connaître un utilisateur portant l’ID 123. Cependant, votre partenaire de données peut identifier cet utilisateur avec l’ID 456. Le processus de synchronisation permet à [!DNL Audience Manager] et à un fournisseur de données de réconcilier ces différents identifiants et d’identifier les utilisateurs dans leurs systèmes respectifs. Une fois l’opération terminée, [!DNL Audience Manager] et le fournisseur de données tiers doivent disposer des identifiants correspondants pour chaque utilisateur unique affiché sur nos réseaux.

## Syntaxe de l&#39;URL

Dans un échange d’identifiants, une chaîne [!DNL URL] correctement formatée doit se présenter comme suit :

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Paramètres d’URL

Le [!DNL URL] de votre appel de synchronisation des identifiants entrant doit contenir les variables décrites dans le tableau ci-dessous.

>[!NOTE]
>
>Remplacez le contenu en italique par les valeurs des paramètres réels.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">ID unique du fournisseur de données (attribué par <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID utilisateur unique. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Une redirection d’URL codée avec la macro qui y <code> ${DD_UUID}</code> incorporée. <p><b>Remarque :</b> ajouté uniquement lorsque le fournisseur de données lance l’appel. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> peut être 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique).</p><p><b>Remarque :</b> <ul><li>Les paramètres <code>gdpr</code> et <code>gdpr_consent</code> sont progressivement déployés dans les URL de synchronisation d’identifiants avec les partenaires d’activation. Consultez Partenaires d’activation qui prennent en charge IAB TCF dans <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Module externe Audience Manager pour IAB TCF.</a></li><li>Ce paramètre peut uniquement être utilisé avec <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> est la chaîne de consentement RGPD codée en base64 et compatible avec les URL (voir Spécification <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">’IAB</a>).</p><p><b>Remarque :</b> ce paramètre peut uniquement être utilisé avec <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Méthodes et code de l’API Data Collection Server (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Composants de collecte de données](../../reference/system-components/components-data-collection.md)
