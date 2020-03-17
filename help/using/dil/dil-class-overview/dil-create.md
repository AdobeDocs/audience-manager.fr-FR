---
description: Crée une instance DIL spécifique au partenaire.
seo-description: Crée une instance DIL spécifique au partenaire.
seo-title: Création DIL
solution: Audience Manager
title: Création DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Méthode de création DIL{#dil-create}

## Création DIL {#dil-create-new}

Crée une [!UICONTROL DIL] instance spécifique au partenaire.

**Signature de fonction :** `DIL.create: function (initConfig) {}`

**éléments initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La `visitorService` propriété est *toujours* requise. Les autres propriétés répertoriées ici sont facultatives, sauf indication contraire.

`initConfig` accepte les éléments suivants :

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Cette propriété définit l’identifiant du conteneur utilisé par <span class="keyword">Audience Manager</span> pour la synchronisation des identifiants. Vous pouvez définir <code> containerNSID </code> si le code DIL <span class="wintitle"> est </span> déployé sur plusieurs sites. Chacun de ces sites aura ses propres ID et ID de synchronisés. Lorsque vous ne disposez que d’un site, l’ID de  du est 0 par défaut et vous n’avez pas besoin de le définir correctement. Contactez votre consultant pour obtenir un de vos sites et de leurs ID de. </p> <p>Dans le <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> service d’identité Adobe Experience Platform </a>, la propriété <code> idSyncContainerID </code> correspond à <code> containerNSID </code> dans <span class="wintitle"> DIL </span>. Notez ce qui suit si vous utilisez <span class="wintitle"> DIL </span> <i></i> et le service d’ID sur plusieurs sites : </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Pour chaque site, définissez les mêmes ID de  de sur <code> containerNSID </code> et <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Le <span class="wintitle"> code DIL </span> et le service d’ID tentent tous deux d’envoyer des synchronisations d’ID à notre iFrame de collecte de données. Toutefois, l’iFrame garantit que <span class="wintitle"> DIL </span> ne déclenchera pas de synchronisation des identifiants. Cela évite les doubles emplois. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Seul <span class="wintitle"> le code DIL </span> envoie les données vers une destination <a href="../../features/destinations/destinations.md"> URL </a>. </li> 
     </ul> </p> <p>Voir aussi idSyncContainerID <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html" format="https" scope="external"> </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Envoie les variables <a href="../../features/declared-ids.md"> d’ID déclarés </a> à chaque appel de  de à <span class="keyword">  Gestionnaire de  de </span>. </p> 
    </draft-comment> <p> <code> delcaredId </code> est utilisée pour transmettre l’une des valeurs suivantes : </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID de partenaire de données qui vous a été attribué par  Gestionnaire de  de <span class="keyword"> </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Votre identifiant unique pour un utilisateur. </li> 
    </ul> <p> <p>Important :  Utilisez uniquement des valeurs non codées pour vos ID. Le codage crée des identifiants codés . </p> </p> <p> <p>Remarque :  Si vous utilisez le service d’identité de la plate-forme <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Adobe Experience Platform </a>, définissez les ID de client avec la <code> setCustomerIDs </code> méthode au lieu de <span class="wintitle"> DIL </span>. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Si la valeur est true, repousse l’exécution de toutes les requêtes (IFRAME, appels de , synchronisation des identifiants et destination) jusqu’à ce que l’ du <code> Page Load </code> se déclenche. La valeur par défaut est <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> False par défaut, ce qui signifie <span class="keyword"> Gestionnaire de  de </span> définit un cookie dans le domaine du partenaire (définit un cookie propriétaire). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important :  Cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publiée en août 2018). Utilisez plutôt la <code> visitor.disableIdSyncs </code> fonction <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> </a> dans le service d’identité Adobe Experience Platform. </p> </p> <p> Si <code> true </code>vous le souhaitez, ne joignez pas la publication de destination IFRAME au DOM ou aux destinations de feu. La valeur par défaut est <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important :  Cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publiée en août 2018). Utilisez plutôt la <code> visitor.disableIdSyncs </code> fonction <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-disableidsync.html" format="https" scope="external"> </a> dans le service d’identité Adobe Experience Platform. </p> </p> <p>Désactive la synchronisation des ID. Vous devez désactiver la synchronisation des identifiants lors de l’utilisation de DIL v6.2+ et du service d’ID de. La <code> visitorService </code> fonction (voir l’exemple de code ci-dessous) s’occupe de cette opération. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Définissez cette variable sur <code> true </code> pour activer les  d’erreur pour toutes les instances <span class="wintitle"> DIL </span> de la page. Fonctionne uniquement avec Boolean <code> true </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important :  Cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publiée en août 2018). Utilisez plutôt la <code> visitor.idSyncSSLUseAkamai </code> fonction <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idSyncSSLUseAkamai.html" format="https" scope="external"> </a> dans le service d’identité Adobe Experience Platform. </p> </p> <p> Indique si le modèle de publication de destination doit utiliser Akamai pour les connexions HTTPS. Activée par partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Associe la valeur d’une paire clé-valeur à une autre. Voir <a href="../../dil/dil-use-cases.md#map-key-values"> Association des valeurs clés aux autres clés </a>. Publié avec v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Obligatoire. </p> <p>La paire <code> namespace </code> clé-valeur contient votre <span class="keyword"> ID d’organisation Experience Cloud </span> . Si vous ne possédez pas cet ID, vous pouvez le trouver dans la <span class="wintitle"> section </span> Administration du <span class="keyword"> d’ </span> Experience Cloud. Vous avez besoin d’autorisations d’administrateur pour  cet  de. Voir les FAQ sur les fonctionnalités et les fonctionnalités <a href="../../faq/faq-features.md"> du produit </a> et <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> Administration - Gestion des utilisateurs et FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Obligatoire. </p> <p> Nom du partenaire fourni par <span class="keyword">  Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Supprime les scripts et les rappels. La valeur par défaut est <code> False </code>. S’applique uniquement à l’instance <span class="wintitle"> DIL actuelle </span> . Version 3.3 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Définit un cookie avec l’ID utilisateur unique renvoyé par <span class="keyword">  Manager </span>. Voir Propriétés <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Requis avec <span class="wintitle"> DIL </span> 6.2 ou version ultérieure. </p> <p> Le code DIL s’appuie sur la <code> setCustomerIDs </code> fonction du service d’identité d’ <span class="wintitle"> Adobe Experience Platform </span> pour transmettre les identifiants déclarés dans <span class="keyword">  Manager </span>. Pour plus d’informations, voir <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid-authenticated-state.html" format="https" scope="external">ID de client et états de l’authentification.</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de code**

Un exemple [!UICONTROL DIL] d’appel peut ressembler à ce qui suit :

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

Une réponse réussie renvoie l’ [!UICONTROL DIL] instance. Une tentative infructueuse renvoie un objet d’erreur (non renvoyé) si votre code est mal configuré ou en cas d’erreur.

## Propriétés uuidCookie {#uuidcookie-props}

Définit les propriétés utilisées par la `uuidCookie` variable. Cette variable fait partie de la `DIL.create` méthode.

`uuidCookie` possède les propriétés suivantes :

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nom | Description |
|---|---|
| `name` | The cookie name ( `aam_did` is default). |
| `days` | Durée de vie du cookie (100 jours est la valeur par défaut). |
| `path` | Chemin d’accès au cookie, par exemple `'/test'` ( `/` par défaut). |
| `domain` | Domaine dans lequel le cookie est défini, par exemple `'adobe.com'` ( `'.'+document.domain` est par défaut). |
| `secure` | Définit un indicateur pour envoyer des données uniquement sur une connexion HTTPS. |

## Propriétés de visitorService {#visitor-service-props}

Définit les propriétés utilisées par la `visitorService` variable. Cette variable fait partie de la `DIL.create` méthode.

`visitorService` possède les propriétés suivantes :

| Nom | Type | Description |
|---|---|---|
| `namespace` | Chaîne | Requis. Représente L’ID D’Entreprise Experience Cloud. Ceci est nécessaire pour la fonctionnalité du service principal d’Experience Cloud. Même paramètre utilisé pour instancier la fonctionnalité d’ID de. |

**Exemple de code :**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
