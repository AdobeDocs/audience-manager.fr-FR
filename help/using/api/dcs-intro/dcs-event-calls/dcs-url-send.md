---
description: Commencez ici pour plus d’informations sur l’émission d’appels /event au serveur de collecte de données. Cette section contient des informations sur la syntaxe de l’appel, les paramètres, la mise en forme et un exemple de requête.
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: Envoyer des données au serveur de collecte de données
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---

# Envoyer des données au serveur de collecte de données {#send-data-to-the-dcs}

Commencez ici pour plus d’informations sur la manière d’effectuer des appels `/event` au [!DNL DCS] . Cette section contient des informations sur la syntaxe de l’appel, les paramètres, la mise en forme et un exemple de requête.

>[!NOTE]
>
>Dans le code et les exemples, l’*italique* représente un espace réservé de variable. Remplacez l’espace réservé par une valeur réelle lorsque vous envoyez des données au [!DNL DCS] à l’aide de cette méthode.

## Syntaxe de l&#39;appel {#dcs-call-syntax}

Une chaîne de `URL` de base qui envoie des données à l’[!DNL DCS] utilise la syntaxe présentée ci-dessous.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>Vous pouvez également envoyer des données au [!DNL DCS] à l’aide de la méthode `POST` . La syntaxe de l’appel est décrite dans [Méthodes de l’API DCS](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Paramètres d’appel {#dcs-call-parameters}

Le tableau suivant définit les composants de base d’un appel [!DNL DCS] simple.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Alias de domaine attribué par <span class="keyword"> Audience Manager</span> (par exemple, <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Le domaine de destination, toujours <code> demdex.net</code>. Voir <a href="../../../reference/demdex-calls.md"> Signification des appels vers le domaine Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l’appel : </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifie l’appel comme un appel d’événement. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Définit le début de la chaîne d’URL qui contient les données à envoyer au <span class="wintitle"> DCS</span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Identifiant unique dans la paire clé-valeur. </p> <p>Ces paires clé-valeur utilisent un préfixe spécifique pour identifier le type de données que vous envoyez au <span class="wintitle"> DCS</span>. Pour plus d’informations, voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> des attributs pris en charge pour les appels API DCS</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Valeur de variable appartenant à un ensemble défini par une clé dans la paire clé-valeur. </p> <p>Lorsque vous utilisez des valeurs : </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Placez les données de chaîne entre guillemets doubles (par exemple, <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">Vous pouvez transmettre plusieurs clés sur une seule valeur (par exemple, <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Voir Formatage <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> des paires clé-valeur dans les appels DCS</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Paramètres de réponse facultatifs. </p> <p> Aucun de ces éléments n’est nécessaire pour envoyer des données au <span class="wintitle"> DCS</span>. Cependant, si vous souhaitez que le <span class="wintitle"> DCS</span> renvoie une réponse, vous devez inclure <code> d_rtbd=json</code> dans votre requête. </p> <p>Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> Paires Clé-Valeur D_ Définies</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Exemple d’appel {#dcs-sample-call}

Cet exemple montre la société fictive [!DNL Acme, Inc.] envoyant des données au [!DNL DCS] via un appel [!DNL HTTP]. Notez que cet appel inclut les paramètres facultatifs `d_dst=1`, `d_rtbd=json` et `d_cb=callback`. Elles indiquent que [!DNL Acme] souhaitez recevoir une réponse [!DNL JSON] de la [!DNL DCS] avec une fonction d’appel. N&#39;oubliez pas que ce n&#39;est qu&#39;un exemple. Ne coupez pas et ne collez pas ce code.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Étapes suivantes {#dcs-next-steps}

Maintenant que vous connaissez l’envoi de données au [!DNL DCS], il est temps d’examiner comment récupérer les données et analyser ces informations. Voir [ Recevoir des données du serveur de collecte de données ](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Explication des paires clé-valeur](../../../reference/key-value-pairs-explained.md)
