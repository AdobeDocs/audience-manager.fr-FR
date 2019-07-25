---
description: Une configuration booléenne facultative permet de déterminer si le code DIL envoie (ou n’envoie pas) des données à Adobe Experience Cloud Device Co-op.
seo-description: Une configuration booléenne facultative permet de déterminer si le code DIL envoie (ou n’envoie pas) des données à Adobe Experience Cloud Device Co-op.
seo-title: isCoopSafe
solution: Audience Manager
title: isCoopSafe
uuid: c 5362 a 38-93 c 0-4 edb-bdcb -106 e 43 f 33 a 92
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# isCoopSafe{#iscoopsafe}

Une configuration booléenne facultative permet de déterminer si le code DIL envoie (ou n’envoie pas) des données à Adobe Experience Cloud Device Co-op.

## Conditions requises {#requirements}

To use `isCoopSafe` you must:

* Use [!UICONTROL DIL] v6.11 or higher.
* Participer à [Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/). Les membres potentiels de Co-op doivent également consulter cette documentation pour déterminer si `isCoopSafe` peut répondre à des préoccupations concernant la manière dont les données sont utilisées pour créer la coopérative Device Graph.

* Collaborer avec votre conseiller [!DNL Adobe] afin de définir un indicateur de liste blanche ou de liste noire pour votre compte Device Co-op. Il n'existe pas de chemin d'accès en libre-service pour activer ces indicateurs.

## Cas d’utilisation {#use-cases}

`isCoopSafe` permet de résoudre 2 cas d’utilisation liés à la collecte de données par des membres actuels ou potentiels de Device Co-op. Ces cas d’utilisation concernent la manière dont les données des visiteurs du site sont transmises à Device Co-op pour permettre de créer la coopérative Device Graph. Le tableau suivant décrit comment `isCoopSafe` fonctionne avec ces cas d’utilisation pour bloquer ou envoyer des données à la coopérative Device Graph.

<table id="table_A24C63D2A21F47EDBAC8FA5E7BE888D8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Visiteurs authentifiés</b> </p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code to control how data for authenticated visitors who have or have not accepted term-of-use agreements is used by the Device Co-op to build the device graph. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>DIL sur des sites tiers</b> </p> </td> 
   <td colname="col2"> <p>Add <code> isCoopSafe </code> to your <span class="wintitle"> DIL </span> code for use on third-party sites where you: </p> <p> 
     <ul id="ul_C27BB26510314834A2A7CD99D46DA4AC"> 
      <li id="li_4E6AE574F18646F09C0CF4553EEA1A9E">ne pouvez pas vous assurer que les visiteurs authentifiés ont ou n’ont pas accepté les conditions d’utilisation ; </li> 
      <li id="li_26D0561BF32B4278B0A6B5082C17FED8">devez contrôler la manière dont ces données sont utilisées par Device Co-op pour créer la coopérative Device Graph. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Syntaxe et exemple de code {#syntax-code-sample}

**Syntaxe :**`isCoopSafe: true | false`

Les options booléennes déterminent la manière dont les données des clients sont ou ne sont pas utilisées par Device Co-op.

* `isCoopSafe: true` : les données du visiteur collectées par un SDK mobile ou un site web *peuvent* être utilisées pour créer la coopérative Device Graph.

* `isCoopSafe: false` : les données du visiteur collectées par un SDK mobile ou un site web *ne peuvent pas* être utilisées pour créer la coopérative Device Graph.

**Exemple de code**

Définissez cette option lorsque DIL instancie.

```js
var dilInstance = DIL.create({ 
     ... 
     isCoopSafe: true 
});
```

## Paramètres POST de l’appel d’événement {#post-parameters}

Depending on the flag you set ( `true` or `false`), [!UICONTROL DIL] translates `isCoopSafe` into these POST parameters and sends them to [!DNL Adobe] in an event call:

* `d_coop_safe=1`
* `d_coop_unsafe=1`

Les paramètres POST indiquent à [!DNL Experience Cloud] Device Co-op si cette application peut ou non inclure des données utilisateur dans la coopérative Device Graph. Le tableau ci-dessous définit la relation entre les indicateurs booléens `isCoopSafe` et les paramètres POST transmis dans un appel d’événement. Si vous n’utilisez pas `isCoopSafe`, aucun paramètre n’est transmis dans un appel d’événement.

<table id="table_0A544534CA904F4D9836A34B8C1EACBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> État de la configuration </th> 
   <th colname="col2" class="entry"> Paramètre POST </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: true </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_safe=1 </code> </p> <p>Device Co-op peut utiliser les données du visiteur pour créer la coopérative Device Graph. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> isCoopSafe: false </code> </p> </td> 
   <td colname="col2"> <p> <code> d_coop_unsafe=1 </code> </p> <p>Device Co-op ne peut pas utiliser les données du visiteur pour créer la coopérative Device Graph. </p> </td> 
  </tr> 
 </tbody> 
</table>

## API post-instanciation {#post-instantiation}

Ces API permettent de remplacer l’état `isCoopSafe`. Elles sont nécessaires car elles permettent de modifier l’état post-instanciation/post-connexion d’un visiteur sur un site ou dans une application à une seule page dans le cas où la page ne s’actualise pas. Par exemple, vous devrez appeler ces API si un utilisateur s’authentifie auprès de votre site ou de votre application et accepte par la suite une règle des conditions d’utilisation qui autorise Device Co-op à utiliser ses données.

<table id="table_BAA96B1F82BE48C3A61A1AF1367BA45C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> API </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Dilinstance. api. setascoopsafe () ; </code> </p> </td> 
   <td colname="col2"> <p>Définit le paramètre POST <code>d_coop_safe=1</code> dans tous les appels d’événement suivants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Dilinstance. api. setascoopsafe () ; </code> </p> </td> 
   <td colname="col2"> <p>Définit le paramètre POST <code>d_coop_unsafe=1</code> dans tous les appels d’événement suivants. </p> </td> 
  </tr> 
 </tbody> 
</table>

<!-- 

Wiki page https://wiki.corp.adobe.com/x/RCfFTg

 -->

