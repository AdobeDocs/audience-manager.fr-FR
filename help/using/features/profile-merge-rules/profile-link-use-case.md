---
description: Recommandations et cas d'utilisation pour le reciblage de segments et la qualification des segments personnalisés avec le graphique du périphérique Link Link.
seo-description: Recommandations et cas d'utilisation pour le reciblage de segments et la qualification des segments personnalisés avec le graphique du périphérique Link Link.
seo-title: Cas d'utilisation du graphique de périphérique de lien de profil
solution: Audience Manager
title: Cas d'utilisation du graphique de périphérique de lien de profil
uuid: bd 5567 fd-fcd 5-40 ba-b 6 f 1-035 d 2 ddbcd 3 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Profile Link Device Graph Use Cases {#profile-link-device-graph-use-cases}

Recommendations and use cases for segment retargeting and personalized segment qualification with the [!UICONTROL Profile Link] device graph.

## Recommandations {#recommendations}

Consider the [!UICONTROL Profile Link] device graph for campaigns that:

* Posséder un haut niveau d&#39;authentification dans leurs propriétés numériques. Use an [external device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a small amount of authenticated users.
* Demander un ciblage précis des audiences connues. The [!UICONTROL Profile Link device graph] is built using first-party, authenticated data.
* Ciblez les audiences connues dans leurs états authentifiés et non authentifiés en temps réel.

![](assets/merge-rule-triangle2.png)

## Retargeting Use Case and Profile Merge Rule Configuration {#retargeting-use-cases}

Reciblage des audiences qui ont déjà été authentifiées sur site et/ou dans l&#39;application sur plusieurs périphériques. Les segments peuvent être composés des profils suivants :

* Dernier profil de périphérique authentifié connu.
* Activité anonyme sur chaque profil de périphérique.

>[!NOTE]
>
>Les informations de caractéristique provenant de l&#39;un des types de profil peuvent être utilisées pour créer le segment.

### Exemple de reciblage

Voyons comment cela fonctionne avec un exemple de société de carte de crédit. Cet exemple utilise les informations de caractéristique collectées à partir d&#39;activités anonymes visualisées sur 3 profils de périphérique uniquement.

<table id="table_8C5ABA47A0634EBA9B1AA1B5C2AABF07"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p>Cette situation utilise les conditions suivantes : </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">Un utilisateur dispose de 3 appareils et a été la dernière personne à s'authentifier sur le site/l'application de la société de carte de crédit sur tous les 3 périphériques. </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">Sur le premier périphérique, un utilisateur dans un état non authentifié affiche une offre pour une carte de crédit supérieure. </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">Sur le second périphérique, un utilisateur dans un état non authentifié affiche la page des avantages de carte de crédit supérieure. </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">Sur le troisième périphérique, un utilisateur dans un état non authentifié affiche la carte des frais et des taux de carte de crédit Premium. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">Fusionne l'activité anonyme non authentifiée collectée sur les 3 périphériques à l'aide du dernier profil authentifié sur le périphérique actuel. </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">Evalue l'utilisateur anonyme pour la qualification des segments en fonction de : 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">Combinaison d'activités anonymes sur les 3 périphériques. </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">Dernier profil authentifié sur le périphérique actuel. </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">Envoie le segment à une destination en temps réel pour le reciblage sur l'ensemble des 3 périphériques. </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple de règle de fusion des profils

To set up retargeting with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] Les options sont différentes de cet exemple, car ces paramètres utilisent les noms des sources de données inter-périphériques.

![Configuration des règles de fusion du profil](assets/merge-rules-internal3.png)

## Personalization Use Case and Profile Merge Rule Configuration {#personalization-use-case}

Personnalisez l&#39;expérience pour les audiences authentifiées sur site et/ou dans l&#39;application en fonction de l&#39;activité sur plusieurs périphériques. Les segments peuvent être composés des profils suivants :

* Profil de périphérique authentifié actuellement.
* Profils de périphérique anonymes.

>[!NOTE]
>
>Un utilisateur doit être dans un état authentifié pour remplir un segment.

### Exemple de personnalisation

Voyons comment cela fonctionne avec un exemple de société de carte de crédit.

<table id="table_D2F4D5D27EB54224BB2CC1D843DDEDA3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2"> <p>Notre cas d'utilisation suppose les conditions suivantes : </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">Un utilisateur dispose de 3 appareils et a été la dernière personne à s'authentifier sur le site/l'application de la société de carte de crédit sur tous les 3 périphériques. </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">Sur le premier périphérique, un utilisateur dans un état non authentifié affiche une offre pour une carte de crédit supérieure. </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">Sur le second périphérique, un utilisateur dans un état non authentifié affiche la page des avantages de carte de crédit supérieure. </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">Sur le troisième périphérique, un utilisateur dans un état non authentifié affiche la carte des frais et des taux de carte de crédit Premium. </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">Sur l'un de ces dispositifs, le client s'authentifie (en se connectant) pour vérifier son solde. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">Fusionne l'activité anonyme non authentifiée collectée sur les 3 périphériques à l'aide du profil authentifié actuel. Le profil authentifié fournit un identifiant commun sur chaque périphérique. </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">Evalue l'utilisateur authentifié pour la qualification des segments en fonction de : 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">Combinaison d'activités anonymes sur les 3 périphériques. </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">Leur profil authentifié actuel. </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">Envoie le segment à une destination en temps réel pour créer une expérience de navigation personnalisée pour l'utilisateur lors de son authentification sur son périphérique actuel. <p>Remarque : Cela qualifie les 3 périphériques du segment, quel que soit l'état d'authentification. Ce résultat peut entraîner des problèmes de confidentialité s'il s'agit de périphériques partagés. </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### Exemple de règle de fusion de profil de personnalisation

To set up personalization with [!UICONTROL Profile Link], your [!UICONTROL Authenticated Options] and [!UICONTROL Device Options] should look like the rule configuration shown below. [!UICONTROL Authenticated Profile] Les options sont différentes de cet exemple, car ces paramètres utilisent les noms des sources de données inter-périphériques.

![](assets/merge-rules-internal4.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Cas d’utilisation graphiques des périphériques externes](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Cas d&#39;utilisation général pour les règles de fusion de profils](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [FAQ sur la fusion des profils](../../faq/faq-profile-merge.md)

