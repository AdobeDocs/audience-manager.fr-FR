---
description: Commencez ici pour plus d'informations sur la réalisation d'appels /event au serveur de collecte de données. Cette section contient des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de demande.
seo-description: Commencez ici pour plus d'informations sur la réalisation d'appels /event au serveur de collecte de données. Cette section contient des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de demande.
seo-title: Envoi de données au serveur de collecte de données
solution: Audience Manager
title: Envoi de données au serveur de collecte de données
uuid: 024 e 307 d-bfcb -46 cf-ac 3 a-fc 71 df 0248 fe
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Envoi de données au serveur de collecte de données {#send-data-to-the-dcs}

Commencez ici pour plus d'informations sur la réalisation `/event` d'appels à [!UICONTROL DCS]la fonction. Cette section contient des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de demande.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Remplacez la valeur réelle de l'espace réservé lorsque vous envoyez des données à [!UICONTROL DCS] l'aide de cette méthode.

## Syntaxe d'appel {#dcs-call-syntax}

Chaîne de base `URL` qui envoie les données aux [!UICONTROL DCS] utilisations de la syntaxe illustrée ci-dessous.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Vous pouvez également envoyer des données à l [!UICONTROL DCS] 'aide de la `POST` méthode. La syntaxe d'appel est décrite dans [les méthodes API de DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Paramètres d'appel {#dcs-call-parameters}

Le tableau suivant définit les composants de base d'un appel simple [!UICONTROL DCS] .

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Alias de domaine attribué par <span class="keyword"> Audience Manager</span> (par ex. <code> mon_ domaine. demdex. net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Domaine de destination, toujours <code> demdex. net</code>. Voir <a href="../../../reference/demdex-calls.md">Signification des appels vers le domaine Demdex</a> (Understanding Calls to the Demdex Domain). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l'appel : </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifie l'appel comme appel d'événement. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Définit le début de la chaîne URL qui contient les données que vous souhaitez envoyer au <span class="wintitle"> serveur de collecte de données</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Identifiant unique dans la paire clé-valeur. </p> <p>Ces paires clé-valeur utilisent un préfixe spécifique pour identifier le type de données que vous envoyez au <span class="wintitle"> serveur de collecte de données</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Valeur de variable appartenant à un jeu défini par une clé dans la paire clé-valeur. </p> <p>Lorsque vous travaillez avec des valeurs : </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Placez les données de chaîne en guillemets doubles ( <code> ex. : age = "41 à 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Vous pouvez transmettre plusieurs clés dans une seule valeur (par ex. <i><code>clé</i>=<i>val 1, val 2, val 3</i></code></i>). </i></li> 
     </ul> </p> <p>Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatage des paires clé-valeur dans les appels DCS.</a> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_ cb =<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Paramètres de réponse facultatifs. </p> <p> Aucun d'eux n'est nécessaire pour envoyer des données au <span class="wintitle"> serveur de collecte de données</span>. Toutefois, si vous souhaitez que <span class="wintitle"> le serveur de collecte de données</span> renvoie une réponse, vous devez inclure <code> d_ rtbd = json</code> dans votre requête. </p> <p>Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> Paires d_ clé-valeur définies</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Exemple d'appel {#dcs-sample-call}

Cet exemple montre la société fictive [!DNL Acme, Inc.] qui envoie des données à la [!UICONTROL DCS] suite d' [!DNL HTTP] un appel. Notez que cet appel comprend les paramètres `d_dst=1`facultatifs, `d_rtbd=json`et `d_cb=callback`. Ces informations indiquent qu' [!DNL Acme] il souhaite recevoir [!DNL JSON] une réponse de la [!UICONTROL DCS] fonction avec une fonction de retour. N'oubliez pas que ce n'est qu'un exemple. Ne coupez pas ce code et ne le collez pas.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```
## Étapes suivantes {#dcs-next-steps}

Maintenant que vous êtes familiarisé avec l'envoi de données à la [!UICONTROL DCS], il est temps de savoir comment récupérer les données et analyser ces informations. Voir [Réception des données du serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORE_ LIKE_ THIS]
>
>* [Paires clé-valeur expliquées](../../../reference/key-value-pairs-explained.md)

