---
description: Fonctionnement des ID déclarés, procédures de configuration, exemples de code et variables.
keywords: synchronisation des identifiants
seo-description: Fonctionnement des ID déclarés, procédures de configuration, exemples de code et variables.
seo-title: ID déclarés
solution: Audience Manager
title: ID déclarés
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: 94046c4ed825949451d0dbad37adbe9fba0f9191

---


# Declared IDs {#declared-ids}

Fonctionnement des ID déclarés, procédures de configuration, exemples de code et variables.

## Ciblage de l’ID déclaré {#declared-id-targeting}

Exchange et synchronisation utilisateur - identifiants avec Audience Manager à partir de périphériques ou de navigateurs qui n&#39;utilisent pas ou n&#39;acceptent pas les mécanismes de stockage persistant, tels que les cookies tiers.

<!-- declared_id_about.xml -->

## Purpose of Declared ID Targeting {#declared-id-targeting-purpose}

Certains navigateurs et la plupart des périphériques mobiles n&#39;acceptent pas les cookies tiers. Cela complique la conservation des informations sur les visiteurs du site ou leur attribution à des ID persistants. To resolve this issue, Audience Manager uses [!UICONTROL DIL] to let you pass in [!UICONTROL declared IDs] on an event call. Also, a [!UICONTROL declared ID] can act as a universal ID that applies to the same user across all the solutions in the [!DNL Experience Cloud]. Le tableau suivant décrit le processus de ciblage/correspondance d&#39;ID :

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Processus </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Appel d'événement</b> </td> 
   <td colname="col2"> <p>To work, you need <span class="wintitle"> DIL </span> and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Experience Cloud ID service </a> code on the page. <span class="wintitle"> Le code DIL </span> reçoit <span class="wintitle"> des ID </span> déclarés de la fonction <code> setvisitorid </code> fournie par le <span class="keyword"> service Experience Cloud ID </span> et transmet ce paramètre à <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de correspondance</b> </td> 
   <td colname="col2"> <p>Audience Manager tente de faire correspondre le client et l'identifiant visiteur avec un identifiant correspondant dans notre système. Si un identifiant correspondant n'existe pas, Audience Manager crée un identifiant et l'associe au client et à l'identifiant visiteur. </p> <p> <p>Remarque : Le mappage le plus récent est utilisé si votre ID mappe à plusieurs ID Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retour</b> </td> 
   <td colname="col2"> <p>Audience Manager écrit son identifiant synchronisé dans un cookie propriétaire (ou un autre espace de stockage adressable) dans le domaine client ou l'application. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Appels d'événements suivants</b> </td>
   <td colname="col2"> <p>D'autres appels d'événement lisent l'identifiant Audience Manager à partir du domaine du client et l'envoient à Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

To get started, you need to configure the [!DNL Experience Cloud] ID service and [!UICONTROL DIL] across the pages on your site that you want to use for data collection. See [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Opt-out Calls {#opt-out-calls}

[!UICONTROL declared ID] Le processus respecte les préférences du visiteur du site pour exclure le ciblage Audience Manager de votre site Web. When Audience Manager receives an opt-out request, the [!DNL JSON] returned by the [!UICONTROL DCS] contains the error code 171, with the message &quot;Encountered opt out tag&quot;, instead of the Audience Manager user ID.

* Audience Manager can pass in a [!UICONTROL declared ID] opt-out alongside an Audience Manager [!UICONTROL UUID] in the [!DNL URL].
* The [!UICONTROL declared ID] opt-out is stored in the [!UICONTROL Profile Cache Serveîr ([!UICONTROL PCS]) on a per-partner basis. There is no platform-level opt-out using [!UICONTROL declared IDs]. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross [!UICONTROL DCS] regions).

See [Data Privacy](../overview/data-security-and-privacy/data-privacy.md) for more information about opting-out of data collection.

## Declared ID Opt-Out Examples {#opt-out-examples}

You can make a [!UICONTROL declared ID] opt-out requests with the `d_cid` and `d_cid_ic` key-value pairs. The legacy parameters like `d_dpid` and `d_dpuuid` still work, but are considered deprecated. Voir [CID remplace DPID et DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Exclusions avec CID et CID_ IC

For a description and syntax, see [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion avec </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifiant de fournisseur de données et utilisateur - id. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/demoptout.jpg ? d_ cid = 123 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un code d'intégration et un utilisateur - id. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/déstout ? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/déstout ? d_ cid = 123 % &amp; d_ cid_ ic = 456 013 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exclusions avec DPID, DPUUID et UUID (obsolète)

Ces méthodes fonctionnent toujours mais sont considérées comme obsolètes. Ces informations sont fournies à des fins héritées et référencées. Les exclusions héritées incluent :

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion (obsolète) </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid </code> uniquement </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=AAM<i></i>ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclusion du niveau partenaire </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID &amp; d_ dpid = ID fournisseur de données </code> </p> <p>A partner level opt-out gets stored for the latest mapping of this <code> dpid </code> + <code> dpuuid </code> pair to an AAM UUID. S'il n'existe pas de correspondance existante, Audience Manager vérifie si la requête contient un UUID AAM dans le cookie et, le cas échéant, utilise cette option pour stocker l'exclusion. Sinon, Audience Manager génère un nouvel identifiant AAM et stocke l'exclusion sous celle-ci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> et explicite <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>user ID &amp; d_ dpuuid = user provider's user - id &amp;<i>d_ dpid = data provider ID</i></code> </p> <p> <code> d_ uuid </code> est toujours prioritaire. If the <code> dpid </code> + <code> dpuuid </code> combination maps to another AAM UUID, the opt-out is stored under the AAM UUID passed in the request ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables and Syntax for Declared IDs {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

The following table lists the key-value pairs that pass in your [!DNL Audience Manager] data provider ID and user IDs or integration codes, if used. Note, *italics* indicates a variable placeholder. Des espaces ont été ajoutés pour faciliter la lecture.

Dans chaque paire clé-valeur :

* The `=` symbol separates the key from its related values.
* The non-printing [!DNL ASCII] character `%01` separates the values.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid =<i>ID du fournisseur de données</i> % 01<i>user - id</i></code> </p> </td> 
   <td colname="col2"> <p>Contient un ID de fournisseur de données et un utilisateur unique associé - id dans une paire clé-valeur unique. <code> d_ cid </code> remplace <code> d_ dpid </code> et <code> d_ dpuuid </code>, qui sont considérés comme obsolètes mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic =<i>code d'intégration</i> % 01<i>user - id</i></code> </p> </td> 
   <td colname="col2"> <p>Contient un code d'intégration et un utilisateur unique associé - id dans une paire clé-valeur unique. <code> d_ cid_ ic </code> remplace <code> d_ dpid </code> et <code> d_ dpuuid </code>, qui sont obsolètes mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sample Event Calls {#sample-event-calls}

Étant donné ces paires clé-valeur et la syntaxe requise, vous effectuez les appels d&#39;événement comme illustré ci-dessous.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> L'appel d'événement comprend </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifiant de fournisseur de données et utilisateur - id. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/événement ? d_ cid = 123 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un code d'intégration et un utilisateur - id. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/événement ? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Multiple <code> d_cid </code> and <code> d_cid_ic </code> key-value pairs. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/événement ? d_ cid = 123 % &amp; d_ cid_ ic = 456 013 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID remplace DPID et DPUUID](../reference/cid.md)


## Declared ID Variables {#declared-id-variables}

Describes the configuration variables used to pass declared IDs through [!UICONTROL DIL] to [!DNL Audience Manager.]

## DIL Uses the Experience Cloud ID Service to Pass Declared IDs {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

When used with the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/), you no longer need to pass in [!UICONTROL declared IDs] with the deprecated `dpid` and `dpuuid` variables. Instead, the current versions of [!UICONTROL DIL] rely on the `visitorService` function to get the [!UICONTROL declared IDs] from the `setCustomerIDs` function in the [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). You would call `visitorService` in `DIL.create` as shown below.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

In the `namespace` key-value pair, `MCORG` is your [!DNL Experience Cloud] Organization ID. If you don&#39;t have this ID, you can find it in the [!UICONTROL Administration] section of the [!DNL Experience Cloud] dashboard. Vous devez disposer des autorisations d&#39;administrateur pour afficher ce tableau de bord. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Deprecated Functions {#deprecated-functions}

With the latest versions of [!UICONTROL DIL] (6.2+), you don&#39;t need to use these key-value pairs to pass in [!UICONTROL declared IDs]. That&#39;s because [!UICONTROL DIL] now relies on the `visitorService` function shown in the code sample above. This function gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service]. Toutefois, nous référencons ces variables ici à des fins historiques et héritées. See the code below for an example of how to configure `DIL.create` to get a [!UICONTROL declared ID] from the [!UICONTROL Visitor ID Service].
The following table describes the legacy variables used by the `declaredId` object:

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>Identifiant de partenaire de données attribué par Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>L’identifiant unique du fournisseur de données pour l’utilisateur. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` et `DPUUID`

Audience Manager compares and matches the combined `DPID` and `DPUUID` to a corresponding user ID in our system. If an ID does not exist, Audience Manager creates a new user ID and synchronizes it to the `DPID/DPUUID` combination. Once Audience Manager matches or creates a user ID (the `UUID`) it returns that ID in the [!DNL JSON] response to the cookie in the client&#39;s domain (first-party cookie) or other local storage.

Call this function when you&#39;re using [!UICONTROL DIL] v6.1 or earlier. However, this function has been deprecated in favor of the new version that gets [!UICONTROL declared IDs] from the [!UICONTROL Experience Cloud ID Service].

<pre class="js"><code>DIL. create ({ 
 partenaire : « nom du partenaire », 
 Declaredid : { 
 dpuuid : <i>dpuuid</i>, 
 DPID : <i>dpid</i> 
 } 
 }) ;</code>
</pre>

>[!NOTE]
>
>Note, you need to programmatically develop the code that supplies the ID values for the `d_dpuuid` and `d_dpid` keys.

### Transmettre les identifiants après les instanciations DIL

>[!NOTE]
>
>If you make an [!DNL API] call with a different `declaredID` combination, the new combination will be used for that call only. Further regular event calls will use the original `DIL.create`  `declaredID` combination.

<pre class="js"><code>DIL. getdil ('partner name '). api. signals ({…}). declaredid ({ 
 dpuuid :<i>dpuuid</i> 
 dpid :<i>dpid</i> }). 
submit () ;</code>
</pre>

## Request/Response Examples {#request-response-examples}

La requête envoie un fournisseur de données et un utilisateur - id à Audience Manager :

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

The response returns the Audience Manager ID (e.g., `UUID`) which is written to a first-party cookie in the page domain.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Do Not Target and Opt-Out Calls {#do-not-target}

[!UICONTROL declared ID] Le processus respecte les préférences du visiteur du site pour exclure le ciblage Audience Manager de votre site Web. When Audience Manager receives an opt-out request, the [!UICONTROL DCS] returns an empty [!DNL JSON] object instead of the Audience Manager user ID.