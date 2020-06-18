---
description: Début ici pour obtenir des informations sur l’envoi d’appels /événement au serveur de collecte de données. Cette section comprend des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de requête.
seo-description: Début ici pour obtenir des informations sur l’envoi d’appels /événement au serveur de collecte de données. Cette section comprend des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de requête.
seo-title: Envoyer des données au serveur de collecte de données
solution: Audience Manager
title: Envoyer des données au serveur de collecte de données
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 2%

---


# Envoyer des données au serveur de collecte de données {#send-data-to-the-dcs}

Début ici pour obtenir des informations sur les `/event` appels au [!DNL DCS]. Cette section comprend des informations sur la syntaxe des appels, les paramètres, la mise en forme et un exemple de requête.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Remplacez une valeur réelle pour l’espace réservé lorsque vous envoyez des données à la [!DNL DCS] méthode par cette dernière.

## Syntaxe de l’appel {#dcs-call-syntax}

Une `URL` chaîne de base qui envoie des données à la [!DNL DCS] utilise la syntaxe illustrée ci-dessous.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Vous pouvez également envoyer des données à l’ [!DNL DCS] utilisateur à l’aide de la `POST` méthode. La syntaxe des appels est décrite dans Méthodes [d’API](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)DCS.

## Paramètres d’appel {#dcs-call-parameters}

Le tableau suivant définit les composants de base d’un [!DNL DCS] appel simple.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Composant </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l'appel contient : </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Votre alias de domaine attribué par <span class="keyword"> Audience Manager</span> (par ex. <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Le domaine de destination, qui est toujours <code> demdex.net</code>défini. Voir <a href="../../../reference/demdex-calls.md">Signification des appels vers le domaine Demdex</a> (Understanding Calls to the Demdex Domain). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l'appel : </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifie l’appel en tant qu’appel événement. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Définit le début de la chaîne URL qui contient les données à envoyer au <span class="wintitle"> serveur de collecte de données</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Identificateur unique dans la paire clé-valeur. </p> <p>Ces paires clé-valeur utilisent un préfixe spécifique pour identifier le type de données que vous envoyez au <span class="wintitle"> serveur de collecte de données</span>. For more information, see <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Supported Attributes for DCS API Calls</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Valeur de variable appartenant à un jeu défini par une clé dans la paire clé-valeur. </p> <p>Lorsque vous utilisez des valeurs : </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Placez les données de chaîne entre guillemets de doublon (par exemple <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Vous pouvez transmettre plusieurs clés sur une seule valeur (par exemple <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatage de paires clé-valeur dans les appels</a>DCS. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Paramètres de réponse facultatifs. </p> <p> Aucune de ces méthodes n’est nécessaire pour envoyer des données au <span class="wintitle"> serveur de collecte de données</span>. Cependant, si vous souhaitez que le serveur de collecte de données <span class="wintitle"> renvoie une réponse, vous devez inclure</span> <code> d_rtbd=json</code> dans votre demande. </p> <p>Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Paires de valeurs clés définies</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Exemple d’appel {#dcs-sample-call}

Cet exemple montre la société fictive [!DNL Acme, Inc.] envoyant des données à la [!DNL DCS] suite d&#39;un [!DNL HTTP] appel. Notez que cet appel comprend les paramètres facultatifs `d_dst=1`, `d_rtbd=json`et `d_cb=callback`. Elles indiquent que [!DNL Acme] souhaite recevoir une [!DNL JSON] réponse de la [!DNL DCS] fonction de rappel. Rappelez-vous, ce n&#39;est qu&#39;un exemple. Ne coupez pas et ne collez pas ce code.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Étapes suivantes {#dcs-next-steps}

Maintenant que vous connaissez l&#39;envoi de données à [!DNL DCS], il est temps de regarder comment récupérer les données et analyser ces informations. Voir [Réception de données à partir du serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Paires clé-valeur expliquées](../../../reference/key-value-pairs-explained.md)

