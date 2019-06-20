---
description: Décrit la syntaxe et les paramètres utilisés dans l'appel HTTP initial pour synchroniser l'utilisateur - id entre un fournisseur et Audience Manager. La synchronisation des identifiants peut commencer après l'envoi de votre taxonomie de données à Audience Manager.
seo-description: Décrit la syntaxe et les paramètres utilisés dans l'appel HTTP initial pour synchroniser l'utilisateur - id entre un fournisseur et Audience Manager. La synchronisation des identifiants peut commencer après l'envoi de votre taxonomie de données à Audience Manager.
seo-title: Synchronisation des identifiants pour les transferts de données entrants
solution: Audience Manager
title: Synchronisation des identifiants pour les transferts de données entrants
uuid: 037 e 74 a 6-acfd -4 cef-b 693-16 b 7 aaa 8 e 976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# ID Synchronization for Inbound Data Transfers{#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and Audience Manager. La synchronisation des identifiants peut commencer après l&#39;envoi de votre taxonomie de données à Audience Manager.

<!-- c_id_sync_in.xml -->

La synchronisation des identifiants est la première étape du processus de transfert des données asynchrones. Dans cette étape, Audience Manager et les fournisseurs comparent les identifiants et les identifiants des visiteurs de site respectifs. For example, an [!DNL Audience Manager] customer may know a user by ID 123. Cependant, votre partenaire de données peut identifier cet utilisateur avec l&#39;identifiant 456. The synchronization process allows [!DNL Audience Manager] and a data vendor to reconcile these different IDs and identify users in their respective systems. Once complete, [!DNL Audience Manager] and your third-party partner should have corresponding IDs for each unique user seen on our networks.

You can use the following methods to get your data into [!DNL Audience Manager]:

* [Demande HTTP de synchronisation des identifiants](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Événement d&#39;ID déclaré](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Synchronisation des identifiants à partir d&#39;une image incorporée par courrier électronique](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID Synchronization `HTTP` Request {#id-sync-http}

In an ID exchange, a properly formatted [!DNL URL] string should look like this:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

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
  <tr> 
   <td colname="col1"> <code><i>&lt; PROVIDER_ ID &gt;</i></code> </td> 
   <td colname="col2"> <p>Unique ID for the content provider (assigned by <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; PROVIDER_ UUID &gt;</i></code> </td> 
   <td colname="col2"> <p>Représentation codée d'URL (pourcentage) de votre utilisateur unique - id. Outre le codage des caractères ASCII réservés, tous les caractères non ASCII doivent être codés en pourcentage en fonction du tableau de codage des caractères UTF -8. </p> <p>For more information, see the <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>&lt; REDIRECT_ URL &gt;</i></code> </td> 
   <td colname="col2"> <p>An encoded URL redirect with the macro <code> ${DD_UUID}</code> embedded within it. </p> <p>Remarque : Ajouté uniquement lorsque le fournisseur de contenu initie l'appel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr = &lt; 0|1 &gt;</i></code> </td> 
   <td colname="col2"> <p>Facultatif. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code> gdpr</code> peut être 0 (GDPR ne s'applique pas) ou 1 (GDPR s'applique). </p> <p> <b>Remarque :</b> Ce paramètre ne peut être utilisé qu'avec <code>gdpr_ permission</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_ permission = &lt; CHAÎNE CODÉE &gt;</i></code> </td> 
   <td colname="col2"> <p>Facultatif. Add this parameter if you are using the <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager Plug-in for IAB TCF.</a></p> <p><code>gdpr_ permission</code> est la chaîne de consentement GDPR 64 codées sans URL (voir <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> Spécifications IAB</a>). </p> <p> <b>Remarque :</b> Ce paramètre ne peut être utilisé qu'avec <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Declared ID Event {#declared-id-event}

For more information, see [Declared IDs](../../../features/declared-ids.md).

## ID Synchronization From an Email Embedded Image {#id-sync-email-image}

Le format des ID correspondants par le biais d&#39;une image de courriel est identique à celui indiqué ci-dessus. Notez toutefois que les images d&#39;un courriel doivent être activées pour que cela fonctionne. Cela peut affecter la synchronisation des identifiants par courriel, car la plupart des systèmes de messagerie désactivent les images par défaut.

>[!MORE_ LIKE_ THIS]
>
>* [Composants de collecte de données](../../../reference/system-components/components-data-collection.md)

