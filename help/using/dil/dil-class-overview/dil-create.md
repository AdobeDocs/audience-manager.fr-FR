---
description: Crée une instance DIL spécifique au partenaire.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: Création DIL
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 4%

---

# Méthode de création DIL{#dil-create}

>[!WARNING]
>
>Depuis juillet 2023, Adobe a interrompu le développement du [!DNL Data Integration Library (DIL)] et de l’extension [!DNL DIL].
>
>Les clients existants peuvent continuer à utiliser leur implémentation [!DNL DIL]. Cependant, Adobe ne développera pas d’[!DNL DIL] au-delà de ce point. Nous recommandons aux clients d’évaluer [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent implémenter de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=fr) à la place.

## Création DIL {#dil-create-new}

Crée une instance de [!UICONTROL DIL] spécifique au partenaire.

**Signature de fonction :** `DIL.create: function (initConfig) {}`

**éléments initConfig**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>La propriété `visitorService` est *always* obligatoire. Les autres propriétés répertoriées ici sont facultatives, sauf indication contraire.

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
   <td colname="col3"> <p>Cette propriété définit l’identifiant de conteneur utilisé par <span class="keyword">’</span> Audience Manager pour les synchronisations des identifiants. Il est préférable de définir <code> containerNSID </code> si <span class="wintitle"> </span> DIL est déployé sur plusieurs sites. Chacun de ces sites aura ses propres synchronisations des ID et des conteneurs. Lorsque vous n’avez qu’un seul site, l’ID de conteneur est 0 par défaut et vous n’avez pas besoin de le définir correctement. Contactez votre consultant pour obtenir une liste de vos sites et de leurs ID de conteneur. </p> <p>Dans le <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr" format="https" scope="external"> </a> Adobe Experience Platform Identity Service, la propriété <code> idSyncContainerID </code> correspond à <code> containerNSID </code> dans <span class="wintitle"> </span> DIL. Notez ce qui suit si vous utilisez <span class="wintitle"> DIL </span> <i>et</i> le service d’ID sur plusieurs sites : </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Pour chaque site, définissez les mêmes ID de conteneur sur <code> containerNSID </code> et <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF"><span class="wintitle"> DIL </span> et le service d’ID tenteront d’envoyer les synchronisations des identifiants à notre iFrame de collecte de données. Cependant, l’iFrame garantit que <span class="wintitle"> </span> DIL ne déclenchera pas de synchronisation des identifiants. Cela évite la duplication. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Seul <span class="wintitle"> DIL </span> envoie des données à un <a href="../../features/destinations/destinations.md"> de destination d’URL </a>. </li> 
     </ul> </p> <p>Voir aussi <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=fr" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> est utilisé pour transmettre l’un des éléments suivants : </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code> : ID de partenaire de données qui vous est attribué par <span class="keyword">’</span> Audience Manager. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code> : ID unique d’un utilisateur. </li> 
    </ul> <p> <p>Important : utilisez uniquement des valeurs non codées pour vos identifiants. L’encodage crée des identifiants codés en double. </p> </p> <p> <p>Remarque : si vous utilisez l’<a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, définissez les ID de client avec la méthode <code> setCustomerIDs </code> au lieu de <span class="wintitle"> l’</span> DIL. Voir <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=fr" format="https" scope="external"> les ID de client et les états d’authentification </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Si la valeur est true, reporte l’exécution de toutes les requêtes (IFRAME, appels d’événement, synchronisation des identifiants et destination) jusqu’au déclenchement de l’événement <code> Page Load </code>. La valeur par défaut est <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> False par défaut, ce qui signifie <span class="keyword"> Audience Manager </span> définit un cookie dans le domaine du partenaire (définit un cookie propriétaire). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important : cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publiée en août 2018). Utilisez plutôt la fonction <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=fr" format="https" scope="external"> </a> dans le service d’identités Adobe Experience Platform. </p> </p> <p> Si <code> true </code>, ne joint pas l’IFRAME de publication de destination aux destinations DOM ou déclenche des erreurs. La valeur par défaut est <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important : cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publiée en août 2018). Utilisez plutôt la fonction <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=fr" format="https" scope="external"> </a> dans le service d’identités Adobe Experience Platform. </p> </p> <p>Désactive la synchronisation des identifiants. Vous devez désactiver les synchronisations des identifiants lors de l’utilisation de DIL v6.2+ et du service d’identification des visiteurs. La fonction <code> visitorService </code> (voir l’exemple de code ci-dessous) prend en charge cette opération. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Définissez cette valeur sur <code> true </code> afin d’activer le rapport d’erreurs pour toutes les instances <span class="wintitle"> DIL </span> de la page. Fonctionne uniquement avec les <code> true </code> booléennes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> <p>Important : cet élément a été abandonné avec <span class="wintitle"> DIL </span> version 8.0 (publiée en août 2018). Utilisez plutôt la fonction <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=fr" format="https" scope="external"> </a> dans le service d’identités Adobe Experience Platform. </p> </p> <p> Indique si le modèle de publication de destination doit utiliser Akamai pour les connexions HTTPS. Activée par partenaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Associe la valeur d’une paire clé-valeur à une autre. Voir <a href="../../dil/dil-use-cases.md#map-key-values"> Mapper des valeurs de clé à d’autres clés </a>. Version v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Obligatoire. </p> <p>La paire clé-valeur <code> namespace </code> contient l’identifiant d’organisation <span class="keyword"> Experience Cloud </span>. Si vous ne disposez pas de cet identifiant, vous pouvez le trouver dans la section <span class="wintitle"> d’administration </span> du tableau de bord de l’<span class="keyword"> d’</span> Experience Cloud. Vous avez besoin d’autorisations d’administrateur pour afficher ce tableau de bord. Consultez les FAQ sur les fonctionnalités du produit <a href="../../faq/faq-features.md"> et Administration des </a> et des <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=fr" format="https" scope="external"> - Gestion des utilisateurs et FAQ </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Obligatoire. </p> <p> Nom du partenaire fourni par <span class="keyword">’</span> Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Booléen </p> </td> 
   <td colname="col3"> <p> Supprime les scripts et les rappels. La valeur par défaut est <code> False </code>. S’applique uniquement à l’instance <span class="wintitle"> DIL </span> actuelle. Publié avec la version 3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Définit un cookie avec l’ID d’utilisateur unique renvoyé par <span class="keyword">’</span> Audience Manager. Voir <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> Propriétés uuidCookie </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Objet </p> </td> 
   <td colname="col3"> <p>Requis avec <span class="wintitle"> DIL </span> 6.2 ou une version ultérieure. </p> <p> DIL s’appuie sur la fonction <code> setCustomerIDs </code> du <span class="wintitle"> Adobe Experience Platform Identity Service </span> pour transmettre les identifiants déclarés à <span class="keyword">’</span> Audience Manager. Pour plus d’informations, voir <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=fr" format="https" scope="external"> les ID de client et les états d’authentification </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple de code**

Un exemple d’appel [!UICONTROL DIL] pourrait ressembler à ce qui suit :

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

Une réponse réussie renvoie l’instance [!UICONTROL DIL]. Une tentative infructueuse renvoie un objet d’erreur (non généré) si votre code n’est pas correctement configuré ou si une erreur se produit.

## Propriétés uuidCookie {#uuidcookie-props}

Définit les propriétés utilisées par la variable `uuidCookie`. Cette variable fait partie de la méthode `DIL.create`.

`uuidCookie` possède les propriétés suivantes :

<!-- 

r_dil_uuid_cookie.xml

 -->

| Nom | Description |
|---|---|
| `name` | Le nom du cookie ( `aam_did` est la valeur par défaut). |
| `days` | Durée de vie des cookies (100 jours par défaut). |
| `path` | Chemin du cookie, par exemple `'/test'` ( `/` est la valeur par défaut). |
| `domain` | Le domaine dans lequel le cookie est défini, par exemple `'adobe.com'` (`'.'+document.domain` est la valeur par défaut). |
| `secure` | Définit un indicateur pour envoyer des données via une connexion HTTPS uniquement. |

## visitorService Properties {#visitor-service-props}

Définit les propriétés utilisées par la variable `visitorService`. Cette variable fait partie de la méthode `DIL.create`.

`visitorService` possède les propriétés suivantes :

| Nom | Type | Description |
|---|---|---|
| `namespace` | Chaîne | Requis. Représente L’ID d’organisation Experience Cloud. Cela est nécessaire pour la fonctionnalité Experience Cloud Core Service. Même paramètre que celui utilisé pour instancier la fonctionnalité d’identifiant visiteur. |

**Exemple de code :**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
