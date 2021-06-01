---
description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les identifiants utilisateur entre l’Audience Manager et un fournisseur de données tiers. Contactez votre consultant Adobe Audience Manager avant de tenter votre première synchronisation des identifiants.
seo-description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les identifiants utilisateur entre l’Audience Manager et un fournisseur de données tiers. Contactez votre consultant Adobe Audience Manager avant de tenter votre première synchronisation des identifiants.
seo-title: Synchronisation d’identifiants pour les transferts de données sortantes
solution: Audience Manager
title: Synchronisation d’identifiants pour les transferts de données sortantes
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Transferts de données sortantes
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 12%

---

# Synchronisation d’identifiants pour les transferts de données sortantes{#id-synchronization-for-outbound-data-transfers}

Décrit la syntaxe et les paramètres utilisés dans l’appel `HTTP` initial pour synchroniser les identifiants utilisateur entre l’Audience Manager et un fournisseur de données tiers. Contactez votre consultant Adobe Audience Manager avant de tenter votre première synchronisation des identifiants.

<!-- c_id_sync_out.xml -->

## Objectif de la synchronisation des identifiants

La synchronisation des identifiants est la première étape du processus de transfert de données asynchrone et sortant. Au cours de cette étape, [!DNL Audience Manager] et le fournisseur comparent les identifiants des visiteurs de leur site respectifs et les font correspondre. Par exemple, un client [!DNL Audience Manager] peut connaître un utilisateur par son ID 123. Cependant, votre partenaire de données peut identifier cet utilisateur avec l’ID 456. Le processus de synchronisation permet à [!DNL Audience Manager] et à un fournisseur de données de réconcilier ces différents identifiants et d’identifier les utilisateurs dans leurs systèmes respectifs. Une fois terminé, [!DNL Audience Manager] et le fournisseur de données tiers doivent avoir les identifiants correspondants pour chaque utilisateur unique affiché sur nos réseaux.

## Syntaxe de l’URL

Dans un échange d’identifiants, une chaîne [!DNL URL] correctement formatée doit ressembler à ceci :

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## Paramètres d’URL

La balise [!DNL URL] de votre appel de synchronisation des identifiants entrants doit contenir les variables décrites dans le tableau ci-dessous.

>[!NOTE]
>
>Remplacez le contenu en italique par les valeurs réelles des paramètres.

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
   <td colname="col2">Identifiant unique du fournisseur de données (attribué par <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Identifiant utilisateur unique. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Redirection d’URL codée avec la macro <code> ${DD_UUID}</code> incorporée dans celle-ci. <p><b>Remarque :</b> ajoutée uniquement lorsque le fournisseur de données lance l’appel. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> peut être 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique).</p><p><b>Remarque :</b> <ul><li>Les paramètres <code>gdpr</code> et <code>gdpr_consent</code> sont progressivement déployés dans les URL de synchronisation des identifiants avec les partenaires d’activation. Voir Partenaires d’activation qui prennent en charge le TCF de l’IAB dans le <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">module d’Audience Manager pour le TCF de l’IAB.</a></li><li>Ce paramètre ne peut être utilisé qu’avec <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> est la chaîne de consentement RGPD codée en base 64 et sécurisée par URL (voir <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> spécification IAB</a>).</p><p><b>Remarque :</b> Ce paramètre ne peut être utilisé qu’avec  <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Méthodes et code de l’API du serveur de collecte de données (DCS) ](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
* [Composants de collecte de données](../../reference/system-components/components-data-collection.md)

