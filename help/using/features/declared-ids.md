---
description: Fonctionnement des ID déclarés, procédures de configuration, exemples de code et variables.
keywords: synchronisation des identifiants
seo-description: Fonctionnement des ID déclarés, procédures de configuration, exemples de code et variables.
seo-title: ID déclarés
solution: Audience Manager
title: ID déclarés
uuid: 49 bb 4 f 7 e-b 4 a 7-4 d 87-a 29 c-c 3 dca 036 d 2 a 3
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# ID déclarés {#declared-ids}

Fonctionnement des ID déclarés, procédures de configuration, exemples de code et variables.

## Ciblage de l’ID déclaré {#declared-id-targeting}

Exchange et synchronisation utilisateur - identifiants avec Audience Manager à partir de périphériques ou de navigateurs qui n'utilisent pas ou n'acceptent pas les mécanismes de stockage persistant, tels que les cookies tiers.

<!-- declared_id_about.xml -->

## Objectif du ciblage d'ID déclaré {#declared-id-targeting-purpose}

Certains navigateurs et la plupart des périphériques mobiles n'acceptent pas les cookies tiers. Cela complique la conservation des informations sur les visiteurs du site ou leur attribution à des ID persistants. Pour résoudre ce problème, Audience Manager vous [!UICONTROL DIL] permet de transmettre [!UICONTROL declared IDs] un appel d'événement. En outre, un [!UICONTROL declared ID] utilisateur peut agir comme un ID universel qui s'applique au même utilisateur pour toutes les solutions de [!DNL Experience Cloud]la section. Le tableau suivant décrit le processus de ciblage/correspondance d'ID :

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Processus </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Appel d'événement</b> </td> 
   <td colname="col2"> <p>Pour travailler, vous devez <span class="wintitle"> disposer du code DIL </span> et du <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> code du service </a> Experience Cloud ID sur la page. <span class="wintitle"> Le code DIL </span> reçoit <span class="wintitle"> des ID </span> déclarés de la fonction <code> setvisitorid </code> fournie par le <span class="keyword"> service Experience Cloud ID </span> et transmet ce paramètre à <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de correspondance</b> </td> 
   <td colname="col2"> <p>Audience Manager tente de faire correspondre le client et l'identifiant visiteur avec un identifiant correspondant dans notre système. Si un identifiant correspondant n'existe pas, Audience Manager crée un identifiant et l'associe au client et à l'identifiant visiteur. </p> <p> <p>Remarque : Le mappage le plus récent est utilisé si votre ID mappe à plusieurs ID Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retour</b> </td> 
   <td colname="col2"> <p>Audience Manager écrit son identifiant synchronisé dans un cookie propriétaire (ou un autre espace de stockage adressable) dans le domaine client ou l'application. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Appels d'événements suivants</b> </td>
   <td colname="col2"> <p>D'autres appels d'événement lisent l'identifiant Audience Manager à partir du domaine du client et l'envoient à Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Pour commencer, vous devez configurer le service [!DNL Experience Cloud] d'ID et [!UICONTROL DIL] les pages de votre site que vous souhaitez utiliser pour la collecte de données. Voir [Création](../dil/dil-class-overview/dil-create.md#dil-create) de variables d'ID [déclarées et création de rapports DIL](../features/declared-ids.md#declared-id-variables).

## Appels d'exclusion {#opt-out-calls}

[!UICONTROL declared ID] Le processus respecte les préférences du visiteur du site pour exclure le ciblage Audience Manager de votre site Web. Lorsque Audience Manager reçoit une demande d'exclusion, le [!DNL JSON] renvoyé par le [!UICONTROL DCS] contient le code d'erreur 171, avec le message « Tag exclusion out tag », au lieu de l'utilisateur Audience Manager - id.

* Audience Manager peut transmettre une [!UICONTROL declared ID] exclusion à côté d'Audience Manager [!UICONTROL UUID] dans [!DNL URL]le champ.
* L [!UICONTROL declared ID] 'exclusion est stockée dans le [! UICONTROL Profile Cache Server ([!UICONTROL PCS]) par partenaire. Il n'y a pas d'exclusion au niveau de la plate [!UICONTROL declared IDs]-forme. De plus, Audience Manager exclut l'utilisateur de cette région particulière sur le bord (l'exclusion ne fait pas partie [!UICONTROL DCS] des régions).

Pour plus d'informations sur l'exclusion de la collecte de données, reportez-vous à [la section Confidentialité](../overview/data-security-and-privacy/data-privacy.md) des données.

## Exemples d'exclusion de l'identifiant déclarés {#opt-out-examples}

Vous pouvez effectuer une [!UICONTROL declared ID] demande d'exclusion avec `d_cid` les paires `d_cid_ic` clé-valeur. Les paramètres hérités tels que `d_dpid` continuent `d_dpuuid` à fonctionner, mais sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Exclusions avec CID et CID_ IC

Pour obtenir une description et une syntaxe, reportez-vous à la [section Variables URL et syntaxe pour les ID déclarés](../features/declared-ids.md#variables-and-syntax).

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion avec </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifiant de fournisseur de données et utilisateur - id. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/demoptout.jpg ? d_ cid = 123 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un code d'intégration et un utilisateur - id. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/déstout ? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs paires <code> d_ cid </code> et <code> d_ cid_ ic_ cid_ ic </code> . </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/déstout ? d_ cid = 123 % &amp; d_ cid_ ic = 456 013 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exclusions avec DPID, DPUUID et UUID (obsolète)

Ces méthodes fonctionnent toujours mais sont considérées comme obsolètes. Ces informations sont fournies à des fins héritées et référencées. Les exclusions héritées incluent :

<table id="table_0E180EBE84624F338494F49D9F6EBC8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion (obsolète) </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ uuid </code> uniquement </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=AAM<i></i>ID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exclusion du niveau partenaire </p> </td> 
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID &amp; d_ dpid = ID fournisseur de données </code> </p> <p>Une exclusion de niveau partenaire est stockée pour le mappage le plus récent de cette <code> paire dpid </code> + <code> dpuuid </code> à un UUID AAM. S'il n'existe pas de correspondance existante, Audience Manager vérifie si la requête contient un UUID AAM dans le cookie et, le cas échéant, utilise cette option pour stocker l'exclusion. Sinon, Audience Manager génère un nouvel identifiant AAM et stocke l'exclusion sous celle-ci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ dpuuid </code> + <code> d_ dpid </code> et explicite <code> d_ uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://domain/demoptout.jpg?d_uuid=<i></i>user ID &amp; d_ dpuuid = user provider's user - id &amp;<i>d_ dpid = data provider ID</i></code> </p> <p> <code> d_ uuid </code> est toujours prioritaire. Si la combinaison <code> dpid </code> + <code> dpuuid </code> associe un autre UUID AAM, l'exclusion est stockée sous l'UUID AAM transmis dans la requête ( <code> d_ uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables et syntaxe pour les ID déclarés {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

Le tableau suivant répertorie les paires clé-valeur qui transmettent votre ID de fournisseur [!DNL Audience Manager] de données et votre utilisateur - les identifiants ou les codes d'intégration, s'ils sont utilisés. Note, *italics* indicates a variable placeholder. Des espaces ont été ajoutés pour faciliter la lecture.

Dans chaque paire clé-valeur :

* Le `=` symbole sépare la clé de ses valeurs associées.
* Le caractère non imprimable [!DNL ASCII]`%01` sépare les valeurs.

<table id="table_DFA9A584A5DE40669EAF0DB62DDC5AAF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid =<i>ID du fournisseur de données</i> % 01<i>user - id</i></code> </p> </td> 
   <td colname="col2"> <p>Contient un ID de fournisseur de données et un utilisateur unique associé - id dans une paire clé-valeur unique. <code> d_ cid </code> remplace <code> d_ dpid </code> et <code> d_ dpuuid </code>, qui sont considérés comme obsolètes mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_ cid_ ic =<i>code d'intégration</i> % 01<i>user - id</i></code> </p> </td> 
   <td colname="col2"> <p>Contient un code d'intégration et un utilisateur unique associé - id dans une paire clé-valeur unique. <code> d_ cid_ ic </code> remplace <code> d_ dpid </code> et <code> d_ dpuuid </code>, qui sont obsolètes mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples d'appels d'événement {#sample-event-calls}

Étant donné ces paires clé-valeur et la syntaxe requise, vous effectuez les appels d'événement comme illustré ci-dessous.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> L'appel d'événement comprend </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identifiant de fournisseur de données et utilisateur - id. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/événement ? d_ cid = 123 01987… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Un code d'intégration et un utilisateur - id. </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/événement ? d_ cid_ ic = 456% 01321… </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs paires <code> d_ cid </code> et <code> d_ cid_ ic_ cid_ ic </code> . </p> </td> 
   <td colname="col2"> <p> <code> https://domain<i>nom</i>/événement ? d_ cid = 123 % &amp; d_ cid_ ic = 456 013 01321… </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [CID remplace DPID et DPUUID](../reference/cid.md)


## Variables d'ID déclarées {#declared-id-variables}

Décrit les variables de configuration utilisées pour transmettre les ID déclarés jusqu [!UICONTROL DIL] 'à [!DNL Audience Manager.]

## Le code DIL utilise le service Experience Cloud ID pour transmettre des ID déclarés. {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Lorsqu'il est utilisé avec le service [Experience Cloud ID,](https://marketing.adobe.com/resources/help/en_US/mcvid/)vous n'avez plus besoin de transmettre [!UICONTROL declared IDs] les variables obsolètes `dpid` et `dpuuid` variables. Les versions actuelles [!UICONTROL DIL] de la fonction reposent sur la `visitorService` fonction pour obtenir la [!UICONTROL declared IDs] fonction `setCustomerIDs` dans [!UICONTROL Experience Cloud ID Service]la fonction. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Vous pouvez appeler `visitorService` comme `DIL.create` illustré ci-dessous.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Dans la paire `namespace` clé-valeur, `MCORG` correspond à votre ID [!DNL Experience Cloud] d'organisation. Si vous ne possédez pas cet ID, vous pouvez le trouver dans la [!UICONTROL Administration] section du [!DNL Experience Cloud] tableau de bord. Vous devez disposer des autorisations d'administrateur pour afficher ce tableau de bord. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Fonctions obsolètes {#deprecated-functions}

Avec les dernières versions de [!UICONTROL DIL] (6.2 +), vous n'avez pas besoin d'utiliser ces paires clé-valeur pour transmettre [!UICONTROL declared IDs]. Cela se produit car [!UICONTROL DIL] se repose désormais sur `visitorService` la fonction illustrée dans l'exemple de code ci-dessus. Cette fonction provient [!UICONTROL declared IDs] de [!UICONTROL Experience Cloud ID Service]la. Toutefois, nous référencons ces variables ici à des fins historiques et héritées. Voir le code ci-dessous pour obtenir un exemple de configuration `DIL.create` pour obtenir un [!UICONTROL declared ID] élément de [!UICONTROL Visitor ID Service]la section.
Le tableau suivant décrit les variables héritées utilisées par l' `declaredId` objet :

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
   <td colname="col3"> <p>Identifiant de partenaire de données attribué par Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>L’identifiant unique du fournisseur de données pour l’utilisateur. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` et `DPUUID`

Audience Manager compare et correspond à l'utilisateur combiné `DPID` et `DPUUID` à un utilisateur correspondant - id dans notre système. Si un identifiant n'existe pas, Audience Manager crée un nouvel utilisateur - id et le synchronise avec `DPID/DPUUID` la combinaison. Une fois qu'Audience Manager correspond ou crée un utilisateur - id (le `UUID`), il renvoie cet identifiant dans [!DNL JSON] la réponse au cookie du domaine du client (cookie propriétaire) ou d'un autre stockage local.

Appelez cette fonction lorsque vous utilisez [!UICONTROL DIL] la version v 6.1 ou une version antérieure. Toutefois, cette fonction est déconseillée en faveur de la nouvelle version qui provient [!UICONTROL declared IDs] de [!UICONTROL Experience Cloud ID Service].

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
>Remarque : vous devez développer par programmation le code qui fournit les valeurs d'ID pour les clés `d_dpuuid` et les `d_dpid` clés.

### Transmettre les identifiants après les instanciations DIL

>[!NOTE]
>
>Si vous [!DNL API] effectuez un appel avec `declaredID` une combinaison différente, la nouvelle combinaison sera utilisée pour cet appel uniquement. D'autres appels d'événements réguliers utilisent la `DIL.create``declaredID` combinaison d'origine.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exemples de demande/réponse {#request-response-examples}

La requête envoie un fournisseur de données et un utilisateur - id à Audience Manager :

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La réponse renvoie l'identifiant Audience Manager (par exemple `UUID`,) qui est écrit dans un cookie propriétaire dans le domaine de la page.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Ne pas cibler et les appels d'exclusion {#do-not-target}

[!UICONTROL declared ID] Le processus respecte les préférences du visiteur du site pour exclure le ciblage Audience Manager de votre site Web. Lorsque Audience Manager reçoit une demande d'exclusion, la [!UICONTROL DCS] renvoie un objet vide [!DNL JSON] plutôt que l'utilisateur Audience Manager - id.
