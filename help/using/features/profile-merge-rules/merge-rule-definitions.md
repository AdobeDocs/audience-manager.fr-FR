---
description: Les options de règle de fusion vous permettent de contrôler le type de données utilisé par Audience Manager pour la segmentation. Une règle de fusion peut inclure les profils de périphérique mappés par le graphique de périphérique Lien de profil, Adobe Experience Cloud Device Co-op et/ou d’autres fournisseurs de graphiques de périphériques tiers intégrés à Audience Manager. Vous pouvez créer un maximum de 4 règles de fusion de profils.
seo-description: Les options de règle de fusion vous permettent de contrôler le type de données utilisé par Audience Manager pour la segmentation. Une règle de fusion peut inclure les profils de périphérique mappés par le graphique de périphérique Lien de profil, Adobe Experience Cloud Device Co-op et/ou d’autres fournisseurs de graphiques de périphériques tiers intégrés à Audience Manager. Vous pouvez créer un maximum de 4 règles de fusion de profils.
seo-title: Définition des options de règle de fusion de profil
solution: Audience Manager
title: Définition des options de règle de fusion de profil
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

Les options de règle de fusion vous permettent de contrôler le type de données utilisé par Audience Manager pour la segmentation. Une règle de fusion peut inclure les profils de périphérique mappés par le graphique de périphérique, le [!UICONTROL Profile Link] [!UICONTROL Adobe Experience Cloud Device Co-op]fournisseur de graphiques de périphérique tiers et/ou d’autres fournisseurs de graphiques de périphérique tiers intégrés à Audience Manager. Vous pouvez créer un maximum de 4 [!UICONTROL Profile Merge Rules]. La quatrième [!UICONTROL Profile Merge Rule] est réservée aux clients qui ont acheté le [!UICONTROL People-Based Destinations] module complémentaire.

Vous créez un [!UICONTROL Profile Merge Rule] formulaire en effectuant une sélection à partir des options décrites ci-dessous, dans [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

Les règles de fusion de profils permettent plusieurs combinaisons de règles, chacune étant orientée vers des cas d’utilisation spécifiques. Consultez le tableau ci-dessous pour savoir quand utiliser chaque combinaison de règles.

| Option sur plusieurs périphériques | Option de périphérique | Disponibilité | Type d’évaluation | Prise en charge d’Audience Lab | Cas d’utilisation |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| Aucun profil sur plusieurs périphériques | Profil du périphérique | Tous les clients | Temps réel et lot | Oui | [Ciblage de périphériques](merge-rule-targeting-options.md#device-personalization) |
| Aucun profil sur plusieurs périphériques | Graphique de périphérique externe (inclut graphique de périphérique Co-op) | Tous les clients | Temps réel et lot | Non | [Ciblage étendu des périphériques](external-graph-use-cases.md#audience-expansion) |
| Profils authentifiés actuels | Aucun profil de périphérique | Tous les clients | Temps réel uniquement | Non | [Ciblage de périphériques partagés](merge-rule-targeting-options.md#target-shared-devices) |
| Derniers profils authentifiés | Profil du périphérique | Tous les clients | Temps réel et lot | Oui | [Ciblage en ligne/hors ligne](merge-rule-targeting-options.md#device-household-targeting) |
| Derniers profils authentifiés |  Graphique de périphérique de lien de profil | Tous les clients | Temps réel et lot | Oui | [Ciblage sur plusieurs périphériques](profile-link-use-case.md#cross-device-personalization) |
| Derniers profils authentifiés | Graphique de périphérique externe (inclut graphique de périphérique Co-op) | Tous les clients | Temps réel et lot | Non | [Ciblage avancé sur plusieurs périphériques](external-graph-use-cases.md#advanced-graph-expansion) |
|  Tous les profils sur plusieurs périphériques | S.O. | Exclusif aux clients des destinations [basées sur les](../destinations/people-based-destinations-overview.md) personnes | Lot uniquement | Non | [Ciblage pour les destinations basées sur les personnes](merge-rule-targeting-options.md#all-cross-device) |

## Évaluation du segment de règle de fusion de profils {#segment-evaluation}

Selon votre [!UICONTROL Profile Merge Rules] configuration, Audience Manager peut effectuer l’évaluation des segments en temps réel, par lot ou les deux.

* L’évaluation des segments en temps réel requiert que les visiteurs [!DNL DCS] voient vos propriétés numériques en temps réel, afin de pouvoir bénéficier du segment.
* L’évaluation des segments par lots est effectuée par rapport aux caractéristiques précédemment qualifiées.
* [!UICONTROL Profile Merge Rules] qui prennent en charge l’évaluation des segments en temps réel et par lot combinent l’activité des visiteurs en temps réel aux caractéristiques précédemment qualifiées.

## Règles de fusion de profils Latence des rapports {#reporting-latency}

L’évaluation des segments en temps réel est immédiatement reflétée dans les [!UICONTROL Profile Merge Rules] rapports.

L’évaluation des segments par lot peut prendre jusqu’à 24 heures pour être prise en compte dans les rapports [Règles de fusion des](profile-link-metrics.md)profils.

## Options sur plusieurs périphériques {#auth-options}

Vous [!UICONTROL Cross-Device Options] pouvez sélectionner des utilisateurs authentifiés et non authentifiés et exploiter leur profil sur plusieurs périphériques pour la segmentation. Ces options vous aident à identifier et à atteindre des utilisateurs spécifiques sur un périphérique partagé. Pour plus d’informations sur les utilisateurs anonymes et authentifiés, voir Etats d’authentification des [visiteurs dans Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option sur plusieurs périphériques </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aucun profil sur plusieurs périphériques</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de ne pas utiliser les données collectées auprès d’utilisateurs authentifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profils authentifiés actuels</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire et d’écrire des données dans le profil authentifié si un visiteur s’est connecté à votre site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Derniers profils authentifiés</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire les données du profil authentifié de l’utilisateur qui s’est connecté pour la dernière fois sur le périphérique. </p> <p>Lorsqu’il est sélectionné, <span class="keyword"> Audience Manager</span> n’écrit pas de nouvelles données de caractéristiques dans le profil authentifié si l’utilisateur est anonyme. Lors de l’authentification, les nouvelles données de caractéristique sont écrites dans le profil authentifié de l’utilisateur. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tous les profils sur plusieurs périphériques</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à Audience Manager de lire les données de tous les profils multipériphériques, quel que soit l’état d’authentification. Cette option est disponible uniquement pour les clients d’Audience Manager qui ont acheté le module complémentaire Destinations basées sur les personnes.</p> </td>
  </tr>
 </tbody>
</table>

## Options de profil sur plusieurs périphériques {#profile-options}

La [!UICONTROL Cross-Device Profile Options] liste répertorie vos sources de données sur plusieurs périphériques. Ces options utilisent les noms que vous avez fournis lors de la création d’une source de données sur plusieurs périphériques (voir [Création d’une source](merge-rules-start.md#create-data-source)de données sur plusieurs périphériques). Vous pouvez sélectionner jusqu’à 3 sources de données inter-périphériques à utiliser avec chaque règle de profil. Elles [!UICONTROL Authenticated Profile Options] sont disponibles au choix **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## Options du périphérique {#device-options}

Vous [!UICONTROL Device Options] pouvez sélectionner le type de *`device profile`* utilisé par un [!UICONTROL Profile Merge Rule]. Un profil de périphérique est créé à partir de caractéristiques collectées à partir d’une activité de navigation anonyme. Au minimum, une règle de fusion de profil comprend une option authentifiée et une option de périphérique.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option de périphérique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aucun profil de périphérique</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de ne pas utiliser les caractéristiques contenues dans le profil anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profil du périphérique</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> d’utiliser le profil de périphérique anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Graphique de périphérique de lien de profil</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire les profils du périphérique actuel et jusqu’à 100 autres périphériques à partir desquels l’utilisateur s’est authentifié. Ce graphique de périphérique est construit sur vos propres données propriétaires dans <span class="keyword"> Audience Manager</span>. Il est idéal pour les clients qui disposent d’un niveau élevé d’authentification sur leurs propriétés numériques. Le graphique du périphérique Lien <span class="wintitle"></span> de profil est mis à jour en temps réel. Cette option est disponible lorsque vous sélectionnez Profil <b><span class="uicontrol"> authentifié</span></b> actif ou Dernier profil <b><span class="uicontrol"> authentifié</span></b>. Lorsque vous utilisez cette option, vous ne pouvez choisir qu’un seul profil authentifié (<span class="keyword"> Audience Manager</span> grise automatiquement les autres). Voir aussi Cas <a href="profile-link-use-case.md"></a>d’utilisation de graphiques de périphériques de lien de profil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Graphique du périphérique de co-op</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire les profils du périphérique actuel et jusqu’à 100 autres périphériques à l’aide des liens fournis par <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> est une coopérative numérique au sein de laquelle les membres partagent des informations au sujet des liaisons de périphériques. La <span class="keyword"> Device Co-op</span> traite ces données dans un graphique <span class="term"> de</span>périphérique. Un graphique de périphérique relie les périphériques à des grappes de périphériques. Ces liens sont construits à partir de données <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> probabilistes et déterministes</a>. Les grappes représentent un groupe de dispositifs utilisés par une personne inconnue. <span class="keyword">Device Co-op</span> partage ces grappes avec ses membres afin de les aider à proposer à leurs clients des contenus utiles et cohérents sur tous leurs périphériques. </p> <p> Pour plus d'informations sur <span class="wintitle"> Device Co-op</span>, consultez la section : </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Présentation de Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Conditions d’adhésion</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Graphique du périphérique : Processus internes et sortie</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager et graphiques</a> de périphériques externes (téléchargement PDF). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Options</b> graphiques de périphériques tiers (personne et foyer) </p> </td>
   <td colname="col2"> <p>Ces options vous permettent de créer des règles de fusion basées sur la technologie de graphique de périphérique fournie par un fournisseur tiers. Un graphique de périphériques tiers fournit les éléments suivants : </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Données probabilistes et/ou déterministes. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Données au niveau de la personne ou du ménage. </li> 
     </ul> </p> <p>Pour utiliser ces options, vous devez être client d’un graphique de périphérique qui est déjà intégré à <span class="keyword"> Audience Manager</span>. Contactez votre gestionnaire de compte pour en savoir plus ou pour commencer. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

