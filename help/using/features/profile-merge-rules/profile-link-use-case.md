---
description: Recommandations et cas d’utilisation pour le reciblage de segments et la qualification de segment personnalisée avec le graphique de périphérique Lien de profil.
seo-description: Recommandations et cas d’utilisation pour le reciblage de segments et la qualification de segment personnalisée avec le graphique de périphérique Lien de profil.
seo-title: Cas d’utilisation de graphiques de périphériques de lien de profil
solution: Audience Manager
title: Cas d’utilisation de graphiques de périphériques de lien de profil
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Cas d’utilisation de graphiques de périphériques de lien de profil {#profile-link-device-graph-use-cases}

Recommandations et cas d’utilisation pour le reciblage des segments et la qualification personnalisée des segments avec le graphique du [!UICONTROL Profile Link] périphérique.

## Recommandations {#recommendations}

Tenez compte du graphique [!UICONTROL Profile Link] de périphériques pour les campagnes qui :

* Posséder un niveau élevé d’authentification sur l’ensemble de leurs propriétés numériques. Utilisez une option [de graphique de périphérique](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) externe si vous avez un petit nombre d’utilisateurs authentifiés.
* Exiger un ciblage précis des audiences connues. Le fichier [!UICONTROL Profile Link device graph] est créé à l’aide de données propriétaires authentifiées.
* Ciblez les audiences connues dans leurs états authentifiés et non authentifiés en temps réel.

![](assets/merge-rule-triangle2.png)

## Configuration de la casse d’utilisation du reciblage et de la règle de fusion de profil {#retargeting-use-cases}

Ciblez les audiences qui ont été précédemment authentifiées sur site et/ou in-app sur plusieurs périphériques. Les segments peuvent être composés des profils suivants :

* Dernier profil de périphérique authentifié connu.
* Activité anonyme sur chaque profil de périphérique.

>[!NOTE]
>
>Les informations de caractéristiques de l’un ou l’autre type de profil peuvent être utilisées pour créer le segment.

### Exemple de ciblage

Examinons comment cela fonctionne avec un exemple de société de carte de crédit. Cet exemple utilise uniquement les informations de caractéristiques collectées à partir d’une activité anonyme vue sur 3 profils de périphérique.

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
   <td colname="col2"> <p>Ce cas d’utilisation suppose les conditions suivantes : </p> <p> 
     <ul id="ul_72373D0F304044AE84E4CC055E3E8154"> 
      <li id="li_375DA786ED4D4F18A74C8FE42ABF8448">Un utilisateur dispose de 3 périphériques et a été la dernière personne à s’authentifier sur le site/l’application de la société de carte de crédit sur les 3 périphériques. </li> 
      <li id="li_77FDBFAED21B4DE19AB2B6C112E0C64B">Sur le premier périphérique, un utilisateur dans un état non authentifié affiche une offre pour une carte de crédit Premium. </li> 
      <li id="li_D3BE1B30BCCA49EA931AA9D97DD5F86D">Sur le deuxième périphérique, un utilisateur dans un état non authentifié affiche la page des avantages de carte de crédit Premium. </li> 
      <li id="li_39D894624FC44806B6DB2C77F459B39E">Sur le troisième périphérique, un utilisateur dans un état non authentifié affiche la page des frais et tarifs de la carte de crédit payante. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Dans ces conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_1B6174F5C3AF4C32831D4217C5113789"> 
      <li id="li_98FE54696B604C3C8D93CC1C1FBB48D9">Fusionne l’activité anonyme non authentifiée collectée sur les 3 périphériques à l’aide du dernier profil authentifié sur le périphérique actuel. </li> 
      <li id="li_A73C7DCE36BA42B6BAD26D8A075416C1">Evalue l’utilisateur anonyme pour la qualification des segments en fonction des éléments suivants : 
       <ul id="ul_EF66EAFD12CA44F5ACCB66319606D937"> 
        <li id="li_541762056ECF4BC1ABF1F5116B5FED6C">Combinaison d’une activité anonyme sur les trois périphériques. </li> 
        <li id="li_C386CB62E5234E10AFEDE900ADC0E261">Dernier profil authentifié sur le périphérique actuel. </li> 
       </ul> </li> 
      <li id="li_5C9BDC8FF886494589F005C9658A923C">Envoie le segment à une destination en temps réel pour le reciblage sur les 3 périphériques. </li>
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple de règle de fusion de profil de reciblage

Pour configurer le reciblage avec [!UICONTROL Profile Link], votre [!UICONTROL Authenticated Options] et [!UICONTROL Device Options] doivent ressembler à la configuration de règle illustrée ci-dessous. Les [!UICONTROL Authenticated Profile] options seront différentes de cet exemple, car ces paramètres utilisent les noms de vos sources de données inter-périphériques.

![Configuration des règles de fusion de profil](assets/merge-rules-internal3.png)

## Configuration de la casse d’utilisation de la personnalisation et de la règle de fusion de profil {#personalization-use-case}

Personnalisez l’expérience pour les audiences authentifiées sur site et/ou in-app en fonction de l’activité sur plusieurs périphériques. Les segments peuvent être composés des profils suivants :

* Profil de périphérique actuellement authentifié.
* Profils de périphériques anonymes.

>[!NOTE]
>
>Un utilisateur doit être dans un état authentifié pour être admissible à un segment.

### Exemple de personnalisation

Examinons comment cela fonctionne avec un exemple de société de carte de crédit.

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
   <td colname="col2"> <p>Notre cas d’utilisation suppose les conditions suivantes : </p> <p> 
     <ul id="ul_C4D2108E7B1C4D3C89411A9CCCDA6DAC"> 
      <li id="li_2F10EB17466B4B91A94DF707C3CB6BE5">Un utilisateur dispose de 3 périphériques et a été la dernière personne à s’authentifier sur le site/l’application de la société de carte de crédit sur les 3 périphériques. </li> 
      <li id="li_1559C4DA51254BCF95291133F32A4057">Sur le premier périphérique, un utilisateur dans un état non authentifié affiche une offre pour une carte de crédit Premium. </li> 
      <li id="li_734465E5619C474291C42921160CEC6B">Sur le deuxième périphérique, un utilisateur dans un état non authentifié affiche la page des avantages de carte de crédit Premium. </li> 
      <li id="li_B96ABC0205384B59A1901708505B8BF8">Sur le troisième périphérique, un utilisateur dans un état non authentifié affiche la page des frais et tarifs de la carte de crédit payante. </li> 
      <li id="li_1A7BDBD546BD4B8EACF4292D885127F2">Sur l’un de ces périphériques, le client s’authentifie (en se connectant) pour vérifier son solde. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Dans ces conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_37DBF5FEABC5463D85C74AD9150EA177"> 
      <li id="li_B60FFA5CF3F64FB69997AA05595900D7">Fusionne l’activité anonyme non authentifiée collectée sur les 3 périphériques à l’aide du profil authentifié actuel. Le profil authentifié fournit un identifiant commun sur chaque périphérique. </li> 
      <li id="li_AB9FD87DD804474BA33805C364B7B92D">Evalue l’utilisateur authentifié pour la qualification des segments en fonction des éléments suivants : 
       <ul id="ul_EAF99E72159D4E329052B71344D9C69B"> 
        <li id="li_0B5E52BA6D8B493980291EA7B0AE235A">Combinaison d’une activité anonyme sur les trois périphériques. </li> 
        <li id="li_07588DEFBEF64F97850CB12CD62D0213">Leur profil actuel authentifié. </li> 
       </ul> </li> 
      <li id="li_E7CFCEAD7610496189F4486000D7860A">Envoie le segment à une destination en temps réel afin de créer une expérience de navigation personnalisée pour l’utilisateur lors de son authentification sur son périphérique actuel. <p>Remarque :  Ce paramètre qualifie les 3 périphériques du segment, quel que soit l’état d’authentification. Ce résultat peut entraîner des problèmes de confidentialité s’il s’agit de périphériques partagés. </p> </li>
     </ul> </p> </td>
  </tr>
 </tbody> 
</table>

### Exemple de règle de fusion de profil de personnalisation

Pour configurer la personnalisation avec [!UICONTROL Profile Link], votre [!UICONTROL Authenticated Options] et [!UICONTROL Device Options] doivent ressembler à la configuration des règles illustrée ci-dessous. Les [!UICONTROL Authenticated Profile] options seront différentes de cet exemple, car ces paramètres utilisent les noms de vos sources de données inter-périphériques.

![](assets/merge-rules-internal4.png)

Pour plus d’informations sur le fonctionnement de ces graphiques de périphériques, téléchargez nos graphiques [PDF,](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf)Audience Manager et externes.

>[!MORE_LIKE_This]
>
>* [Cas d’utilisation graphiques des périphériques externes](../../features/profile-merge-rules/external-graph-use-cases.md)
>* [Cas d’utilisation généraux des règles de fusion de profils](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

