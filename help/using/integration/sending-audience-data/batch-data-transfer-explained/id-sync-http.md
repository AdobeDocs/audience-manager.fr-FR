---
description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les identifiants utilisateur entre un fournisseur et une Audience Manager. La synchronisation des identifiants peut commencer une fois que vous avez envoyé votre taxonomie de données à Audience Manager.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: Synchronisation des identifiants pour les transferts de données entrantes
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 1%

---

# Synchronisation des identifiants pour les transferts de données entrantes {#id-synchronization-for-inbound-data-transfers}

Décrit la syntaxe et les paramètres utilisés dans l’appel `HTTP` initial pour synchroniser les identifiants utilisateur entre un fournisseur et [!DNL Audience Manager]. La synchronisation des identifiants peut commencer une fois que vous avez envoyé votre taxonomie de données à [!DNL Audience Manager].

La synchronisation des identifiants est la première étape du processus de transfert des données asynchrones et entrantes. Au cours de cette étape, [!DNL Audience Manager] et le fournisseur comparent les identifiants des visiteurs de leur site respectifs et les font correspondre. Par exemple, un client [!DNL Audience Manager] peut connaître un utilisateur par son ID 123. Cependant, votre partenaire de données peut identifier cet utilisateur avec l’ID 456. Le processus de synchronisation permet à [!DNL Audience Manager] et à un fournisseur de données de réconcilier ces différents identifiants et d’identifier les utilisateurs dans leurs systèmes respectifs. Une fois terminé, [!DNL Audience Manager] et votre partenaire tiers doivent avoir les identifiants correspondants pour chaque utilisateur unique affiché sur nos réseaux.

Vous pouvez utiliser les méthodes suivantes pour obtenir vos données dans [!DNL Audience Manager] :

* [Requête HTTP de synchronisation des identifiants](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Declared ID Event](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Synchronisation des identifiants à partir d’une image incorporée de courrier électronique](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Requête de synchronisation des identifiants `HTTP` {#id-sync-http}

Dans un exchange d&#39;identifiant, une chaîne [!DNL URL] correctement formatée doit ressembler à ceci :

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

L’ [!DNL URL] de votre appel de synchronisation des identifiants entrants doit contenir les variables décrites dans le tableau ci-dessous.

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
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>Identifiant unique du fournisseur de contenu (attribué par <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (pourcentage) Représentation codée de votre ID utilisateur unique. Outre le codage des caractères ASCII réservés, tout caractère non ASCII doit être codé en pourcentage selon le tableau d’encodage des caractères UTF-8. </p> <p>Pour plus d’informations, voir le site web <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Une redirection d’URL codée avec la macro <code> ${DD_UUID}</code> incorporée dans celle-ci. </p> <p>Remarque : ajoutée uniquement lorsque le fournisseur de contenu lance l’appel . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facultatif. Ajoutez ce paramètre si vous utilisez le <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe d’Audience Manager pour IAB TCF.</a></p> <p><code> gdpr</code> peut être 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique). </p> <p> <b>Remarque :</b> Ce paramètre ne peut être utilisé qu’avec <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Facultatif. Ajoutez ce paramètre si vous utilisez le <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">module externe d’Audience Manager pour IAB TCF.</a></p> <p><code>gdpr_consent</code> est la chaîne de consentement RGPD codée en base 64 et sécurisée par URL (voir <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> spécification IAB</a>). </p> <p> <b>Remarque :</b> Ce paramètre ne peut être utilisé qu’avec <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Événement {#declared-id-event}

Pour plus d’informations, voir [Declared IDs](../../../features/declared-ids.md).

## Synchronisation des identifiants à partir d’une image incorporée de courrier électronique {#id-sync-email-image}

Le format des identifiants correspondants via une image d&#39;email est le même que celui illustré ci-dessus. Notez toutefois que les images d’un email doivent être activées pour que cela fonctionne. Cela peut avoir une incidence sur la synchronisation des identifiants par e-mail, car la plupart des systèmes de messagerie désactivent les images par défaut.

>[!MORELIKETHIS]
>
>* [Composants de collecte de données](../../../reference/system-components/components-data-collection.md)
