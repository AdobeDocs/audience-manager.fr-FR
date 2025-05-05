---
description: Crée une instance de DIL spécifique au partenaire.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: Création de DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# méthode de création de DIL{#dil-create}

>[!WARNING]
>
>Depuis juillet 2023, Adobe a arrêté le développement de l’extension [!DNL Data Integration Library (DIL)] et [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, l’Adobe ne développera pas [!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer le [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent mettre en oeuvre de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) à la place.

## Création de DIL {#dil-create-new}

Crée une instance [!UICONTROL DIL] spécifique au partenaire.

**Signature de fonction :** `DIL.create: function (initConfig) {}`

**éléments initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La propriété `visitorService` est *always* requise. Les autres propriétés répertoriées ici sont facultatives, sauf indication contraire.

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
   <td colname="col3"> <p>Cette propriété définit l’ID de conteneur utilisé par l’ <span class="keyword"> Audience Manager </span> pour la synchronisation des identifiants. Vous définiriez <code> containerNSID </code> si <span class="wintitle"> DIL </span> est déployé sur plusieurs sites. Chacun de ces sites aura son propre ID de conteneur et sa propre synchronisation des identifiants. Si vous ne disposez que d’un site, l’identifiant du conteneur est 0 par défaut et vous n’avez pas besoin de le définir correctement. Contactez votre consultant pour obtenir la liste de vos sites et de leurs ID de conteneur. </p> <p>Dans le <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr" format="https" scope="external"> service Adobe Experience Platform Identity </a>, la propriété <code> idSyncContainerID </code> correspond à <code> containerNSID </code> dans le <span class="wintitle"> DIL </span>. Notez ce qui suit si vous utilisez <span class="wintitle"> DIL </span> <i> et </i> le service d’ID sur plusieurs sites : </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Pour chaque site, définissez les mêmes ID de conteneur sur <code> containerNSID </code> et <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle"> DIL </span> et le service d’ID essaieront tous deux d’envoyer des synchronisations des identifiants à notre iFrame de collecte de données. Cependant, l’iFrame s’assure que <span class="wintitle"> DIL </span> ne déclenche pas de synchronisation des identifiants. Cela empêche la duplication. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Seul <span class="wintitle"> DIL </span> envoie des données vers une destination <a href="../../features/destinations/destinations.md"> d’URL </a>. </li> 
     </ul> </p> <p>Voir aussi <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=fr" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> est utilisé pour transmettre l’un des éléments suivants : </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code> : identifiant du partenaire de données qui vous a été attribué par <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code> : votre identifiant unique pour un utilisateur. </li> 
    </ul> <p> <p>Important : Utilisez uniquement des valeurs non codées pour vos ID. Le codage crée des identifiants codés deux fois. </p> </p> <p> <p>Remarque : Si vous utilisez le <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr" format="https" scope="external"> service Adobe Experience Platform Identity </a>, définissez les ID de client avec la méthode <code> setCustomerIDs </code> au lieu du <span class="wintitle"> DIL </span>. Voir <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=fr" format="https" scope="external"> ID de client et états d’authentification </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Si la valeur est true, empêche toutes les requêtes (IFRAME, appels d’événement, synchronisation des identifiants et destination) de s’exécuter jusqu’au déclenchement de l’événement <code> Page Load </code>. La valeur par défaut est <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> False par défaut, ce qui signifie que <span class="keyword"> l’Audience Manager </span> définit un cookie dans le domaine du partenaire (définit un cookie propriétaire). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important : Cet élément a été abandonné avec la version 8.0 de <span class="wintitle"> DIL </span> (publiée en août 2018). Utilisez plutôt la fonction <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=fr" format="https" scope="external"> </a> dans le service Adobe Experience Platform Identity. </p> </p> <p> Si <code> true </code>, ne joint pas l’IFRAME de publication de destination au DOM ou aux destinations de déclenchement. La valeur par défaut est <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important : Cet élément a été abandonné avec la version 8.0 de <span class="wintitle"> DIL </span> (publiée en août 2018). Utilisez plutôt la fonction <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=fr" format="https" scope="external"> </a> dans le service Adobe Experience Platform Identity. </p> </p> <p>Désactive la synchronisation des identifiants. Vous devez désactiver les synchronisations des identifiants lors de l’utilisation de DIL v6.2+ et du service d’identification des visiteurs. La fonction <code> visitorService </code> (voir l’exemple de code ci-dessous) s’occupe de cette opération. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Définissez cette variable sur <code> true </code> pour activer la création de rapports d’erreurs pour toutes les instances <span class="wintitle"> de DIL </span> sur la page. Fonctionne uniquement avec le booléen <code> true </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important : Cet élément a été abandonné avec la version 8.0 de <span class="wintitle"> DIL </span> (publiée en août 2018). Utilisez plutôt la fonction <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=fr" format="https" scope="external"> </a> dans le service Adobe Experience Platform Identity. </p> </p> <p> Indique si le modèle de publication de destination doit utiliser Akamai pour les connexions HTTPS. Activée par partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Associe la valeur d’une paire clé-valeur à une autre. Voir <a href="../../dil/dil-use-cases.md#map-key-values"> Mappage des valeurs de clé aux autres clés </a>. Publié avec la version 2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Obligatoire. </p> <p>La paire clé-valeur <code> namespace </code> contient votre ID d’organisation <span class="keyword"> Experience Cloud </span>. Si vous ne possédez pas cet identifiant, vous pouvez le trouver dans la section <span class="wintitle"> Administration </span> du tableau de bord <span class="keyword"> Experience Cloud </span>. Vous avez besoin des autorisations d’administrateur pour afficher ce tableau de bord. Voir les <a href="../../faq/faq-features.md"> FAQ sur les fonctions et fonctionnalités du produit </a> et <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=fr" format="https" scope="external"> Administration - Gestion des utilisateurs et FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Obligatoire. </p> <p> Nom du partenaire fourni par l’Audience Manager <span class="keyword"> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Supprime les scripts et les rappels. La valeur par défaut est <code> False </code>. S’applique uniquement à l’instance <span class="wintitle"> de DIL </span> actuelle. Publié avec la version 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Définit un cookie avec l’identifiant utilisateur unique renvoyé par l’Audience Manager <span class="keyword"> </span>. Voir <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propriétés uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Requis avec <span class="wintitle"> DIL </span> 6.2 ou version ultérieure. </p> <p> DIL s'appuie sur la fonction <code> setCustomerIDs </code> du <span class="wintitle"> service Adobe Experience Platform Identity </span> pour transmettre les identifiants déclarés à l'Audience Manager <span class="keyword"> </span>. Voir <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=fr" format="https" scope="external"> ID de client et états de l’authentification </a> pour plus d’informations. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de code**

Un exemple d’appel [!UICONTROL DIL] peut ressembler à ce qui suit :

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

Une réponse réussie renvoie l’instance [!UICONTROL DIL]. Une tentative manquée renvoie un objet d’erreur (non généré) si votre code est mal configuré ou en cas d’erreur.

## Propriétés du cookie uuid {#uuidcookie-props}

Définit les propriétés utilisées par la variable `uuidCookie`. Cette variable fait partie de la méthode `DIL.create`.

`uuidCookie` possède les propriétés suivantes :

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nom | Description |
|---|---|
| `name` | Le nom du cookie ( `aam_did` est par défaut). |
| `days` | Durée de vie du cookie (100 jours par défaut). |
| `path` | Chemin d’accès au cookie, par exemple `'/test'` ( `/` est la valeur par défaut). |
| `domain` | Domaine dans lequel le cookie est défini, par exemple `'adobe.com'` ( `'.'+document.domain` par défaut). |
| `secure` | Définit un indicateur pour envoyer des données sur une connexion HTTPS uniquement. |

## Propriétés visitorService {#visitor-service-props}

Définit les propriétés utilisées par la variable `visitorService`. Cette variable fait partie de la méthode `DIL.create`.

`visitorService` possède les propriétés suivantes :

| Nom | Type | Description |
|---|---|---|
| `namespace` | Chaîne | Requis. Représente L’ID De L’Organisation Experience Cloud. Ceci est nécessaire pour la fonctionnalité Core Service Experience Cloud. Même paramètre utilisé pour instancier la fonctionnalité d’identifiant visiteur. |

**Exemple de code :**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
