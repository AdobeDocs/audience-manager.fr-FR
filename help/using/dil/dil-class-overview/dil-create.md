---
description: Crée une instance de DIL spécifique au partenaire.
seo-description: Crée une instance de DIL spécifique au partenaire.
seo-title: Création DIL
solution: Audience Manager
title: Création DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: fc13643681eebec17a95607482f2864e81b95820
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 12%

---


# DIL create method{#dil-create}

## Création DIL {#dil-create-new}

Crée une instance [!UICONTROL DIL] spécifique au partenaire.

**Signature de fonction :** `DIL.create: function (initConfig) {}`

**Éléments initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La propriété `visitorService` est *toujours* requise. Les autres propriétés répertoriées ici sont facultatives, sauf indication contraire.

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
   <td colname="col3"> <p>Cette propriété définit l’identifiant du conteneur utilisé par <span class="keyword">Audience Manager</span> pour la synchronisation des identifiants. Vous pouvez définir <code> containerNSID </code> si <span class="wintitle"> DIL </span> est déployé sur plusieurs sites. Chacun de ces sites aura son propre conteneur ID et ID synchronisés. Si vous ne disposez que d’un site, l’ID de conteneur est 0 par défaut et vous n’avez pas besoin de définir cette valeur correctement. Contactez votre consultant pour obtenir une liste de vos sites et de leurs ID de conteneur. </p> <p>Dans <a href="https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, la propriété <code> idSyncContainerID </code> correspond à <code> containerNSID </code> dans <span class="wintitle"> DIL </span>. Notez ce qui suit si vous utilisez <span class="wintitle"> DIL </span> <i>et </i> le service d’ID sur plusieurs sites : </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Pour chaque site, définissez les mêmes ID de conteneur sur <code> containerNSID </code> et <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Le DIL <span class="wintitle"> </span> et le service d’ID essaieront tous deux d’envoyer des synchronisations d’ID à notre iFrame de collecte de données. Cependant, l’iFrame s’assure que le DIL <span class="wintitle"> </span> ne déclenche pas de synchronisation d’ID. Cela permet d'éviter les doublons. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Seul le DIL <span class="wintitle"> </span> envoie des données à une destination URL <a href="../../features/destinations/destinations.md"> </a>. </li> 
     </ul> </p> <p>Voir aussi <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> est utilisée pour transmettre l’une des valeurs suivantes : </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID de partenaire de données qui vous a été attribué par  <span class="keyword"> Audience Manager  </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Votre identifiant unique pour un utilisateur. </li> 
    </ul> <p> <p>Important :  Utilisez uniquement des valeurs non codées pour vos identifiants. Le codage crée des identifiants codés par doublon. </p> </p> <p> <p>Remarque :  Si vous utilisez <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, définissez les ID de client avec la méthode <code> setCustomerIDs </code> au lieu du DIL <span class="wintitle"> </span>. Voir <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> ID de client et états d’authentification </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Si la valeur est true, empêche l’exécution de toutes les requêtes (IFRAME, appels de événement, synchronisation des identifiants et destination) jusqu’à ce que le événement <code> Page Load </code> se déclenche. La valeur par défaut est <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> False par défaut, ce qui signifie <span class="keyword"> Audience Manager </span> définit un cookie dans le domaine du partenaire (définit un cookie propriétaire). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important :  Cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publié en août 2018). Utilisez plutôt la fonction <code> visitor.disableIdSyncs </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> dans le service d’identité Adobe Experience Platform. </p> </p> <p> Si <code> true </code>, ne joint pas la destination de publication IFRAME au DOM ou aux destinations de feu. La valeur par défaut est <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important :  Cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publié en août 2018). Utilisez plutôt la fonction <code> visitor.disableIdSyncs </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> dans le service d’identité Adobe Experience Platform. </p> </p> <p>Désactive la synchronisation des ID. Vous devez désactiver les synchronisations d’ID lors de l’utilisation de DIL v6.2+ et du service d’identification des Visiteurs. La fonction <code> visitorService </code> (voir l'exemple de code ci-dessous) s'occupe de cette opération. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Définissez sur <code> true </code> pour activer le rapports d’erreur pour toutes les instances <span class="wintitle"> DIL </span> de la page. Fonctionne uniquement avec Boolean <code> true </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important :  Cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publié en août 2018). Utilisez plutôt la fonction <code> visitor.idSyncSSLUseAkamai </code> <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> </a> dans le service d’identité Adobe Experience Platform. </p> </p> <p> Indique si le modèle de publication de destination doit utiliser Akamai pour les connexions HTTPS. Activée par partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Associe la valeur d’une paire clé-valeur à une autre. Voir <a href="../../dil/dil-use-cases.md#map-key-values"> Faire correspondre les valeurs clés aux autres clés </a>. Publié avec v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Obligatoire. </p> <p>La paire <code> namespace </code> clé-valeur contient votre <span class="keyword"> Experience Cloud </span> ID d'organisation. Si vous ne possédez pas cet ID, vous pouvez le trouver dans la section <span class="wintitle"> Administration </span> du tableau de bord <span class="keyword"> Experience Cloud </span>. Vous avez besoin d'autorisations d'administrateur pour vue ce tableau de bord. Voir les <a href="../../faq/faq-features.md"> FAQ sur les fonctionnalités et les fonctionnalités du produit </a> et <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Administration - Gestion des utilisateurs et FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Obligatoire. </p> <p> Nom du partenaire fourni par l'Audience Manager <span class="keyword"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Supprime les scripts et les rappels. La valeur par défaut est <code> False </code>. S'applique uniquement à l'instance actuelle <span class="wintitle"> du DIL </span>. Publié avec v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Définit un cookie dont l’ID utilisateur unique est renvoyé par l’Audience Manager <span class="keyword"> </span>. Voir <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propriétés uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Requis avec <span class="wintitle"> DIL </span> 6.2 ou supérieur. </p> <p> Le DIL s'appuie sur la fonction <code> setCustomerIDs </code> du service d'identité <span class="wintitle"> Adobe Experience Platform </span> pour transmettre les identifiants déclarés à l'Audience Manager <span class="keyword"> </span>. Pour plus d’informations, voir <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external">ID de client et états de l’authentification.</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de code**

Un exemple d&#39;appel [!UICONTROL DIL] peut ressembler à ce qui suit :

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

Une réponse réussie renvoie l&#39;instance [!UICONTROL DIL]. Une tentative infructueuse renvoie un objet d&#39;erreur (non renvoyé) si votre code est mal configuré ou en cas d&#39;erreur.

## Propriétés du cookie uuid {#uuidcookie-props}

Définit les propriétés utilisées par la variable `uuidCookie`. Cette variable fait partie de la méthode `DIL.create`.

`uuidCookie` possède les propriétés suivantes :

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nom | Description |
|---|---|
| `name` | Le nom du cookie ( `aam_did` est par défaut). |
| `days` | Durée de vie du cookie (100 jours est par défaut). |
| `path` | Chemin d’accès au cookie, par exemple `'/test'` ( `/` est la valeur par défaut). |
| `domain` | Domaine dans lequel le cookie est défini, par exemple `'adobe.com'` ( `'.'+document.domain` est par défaut). |
| `secure` | Définit un indicateur pour envoyer uniquement des données via une connexion HTTPS. |

## Propriétés de visitorService {#visitor-service-props}

Définit les propriétés utilisées par la variable `visitorService`. Cette variable fait partie de la méthode `DIL.create`.

`visitorService` possède les propriétés suivantes :

| Nom | Type | Description |
|---|---|---|
| `namespace` | Chaîne | Requis. Représente L’ID D’Entreprise Experience Cloud. Ceci est nécessaire pour la fonctionnalité Experience Cloud Core Service. Paramètre identique à celui utilisé pour instancier la fonctionnalité d’ID de Visiteur. |

**Exemple de code:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
