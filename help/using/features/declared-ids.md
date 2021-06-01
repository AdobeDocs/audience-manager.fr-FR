---
description: Fonctionnement des identifiants déclarés, configuration des procédures, des exemples de code et des variables.
keywords: synchronisation des identifiants
seo-description: Fonctionnement des identifiants déclarés, configuration des procédures, des exemples de code et des variables.
seo-title: Identifiants déclarés
solution: Audience Manager
title: Identifiants déclarés
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: Synchronisations des identifiants
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 10%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Fonctionnement de [!UICONTROL declared IDs], configuration des procédures, des exemples de code et des variables.

## [!UICONTROL Declared ID] Ciblage {#declared-id-targeting}

Échangez et synchronisez les ID utilisateur avec [!DNL Audience Manager] à partir de périphériques ou de navigateurs qui n’utilisent pas ou n’acceptent pas les mécanismes de stockage persistant, tels que [!DNL cookies] tiers.

## Objectif de [!UICONTROL Declared ID] Ciblage {#declared-id-targeting-purpose}

Certains navigateurs et la plupart des périphériques mobiles n’acceptent pas les [!DNL cookies] tiers. Il est ainsi difficile de conserver des informations sur les visiteurs du site ou d’attribuer des identifiants persistants. Pour résoudre ce problème, [!DNL Audience Manager] utilise [!UICONTROL DIL] pour vous permettre de transmettre [!UICONTROL declared IDs] à un appel d’événement. En outre, un [!UICONTROL declared ID] peut agir comme un ID universel qui s’applique au même utilisateur dans toutes les solutions de [!DNL Experience Cloud]. Le tableau suivant décrit le processus de ciblage/correspondance des identifiants :

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Processus </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Appel d’événement</b> </td> 
   <td colname="col2"> <p>Pour fonctionner, vous avez besoin du code <span class="wintitle"> DIL </span> et du <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> service Adobe Experience Platform Identity </a> sur la page. <span class="wintitle"> DIL  </span> récupère les identifiants  <span class="wintitle"> déclarés  </span> de la  <code> setVisitorID </code> fonction fournie par le service  <span class="keyword"> Adobe Experience Platform Identity  </span> et les transmet à  <span class="keyword"> l’Audience Manager  </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identifiant de correspondance</b> </td> 
   <td colname="col2"> <p>L’Audience Manager tente de faire correspondre l’identifiant client et l’identifiant visiteur avec un identifiant correspondant dans notre système. Si aucun identifiant correspondant n’existe, l’Audience Manager crée un nouvel identifiant et l’associe à l’identifiant client et à l’identifiant visiteur. </p> <p> <p>Remarque :  Le mappage le plus récent est utilisé si votre ID correspond à plusieurs ID d’Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identifiant de retour</b> </td> 
   <td colname="col2"> <p>Audience Manager écrit son ID synchronisé dans un cookie propriétaire (ou tout autre espace de stockage adressable) dans le domaine client ou l’application. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Appels d’événement suivants</b> </td>
   <td colname="col2"> <p>D’autres appels d’événement lisent l’ID d’Audience Manager du domaine du client et l’envoient à l’Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Pour commencer, vous devez configurer le service [!DNL Experience Cloud] ID et [!UICONTROL DIL] sur les pages de votre site que vous souhaitez utiliser pour la collecte de données. Voir [Création de DIL](../dil/dil-class-overview/dil-create.md#dil-create) et [Variables d’ID déclarées](../features/declared-ids.md#declared-id-variables).

## Appels d’exclusion {#opt-out-calls}

Le processus [!UICONTROL declared ID] honore les préférences des visiteurs du site en ce qui concerne l’exclusion du ciblage [!DNL Audience Manager] par votre site Web. Lorsque [!DNL Audience Manager] reçoit une demande d’opposition, la valeur [!DNL JSON] renvoyée par la balise [!DNL DCS] contient le code d’erreur 171, avec le message `Encountered opt out tag`, au lieu de l’ID utilisateur [!DNL Audience Manager].

* [!DNL Audience Manager] peut transmettre une  [!UICONTROL declared ID] exclusion avec un  [!DNL Audience Manager] [!UICONTROL UUID] dans le  [!DNL URL].
* Le droit d’opposition [!UICONTROL declared ID] est stocké dans la balise [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) par partenaire. Il n’existe pas de droit d’opposition au niveau de la plateforme utilisant [!UICONTROL declared IDs]. En outre, [!DNL Audience Manager] exclut l’utilisateur de cette région spécifique sur le bord (l’exclusion ne traverse pas [!DNL DCS] régions).

Voir [Confidentialité des données](../overview/data-security-and-privacy/data-privacy.md) pour plus d’informations sur l’exclusion de la collecte de données.

## [!UICONTROL Declared ID] Exemples d’exclusion  {#opt-out-examples}

Vous pouvez effectuer des demandes d’exclusion [!UICONTROL declared ID] avec les paires `d_cid` et `d_cid_ic` clé-valeur. Les paramètres hérités comme `d_dpid` et `d_dpuuid` fonctionnent toujours, mais sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../reference/cid.md). Dans les exemples, le texte en *italique* indique un espace réservé de variable.

### Exclusions avec [!UICONTROL CID] et [!UICONTROL CID_IC]

Pour obtenir une description et une syntaxe, consultez les [variables et la syntaxe d’URL pour les identifiants déclarés](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion à l’aide </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>d’un identifiant de fournisseur de données et d’un identifiant utilisateur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>d’un code d’intégration et d’un identifiant utilisateur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs paires <code> d_cid </code> et <code> d_cid_ic </code> clé-valeur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exclusions avec [!UICONTROL DPID], [!UICONTROL DPUUID] et [!UICONTROL UUID] (obsolète)

Ces méthodes fonctionnent toujours, mais sont considérées comme obsolètes. Ces informations sont fournies à des fins héritées et à titre de référence. Les désinscriptions héritées incluent :

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion (obsolète) </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> uniquement </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclusion au niveau du partenaire </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Une exclusion au niveau du partenaire est stockée pour le dernier mappage de cette paire <code> dpid </code> + <code> dpuuid </code> à un UUID AAM. S’il n’existe aucun mappage existant auparavant, l’Audience Manager vérifie si la requête contient un UUID AAM dans le cookie et, si tel est le cas, l’utilise pour stocker l’exclusion. Dans le cas contraire, l’Audience Manager génère un nouvel UUID AAM et stocke l’exclusion sous celui-ci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> +  <code> d_dpid </code> et explicite  <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> a toujours la priorité. Si la combinaison <code> dpid </code> + <code> dpuuid </code> correspond à un autre UUID AAM, l’exclusion est stockée sous l’UUID AAM transmis dans la requête ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables et syntaxe pour [!UICONTROL Declared IDs] {#variables-and-syntax}

Le tableau suivant répertorie les paires clé-valeur qui transmettent l’ID de fournisseur de données [!DNL Audience Manager] et les ID utilisateur ou les codes d’intégration, le cas échéant. Remarque : *italics* indique un espace réservé de variable. Des espaces ont été ajoutés pour les rendre plus faciles à lire.

Dans chaque paire clé-valeur :

* Le symbole `=` sépare la clé de ses valeurs associées.
* Le caractère [!DNL ASCII] non imprimable `%01` sépare les valeurs.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid =<i>data provider ID</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contient un identifiant de fournisseur de données et un identifiant d’utilisateur unique associé dans une seule paire clé-valeur. <code> d_cid </code> remplace  <code> d_dpid </code> et  <code> d_dpuuid </code>, qui sont considérés comme obsolètes, mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contient un code d’intégration et un identifiant utilisateur unique associé dans une seule paire clé-valeur. <code> d_cid_ic </code> remplace  <code> d_dpid </code> et  <code> d_dpuuid </code>, qui sont obsolètes, mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples d’appels d’événement {#sample-event-calls}

Compte tenu de ces paires clé-valeur et de leur syntaxe requise, vous effectueriez des appels d’événement comme illustré ci-dessous.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Inclusion de l’appel d’événement </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>d’un identifiant de fournisseur de données et d’un identifiant utilisateur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>d’un code d’intégration et d’un identifiant utilisateur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs paires <code> d_cid </code> et <code> d_cid_ic </code> clé-valeur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variables {#declared-id-variables}

Décrit les variables de configuration utilisées pour transmettre [!UICONTROL declared IDs] à [!UICONTROL DIL] à [!DNL Audience Manager.].

## [!UICONTROL DIL] utilise le  [!DNL Adobe Experience Platform Identity Service] à transférer  [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Lorsqu’il est utilisé avec le [service Adobe Experience Platform Identity](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html), vous n’avez plus besoin de transmettre [!UICONTROL declared IDs] avec les variables `dpid` et `dpuuid` obsolètes. Les versions actuelles de [!UICONTROL DIL] reposent plutôt sur la fonction `visitorService` pour obtenir la fonction [!UICONTROL declared IDs] de la fonction `setCustomerIDs` dans la balise [!UICONTROL Adobe Experience Platform Identity Service]. Pour plus d’informations, voir [ID de client et états d’authentification](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Vous appelleriez `visitorService` dans `DIL.create` comme illustré ci-dessous.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Dans la paire `namespace` valeur-clé, `MCORG` correspond à votre [!DNL Experience Cloud] ID d’organisation. Si vous ne possédez pas cet ID, vous pouvez le trouver dans la section [!UICONTROL Administration] du tableau de bord [!DNL Experience Cloud]. Vous avez besoin des autorisations d’administrateur pour afficher ce tableau de bord. Voir [Administration : Services principaux](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Fonctions obsolètes {#deprecated-functions}

Avec les dernières versions de [!UICONTROL DIL] (6.2+), vous n’avez pas besoin d’utiliser ces paires clé-valeur pour transmettre [!UICONTROL declared IDs]. En effet, [!UICONTROL DIL] s’appuie désormais sur la fonction `visitorService` affichée dans l’exemple de code ci-dessus. Cette fonction récupère [!UICONTROL declared IDs] à partir de [!UICONTROL Adobe Experience Platform Identity Service]. Cependant, nous référençons ces variables ici à des fins historiques et héritées. Consultez le code ci-dessous pour obtenir un exemple de configuration de `DIL.create` pour obtenir une [!UICONTROL declared ID] à partir de [!UICONTROL Visitor ID Service].
Le tableau suivant décrit les variables héritées utilisées par l’objet `declaredId` :

<table id="table_A1884B72950F4BBDA87F17DDFF173628"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nom </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>Identifiant du partenaire de données attribué par Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>L’ID unique du fournisseur de données pour l’utilisateur. </p> </td> 
  </tr> 
 </tbody> 
</table>

### [!UICONTROL DPID] et [!UICONTROL DPUUID]

[!DNL Audience Manager] compare et fait correspondre la combinaison  `DPID` et  `DPUUID` à un ID utilisateur correspondant dans notre système. Si aucun ID n’existe, [!DNL Audience Manager] crée un ID utilisateur et le synchronise avec la combinaison `DPID/DPUUID`. Une fois que [!DNL Audience Manager] correspond ou crée un ID utilisateur (le `UUID`), il renvoie cet ID dans la réponse [!DNL JSON] à [!DNL cookie] dans le domaine du client (propriétaire [!DNL cookie]) ou tout autre stockage local.

Appelez cette fonction lorsque vous utilisez [!UICONTROL DIL] v6.1 ou une version antérieure. Cependant, cette fonction a été abandonnée au profit de la nouvelle version qui obtient [!UICONTROL declared IDs] à partir de [!DNL Adobe Experience Platform Identity Service].

```js
DIL.create({
    partner : "partner name",
    declaredId : {
       dpuuid : dpuuid,
       DPID : dpid
    }
 });
```

>[!NOTE]
>
>Vous devez développer par programmation le code qui fournit les valeurs d’identifiant pour les clés `d_dpuuid` et `d_dpid`.

### Transmettre les identifiants après les instances [!UICONTROL DIL]

>[!NOTE]
>
>Si vous effectuez un appel [!DNL API] avec une combinaison `declaredID` différente, la nouvelle combinaison sera utilisée uniquement pour cet appel. D’autres appels d’événement standard utiliseront la combinaison `DIL.create` `declaredID` d’origine.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exemples de requêtes/réponses {#request-response-examples}

La requête envoie un fournisseur de données et un ID utilisateur à [!DNL Audience Manager] :

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La réponse renvoie l’ID d’Audience Manager (par exemple, `UUID`) qui est écrit dans un cookie propriétaire dans le domaine de la page.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Ne pas cibler et ne pas exclure les appels {#do-not-target}

Le processus [!UICONTROL declared ID] honore les préférences des visiteurs du site en ce qui concerne l’exclusion du ciblage [!DNL Audience Manager] par votre site Web. Lorsque [!DNL Audience Manager] reçoit une demande d’opposition, [!DNL DCS] renvoie un objet [!DNL JSON] vide au lieu de l’ID utilisateur [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [CID remplace DPID et DPUUID](../reference/cid.md)

