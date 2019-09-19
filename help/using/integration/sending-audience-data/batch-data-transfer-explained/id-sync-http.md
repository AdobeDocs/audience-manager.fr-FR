---
description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les ID utilisateur entre un fournisseur et Audience Manager. La synchronisation des identifiants peut commencer une fois que vous avez envoyé votre taxonomie de données à Audience Manager.
seo-description: Décrit la syntaxe et les paramètres utilisés dans l’appel HTTP initial pour synchroniser les ID utilisateur entre un fournisseur et Audience Manager. La synchronisation des identifiants peut commencer une fois que vous avez envoyé votre taxonomie de données à Audience Manager.
seo-title: Synchronisation des identifiants pour les transferts de données entrants
solution: Audience Manager
title: Synchronisation des identifiants pour les transferts de données entrants
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
translation-type: tm+mt
source-git-commit: 0fac081c93be36d2aa40023c7323ef1886b3860a

---


# Synchronisation des identifiants pour les transferts de données entrants{#id-synchronization-for-inbound-data-transfers}

Décrit la syntaxe et les paramètres utilisés dans l’ `HTTP` appel initial pour synchroniser les ID utilisateur entre un fournisseur et Audience Manager. La synchronisation des identifiants peut commencer une fois que vous avez envoyé votre taxonomie de données à Audience Manager.

<!-- c_id_sync_in.xml -->

La synchronisation des identifiants est la première étape du processus de transfert des données asynchrones et entrantes. Au cours de cette étape, Audience Manager et le fournisseur comparent les identifiants des visiteurs de leur site respectifs et les font correspondre. Par exemple, un [!DNL Audience Manager] client peut connaître un utilisateur à l’aide de l’ID 123. Toutefois, votre partenaire de données peut identifier cet utilisateur avec l’ID 456. Le processus de synchronisation permet [!DNL Audience Manager] et à un fournisseur de données de concilier ces différents ID et d’identifier les utilisateurs dans leurs systèmes respectifs. Une fois terminé, [!DNL Audience Manager] et votre partenaire tiers doivent avoir les identifiants correspondants pour chaque utilisateur unique affiché sur nos réseaux.

Vous pouvez utiliser les méthodes suivantes pour récupérer vos données [!DNL Audience Manager]:

* [Demande HTTP de synchronisation des identifiants](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Evénement d’identifiant déclaré](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [Synchronisation des identifiants à partir d’une image incorporée par courrier électronique](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## Demande de synchronisation des identifiants `HTTP`{#id-sync-http}

Dans un échange d’ID, une [!DNL URL] chaîne correctement formatée doit se présenter comme suit :

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

L’appel [!DNL URL] de synchronisation des identifiants entrants doit contenir les variables décrites dans le tableau ci-dessous.

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
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i></code> </td> 
   <td colname="col2"> <p>Identifiant unique du fournisseur de contenu (attribué par <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i></code> </td> 
   <td colname="col2"> <p>Représentation codée URL (pourcentage) de votre ID utilisateur unique. Outre le codage des caractères ASCII réservés, les caractères non ASCII doivent être codés en pourcentage selon la table de codage des caractères UTF-8. </p> <p>Pour plus d'informations, consultez le site Web <a href="https://www.url-encode-decode.com" format="http" scope="external"> Encode/décoder en ligne</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i></code> </td> 
   <td colname="col2"> <p>Une redirection d’URL codée avec la macro <code> ${DD_UUID}</code> qui y est incorporée. </p> <p>Remarque :  Ajouté uniquement lorsque le fournisseur de contenu lance l’appel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i></code> </td> 
   <td colname="col2"> <p>Facultatif. Ajoutez ce paramètre si vous utilisez le module externe <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager pour IAB TCF.</a></p> <p><code> gdpr</code> peut être égal à 0 (le RGD ne s’applique pas) ou à 1 (le RGD s’applique). </p> <p> <b></b> Remarque : Ce paramètre ne peut être utilisé qu'avec <code>gdpr_consentement</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consentement=&lt;CHAÎNE ENCODED&gt;</i></code> </td> 
   <td colname="col2"> <p>Facultatif. Ajoutez ce paramètre si vous utilisez le module externe <a href="../../../overview/aam-gdpr/aam-iab-plugin.md">Audience Manager pour IAB TCF.</a></p> <p><code>gdpr_consentement</code> est la chaîne de consentement GDPR codée en base 64 et compatible avec les URL (voir la spécification <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"></a>IAB). </p> <p> <b></b> Remarque : Ce paramètre ne peut être utilisé qu'avec <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Evénement d’identifiant déclaré {#declared-id-event}

Pour plus d’informations, voir ID [déclarés](../../../features/declared-ids.md).

## Synchronisation des identifiants à partir d’une image incorporée par courrier électronique {#id-sync-email-image}

Le format des ID correspondants par le biais d’une image de courrier électronique est identique à celui illustré ci-dessus. Notez toutefois que les images d’un courrier électronique doivent être activées pour que cela fonctionne. Cela peut avoir une incidence sur la synchronisation des identifiants par courrier électronique, car la plupart des systèmes de messagerie désactivent les images par défaut.

>[!MORE_LIKE_This]
>
>* [Composants de collecte de données](../../../reference/system-components/components-data-collection.md)

