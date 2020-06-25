---
description: Mettez à jour votre code pour utiliser d_cid ou d_cid_ic au lieu de d_dpid et d_dpuuid. Les variables DPID et DPUUID continueront à fonctionner, mais vous devez les considérer comme obsolètes. Cela inclut les variantes DPID et DPUUID sans préfixe d_.
seo-description: Mettez à jour votre code pour utiliser d_cid ou d_cid_ic au lieu de d_dpid et d_dpuuid. Les variables DPID et DPUUID continueront à fonctionner, mais vous devez les considérer comme obsolètes. Cela inclut les variantes DPID et DPUUID sans préfixe d_.
seo-title: CID remplace DPID et DPUUID
solution: Audience Manager
title: CID remplace DPID et DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 2%

---


# CID Replaces DPID and DPUUID{#cid-replaces-dpid-and-dpuuid}

Mettez à jour votre code pour l’utiliser `d_cid` ou `d_cid_ic` au lieu de `d_dpid` et `d_dpuuid`. Les variables DPID et DPUUID continueront à fonctionner, mais vous devez les considérer comme obsolètes. Cela inclut les variantes DPID et DPUUID sans le `d_ prefix`.

## DPID et DPUUID : Une révision {#dpid-dpuuid-review}

Le DPID et le DPUUID sont des paires clé-valeur qui contiennent un ID de fournisseur de données et un ID d’utilisateur. Ces paires clé-valeur lient les ID du fournisseur à ceux de l’utilisateur. Ils envoient des données pendant les appels de événement, pour les événements de synchronisation entrants et pour les appels d’ID. Sans eux, [!DNL Audience Manager]ainsi que d’autres services ou fonctionnalités, n’auraient pas de moyen de faire correspondre et de synchroniser les identifiants. Ces variables sont parfois exprimées avec ou sans le `d_` préfixe, comme illustré ci-dessous. Remarque : dans le code, l’ *italique* indique une balise d’emplacement de variable.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Syntaxe </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID du fournisseur de données (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID utilisateur unique du fournisseur de données (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Ces paires clé-valeur fonctionnent toujours, mais elles sont obsolètes. Mettez à jour votre code pour utiliser CID ou CID_IC à la place.

## CID et CID_IC : A propos {#cid-cidic-about}

Les paires clé-valeur CID et CID_IC remplacent DPID et DPUUID. Ils offrent les mêmes fonctions que les DPID et DPUUID, mais sont plus efficaces car ils incluent l’ID du fournisseur de données (ou code d’intégration) et l’ID utilisateur dans une seule paire clé-valeur. Dans chaque paire clé-valeur :

* Le symbole = sépare la clé de ses valeurs associées.
* Le caractère ASCII non imprimable %01 sépare les valeurs.

`d_cid` et `d_cid_ic` utilisez la syntaxe illustrée ci-dessous. Remarque : dans le code, l’ *italique* indique une balise d’emplacement de variable.

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
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code d’intégration d’ID de client (CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> Un code <span class="term"></span> d’intégration est un autre ID que vous pouvez utiliser à la place de l’ID de source de données, attribué par <span class="keyword"> Audience Manager</span>. Voir <a href="../features/manage-datasources.md#create-data-source"> Création d’une source</a> de données si vous devez configurer un code d’intégration. </p> </td> 
  </tr> 
 </tbody> 
</table>

Voir aussi Variables [d’URL et Syntaxe pour les identifiants](../features/declared-ids.md#variables-and-syntax)déclarés.

>[!NOTE]
>
>Vous pouvez utiliser des codes d’intégration pour vos propres sources de données et pour les sources [de données](../features/datasources-list-and-settings.md#settings-menu-options)partagées globales, auxquelles vous avez accès. Par exemple, vous pouvez utiliser des codes d’intégration lorsque vous utilisez des sources de données d’identifiants mobiles. Utilisez les codes d’intégration suivants, exactement comme indiqué ci-dessous :

* **DSID_20914** pour GAID, représentant les périphériques exécutant le système d’exploitation Android.
* **DSID_20915** pour IDFA, représentant les périphériques exécutant le système d’exploitation iOS.

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
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">Nouvelle API: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Obsolète: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Synchronisation entrante (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">Nouvelle API: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Obsolète: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Générer un identifiant d’Audience Manager (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">Nouvelle API: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Obsolète: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Chaque appel peut également inclure plusieurs paires `d_cid` et `d_cid_ic` valeurs clés, comme celle-ci :

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Considérations importantes pour les équipes de développement {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Élément </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Codage de l’URL </p> </td> 
   <td colname="col2"> <p>Vos équipes de développement <i>doivent</i> appliquer le codage d’URL aux variables suivantes de la paire clé-valeur du CID : </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Remarque : Vous devez coder l’URL de l’ID utilisateur et du code d’intégration <i>avant</i> de les concaténer en chaîne. Cela est dû au fait que le caractère ASCII %01 qui sépare les deux variables ne doit pas être capturé dans l'encodage de l'URL. </p> </p> <p>Le codage d’URL garantit que vos ID utilisateur et codes d’intégration contenant des caractères réservés ou non sûrs, tels que, mais sans s’y limiter, + ou =, sont correctement transmis à nos serveurs. </p> <p>Utilisez la table <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> de codage</a> ASCII à titre de référence. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utilisation des codes d’intégration pour les sources de données partagées globales </p> </td> 
   <td colname="col2"> <p>Vous pouvez utiliser des codes d’intégration pour vos propres sources de données et pour les sources <a href="../features/datasources-list-and-settings.md#settings-menu-options"> de données</a>partagées globales, auxquelles vous avez accès. Par exemple, vous pouvez utiliser des codes d’intégration lorsque vous utilisez des sources de données d’identifiants mobiles. Utilisez les codes d’intégration suivants, exactement comme indiqué ci-dessous : </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> pour GAID, représentant les périphériques exécutant le système d’exploitation Android. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> pour IDFA, représentant les périphériques exécutant le système d’exploitation iOS. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

