---
description: Fonctionnement des identifiants déclarés, configuration des procédures, des exemples de code et des variables.
keywords: id sync
seo-description: Fonctionnement des identifiants déclarés, configuration des procédures, des exemples de code et des variables.
seo-title: ID déclarés
solution: Audience Manager
title: ID déclarés
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# ID déclarés {#declared-ids}

Fonctionnement des identifiants déclarés, configuration des procédures, des exemples de code et des variables.

## Ciblage de l’ID déclaré {#declared-id-targeting}

Echanger et synchroniser les ID utilisateur avec Audience Manager à partir de périphériques ou de navigateurs qui n’utilisent pas ou n’acceptent pas les mécanismes de stockage persistant, tels que les cookies tiers.

<!-- declared_id_about.xml -->

## Objectif du ciblage des identifiants déclarés {#declared-id-targeting-purpose}

Certains navigateurs et la plupart des périphériques mobiles n’acceptent pas les cookies tiers. Cela rend difficile la conservation des informations sur les visiteurs du site ou l’attribution d’ID persistants. Pour résoudre ce problème, Audience Manager vous permet [!UICONTROL DIL] de transmettre [!UICONTROL declared IDs] un appel d’événement. En outre, un [!UICONTROL declared ID] peut agir comme un ID universel qui s’applique au même utilisateur dans toutes les solutions du [!DNL Experience Cloud]. Le tableau suivant décrit le processus de ciblage/correspondance des identifiants :

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
   <td colname="col2"> <p>Pour fonctionner, vous avez besoin du code <span class="wintitle"> DIL </span> et du code du service <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> d’ID d’expérience Cloud </a> sur la page. <span class="wintitle"> Le code DIL </span> récupère les ID <span class="wintitle"> déclarés </span> de la <code> setVisitorID </code> fonction fournie par le service <span class="keyword"> d’ID d’Experience Cloud </span> <span class="keyword"> et les transmet à la  d’Audience Manager.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identifiant de correspondance</b> </td> 
   <td colname="col2"> <p>Audience Manager tente de faire correspondre l’identifiant client et l’identifiant visiteur avec un identifiant correspondant dans notre système. Si aucun ID correspondant n’existe, Audience Manager crée un nouvel ID et l’associe au client et à l’identifiant visiteur. </p> <p> <p>Remarque :  Le mappage le plus récent est utilisé si votre ID correspond à plusieurs identifiants Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retour</b> </td> 
   <td colname="col2"> <p>Audience Manager écrit son identifiant synchronisé dans un cookie propriétaire (ou tout autre espace de stockage adressable) dans le domaine ou l’application client. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Appels d’événement suivants</b> </td>
   <td colname="col2"> <p>D’autres appels d’événement lisent l’identifiant Audience Manager depuis le domaine du client et l’envoient à Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Pour commencer, vous devez configurer le service [!DNL Experience Cloud] d’ID et [!UICONTROL DIL] les pages de votre site que vous souhaitez utiliser pour la collecte de données. Voir [Création](../dil/dil-class-overview/dil-create.md#dil-create) DIL et Variables [d’ID](../features/declared-ids.md#declared-id-variables)déclarées.

## Appels d’exclusion {#opt-out-calls}

Le [!UICONTROL declared ID] processus respecte les préférences des visiteurs du site quant à l’exclusion du ciblage d’Audience Manager par votre site Web. Lorsqu’Audience Manager reçoit une demande d’exclusion, le code [!DNL JSON] renvoyé par le [!UICONTROL DCS] contient le code d’erreur 171, avec le message "Balise d’exclusion rencontrée", au lieu de l’ID utilisateur d’Audience Manager.

* Audience Manager peut transmettre une [!UICONTROL declared ID] exclusion en même temps qu’un Audience Manager [!UICONTROL UUID] dans le [!DNL URL].
* L’ [!UICONTROL declared ID] exclusion est stockée dans le serveur de cache de profil [!UICONTROL ([!UICONTROL PCS]) par partenaire. Il n’existe pas d’exclusion au niveau de la plateforme utilisant [!UICONTROL declared IDs]. De plus, Audience Manager exclut l’utilisateur de cette région spécifique sur le bord (l’exclusion ne s’applique pas à plusieurs [!UICONTROL DCS] régions).

Voir Confidentialité [des](../overview/data-security-and-privacy/data-privacy.md) données pour plus d’informations sur l’exclusion de la collecte de données.

## Exemples d’exclusion d’ID déclarés {#opt-out-examples}

Vous pouvez effectuer des demandes d’exclusion avec les paires [!UICONTROL declared ID] et `d_cid` `d_cid_ic` valeur-clé. Les paramètres hérités, comme `d_dpid` et `d_dpuuid` fonctionnent toujours, sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Exclusions avec CID et CID_IC

Pour obtenir une description et une syntaxe, voir Variables [d’URL et Syntaxe pour les ID](../features/declared-ids.md#variables-and-syntax)déclarés.

<table id="table_159D92242D8F4FCBAC733295DE474CA6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion à l’aide de </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de fournisseur de données et ID d’utilisateur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout.jpg?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code d’intégration et ID utilisateur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs paires <code> d_cid </code> et <code> d_cid_ic </code> clé-valeur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/demoptout?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exclusions avec DPID, DPUUID et UUID (obsolète)

Ces méthodes fonctionnent toujours mais sont considérées comme obsolètes. Ces informations sont fournies à des fins d’héritage et de référence. Les exclusions héritées comprennent :

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Une exclusion au niveau du partenaire est stockée pour le dernier mappage de cette paire <code> dpid </code> + <code> dpuuid </code> sur un UUID AAM. S’il n’existe aucun mappage existant auparavant, Audience Manager vérifie si la requête contient un UUID AAM dans le cookie et, le cas échéant, l’utilise pour stocker l’exclusion. Sinon, Audience Manager génère un nouvel UUID AAM et stocke l’exclusion sous-jacente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> et explicite <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> a toujours la priorité. Si la combinaison <code> dpid </code> + <code> dpuuid </code> correspond à un autre UUID AAM, l’exclusion est stockée sous l’UUID AAM transmis dans la requête ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables et syntaxe pour les ID déclarés {#variables-and-syntax}

<!-- c_declared_id_var_syntax.xml -->

Le tableau suivant répertorie les paires clé-valeur qui transmettent l’ID de votre fournisseur de [!DNL Audience Manager] données et vos ID utilisateur ou codes d’intégration, le cas échéant. Note, *italics* indicates a variable placeholder. Des espaces ont été ajoutés pour les rendre plus faciles à lire.

Dans chaque paire clé-valeur :

* Le `=` symbole sépare la clé de ses valeurs associées.
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
   <td colname="col2"> <p>Contient un ID de fournisseur de données et un ID d’utilisateur unique associé dans une seule paire clé-valeur. <code> d_cid </code> remplace <code> d_dpid </code> et <code> d_dpuuid </code>, considérés comme obsolètes, mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contient un code d’intégration et un ID utilisateur unique associé dans une seule paire clé-valeur. <code> d_cid_ic </code> remplace <code> d_dpid </code> et <code> d_dpuuid </code>, qui sont obsolètes, mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples d’appels d’événement {#sample-event-calls}

Compte tenu de ces paires clé-valeur et de leur syntaxe requise, vous effectuerez des appels d’événement comme illustré ci-dessous.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> L’appel d’événement inclut </th> 
   <th colname="col2" class="entry"> Exemple de code </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de fournisseur de données et ID d’utilisateur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code d’intégration et ID utilisateur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Plusieurs paires <code> d_cid </code> et <code> d_cid_ic </code> clé-valeur. </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain name</i>/event?d_cid=123%01987&amp;d_cid_ic=456%01321... </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables d’ID déclarées {#declared-id-variables}

Décrit les variables de configuration utilisées pour transmettre les ID déclarés [!UICONTROL DIL] à [!DNL Audience Manager.]

## DIL utilise le service d’ID d’Experience Cloud pour transmettre des ID déclarés. {#dil-id-service-pass-declared-ids}

<!-- r_dil_declared_id_vars.xml -->

Lorsqu’il est utilisé avec le service [d’ID](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud, vous n’avez plus besoin de transmettre [!UICONTROL declared IDs] les variables `dpid` et `dpuuid` obsolètes. Au lieu de cela, les versions actuelles de [!UICONTROL DIL] s’appuient sur la `visitorService` fonction pour obtenir le [!UICONTROL declared IDs] de la `setCustomerIDs` fonction dans la [!UICONTROL Experience Cloud ID Service]. For more information, see [Customer IDs and Authentication States](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). Vous appelez `visitorService` dans `DIL.create` comme illustré ci-dessous.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Dans la paire `namespace` clé-valeur, `MCORG` correspond à votre [!DNL Experience Cloud] ID d’organisation. Si vous ne possédez pas cet ID, vous le trouverez dans la [!UICONTROL Administration] section du [!DNL Experience Cloud] tableau de bord. Vous avez besoin d’autorisations d’administrateur pour afficher ce tableau de bord. See [Administration: Core Services](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

## Fonctions obsolètes {#deprecated-functions}

Avec les dernières versions de [!UICONTROL DIL] (6.2+), vous n’avez pas besoin d’utiliser ces paires clé-valeur pour transmettre [!UICONTROL declared IDs]. C'est parce que [!UICONTROL DIL] maintenant repose sur la `visitorService` fonction illustrée dans l'exemple de code ci-dessus. Cette fonction provient [!UICONTROL declared IDs] du [!UICONTROL Experience Cloud ID Service]. Cependant, nous référençons ces variables ici à des fins historiques et héritées. Consultez le code ci-dessous pour obtenir un exemple de configuration `DIL.create` pour obtenir un [!UICONTROL declared ID] de la [!UICONTROL Visitor ID Service].
Le tableau suivant décrit les variables héritées utilisées par l’ `declaredId` objet :

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
   <td colname="col3"> <p>ID de partenaire de données attribué par Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> Chaîne </td> 
   <td colname="col3"> <p>L’identifiant unique du fournisseur de données pour l’utilisateur. </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPID` et `DPUUID`

Audience Manager compare et fait correspondre la combinaison `DPID` et `DPUUID` à un ID utilisateur correspondant dans notre système. Si aucun ID n’existe, Audience Manager crée un nouvel ID utilisateur et le synchronise avec la `DPID/DPUUID` combinaison. Une fois qu’Audience Manager correspond ou crée un ID utilisateur (le `UUID`), il renvoie cet ID dans la [!DNL JSON] réponse au cookie dans le domaine du client (cookie propriétaire) ou dans un autre stockage local.

Appelez cette fonction lorsque vous utilisez [!UICONTROL DIL] la version 6.1 ou une version antérieure. Cependant, cette fonction a été déconseillée au profit de la nouvelle version qui provient [!UICONTROL declared IDs] de [!UICONTROL Experience Cloud ID Service].

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
>Remarque : vous devez développer par programmation le code qui fournit les valeurs d’ID pour les clés `d_dpuuid` et `d_dpid` .

### Transmission des ID après l’installation du code DIL

>[!NOTE]
>
>Si vous effectuez un [!DNL API] appel avec une `declaredID` combinaison différente, la nouvelle combinaison sera utilisée pour cet appel uniquement. D'autres appels d'événement réguliers utiliseront la `DIL.create` combinaison originale `declaredID` .

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exemples de demande/réponse {#request-response-examples}

La requête envoie un fournisseur de données et un ID utilisateur à Audience Manager :

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La réponse renvoie l’identifiant Audience Manager (par exemple, `UUID`) écrit dans un cookie propriétaire du domaine de la page.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Ne pas cibler et ne pas exclure les appels {#do-not-target}

Le [!UICONTROL declared ID] processus respecte les préférences des visiteurs du site quant à l’exclusion du ciblage d’Audience Manager par votre site Web. Lorsqu’Audience Manager reçoit une demande d’exclusion, il [!UICONTROL DCS] renvoie un [!DNL JSON] objet vide au lieu de l’ID utilisateur d’Audience Manager.

>[!MORELIKETHIS]
>
>* [CID remplace DPID et DPUUID](../reference/cid.md)

