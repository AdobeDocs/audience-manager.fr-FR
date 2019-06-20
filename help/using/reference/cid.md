---
description: Mettez à jour votre code pour utiliser d_ cid ou d_ cid_ ic au lieu d_ dpid et d_ dpuuid. Les variables DPID et DPUUID continueront à fonctionner, mais vous devez les considérer comme obsolètes. Cela inclut les variantes DPID et DPUUID sans le préfixe d_.
seo-description: Mettez à jour votre code pour utiliser d_ cid ou d_ cid_ ic au lieu d_ dpid et d_ dpuuid. Les variables DPID et DPUUID continueront à fonctionner, mais vous devez les considérer comme obsolètes. Cela inclut les variantes DPID et DPUUID sans le préfixe d_.
seo-title: CID remplace DPID et DPUUID
solution: Audience Manager
title: CID remplace DPID et DPUUID
uuid: 3641 eac 5-b 19 e -45 d 5-bc 1 c -35 a 23 b 4 bab 8 c
translation-type: tm+mt
source-git-commit: cb3819192c523f9c20e9a15ca5d43ef36c49e900

---


# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

Update your code to use `d_cid` or `d_cid_ic` instead of `d_dpid` and `d_dpuuid`. Les variables DPID et DPUUID continueront à fonctionner, mais vous devez les considérer comme obsolètes. This includes DPID and DPUUID variants without the `d_ prefix`.

## DPID and DPUUID: A Review {#dpid-dpuuid-review}

DPID et DPUUID sont des paires clé-valeur qui contiennent un identifiant de fournisseur de données et un utilisateur - id. Ces paires de clés-valeurs de valeurs clés sont des identifiants de fournisseur à l&#39;utilisateur - id. Elles envoient des données lors des appels d&#39;événement, pour les événements de synchronisation entrants et pour les appels d&#39;ID. Without them, [!DNL Audience Manager], and other services or features, would not have a way to match and synchronize IDs. These variables are sometimes expressed with or without the `d_` prefix as shown below. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntaxe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifiant du fournisseur de données (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_ dpid =<i>ID du fournisseur de données</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid =<i>ID du fournisseur de données</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisateur unique du fournisseur de données - id (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_ dpuuid =<i>user provider unique user - id</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid =<i>user provider unique user - id</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Ces paires clé-valeur fonctionnent toujours, mais elles sont obsolètes. Vous devez mettre à jour votre code pour utiliser CID ou CID_ IC à la place.

## CID and CID_IC: About {#cid-cidic-about}

Les paires CID et CID_ IC sont remplacées par DPID et DPUUID. Elles fournissent les mêmes fonctions que DPID et DPUUID, mais elles sont plus efficaces car elles incluent l&#39;identifiant de fournisseur de données (ou le code d&#39;intégration) et l&#39;utilisateur - id dans une paire clé-valeur unique. Dans chaque paire clé-valeur :

* Le symbole = sépare la clé de ses valeurs associées.
* Le caractère ASCII non imprimable % 01 sépare les valeurs.

`d_cid` et `d_cid_ic` utilisez la syntaxe illustrée ci-dessous. Note, in the code, *italics* indicates a variable placeholder.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntaxe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID client (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid =<i>ID du fournisseur de données</i>% 01<i>user - id</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code d'intégration de l'ID client (CID_ IC) </p> </td> 
   <td colname="col2"> <p> <code>d_ cid_ ic =<i>code d'intégration</i>% 01<i>user - id</i></code> </p> <p> An <span class="term"> integration code</span> is an alternate ID you can use instead of the Data Source ID, assigned by <span class="keyword"> Audience Manager</span>. See <a href="../features/manage-datasources.md#create-data-source"> Create a Data Source</a> if you need to configure an integration code. </p> </td> 
  </tr> 
 </tbody> 
</table>

See also, [URL Variables and Syntax for Declared IDs](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>You can use integration codes for your own data sources and for global [shared data sources](../features/datasources-list-and-settings.md#settings-menu-options), which you have access to. Par exemple, vous pouvez utiliser des codes d&#39;intégration lorsque vous travaillez avec des sources de données d&#39;identifiants mobiles. Utilisez les codes d&#39;intégration suivants, exactement comme indiqué ci-dessous :

* **DSID_ 20914** pour GAID, qui représente les périphériques exécutant le système d&#39;exploitation Android.
* **DSID_ 20915** pour IDFA, représentant les périphériques exécutant le système d&#39;exploitation ios.

**Exemples**

Le tableau suivant fournit des exemples par type d&#39;événement.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’événement </th> 
   <th colname="col2" class="entry"> Exemple </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Événement </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">New: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Deprecated: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Synchronisation inbound (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">New: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Deprecated: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Générer UUID d'Audience Manager (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">New: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Deprecated: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Each call can also include multiple `d_cid` and `d_cid_ic` key value pairs like this:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Important Considerations for Development Teams {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Élément </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Codage URL </p> </td> 
   <td colname="col2"> <p>Your development teams <i>must</i> apply URL encoding to the following variables in the CID key-value pair: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user - id</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Note: You must URL encode the user ID and integration code <i>before</i> concatenating them into a string. Ceci est dû au fait que le caractère ASCII % 01 qui sépare les deux variables ne doit pas être capturé dans le codage d'URL. </p> </p> <p>L'encodage URL garantit que votre utilisateur - les identifiants et les codes d'intégration contenant des caractères réservés ou non sûrs tels que, mais pas seulement, + ou = sont transmis correctement à nos serveurs. </p> <p>Use the <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII encoding table</a> for reference. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisation de codes d'intégration pour les sources de données partagées globales </p> </td> 
   <td colname="col2"> <p>You can use integration codes for your own data sources and for global <a href="../features/datasources-list-and-settings.md#settings-menu-options"> shared data sources</a>, which you have access to. Par exemple, vous pouvez utiliser des codes d'intégration lorsque vous travaillez avec des sources de données d'identifiants mobiles. Utilisez les codes d'intégration suivants, exactement comme indiqué ci-dessous : </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_ 20914</b> pour GAID, qui représente les périphériques exécutant le système d'exploitation Android. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_ 20915</b> pour IDFA, représentant les périphériques exécutant le système d'exploitation ios. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

