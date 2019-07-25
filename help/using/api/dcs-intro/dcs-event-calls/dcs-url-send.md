---
description: Commencez ici pour plus d'informations sur la réalisation d'appels /event au serveur de collecte de données. Cette section contient des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de demande.
seo-description: Commencez ici pour plus d'informations sur la réalisation d'appels /event au serveur de collecte de données. Cette section contient des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de demande.
seo-title: Envoi de données au serveur de collecte de données
solution: Audience Manager
title: Envoi de données au serveur de collecte de données
uuid: 024 e 307 d-bfcb -46 cf-ac 3 a-fc 71 df 0248 fe
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Send Data to the DCS {#send-data-to-the-dcs}

Start here for information about making `/event` calls to the [!UICONTROL DCS]. Cette section contient des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de demande.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you send data to the [!UICONTROL DCS] with this method.

## Call Syntax {#dcs-call-syntax}

A basic `URL` string that sends data to the [!UICONTROL DCS] uses the syntax shown below.

<pre><code>https://domain alias.demdex.net/event<i></i>?<i>key 1</i>=<i>val 1</i>, &amp;<i>key 2</i>=<i>val 2</i>&amp; d_ dst = 1 &amp; d_ rtbd = json &amp; d_ cb =<i>callback</i></code>
</pre>

>[!NOTE]
>
>You can also send data to the [!UICONTROL DCS] by using the `POST` method. The call syntax is described in [DCS API Methods](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Call Parameters {#dcs-call-parameters}

The following table defines the basic components of a simple [!UICONTROL DCS] call.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Composant </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> alias de domaine. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l'appel contient : </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Your domain alias assigned by <span class="keyword"> Audience Manager</span> (e.g., <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <code> demdex.net</code>. Voir <a href="../../../reference/demdex-calls.md">Signification des appels vers le domaine Demdex</a> (Understanding Calls to the Demdex Domain). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l'appel : </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifie l'appel comme appel d'événement. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Defines the start of the URL string that contains the data you want to send to the <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Identifiant unique dans la paire clé-valeur. </p> <p>These key-value pairs use a specific prefix to identify the type of data you're sending to the <span class="wintitle"> DCS</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Valeur de variable appartenant à un jeu défini par une clé dans la paire clé-valeur. </p> <p>Lorsque vous travaillez avec des valeurs : </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Enclose string data in double quotes (e.g., <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">You can pass multiple keys in on a single value (e.g., <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </i></li> 
     </ul> </p> <p>See <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatting Key-Value Pairs in DCS Calls</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb =<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Paramètres de réponse facultatifs. </p> <p> None of these are required to send data to the <span class="wintitle"> DCS</span>. However, if you want the <span class="wintitle"> DCS</span> to return a response, you must include <code> d_rtbd=json</code> in your request. </p> <p>See <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Value Pairs Defined</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Sample Call {#dcs-sample-call}

This example shows the fictional company [!DNL Acme, Inc.] sending data to the [!UICONTROL DCS] via an HTTP call. Note that this call includes the optional parameters `d_dst=1`, `d_rtbd=json`, and `d_cb=callback`. These indicate that [!DNL Acme] wants to receive a [!DNL JSON] response from the [!UICONTROL DCS] with a call back function. N'oubliez pas que ce n'est qu'un exemple. Ne coupez pas ce code et ne le collez pas.

`https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback`

## Étapes suivantes {#dcs-next-steps}

Now that you're familiar with sending data to the [!UICONTROL DCS], it's time to look at how to get data back from it and parse that information. See [Receive Data From the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORE_ LIKE_ THIS]
>
>* [Paires clé-valeur expliquées](../../../reference/key-value-pairs-explained.md)

