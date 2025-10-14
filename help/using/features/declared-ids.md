---
description: Fonctionnement des ID déclarés, configuration des procédures, exemples de code et variables.
keywords: synchronisation des identifiants
seo-description: How declared IDs work, set up procedures, code examples, and variables.
seo-title: Declared IDs
solution: Audience Manager
title: ID déclarés
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
feature: ID Syncs
exl-id: a480671a-797d-405d-905d-98ab4ef71369
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 8%

---

# [!UICONTROL Declared IDs] {#declared-ids}

Fonctionnement, configuration [!UICONTROL declared IDs] procédures, exemples de code et variables.

## [!UICONTROL Declared ID] Ciblage {#declared-id-targeting}

Échangez et synchronisez les ID utilisateur avec des [!DNL Audience Manager] provenant d’appareils ou de navigateurs qui n’utilisent pas ou n’acceptent pas les mécanismes de stockage persistants, tels que les [!DNL cookies] tiers.

## Objectif du ciblage [!UICONTROL Declared ID] {#declared-id-targeting-purpose}

Certains navigateurs et la plupart des appareils mobiles n’acceptent pas les [!DNL cookies] tiers. Il est donc difficile de conserver les informations sur les visiteurs du site ou d’attribuer des identifiants persistants. Pour résoudre ce problème, [!DNL Audience Manager] utilise [!UICONTROL DIL] pour vous permettre de transmettre des [!UICONTROL declared IDs] lors d’un appel d’événement. En outre, un [!UICONTROL declared ID] peut agir comme un identifiant universel qui s’applique au même utilisateur pour toutes les solutions du [!DNL Experience Cloud]. Le tableau suivant décrit le processus de ciblage/correspondance des identifiants :

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
   <td colname="col2"> <p>Pour fonctionner, vous avez besoin <span class="wintitle"> code de </span> DIL et du <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr" format="https" scope="external"> Adobe Experience Platform Identity Service </a> sur la page. <span class="wintitle"> </span> DIL obtient <span class="wintitle"> identifiants déclarés </span> à partir de la fonction <code> setVisitorID </code> fournie par le <span class="keyword"> du service d’identités de Adobe Experience Platform </span> et le transmet à <span class="keyword">’</span> Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de correspondance</b> </td> 
   <td colname="col2"> <p>Audience Manager tente de faire correspondre l’identifiant client et l’identifiant visiteur à un identifiant correspondant dans notre système. S’il n’existe pas d’identifiant correspondant, Audience Manager en crée un et l’associe au client et à l’identifiant visiteur. </p> <p> <p>Remarque : le mappage le plus récent est utilisé si votre identifiant correspond à plusieurs identifiants Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retour</b> </td> 
   <td colname="col2"> <p>Audience Manager écrit son identifiant synchronisé dans un cookie propriétaire (ou un autre espace de stockage adressable) dans le domaine ou l’application client. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Appels d’événement suivants</b> </td>
   <td colname="col2"> <p>D’autres appels d’événement lisent l’Audience Manager ID dans le domaine du client et l’envoient à Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Pour commencer, vous devez configurer le service d’ID de [!DNL Experience Cloud] et les [!UICONTROL DIL] sur les pages de votre site que vous souhaitez utiliser pour la collecte de données. Voir les sections [Création &#x200B;](../dil/dil-class-overview/dil-create.md#dil-create) DIL et [Variables d’ID déclarées](../features/declared-ids.md#declared-id-variables).

## Appels d’opt-out {#opt-out-calls}

Le processus [!UICONTROL declared ID] respecte les préférences des visiteurs du site pour leur permettre de se désabonner du ciblage [!DNL Audience Manager] par votre site web. Lorsqu&#39;[!DNL Audience Manager] reçoit une demande d&#39;opt-out, le [!DNL JSON] renvoyé par le [!DNL DCS] contient le code d&#39;erreur 171, avec le message `Encountered opt out tag`, au lieu de l&#39;identifiant utilisateur [!DNL Audience Manager].

* [!DNL Audience Manager] pouvez transmettre un opt-out [!UICONTROL declared ID] avec un [!DNL Audience Manager] [!UICONTROL UUID] dans le [!DNL URL].
* Le processus d’opt-out [!UICONTROL declared ID] est stocké dans le [!UICONTROL Profile Cache Server] ([!UICONTROL PCS]) sur une base par partenaire. Il n’existe aucune désinscription au niveau de la plateforme à l’aide de [!UICONTROL declared IDs]. En outre, [!DNL Audience Manager] exclut l’utilisateur de cette région particulière sur le serveur Edge (l’exclusion ne traverse pas les régions [!DNL DCS]).

Consultez [&#x200B; Confidentialité des données &#x200B;](../overview/data-security-and-privacy/data-privacy.md) pour plus d’informations sur le droit d’opposition à la collecte de données.

## Exemples d’opt-out [!UICONTROL Declared ID] {#opt-out-examples}

Vous pouvez effectuer des demandes d’opt-out [!UICONTROL declared ID] avec les paires clé-valeur `d_cid` et `d_cid_ic`. Les paramètres hérités comme `d_dpid` et `d_dpuuid` fonctionnent toujours, mais sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../reference/cid.md). Dans les exemples, le texte en *italique* indique un espace réservé de variable.

### Opt-outs avec [!UICONTROL CID] et [!UICONTROL CID_IC]

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
   <td colname="col1"> <p>Plusieurs <code> d_cid </code> et <code> d_cid_ic </code> paires clé-valeur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Opt-outs avec [!UICONTROL DPID], [!UICONTROL DPUUID] et [!UICONTROL UUID] (obsolète)

Ces méthodes fonctionnent toujours, mais sont considérées comme obsolètes. Ces informations sont fournies à des fins héritées et à titre de référence. Les opt-outs hérités sont les suivants :

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-Out (Obsolète) </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid </code> uniquement </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid=AAM ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Désinscription au niveau du partenaire </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Un processus d’opt-out au niveau du partenaire est stocké pour le dernier mappage de cette paire <code> dpid </code> + <code> dpuuid </code> à un UUID AAM. En l’absence de mappage existant, Audience Manager vérifie si la requête contient un UUID AAM dans le cookie et, le cas échéant, l’utilise pour stocker le processus d’opt-out. Dans le cas contraire, Audience Manager génère un nouvel UUID AAM et stocke le code d'opt-out sous celui-ci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> et <code> d_uuid </code> explicite </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> a toujours la priorité. Si la combinaison <code> dpid </code> + <code> dpuuid </code> est mappée à un autre UUID AAM, le processus d’opt-out est stocké sous l’UUID AAM transmis dans la requête ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables et syntaxe pour [!UICONTROL Declared IDs] {#variables-and-syntax}

Le tableau suivant répertorie les paires clé-valeur qui transmettent l’ID de votre fournisseur de données [!DNL Audience Manager] et les ID utilisateur ou les codes d’intégration, le cas échéant. Notez que *l’italique* indique un espace réservé de variable. Des espaces ont été ajoutés pour faciliter leur lecture.

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
   <td colname="col2"> <p>Contient un ID de fournisseur de données et un ID d’utilisateur unique associé dans une seule paire clé-valeur. <code> d_cid </code> remplace <code> d_dpid </code> et <code> d_dpuuid </code>, qui sont considérés comme obsolètes, mais toujours pris en charge. Voir <a href="../reference/cid.md"> CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contient un code d’intégration et un ID utilisateur unique associé dans une seule paire clé-valeur. <code> d_cid_ic </code> remplace <code> d_dpid </code> et <code> d_dpuuid </code>, qui sont obsolètes, mais toujours pris en charge. Voir <a href="../reference/cid.md"> CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples d’appels d’événement {#sample-event-calls}

Compte tenu de ces paires clé-valeur et de leur syntaxe requise, vous effectueriez des appels d’événement comme illustré ci-dessous.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> L’Appel D’Événement Comprend Les Éléments Suivants : </th> 
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
   <td colname="col1"> <p>Plusieurs <code> d_cid </code> et <code> d_cid_ic </code> paires clé-valeur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Variables {#declared-id-variables}

Décrit les variables de configuration utilisées pour transmettre des [!UICONTROL declared IDs] de [!UICONTROL DIL] à [!DNL Audience Manager.]

## [!UICONTROL DIL] utilise l’[!DNL Adobe Experience Platform Identity Service] pour transmettre des [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Lorsqu’il est utilisé avec le service d’identités [Adobe Experience Platform](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr), vous n’avez plus besoin de transmettre des [!UICONTROL declared IDs] avec les variables `dpid` et `dpuuid` obsolètes. Au lieu de cela, les versions actuelles de [!UICONTROL DIL] reposent sur la fonction `visitorService` pour obtenir le [!UICONTROL declared IDs] de la fonction `setCustomerIDs` dans le [!UICONTROL Adobe Experience Platform Identity Service]. Pour plus d’informations, voir [&#x200B; ID de client et états d’authentification &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=fr). Vous pouvez appeler `visitorService` en `DIL.create`, comme illustré ci-dessous.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Dans la paire clé-valeur `namespace`, `MCORG` correspond à l’ID d’organisation [!DNL Experience Cloud]. Si vous ne disposez pas de cet identifiant, vous pouvez le trouver dans la section [!UICONTROL Administration] du tableau de bord [!DNL Experience Cloud]. Vous avez besoin d’autorisations d’administrateur pour afficher ce tableau de bord. Voir [Prise en main des services Experience Cloud](https://experienceleague.adobe.com/fr/docs/core-services/interface/services/getting-started).

## Fonctions obsolètes {#deprecated-functions}

Avec les dernières versions d’[!UICONTROL DIL] (6.2+), vous n’avez pas besoin d’utiliser ces paires clé-valeur pour transmettre des [!UICONTROL declared IDs]. En effet, [!UICONTROL DIL] repose désormais sur la fonction `visitorService` affichée dans l’exemple de code ci-dessus. Cette fonction est [!UICONTROL declared IDs] à partir du [!UICONTROL Adobe Experience Platform Identity Service] . Cependant, nous référençons ces variables ici à des fins historiques et héritées. Consultez le code ci-dessous pour obtenir un exemple de configuration d’`DIL.create` afin d’obtenir un [!UICONTROL declared ID] à partir de l’[!UICONTROL Visitor ID Service] .
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

[!DNL Audience Manager] compare et associe les `DPID` et `DPUUID` combinés à un identifiant utilisateur correspondant dans notre système. S’il n’existe pas d’ID, [!DNL Audience Manager] crée un ID utilisateur et le synchronise avec la combinaison `DPID/DPUUID`. Une fois qu’[!DNL Audience Manager] correspond à un ID utilisateur (l’`UUID`) ou qu’il le crée, il le renvoie dans la réponse [!DNL JSON] au [!DNL cookie] dans le domaine du client ([!DNL cookie] propriétaire) ou dans tout autre stockage local.

Appelez cette fonction lorsque vous utilisez [!UICONTROL DIL] v6.1 ou une version antérieure. Cependant, cette fonction a été abandonnée au profit de la nouvelle version qui est [!UICONTROL declared IDs] à partir du [!DNL Adobe Experience Platform Identity Service].

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

### Transmission Des Identifiants Après L’Instanciation De [!UICONTROL DIL]

>[!NOTE]
>
>Si vous effectuez un appel [!DNL API] avec une autre combinaison de `declaredID`, la nouvelle combinaison sera utilisée uniquement pour cet appel. D’autres appels d’événement réguliers utiliseront la combinaison de `DIL.create` `declaredID` d’origine.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exemples de requêtes/réponses {#request-response-examples}

La requête envoie un fournisseur de données et un identifiant utilisateur à [!DNL Audience Manager] :

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La réponse renvoie l’ID Audience Manager (par exemple, `UUID`) qui est écrit dans un cookie propriétaire dans le domaine de la page.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Appels de non-ciblage et d’opt-out {#do-not-target}

Le processus [!UICONTROL declared ID] respecte les préférences des visiteurs du site pour leur permettre de se désabonner du ciblage [!DNL Audience Manager] par votre site web. Lorsqu’[!DNL Audience Manager] reçoit une demande d’opt-out, le [!DNL DCS] renvoie un objet [!DNL JSON] vide au lieu de l’ID utilisateur [!DNL Audience Manager].

>[!MORELIKETHIS]
>
>* [CID remplace DPID et DPUUID](../reference/cid.md)
