---
description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les ID utilisateur entre l’Audience Manager et un fournisseur de données tiers. Contactez votre consultant en Adobe Audience Manager avant de tenter votre première synchronisation des identifiants.
seo-description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les ID utilisateur entre l’Audience Manager et un fournisseur de données tiers. Contactez votre consultant en Adobe Audience Manager avant de tenter votre première synchronisation des identifiants.
seo-title: Synchronisation des identifiants pour les transferts de données sortants
solution: Audience Manager
title: Synchronisation des identifiants pour les transferts de données sortants
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 4%

---


# Synchronisation des identifiants pour les transferts de données sortants{#id-synchronization-for-outbound-data-transfers}

Décrit la syntaxe et les paramètres utilisés dans l’ `HTTP` appel initial pour synchroniser les ID utilisateur entre l’Audience Manager et un fournisseur de données tiers. Contactez votre consultant en Adobe Audience Manager avant de tenter votre première synchronisation des identifiants.

<!-- c_id_sync_out.xml -->

## Objectif de la synchronisation des identifiants

La synchronisation des identifiants est la première étape du processus de transfert de données asynchrone et sortant. Au cours de cette étape, [!DNL Audience Manager] et le fournisseur comparent les ID de leurs visiteurs de site respectifs et les font correspondre. Par exemple, un [!DNL Audience Manager] client peut connaître un utilisateur par ID 123. Toutefois, votre partenaire de données peut identifier cet utilisateur avec l’ID 456. Le processus de synchronisation permet [!DNL Audience Manager] à un fournisseur de données de concilier ces différents identifiants et d’identifier les utilisateurs dans leurs systèmes respectifs. Une fois terminé, [!DNL Audience Manager] et le fournisseur de données tiers doit avoir les identifiants correspondants pour chaque utilisateur unique affiché sur nos réseaux.

## Syntaxe de l’URL

Dans un échange d’ID, une [!DNL URL] chaîne correctement formatée doit ressembler à ceci :

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Paramètres d’URL

L&#39;appel [!DNL URL] de synchronisation des identifiants entrants doit contenir les variables décrites dans le tableau ci-dessous.

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
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">ID unique du fournisseur de données (attribué par <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> ID utilisateur unique. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Redirection d’URL codée avec la macro <code> ${DD_UUID}</code> incorporée. <p><b>Remarque :</b> Ajouté uniquement lorsque le fournisseur de données lance l’appel. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> peut être 0 (le RGPD ne s'applique pas) ou 1 (le RGPD s'applique).</p><p><b>Remarque :</b> <ul><li>Les <code>gdpr</code> paramètres et <code>gdpr_consent</code> les paramètres sont progressivement déployés dans les URL de synchronisation des identifiants avec les partenaires d’activation. Reportez-vous à la page Partenaires d’Activations qui prennent en charge le TCF IAB dans le module d’ <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager pour le TCF IAB.</a></li><li>Ce paramètre ne peut être utilisé qu'avec <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> est la chaîne de consentement GDPR codée en base 64 et compatible avec les URL (voir la spécification <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"></a>IAB).</p><p><b>Remarque :</b> Ce paramètre ne peut être utilisé qu'avec <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Méthodes et code d’API du serveur de collecte de données (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Composants de collecte de données](../../reference/system-components/components-data-collection.md)

