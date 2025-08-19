---
description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les ID utilisateur entre un fournisseur et Audience Manager. La synchronisation des identifiants peut commencer une fois que vous avez envoyé votre taxonomie de données à Audience Manager.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: Synchronisation des identifiants pour les transferts de données entrants
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 1%

---

# Synchronisation des identifiants pour les transferts de données entrants {#id-synchronization-for-inbound-data-transfers}

Décrit la syntaxe et les paramètres utilisés dans l’appel `HTTP` initial pour synchroniser les ID utilisateur entre un fournisseur et un [!DNL Audience Manager]. La synchronisation des identifiants peut commencer une fois que vous avez envoyé votre taxonomie de données à [!DNL Audience Manager].

La synchronisation des identifiants est la première étape du processus de transfert de données asynchrone entrant. Au cours de cette étape, [!DNL Audience Manager] et le fournisseur comparent les identifiants des visiteurs de leur site respectifs et les font correspondre. Par exemple, un client [!DNL Audience Manager] peut connaître un utilisateur portant l’ID 123. Cependant, votre partenaire de données peut identifier cet utilisateur avec l’ID 456. Le processus de synchronisation permet à [!DNL Audience Manager] et à un fournisseur de données de réconcilier ces différents identifiants et d’identifier les utilisateurs dans leurs systèmes respectifs. Une fois l’opération terminée, [!DNL Audience Manager] et votre partenaire tiers doivent disposer des identifiants correspondants pour chaque utilisateur unique affiché sur nos réseaux.

Vous pouvez utiliser les méthodes suivantes pour intégrer vos données dans [!DNL Audience Manager] :

* [Requête HTTP de synchronisation des identifiants](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Événement d’ID déclaré](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Synchronisation des identifiants à partir d’une image incorporée d’e-mail](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Demande de `HTTP` de synchronisation des identifiants {#id-sync-http}

Dans un échange d’identifiants, une chaîne [!DNL URL] correctement formatée doit se présenter comme suit :

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>ID unique du fournisseur de contenu (attribué par <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (pourcentage) Représentation codée de votre ID utilisateur unique. En plus de coder les caractères ASCII réservés, tous les caractères non-ASCII doivent être codés en pourcentage en fonction du tableau de codage des caractères UTF-8. </p> <p>Pour plus d’informations, consultez le site web <a href="https://www.url-encode-decode.com" format="http" scope="external"> Encoder/décoder l’URL en ligne </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Une redirection d’URL codée avec la macro qui y <code> ${DD_UUID}</code> incorporée. </p> <p>Remarque : ajouté uniquement lorsque le fournisseur de contenu lance l’appel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facultatif. Ajoutez ce paramètre si vous utilisez le module externe <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager pour IAB TCF.</a></p> <p><code> gdpr</code> peut être 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique). </p> <p> <b>Remarque :</b> ce paramètre peut uniquement être utilisé avec <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facultatif. Ajoutez ce paramètre si vous utilisez le module externe <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager pour IAB TCF.</a></p> <p><code>gdpr_consent</code> est la chaîne de consentement RGPD codée en base64 et compatible avec les URL (voir Spécification <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external">’IAB</a>). </p> <p> <b>Remarque :</b> ce paramètre peut uniquement être utilisé avec <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Événement [!UICONTROL Declared ID] {#declared-id-event}

Pour plus d’informations, voir [ID déclarés](../../../features/declared-ids.md).

## Synchronisation des identifiants à partir d’une image incorporée d’e-mail {#id-sync-email-image}

Le format de correspondance des identifiants via une image d’e-mail est le même que celui illustré ci-dessus. Notez toutefois que les images d’un e-mail doivent être activées pour que cela fonctionne. Cela peut affecter la synchronisation des identifiants par e-mail, car la plupart des systèmes de messagerie désactivent les images par défaut.

>[!MORELIKETHIS]
>
>* [Composants de collecte de données](../../../reference/system-components/components-data-collection.md)
