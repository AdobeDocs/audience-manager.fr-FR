---
description: Les API de DIL au niveau de l’instance vous permettent de créer et d’utiliser des objets d’Audience Manager par programmation. Les méthodes au niveau de l’instance améliorent la fonctionnalité de l’API établie par les méthodes au niveau de la classe.
keywords: créer des caractéristiques, créer une caractéristique
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: Méthodes DIL au niveau de l’instance
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 13%

---

# Méthodes DIL au niveau de l’instance{#instance-level-dil-methods}

>[!WARNING]
>
>Depuis juillet 2023, l’Adobe a cessé de développer la [!DNL Data Integration Library (DIL)] et la variable [!DNL DIL] extension .
>
>Les clients existants peuvent continuer à utiliser leurs [!DNL DIL] implémentation. Cependant, l’Adobe ne se développera pas. [!DNL DIL] au-delà de ce point. Les clients sont encouragés à évaluer [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent mettre en oeuvre de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) au lieu de .

Au niveau de l’instance [!UICONTROL DIL] Les API vous permettent de créer et d’utiliser des objets d’Audience Manager par programmation. Les méthodes au niveau de l’instance améliorent la fonctionnalité de l’API établie par les méthodes au niveau de la classe.

## Prise en main des méthodes de DIL au niveau de l’instance {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Lorsque vous utilisez l’instance [!UICONTROL DIL] API :

* L’accès nécessite un nom de partenaire et un identifiant d’espace de noms de conteneur (NSID). Contactez votre gestionnaire de compte d’Audience Manager pour obtenir ces informations.
* Remplacer un exemple *italicized* texte dans la documentation de l’API avec la valeur, l’identifiant ou une autre variable, comme requis par la méthode que vous utilisez.

<!-- 

c_instance_start.xml

 -->

## signals {#signals}

Ajoute des mappages au niveau du client et de la plateforme à la chaîne de requête d’une requête en attente.

<!-- 

r_dil_signals.xml

 -->

**Signature de fonction :** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* Vous pouvez associer d’autres appels API à cette méthode.
>* Si la bibliothèque JavaScript Adobe Experience Cloud se trouve sur la page, `submit()` attend que le cloud définisse un cookie avant d’envoyer une demande.

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
| `obj` | Objet | Objet représentant les paires clé-valeur pour les mappages au niveau de la plateforme. Le paramètre accepte les chaînes et les tableaux en tant que valeurs de propriété dans l’objet . |
| `prefix` | Chaîne | Facultatif. La valeur string préfixée à chaque clé d’objet (remplace la clé d’origine). |
| `return` | DIL.api | Renvoie l’objet API de l’instance de DIL actuelle. |

**Réponse**

Renvoie l’objet API du [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## traits {#traits}

Ajoute des SID à la chaîne de requête d’une requête en attente.

<!-- 

r_dil_traits.xml

 -->

**Signature de fonction :** `traits:function (sids){}`

>[!NOTE]
>
>Vous pouvez associer d’autres appels API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `sids` | Tableau | Identifiants de segment de caractéristiques dans un tableau. |

**Réponse**

Renvoie l’objet API du [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Ajoutez des données aux fichiers journaux dans la requête en attente.

<!-- 

r_dil_logs.xml

 -->

**Signature de fonction :** `logs: function {key1:value1, key2:value2}`

**Réponse**

Renvoie l’objet API du [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## submit {#submit}

Envoie toutes les données en attente à l’Audience Manager pour le [!UICONTROL DIL] instance.

<!-- 

r_dil_submit.xml

 -->

**Signature de fonction :** `submit: function () {}`

>[!NOTE]
>
>Vous pouvez associer d’autres appels API à cette méthode. En outre, [!UICONTROL DIL] écrit des données codées dans un cookie de destination. Par exemple, les espaces sont codés comme `%20` et points-virgules comme `%3B`.

**Réponse**

Renvoie l’objet API du [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

Fonction qui s’exécute après le rappel de publication de destination par défaut.

<!-- 

r_dil_after_result.xml

 -->

**Signature de fonction :** `afterResult: function (fn) {}`

>[!NOTE]
>
>Vous pouvez associer d’autres appels API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `fn` | Fonction | La fonction que vous souhaitez exécuter après le traitement de JSON par le rappel par défaut qui traite la publication de destination. |

**Réponse**

Renvoie un objet API de l’objet actif [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

Efface toutes les données d’une requête en attente.

<!-- 

r_dil_clear_data.xml

 -->

**Signature de fonction :** `clearData: function () {}`

>[!NOTE]
>
>Vous pouvez associer d’autres appels API à cette méthode.

**Réponse**

Renvoie l’objet API du [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Ajoute des paramètres de requête personnalisés qui ne sont pas explicitement définis par le serveur de collecte de données à une requête en attente.

<!-- 

r_dil_custom_query_params.xml

 -->

**Signature de fonction :** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>Vous pouvez associer d’autres appels API à cette méthode.

**Clés de requête réservées**

Les clés de requête suivantes sont réservées et ne peuvent pas être remplacées par cette méthode :

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Réponse**

Renvoie l’objet API de l’instance de DIL actuelle.

**Exemple de code**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Renvoie la valeur du conteneur NSID pour la variable [!UICONTROL DIL] instance. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Signature de fonction :** `dil.api.getContainerNSID: function () {}`

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Renvoie les données du journal des événements triées chronologiquement sous la forme d’un tableau de chaînes. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_event_log.xml

 -->

**Signature de fonction :** `dil.api.getEventLog: function () {}`

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

Renvoie le nom du partenaire pour un [!UICONTROL DIL] instance. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_partner.xml

 -->

**Signature de fonction :** `dil.api.getPartner: function () {}`

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Renvoie l’état du [!UICONTROL DIL] instance. Utile pour le débogage et le dépannage.

<!-- 

r_dil_get_state.xml

 -->

**Signature de fonction :** `dil.api.getState: function () {}`

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

Comprend deux fonctions qui permettent aux partenaires de données d’échanger et de synchroniser les identifiants utilisateur entre eux et entre les Audiences Manager.

<!-- 

r_dil_idsync.xml

 -->

**Signature de fonction :**

fonctionne avec [!UICONTROL DIL] versions 2.10 et 3.1 ou ultérieures.

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
   <td colname="col2"> <p>Entre différents partenaires de données et Audience Manager. Par exemple, le partenaire x l’utilise pour synchroniser un identifiant utilisateur avec le partenaire y, puis l’envoie à l’Audience Manager. </p> <p> <p><b>Important :</b>  Cette méthode est obsolète. Veuillez utiliser la variable <code> idSyncByURL </code> de l’instance de service Adobe Experience Platform Identity. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Lorsque vous connaissez déjà l’identifiant utilisateur et souhaitez l’envoyer à l’Audience Manager. </p> <p> <p><b>Important :</b>  Cette méthode est obsolète. Veuillez utiliser la variable <code> idSyncByDataSource </code> de l’instance de service Adobe Experience Platform Identity. </p> </p> </td> 
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
   <td colname="col3"> <p>L’ID unique du fournisseur de données pour l’utilisateur. </p> </td> 
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
* **`%DID%`:** Insère l’ID d’Audience Manager de l’utilisateur.
* **`%HTTP_PROTO%`:** Définit le protocole de la page ( `http` ou `https`).

**Réponse**

Les deux fonctions renvoient `Successfully queued` en cas de réussite. Autrement, elles renvoient une chaîne contenant un message d’erreur.

**Exemple de code**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## result {#result}

Ajoute un rappel (qui reçoit JSON) à la requête en attente.

<!-- 

r_dil_result.xml

 -->

**Signature de fonction :** `result: function (callback) {}`

Ce rappel remplace le rappel par défaut qui gère la publication de destination.

>[!NOTE]
>
>Vous pouvez associer d’autres appels API à cette méthode.

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `callback` | Fonction | Fonction JavaScript exécutée par le rappel JSONP. |

**Réponse**

Renvoie l’objet API du [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` est un paramètre booléen qui contrôle la manière dont [!UICONTROL DIL] effectue des appels à la fonction [!UICONTROL Data Collection Servers (DCS)] et Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* When `secureDataCollection= true` (par défaut), [!UICONTROL DIL] effectue toujours des appels HTTPS sécurisés.

* When `secureDataCollection= false`, [!UICONTROL DIL] effectue des appels HTTP ou HTTPS en suivant le protocole de sécurité défini par la page.

>[!IMPORTANT]
>
>Définir `secureDataCollection= false` si vous utilisez visitorAPI.js et [!UICONTROL DIL] sur la même page. Consultez l’exemple de code ci-dessous.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` est un paramètre booléen true/false qui contrôle la manière dont le navigateur demande des ressources à d’autres domaines.

<!-- 

dil-use-cors-only.xml

 -->

**Présentation**

`useCORSOnly` est définie sur false par défaut. False signifie que le navigateur peut effectuer des vérifications de ressources avec CORS ou JSONP. Cependant, [!UICONTROL DIL] essaie toujours de demander des ressources avec CORS en premier. Il revient à JSONP sur les navigateurs plus anciens qui ne prennent pas en charge CORS. Si vous devez forcer le navigateur à utiliser uniquement la norme CORS, par exemple pour les sites qui ont des exigences de sécurité élevées, définissez `useCORSOnly:true`.

**Exemple de code**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* Nous vous recommandons de définir `useCORSOnly: true` uniquement lorsque vous êtes certain que les visiteurs de votre site disposent de navigateurs prenant en charge cette fonctionnalité.
>* When `useCORSOnly: true`, [!UICONTROL DIL] n’effectuera pas d’appels d’ID à partir d’Internet Explorer version 9 ou antérieure.
>

## useImageRequest {#useimagerequest}

Modifie le type de demande en image. `<img>` à partir du script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Signature de fonction :** `useImageRequest: function () {}`

>[!NOTE]
>
>Vous pouvez associer d’autres appels API à cette méthode.

**Réponse**

Renvoie un objet API de l’objet actif [!UICONTROL DIL] instance.

**Exemple de code**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Exigences de nom pour les variables clés](../features/traits/trait-key-name-requirements.md)
>* [Exigences de préfixe pour les variables clés](../features/traits/trait-variable-prefixes.md)
>* [Fonctions de synchronisation dans le service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [Création DIL](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Service Adobe Experience Platform Identity : UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [Prise en charge de la norme CORS dans le service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
