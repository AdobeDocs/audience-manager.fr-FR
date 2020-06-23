---
description: Fonctionnement des identifiants déclarés, configuration de procédures, d’exemples de code et de variables.
keywords: id sync
seo-description: Fonctionnement des identifiants déclarés, configuration de procédures, d’exemples de code et de variables.
seo-title: ID déclarés
solution: Audience Manager
title: ID déclarés
uuid: 49bb4f7e-b4a7-4d87-a29c-c3dca036d2a3
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1191'
ht-degree: 3%

---


# [!UICONTROL Declared IDs] {#declared-ids}

Comment [!UICONTROL declared IDs] fonctionner, configurer des procédures, des exemples de code et des variables.

## [!UICONTROL Declared ID] Ciblage {#declared-id-targeting}

Échangez et synchronisez les identifiants des utilisateurs avec [!DNL Audience Manager] les périphériques ou navigateurs qui n’utilisent pas ou n’acceptent pas les mécanismes d’enregistrement persistants, tels que les tiers [!DNL cookies].

## Objectif du [!UICONTROL Declared ID] ciblage {#declared-id-targeting-purpose}

Certains navigateurs et la plupart des périphériques mobiles n’acceptent pas les tiers [!DNL cookies]. Il est donc difficile de conserver des informations sur les visiteurs du site ou d’attribuer des identifiants persistants. Pour résoudre ce problème, [!DNL Audience Manager] utilise [!UICONTROL DIL] pour vous permettre de transmettre [!UICONTROL declared IDs] un appel de événement. En outre, un [!UICONTROL declared ID] peut agir en tant qu’identifiant universel qui s’applique au même utilisateur dans toutes les solutions du [!DNL Experience Cloud]. Le tableau suivant décrit le processus de ciblage/correspondance des identifiants :

<table id="table_5D59CD5AF70B44C3B45D279283D4691F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Processus </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Appel Événement</b> </td> 
   <td colname="col2"> <p>Pour fonctionner, vous avez besoin de <span class="wintitle"> code DIL </span> et du <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> code du service d'identité </a> d'Adobe Experience Platform sur la page. <span class="wintitle"> Le code DIL </span> récupère les identifiants <span class="wintitle"> déclarés </span> de la <code> setVisitorID </code> fonction fournie par le service d'identité de l' <span class="keyword"> Adobe Experience Platform </span> et les transmet à l' d'Audience Manager <span class="keyword"> .</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Identifiant de correspondance</b> </td> 
   <td colname="col2"> <p>L’Audience Manager tente de faire correspondre l’ID du client et du visiteur avec un ID correspondant dans notre système. Si aucun ID correspondant n’existe, l’Audience Manager crée un nouvel ID et l’associe à l’ID du client et de l’visiteur. </p> <p> <p>Remarque :  Le mappage le plus récent est utilisé si votre ID correspond à plusieurs identifiants d’Audience Manager. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>ID de retour</b> </td> 
   <td colname="col2"> <p>L’Audience Manager écrit son identifiant synchronisé dans un cookie propriétaire (ou tout autre espace d’enregistrement adressable) dans le domaine ou l’application client. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <b>Appels de Événement consécutifs</b> </td>
   <td colname="col2"> <p>D’autres appels de événement lisent l’ID d’Audience Manager du domaine du client et l’envoient à l’Audience Manager. </p> </td>
  </tr> 
 </tbody>
</table>

Pour commencer, vous devez configurer le service d’ [!DNL Experience Cloud] ID et [!UICONTROL DIL] les pages de votre site que vous souhaitez utiliser pour la collecte de données. Voir [DIL create](../dil/dil-class-overview/dil-create.md#dil-create) and [Declared ID Variables](../features/declared-ids.md#declared-id-variables).

## Appels d’exclusion {#opt-out-calls}

Le [!UICONTROL declared ID] processus respecte les préférences du visiteur du site pour l’exclusion du [!DNL Audience Manager] ciblage par votre site Web. Lorsque [!DNL Audience Manager] reçoit une demande d’exclusion, la [!DNL JSON] valeur renvoyée par le [!DNL DCS] contient le code d’erreur 171, avec le message `Encountered opt out tag`, au lieu de l’ [!DNL Audience Manager] ID utilisateur.

* [!DNL Audience Manager] peut transmettre une [!UICONTROL declared ID] exclusion en même temps qu’une [!DNL Audience Manager][!UICONTROL UUID] dans le [!DNL URL].
* L&#39; [!UICONTROL declared ID] exclusion est stockée dans le serveur de cache de Profil [ !UICONTROL ([!UICONTROL PCS]) par partenaire. Il n’existe pas d’exclusion au niveau de la plateforme utilisant [!UICONTROL declared IDs]. En outre, [!DNL Audience Manager] désactive l’utilisateur de cette région spécifique sur le bord (l’exclusion ne s’applique pas à [!DNL DCS] plusieurs régions).

Voir Confidentialité [des](../overview/data-security-and-privacy/data-privacy.md) données pour en savoir plus sur l’exclusion de la collecte de données.

## [!UICONTROL Declared ID] Exemples d’exclusion {#opt-out-examples}

Vous pouvez effectuer des demandes d’ [!UICONTROL declared ID] exclusion avec les paires `d_cid` et `d_cid_ic` clé-valeur. Les paramètres hérités, tels que `d_dpid` et `d_dpuuid` fonctionnent toujours, sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

### Exclusions avec [!UICONTROL CID] et [!UICONTROL CID_IC]

Pour obtenir une description et une syntaxe, voir Variables [d’URL et Syntaxe pour les identifiants](../features/declared-ids.md#variables-and-syntax)déclarés.

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

### Exclusions avec [!UICONTROL DPID], [!UICONTROL DPUUID]et [!UICONTROL UUID] (obsolète)

Ces méthodes fonctionnent toujours mais sont considérées comme obsolètes. Ces renseignements sont fournis à des fins héritées et à titre de référence. Les exclusions héritées comprennent :

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
   <td colname="col2"> <p> <code> https://demoptout.jpg?d_dpuuid= user ID&amp;d_dpid= data provider ID </code> </p> <p>Une exclusion au niveau du partenaire est stockée pour la dernière mise en correspondance de cette paire <code> dpid </code> + <code> dpuuid </code> avec un UUID AAM. S’il n’existe aucun mappage existant auparavant, l’Audience Manager vérifie si la requête contient un UUID AAM dans le cookie et, dans ce cas, l’utilise pour stocker l’exclusion. Dans le cas contraire, l’Audience Manager génère un nouvel identifiant UUID AAM et stocke l’exclusion sous-jacente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid </code> + <code> d_dpid </code> et explicite <code> d_uuid </code> </p> </td> 
   <td colname="col2"> <p> <code> https://<i>domain</i>/demoptout.jpg?d_uuid= user ID&amp;d_dpuuid= data provider's user ID&amp;<i>d_dpid=data provider ID</i> </code> </p> <p> <code> d_uuid </code> a toujours la priorité. Si la combinaison <code> dpid </code> + <code> dpuuid </code> correspond à un autre UUID AAM, l’exclusion est stockée sous l’UUID AAM transmis dans la demande ( <code> d_uuid </code>). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variables et syntaxe pour [!UICONTROL Declared IDs] {#variables-and-syntax}

Le tableau suivant liste les paires clé-valeur qui transmettent l’ID de votre fournisseur de données et vos ID d’utilisateur ou codes d’intégration, le cas échéant. [!DNL Audience Manager] Note, *italics* indicates a variable placeholder. Des espaces ont été ajoutés pour les rendre plus faciles à lire.

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
   <td colname="col2"> <p>Contient un ID de fournisseur de données et un ID d’utilisateur unique associé dans une seule paire clé-valeur. <code> d_cid </code> remplace <code> d_dpid </code> et <code> d_dpuuid </code>, qui sont considérés comme obsolètes, mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_cid_ic =<i>integration code</i> %01<i>user ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Contient un code d’intégration et un ID utilisateur unique associé dans une seule paire clé-valeur. <code> d_cid_ic </code> remplace <code> d_dpid </code> et <code> d_dpuuid </code>, qui sont obsolètes, mais toujours pris en charge. Voir <a href="../reference/cid.md">CID remplace DPID et DPUUID </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemples d’appels de Événement {#sample-event-calls}

Compte tenu de ces paires clé-valeur et de leur syntaxe requise, vous effectueriez des appels de événement comme illustré ci-dessous.

<table id="table_4C8E23CC663942BA8FA6BB1EE5929440"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> L'appel de Événement inclut </th> 
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

## [!UICONTROL Declared ID] Variables {#declared-id-variables}

Décrit les variables de configuration utilisées pour transmettre [!UICONTROL declared IDs][!UICONTROL DIL] à [!DNL Audience Manager.]

## [!UICONTROL DIL] utilise [!DNL Adobe Experience Platform Identity Service] to Pass [!UICONTROL Declared IDs] {#dil-id-service-pass-declared-ids}

Lorsqu&#39;il est utilisé avec le service [d&#39;identité de l&#39;](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform, il n&#39;est plus nécessaire de transmettre [!UICONTROL declared IDs] les variables `dpid` et `dpuuid` les variables obsolètes. Au lieu de cela, les versions actuelles de [!UICONTROL DIL] reposent sur la `visitorService` fonction pour obtenir la [!UICONTROL declared IDs] de la fonction `setCustomerIDs` dans le [!UICONTROL Adobe Experience Platform Identity Service]. For more information, see [Customer IDs and Authentication States](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). Vous appellerez `visitorService` dans `DIL.create` comme illustré ci-dessous.

```js
var vDil = DIL.create({
  partner:"partner name",
  visitorService:{
    namespace:"INSERT-MCORG-ID-HERE"
  }
});
```

Dans la paire `namespace` clé-valeur, `MCORG` correspond votre [!DNL Experience Cloud] ID d’organisation. Si vous ne possédez pas cet identifiant, vous pouvez le trouver dans la [!UICONTROL Administration] section du [!DNL Experience Cloud] tableau de bord. Vous avez besoin d&#39;autorisations d&#39;administrateur pour vue ce tableau de bord. See [Administration: Core Services](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html).

## Fonctions obsolètes {#deprecated-functions}

Avec les dernières versions de [!UICONTROL DIL] (6.2+), vous n&#39;avez pas besoin d&#39;utiliser ces paires clé-valeur pour transmettre [!UICONTROL declared IDs]. C&#39;est parce que [!UICONTROL DIL] maintenant repose sur la `visitorService` fonction illustrée dans l&#39;exemple de code ci-dessus. Cette fonction provient [!UICONTROL declared IDs] du [!UICONTROL Adobe Experience Platform Identity Service]. Cependant, nous référençons ces variables ici à des fins historiques et héritées. Consultez le code ci-dessous pour un exemple de configuration `DIL.create` pour obtenir un [!UICONTROL declared ID] formulaire à partir du [!UICONTROL Visitor ID Service].
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

### [!UICONTROL DPID] et [!UICONTROL DPUUID]

[!DNL Audience Manager] compare et correspond à la combinaison `DPID` et `DPUUID` à un ID utilisateur correspondant dans notre système. Si un ID n’existe pas, [!DNL Audience Manager] crée un nouvel ID utilisateur et le synchronise avec la `DPID/DPUUID` combinaison. Une fois que [!DNL Audience Manager] correspond ou crée un ID utilisateur (le `UUID`), il renvoie cet ID dans la [!DNL JSON] réponse au [!DNL cookie] domaine du client (propriétaire [!DNL cookie]) ou à un autre enregistrement local.

Appelez cette fonction lorsque vous utilisez [!UICONTROL DIL] v6.1 ou une version antérieure. Cependant, cette fonction a été abandonnée en faveur de la nouvelle version qui provient [!UICONTROL declared IDs] de la [!DNL Adobe Experience Platform Identity Service].

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
>Vous devez développer par programmation le code qui fournit les valeurs d’ID pour les clés `d_dpuuid` et `d_dpid` clés.

### Transmission d’ID après [!UICONTROL DIL] instanciation

>[!NOTE]
>
>Si vous effectuez un [!DNL API] appel avec une `declaredID` combinaison différente, la nouvelle combinaison sera utilisée pour cet appel uniquement. D&#39;autres événements réguliers utiliseront la `DIL.create` `declaredID` combinaison originale.

```js
DIL.getDil('partner name').api.signals({...}).declaredId({
  dpuuid : dpuuid
  dpid : dpid
}).submit();
```

## Exemples de demandes/réponses {#request-response-examples}

La demande envoie un fournisseur de données et un ID utilisateur à [!DNL Audience Manager]:

```
https://my_domain.net/event?d_rtbd=json&d_cb=myCallback&key=val&d_dpuuid=1234&d_dpid=5678
```

La réponse renvoie l’identifiant d’Audience Manager ( `UUID`par exemple) écrit dans un cookie propriétaire du domaine de la page.

```js
myCallback({
...
   "uuid":"abc123"
})
```

## Appels de non-Cible et d’exclusion {#do-not-target}

Le [!UICONTROL declared ID] processus respecte les préférences du visiteur du site pour l’exclusion du [!DNL Audience Manager] ciblage par votre site Web. Lorsque [!DNL Audience Manager] reçoit une demande d’exclusion, le [!DNL DCS] renvoie un [!DNL JSON] objet vide au lieu de l’ [!DNL Audience Manager] ID utilisateur.

>[!MORELIKETHIS]
>
>* [CID remplace DPID et DPUUID](../reference/cid.md)

