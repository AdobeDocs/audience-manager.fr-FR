---
description: Les API DIL au niveau de l'instance vous permettent de créer et d'utiliser par programmation les objets Audience Manager. Les méthodes de niveau instance améliorent la fonctionnalité d'API définie par les méthodes de niveau classe.
keywords: créer des caractéristiques ; créer une caractéristique
seo-description: Les API DIL au niveau de l'instance vous permettent de créer et d'utiliser par programmation les objets Audience Manager. Les méthodes de niveau instance améliorent la fonctionnalité d'API définie par les méthodes de niveau classe.
seo-title: Méthodes DIL au niveau de l'instance
solution: Audience Manager
title: Méthodes DIL au niveau de l'instance
uuid: aa 5147 bb -51 d 5-41 d 4-a 78 a-e 550 f 7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Instance-level DIL Methods{#instance-level-dil-methods}

The instance-level [!UICONTROL DIL] APIs let you programmatically create and work with Audience Manager objects. Les méthodes de niveau instance améliorent la fonctionnalité d'API définie par les méthodes de niveau classe.

## Getting started with Instance-level DIL Methods {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

When working with the instance-level [!UICONTROL DIL] APIs:

* L'accès requiert un nom de partenaire et un identifiant de namespace de noms de conteneur (NSID). Contactez votre gestionnaire de compte Audience Manager pour obtenir ces informations.
* Replace any sample *italicized* text in the API documentation with value, ID, or other variable as required by the method you're working with.

<!-- 

c_instance_start.xml

 -->

## signals {#signals}

Ajoute des mappages au niveau des clients et des plateformes à la chaîne de requête d'une requête en attente.

<!-- 

r_dil_signals.xml

 -->

**Signature de fonction :**`signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Vous pouvez chaîner d'autres appels d'API à cette méthode.
>* If the Adobe Experience Cloud JavaScript library is on the page, `submit()` waits for the Cloud to set a cookie before sending a request.


**Clés de requête réservées**

Les clés de requête suivantes sont réservées et ne peuvent pas être remplacées par cette méthode :

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `obj` | Objet | Objet représentant les paires clé-valeur pour les mappages au niveau de la plate-forme. Le paramètre accepte les chaînes et les tableaux comme valeurs de propriété dans l'objet. |
| `prefix` | Chaîne | Facultatif. Valeur de chaîne préfixée à chaque clé d'objet (remplace la clé d'origine). |
| `return` | DIL. api | Renvoie l'objet API de l'instance DIL active. |

**Réponse**

Returns the API object of the current [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>' 
 Containernsid : <i>Containernsid</i> }) 
; 
 
// Method 1 
var obj = {key 1 : 1, clé 2 : 2} ; 
Datalib. api. signals (obj,'c_'). submit () ; 
 
// Method 2 
datalib. api. signals ({c_ zdid : 54321}). submit () ; 
 
// Méthode 3 
// will send'c_ key = a &amp; c_ key = 2 &amp; c_ key = 3 'to Audience Manager 
var obj = {key : ['a ','b ','c ']} ; 
Datalib. api. signals (obj,'c_'). submit () ;</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Exigences en matière de nom pour les variables clés](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

Ajoute des ID à la chaîne de requête d'une requête en attente.

<!-- 

r_dil_traits.xml

 -->

**Signature de fonction :**`traits:function (sids){}`

>[!NOTE]
>
>Vous pouvez chaîner d'autres appels d'API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `sids` | Tableau | ID de segment caractéristique dans un tableau. |

**Réponse**

Returns the API object of the current [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>var partnerobject = DIL. create ({ 
 partenaire : '<i>nom du partenaire</i>', 
 Containernsid : <i>NSID</i> }) 
; 
Partnerobject. api. caractéristiques (<i>[123, 456, 789]</i>) ;</code>
</pre>

## logs {#logs}

Ajoutez des données aux fichiers journaux dans la requête en attente.

<!-- 

r_dil_logs.xml

 -->

**Signature de fonction :**`logs: function {key1:value1, key2:value2}`

**Réponse**

Returns the API object of the current [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>var partnerobject = DIL. create ({ 
 partenaire : '<i>partner</i>', 
 Containernsid : <i>NSID</i> }) 
; 
Partnerobject. api. logs ({ 
 fichier : ' dil. js ', 
 message : ' Il s'agit de la première requête '}) 
;</code>
</pre>

## submit {#submit}

Submits all pending data to Audience Manager for the [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**Signature de fonction :**`submit: function () {}`

>[!NOTE]
>
>Vous pouvez chaîner d'autres appels d'API à cette méthode. Also, [!UICONTROL DIL] writes encoded data to a destination cookie. For example, spaces are encoded as `%20` and semicolons as `%3B`.

**Réponse**

Returns the API object of the current [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>', 
 Containernsid : <i>Containernsid</i> }) 
; 
 
Datalib. api. caractéristiques ([<i>123,456, 
789</i>]). logs ({ 
 fichier : ' dil. js ', 
 message : ' Il s'agit de la première requête '}). 
signaux ({ 
 c_ zdid : <i>1111</i> 
 d_ dma : '<i>default</i>'}). 
submit () ;</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Exigences en matière de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

Fonction exécutée après le rappel de publication de destination par défaut.

<!-- 

r_dil_after_result.xml

 -->

**Signature de fonction :**`afterResult: function (fn) {}`

>[!NOTE]
>
>Vous pouvez chaîner d'autres appels d'API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `fn` | Fonction | Fonction que vous souhaitez exécuter après le traitement de JSON par le rappel par défaut qui gère la publication de destination. |

**Réponse**

Returns an API object of the current [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>', 
 Containernsid : <i>Containernsid</i> }) 
; 
 
Datalib. api. signals ({ 
 c_ zdid : <i>54321</i> 
 d_ dma : '<i>default</i>'}). 
afterresult (function (json) { 
 //do un élément avec les données JSON renvoyées par le serveur. 
}).submit();
</code></pre>

## clearData {#cleardata}

Efface toutes les données d'une requête en attente.

<!-- 

r_dil_clear_data.xml

 -->

**Signature de fonction :**`clearData: function () {}`

>[!NOTE]
>
>Vous pouvez chaîner d'autres appels d'API à cette méthode.

**Réponse**

Returns the API object of the current [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>', 
 Containernsid : <i>Containernsid</i> }) 
; 
 
Datalib. api. caractéristiques ([<i>123,456, 789</i>]). logs ({ 
 fichier : ' dil. js ' 
 message : ' Il s'agit de la première requête '}). 
signaux ({ 
 c_ zdid : <i>1111</i> 
 d_ dma : '<i>default</i>'}) 
; 
 
//reset the pending data 
datalib. cleardata () ;</code>
</pre>

## customQueryParams {#customqueryparams}

Ajoute des paramètres de requête personnalisés qui ne sont pas explicitement définis par le serveur de collecte de données à une requête en attente.

<!-- 

r_dil_custom_query_params.xml

 -->

**Signature de fonction :**`customQueryParams: function (obj) {}`

>[!NOTE]
>
>Vous pouvez chaîner d'autres appels d'API à cette méthode.

**Clés de requête réservées**

Les clés de requête suivantes sont réservées et ne peuvent pas être remplacées par cette méthode :

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Réponse**

Renvoie l'objet API de l'instance DIL active.

**Exemple de code**

<pre><code>var partnerobject = DIL. create ({ 
 partenaire : '<i>partner</i>', 
 Containernsid : <i>NSID</i> }) 
; 
Partnerobject. api. customqueryparams ({ 
 nid : 54231, 
 ntype : ' default '}) 
;</code>
</pre>

## getContainerNSID {#getcontainernsid}

Returns the value of the container NSID for the [!UICONTROL DIL] instance. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Signature de fonction :**`dil.api.getContainerNSID: function () {}`

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>', 
 Containernsid : <i>Containernsid</i> }) 
; 
 
//verify the container NSID 
var nsid = datalib. api. getcontainernsid () ;</code>
</pre>

## getEventLog {#geteventlog}

Renvoie les données du journal d'événements chronologiquement triées sous la forme d'un tableau de chaînes. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_event_log.xml

 -->

**Signature de fonction :**`dil.api.getEventLog: function () {}`

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>', 
 Containernsid : <i>Containernsid</i> }) 
; 
 
Datalib. api. caractéristiques ([<i>123, 456, 789</i>]). logs ({ 
 fichier : ' dil. js ', 
 message : ' Il s'agit de la première requête '}) 
; . signaux ({ 
 c_ zdid : <i>1111</i> 
 d_ dma : '<i>default</i>'}) 
; . submit () ; 
 
//check log for messages 
var log = datalib. api. geteventlog () ; 
if (log &amp; &amp; log. length) { 
 alert (log. join ('\ n ')) ; 
} else { 
 alert ("No log messages ') ; 
}</code>
</pre>

## getPartner {#getpartner}

Returns the partner name for a [!UICONTROL DIL] instance. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_partner.xml

 -->

**Signature de fonction :**`dil.api.getPartner: function () {}`

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>' 
 Containernsid : <i>Containernsid</i> }) 
; 
 
//Verify the partner name 
var partner = datalib. api. getpartner () ;</code>
</pre>

## getState {#getstate}

Returns the state of the current [!UICONTROL DIL] instance. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_state.xml

 -->

**Signature de fonction :**`dil.api.getState: function () {}`

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>', 
 Containernsid : <i>Containernsid</i> }) 
; 
 
Datalib. api. caractéristiques ([<i>123, 456, 789</i>]). logs ({ 
 fichier : ' dil. js ', 
 message : ' Il s'agit de la première requête '}) 
; . signaux ({ 
 c. zdid : <i>1111</i> 
 d_ dma : '<i>default</i>'}) 
; . submit () ; 
 
var state = datalib. api. getstate () ; 
 
/* Contour d'objet de state 
state = { 
 Pendingrequest : {<i>pending data for call to server</i>}, 
 Otherrequestinfo : { 
 Firingqueue : [], 
 déclenché : [], 
 déclenchement : false, 
 errored : [], 
 Reservedkeys : { 
 frères : true, 
 pdata : true, 
 logdata : true, 
 rappel : true, 
 Postcallbackfn : true, 
 Useimagerequest : true, 
 }, 
 Firstrequesthasflow: false, 
 num_ of_ jsonp_ responses : 0, 
 num_ of_ jsonp_ errors : 0, 
 num_ of_ img_ responses : 0, 
 num_ of_ img_ errors : 0 
 }, 
 Destinationpublishinginfo : { 
 THROTTLE_ START : 3000, 
 Throttletimerset : false, 
 id : « destination_ publishing_ iframe_'+ partner +'_'+ containernsid, 
 url : (constantes. ishttps ? ' https://' : ' https://fast.') + partner +'.demdex.net/dest3.html?d_nsid=' 
 + Containernsid +'#'+ encodeuricomponent (document. location. href), 
 iframe : null, 
 Iframehasloaded : false, 
 Sendingmessages : false, 
 messages : [], 
 Messagesendinginterval : constants. POST_ MESSAGE_ ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 &amp; 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

Comprend deux fonctions qui permettent aux partenaires de données d'échanger et de synchroniser les utilisateurs : les identifiants entre eux et Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Signature de fonction :**

Works with [!UICONTROL DIL] versions 2.10 and 3.1 or higher.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code </th> 
   <th colname="col2" class="entry"> Synchronise les identifiants des utilisateurs </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. idsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Entre différents partenaires de données et Audience Manager. Par exemple, le partenaire x l'utilise pour synchroniser un utilisateur - id avec le partenaire y, puis l'envoyer à Audience Manager. </p> <p> <p><b>Important :</b> Cette méthode est obsolète. Please use the <code> idSyncByURL </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil. Instance. api. aamidsync (initconfig) </code> </td> 
   <td colname="col2"> <p>Lorsque vous connaissez déjà l'utilisateur - id et souhaitez l'envoyer à Audience Manager. </p> <p> <p><b>Important :</b> Cette méthode est obsolète. Please use the <code> idSyncByDataSource </code> method of the Experience Cloud ID Service instance. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Eléments idsync**

`idSync` peut se composer des éléments suivants :

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>Identifiant de fournisseur de données attribué par Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>L’identifiant unique du fournisseur de données pour l’utilisateur. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Nombre </td> 
   <td colname="col3"> <p><i>(Optionnel)</i> Définit le délai d’expiration du cookie. Doit être un nombre entier. Sa valeur par défaut est de 20 160 minutes (14 jours). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>URL de destination. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Macros**

`idSync` accepte les macros suivantes :

* **`%TIMESTAMP%`:** Génère un horodatage (en millisecondes). Utilisé pour la mise en cache.
* **`%DID%`:** Insère l'identifiant Audience Manager pour l'utilisateur.
* **`%HTTP_PROTO%`:** Définit le protocole de la page ( `http` ou `https`).

**Réponse**

Both functions return `Successfully queued` if successful. Autrement, elles renvoient une chaîne contenant un message d’erreur.

**Exemple de code**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">// Fire url with macros replace 
dilinstance. api. idsync ({ 
 dpid : ' 23 ', // doit être une chaîne 
 url : '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
% 2 Fibs % 3 Adpid % 3 D 420% 26 dpuuid % 3 D % 7 B % 7 Buid % 7 D % 7 D ', 
 Minutestolive : 20160 // optional, default to 20160 minutes (14 days)}) 
;</code>
</pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">// Fires 'https:/https:' +'//dpm.demdex.net/ibs:dpid= &lt; dpid &gt; &amp; dpuuid = &lt; dpuuid &gt;'diinstance. api. aamidsync ({ 
 dpid : ' 23 ', // doit être une chaîne 
 dpuuid : ' 98765 ', // doit être une chaîne 
 Minutestolive : 20160 // optional, default to 20160 minutes (14 days)}) 
;</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Fonctions de synchronisation dans le service Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

Ajoute un rappel (qui reçoit JSON) à la requête en attente.

<!-- 

r_dil_result.xml

 -->

**Signature de fonction :**`result: function (callback) {}`

Ce rappel remplace le rappel par défaut qui gère la publication de destination.

>[!NOTE]
>
>Vous pouvez chaîner d'autres appels d'API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `callback` | Fonction | Fonction JavaScript exécutée par le rappel JSONP. |

**Réponse**

Returns the API object of the current [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>', 
 Containernsid : <i>Containernsid</i> }) 
; 
 
Datalib. api. caractéristiques ([<i>123, 456, 789</i>]). result (function (json) { 
 //do quelque chose, éventuellement avec les données JSON renvoyées par le serveur. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` est un paramètre booléen qui contrôle la manière dont [!UICONTROL DIL] les appels ont lieu à [!UICONTROL Data Collection Servers (DCS)] et Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* When `secureDataCollection= true` (default), [!UICONTROL DIL] always makes secure, HTTPS calls.

* When `secureDataCollection= false`, [!UICONTROL DIL] makes either HTTP or HTTPS calls by following the security protocol set by the page.

>[!IMPORTANT]
>
>Set `secureDataCollection= false` if you use visitorAPI.js and [!UICONTROL DIL] on the same page. Voir l'exemple de code ci-dessous.

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Securedatacollection : false}) 
;</code>
</pre>

>[!MORE_ LIKE_ THIS]
>
>* [Création de DIL](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` est un paramètre booléen true/false qui contrôle la manière dont le navigateur demande des ressources à d'autres domaines.

<!-- 

dil-use-cors-only.xml

 -->

**Aperçu**

`useCORSOnly` est définie sur false par défaut. False signifie que le navigateur peut effectuer des contrôles de ressource avec CORS ou JSONP. However, [!UICONTROL DIL] always tries to request resources with CORS first. Il revient à JSONP sur les navigateurs plus anciens qui ne prennent pas en charge CORS. If you need to force the browser to use CORS only, such as with sites that have high-security requirements, set `useCORSOnly:true`.

**Exemple de code**

<pre><code class="js">var dilinstance = DIL. create ({ 
 … 
 Usecorsonly : true}) 
;</code>
</pre>

>[!IMPORTANT]
>
>* We recommend that you set `useCORSOnly: true` only when you're sure that your site visitors have browsers that support this feature.
>* When `useCORSOnly: true`, [!UICONTROL DIL] will not make ID calls from Internet Explorer version 9 or older.
>



>[!MORE_ LIKE_ THIS]
>
>* [Création de DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Experience Cloud ID Service : Usecorsonly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Prise en charge de CORS dans le service Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Changes the request type to image `<img>` from script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Signature de fonction :**`useImageRequest: function () {}`

>[!NOTE]
>
>Vous pouvez chaîner d'autres appels d'API à cette méthode.

**Réponse**

Returns an API object of the current [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>var datalib = DIL. create ({ 
 partenaire : '<i>Partnership partnerName</i>', 
 Containernsid : <i>Containernsid</i> }) 
; 
 
Datalib. api. caractéristiques ([<i>123, 456, 789</i>]). useimagerequest (). submit () ;</code>
</pre>

