---
description: Les API DIL au niveau de l’instance vous permettent de créer et d’utiliser par programmation des objets Audience Manager. Les méthodes au niveau de l’instance améliorent la fonctionnalité de l’API établie par les méthodes au niveau de la classe.
keywords: créer des caractéristiques;créer des caractéristiques
seo-description: Les API DIL au niveau de l’instance vous permettent de créer et d’utiliser par programmation des objets Audience Manager. Les méthodes au niveau de l’instance améliorent la fonctionnalité de l’API établie par les méthodes au niveau de la classe.
seo-title: Méthodes DIL de niveau instance
solution: Audience Manager
title: Méthodes DIL de niveau instance
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Méthodes DIL de niveau instance{#instance-level-dil-methods}

Les [!UICONTROL DIL] API de niveau instance vous permettent de créer et d’utiliser par programmation des objets Audience Manager. Les méthodes au niveau de l’instance améliorent la fonctionnalité de l’API établie par les méthodes au niveau de la classe.

## Prise en main des méthodes DIL au niveau de l’instance {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Lorsque vous travaillez avec des [!UICONTROL DIL] API de niveau instance :

* L’accès requiert un nom de partenaire et un ID d’espace de noms de conteneur (NSID). Contactez votre gestionnaire de compte Audience Manager pour obtenir ces informations.
* Remplacez tout exemple de texte *en italique* dans la documentation de l’API par la valeur, l’ID ou toute autre variable, comme l’exige la méthode utilisée.

<!-- 

c_instance_start.xml

 -->

## signaux {#signals}

Ajoute des mappages au niveau du client et de la plate-forme à la chaîne de requête d’une requête en attente.

<!-- 

r_dil_signals.xml

 -->

**** Signature de fonction : `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Vous pouvez lier d’autres appels d’API à cette méthode.
>* Si la bibliothèque JavaScript Adobe Experience Cloud se trouve sur la page, `submit()` attend que le cloud définisse un cookie avant d’envoyer une requête.


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
| `obj` | Objet | Objet représentant les paires clé-valeur pour les mappages au niveau de la plate-forme. Le paramètre accepte les chaînes et les tableaux comme valeurs de propriété dans l’objet. |
| `prefix` | Chaîne | Facultatif. La valeur de chaîne préfixe sur chaque clé d’objet (remplace la clé d’origine). |
| `return` | DIL.api | Renvoie l’objet API de l’instance DIL active. |

**Réponse**

Renvoie l’objet API de l’ [!UICONTROL DIL] instance active.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>' containerNSID : <i>containerNSID</i> }); 
 
// Méthode 1 var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signaux(obj, 'c_').submit(); 
 
// Méthode 2 dataLib.api.signaux({c_zdid: 54321}).submit(); 
 
// Méthode 3 // Envoie 'c_key=a&amp;c_key=2&amp;c_key=3' à Audience Manager var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signaux(obj, 'c_').submit(); 
</code></pre>

>[!MORE_LIKE_This]
>
>* [Exigences de nom pour les variables clés](../features/traits/trait-key-name-requirements.md)


## traits {#traits}

Ajoute des SID à la chaîne de requête d’une requête en attente.

<!-- 

r_dil_traits.xml

 -->

**** Signature de fonction : `traits:function (sids){}`

>[!NOTE]
>
>Vous pouvez lier d’autres appels d’API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `sids` | Tableau | Identifiants de segment de caractéristiques dans un tableau. |

**Réponse**

Renvoie l’objet API de l’ [!UICONTROL DIL] instance active.

**Exemple de code**

<pre><code>
var partnerObject = DIL.create({ partner : '<i>partner name</i>', containerNSID: <i>NSID</i> }); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Ajoutez des données aux fichiers journaux dans la requête en attente.

<!-- 

r_dil_logs.xml

 -->

**** Signature de fonction : `logs: function {key1:value1, key2:value2}`

**Réponse**

Renvoie l’objet API de l’ [!UICONTROL DIL] instance active.

**Exemple de code**

<pre><code>
var partnerObject = DIL.create({ partner : '<i>partner</i>', containerNSID: <i>NSID</i> }); 
partnerObject.api.logs({ fichier : 'dil.js', message: 'C'est la première requête' });
</code></pre>

## submit {#submit}

Envoie toutes les données en attente à Audience Manager pour l’ [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**** Signature de fonction : `submit: function () {}`

>[!NOTE]
>
>Vous pouvez lier d’autres appels d’API à cette méthode. En outre, [!UICONTROL DIL] écrit les données codées dans un cookie de destination. Par exemple, les espaces sont codés en tant que `%20` points-virgules `%3B`.

**Réponse**

Renvoie l’objet API de l’ [!UICONTROL DIL] instance active.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ fichier: 'dil.js', message: 'Ceci est la première requête' }).signaux({ c_zdid: <i>1111</i> d_dma: '<i>default</i>' }).submit();
</code></pre>

>[!MORE_LIKE_This]
>
>* [Préfixe requis pour les variables clés](../features/traits/trait-variable-prefixes.md)


## afterResult {#afterresult}

Fonction qui s’exécute après le rappel de publication de destination par défaut.

<!-- 

r_dil_after_result.xml

 -->

**** Signature de fonction : `afterResult: function (fn) {}`

>[!NOTE]
>
>Vous pouvez lier d’autres appels d’API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `fn` | Fonction | Fonction que vous souhaitez exécuter après le traitement de JSON par le rappel par défaut qui gère la publication de destination. |

**Réponse**

Renvoie un objet API de l’ [!UICONTROL DIL] instance active.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.signaux({ c_zdid: <i>54321</i> d_dma: '<i>default</i>' }).afterResult(function(json){ //Faites quelque chose avec les données JSON renvoyées par le serveur. 
}).submit();
</code></pre>

## clearData {#cleardata}

Efface toutes les données d’une requête en attente.

<!-- 

r_dil_clear_data.xml

 -->

**** Signature de fonction : `clearData: function () {}`

>[!NOTE]
>
>Vous pouvez lier d’autres appels d’API à cette méthode.

**Réponse**

Renvoie l’objet API de l’ [!UICONTROL DIL] instance active.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({, fichier : Message "dil.js" : 'Ceci est la première requête' }).signaux({ c_zdid: <i>1111</i> d_dma: '<i>default</i>' }); 
 
//Réinitialiser les données en attente dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Ajoute des paramètres de requête personnalisés qui ne sont pas explicitement définis par le serveur de collecte de données à une requête en attente.

<!-- 

r_dil_custom_query_params.xml

 -->

**** Signature de fonction : `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Vous pouvez lier d’autres appels d’API à cette méthode.

**Clés de requête réservées**

Les clés de requête suivantes sont réservées et ne peuvent pas être remplacées par cette méthode :

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Réponse**

Renvoie l’objet API de l’instance DIL active.

**Exemple de code**

<pre><code>
var partnerObject = DIL.create({ partner : '<i>partner</i>', containerNSID: <i>NSID</i> }); 
partnerObject.api.customQueryParams({ nid: 54231, saisissez : 'default' }); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Renvoie la valeur du conteneur NSID pour l’ [!UICONTROL DIL] instance. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_container_nsid.xml

 -->

**** Signature de fonction : `dil.api.getContainerNSID: function () {}`

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
//Vérifiez le conteneur NSID var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Renvoie les données du journal d’événements triées chronologiquement sous la forme d’un tableau de chaînes. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_event_log.xml

 -->

**** Signature de fonction : `dil.api.getEventLog: function () {}`

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({, fichier : 'dil.js', message: 'Ceci est la première requête' });.signaux({ c_zdid: <i>1111</i> d_dma: '<i>default</i>' });.submit(); 
 
//Consultez le journal des messages var log = dataLib.api.getEventLog(); 
if (log &amp;&amp; log.length) { alert(log.join('\n')); 
else{ alert('No log messages'); 
}</code></pre>

## getPartner {#getpartner}

Renvoie le nom du partenaire pour une [!UICONTROL DIL] instance. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_partner.xml

 -->

**** Signature de fonction : `dil.api.getPartner: function () {}`

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>' containerNSID : <i>containerNSID</i> }); 
 
//Vérifiez le nom du partenaire var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Renvoie l’état de l’ [!UICONTROL DIL] instance active. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_state.xml

 -->

**** Signature de fonction : `dil.api.getState: function () {}`

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({, fichier : 'dil.js', message:'Ceci est la première requête' });.signaux({ c.zdid: <i>1111</i> d_dma: '<i>default</i>' });.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Contour objet de l’état = { en attenteRequest : {données<i>en attente pour un appel au serveur</i>}, otherRequestInfo:{ déclenchementQueue: [], déclenché : [], tir : false, erreur : [], reservedKeys : { sids : true, pdata : true, logdata : true, callback : true, postCallbackFn : true, useImageRequest : true, }, firstRequestHasFired : false, num_of_jsonp_response: 0, num_of_jsonp_errors : 0, num_of_img_response : 0, num_of_img_errors : 0 }, destinationPublishingInfo : { THROTLE_START: 3000, throttleTimerSet: false, id : ''destination_publishing_iframe_' + partenaire + '_' + containerNSID, url : (constantes.isHTTPS ? 'https://' : 'https://fast.') + partenaire + '.demdex.net/dest3.html?d_nsid=' + containerNSID + '#' + encodeURIComponent(document.location.href), iframe: null, iframeHasLoaded : false, sendMessages : false, messages : [], messageSendingInterval : constantes.POST_MESSAGE_ENABLED ? 15 : 100, //Recommander 100 ms pour IE 6 et 7, 15 ms pour les autres navigateurs jsonProcédé : [] } } */</code></pre>

## idSync {#idsync}

Comprend deux fonctions qui permettent aux partenaires de données d’échanger et de synchroniser les ID utilisateur entre eux et Audience Manager.

<!-- 

r_dil_idsync.xml

 -->

**Signature de fonction :**

Fonctionne avec [!UICONTROL DIL] les versions 2.10 et 3.1 ou ultérieures.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code </th> 
   <th colname="col2" class="entry"> Synchronise les identifiants des utilisateurs </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Entre différents partenaires de données et Audience Manager. Par exemple, le partenaire x utiliserait cette fonction pour synchroniser un ID utilisateur avec le partenaire y, puis l’enverrait à Audience Manager. </p> <p> <p><b></b> Important :  Cette méthode est obsolète. Utilisez la méthode <code> idSyncByURL </code> de l’instance du service d’ID d’expérience. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Lorsque vous connaissez déjà l’ID utilisateur et souhaitez l’envoyer à Audience Manager. </p> <p> <p><b></b> Important :  Cette méthode est obsolète. Utilisez la méthode <code> idSyncByDataSource </code> de l’instance du service d’ID d’expérience. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Eléments idSync**

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

* **`%TIMESTAMP%`** : Génère un horodatage (en millisecondes). Utilisé pour la mise en cache.
* **`%DID%`** : Insère l’identifiant Audience Manager de l’utilisateur.
* **`%HTTP_PROTO%`** : Définit le protocole de page ( `http` ou `https`).

**Réponse**

Les deux fonctions retournent `Successfully queued` si elles réussissent. Autrement, elles renvoient une chaîne contenant un message d’erreur.

**Exemple de code**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Enlève l’URL avec les macros remplacées par dilInstance.api.idSync({ dpid : '23', // doit être une URL de chaîne : '//su.addthis.com/red/usync?pid=16&amp;puid=%DID%&amp;url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net %2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D%7D', minutes Live : 20160 // facultatif, 2 0160 minutes par défaut (14 jours) });
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Enflamme 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&amp;dpuuid=&lt;dpuuid&gt;' dilInstance.api.aamIdSync({ dpid: '23', // doit être une chaîne dpuuid : '98765', // doit être une chaîne minutesToLive: 20160 // facultatif, 2 0160 minutes par défaut (14 jours) });
</code></pre>

>[!MORE_LIKE_This]
>
>* [Fonctions de synchronisation dans le service d’ID Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsync.html)


## result {#result}

Ajoute un rappel (qui reçoit JSON) à la requête en attente.

<!-- 

r_dil_result.xml

 -->

**** Signature de fonction : `result: function (callback) {}`

Ce rappel remplace le rappel par défaut qui gère la publication de destination.

>[!NOTE]
>
>Vous pouvez lier d’autres appels d’API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `callback` | Fonction | Fonction JavaScript exécutée par le rappel JSONP. |

**Réponse**

Renvoie l’objet API de l’ [!UICONTROL DIL] instance active.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner : '<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ //Faites quelque chose, éventuellement avec les données JSON renvoyées par le serveur. 
});.submit();
</code></pre>

##  secureDataCollection {#securedatacollection}

`secureDataCollection` est un paramètre booléen qui contrôle la manière dont [!UICONTROL DIL] effectue des appels vers le [!UICONTROL Data Collection Servers (DCS)] et Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Lorsque `secureDataCollection= true` (par défaut), [!UICONTROL DIL] sécurise toujours les appels HTTPS.

* Lorsque `secureDataCollection= false`, [!UICONTROL DIL] effectue des appels HTTP ou HTTPS en suivant le protocole de sécurité défini par la page.

>[!IMPORTANT]
>
>Définissez `secureDataCollection= false` si vous utilisez visitorAPI.js et [!UICONTROL DIL] sur la même page. Consultez l’exemple de code ci-dessous.

<pre><code class="js">
var dilInstance = DIL.create({ ... 
     secureDataCollection : false });
</code></pre>

>[!MORE_LIKE_This]
>
>* [Création DIL](../dil/dil-class-overview/dil-create.md#dil-create)


## useCORSOnly {#usecorsonly}

`useCORSOnly` est un paramètre booléen vrai/faux qui contrôle la manière dont le navigateur demande des ressources à d’autres domaines.

<!-- 

dil-use-cors-only.xml

 -->

**Aperçu**

`useCORSOnly` est définie sur false par défaut. False signifie que le navigateur peut effectuer des contrôles de ressources avec CORS ou JSONP. Cependant, [!UICONTROL DIL] toujours essayer de demander des ressources avec CORS en premier. Il revient à JSONP sur les navigateurs plus anciens qui ne prennent pas en charge CORS. Si vous devez forcer le navigateur à utiliser uniquement CORS, par exemple pour les sites présentant des exigences de sécurité élevées, définissez `useCORSOnly:true`.

**Exemple de code**

<pre><code class="js">
var dilInstance = DIL.create({ ... 
     useCORSOnly : true });
</code></pre>

>[!IMPORTANT]
>
>* Nous vous recommandons de définir `useCORSOnly: true` uniquement lorsque vous êtes certain que les visiteurs de votre site disposent de navigateurs prenant en charge cette fonctionnalité.
>* Quand `useCORSOnly: true`, [!UICONTROL DIL] n’effectuera pas d’appels d’ID depuis Internet Explorer version 9 ou ultérieure.
>



>[!MORE_LIKE_This]
>
>* [Création DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Service d’ID Experience Cloud : UseCORSOnly](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-use-cors-only.html)
>* [Prise en charge de CORS dans le service Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-cors.html)


## useImageRequest {#useimagerequest}

Modifie le type de requête en image `<img>` à partir du script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**** Signature de fonction : `useImageRequest: function () {}`

>[!NOTE]
>
>Vous pouvez lier d’autres appels d’API à cette méthode.

**Réponse**

Renvoie un objet API de l’ [!UICONTROL DIL] instance active.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ partner:'<i>partnerName</i>', containerNSID: <i>containerNSID</i> }); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

