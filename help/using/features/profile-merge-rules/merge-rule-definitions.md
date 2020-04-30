---
description: Les options de règle de fusion vous permettent de contrôler le type de données utilisé par le gestionnaire d’Audiences pour la segmentation. Une règle de fusion peut inclure des profils de périphérique mappés par le graphique de périphérique Lien de Profil, Adobe Experience Cloud Device Co-op et/ou d’autres fournisseurs de graphiques de périphériques tiers intégrés à Audience Manager. Vous pouvez créer un maximum de 4 règles de fusion de Profils.
seo-description: Les options de règle de fusion vous permettent de contrôler le type de données utilisé par le gestionnaire d’Audiences pour la segmentation. Une règle de fusion peut inclure des profils de périphérique mappés par le graphique de périphérique Lien de Profil, Adobe Experience Cloud Device Co-op et/ou d’autres fournisseurs de graphiques de périphériques tiers intégrés à Audience Manager. Vous pouvez créer un maximum de 4 règles de fusion de Profils.
seo-title: Définition des options de règle de fusion de Profil
solution: Audience Manager
title: Définition des options de règle de fusion de Profil
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Profile Merge Rules Options Defined {#profile-merge-rule-options-defined}

Les options de règle de fusion vous permettent de contrôler le type de données utilisé par le gestionnaire d’Audiences pour la segmentation. Une règle de fusion peut inclure des profils de périphérique mappés par le graphique de [!UICONTROL Profile Link] périphérique, les fournisseurs de graphiques de périphérique [!UICONTROL Adobe Experience Cloud Device Co-op]et/ou d’autres fournisseurs tiers intégrés à Audience Manager. Vous pouvez créer un maximum de 4 [!UICONTROL Profile Merge Rules]. Le quatrième [!UICONTROL Profile Merge Rule] est disponible exclusivement aux clients qui ont acheté le [!UICONTROL People-Based Destinations] module complémentaire.

Vous créez un [!UICONTROL Profile Merge Rule] formulaire en effectuant une sélection à partir des options décrites ci-dessous, dans [!UICONTROL Profile Merge Rule Setup].

![profil-fusion-règle-configuration](assets/profile-merge-rule-setup.png)

## Profile Merge Rule Options Overview {#overview}

Les règles de fusion de Profils permettent plusieurs combinaisons de règles, chacune étant orientée vers des cas d’utilisation spécifiques. Consultez le tableau ci-dessous pour savoir quand utiliser chaque combinaison de règles.

| Option sur plusieurs périphériques | Option du périphérique | Disponibilité | Type d’évaluation | Support en Audience Lab | Cas d’utilisation |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| Aucun Profil sur plusieurs périphériques | Profil de périphérique | Tous les clients | Temps réel et par lot | Oui | [Ciblage de périphérique](merge-rule-targeting-options.md#device-personalization) |
| Aucun Profil sur plusieurs périphériques | Graphique des périphériques externes (inclut le graphique des périphériques Co-op) | Tous les clients | Temps réel et par lot | Non | [Ciblage étendu des périphériques](external-graph-use-cases.md#audience-expansion) |
| Profils authentifiés actuels | Aucun Profil de périphérique | Tous les clients | Temps réel uniquement | Non | [Ciblage de périphériques partagés](merge-rule-targeting-options.md#target-shared-devices) |
| Derniers Profils authentifiés | Profil de périphérique | Tous les clients | Temps réel et par lot | Oui | [Ciblage en ligne/hors ligne](merge-rule-targeting-options.md#device-household-targeting) |
| Derniers Profils authentifiés | Graphique du périphérique de lien de Profil | Tous les clients | Temps réel et par lot | Oui | [Ciblage sur plusieurs périphériques](profile-link-use-case.md#cross-device-personalization) |
| Derniers Profils authentifiés | Graphique des périphériques externes (inclut le graphique des périphériques Co-op) | Tous les clients | Temps réel et par lot | Non | [Ciblage avancé sur plusieurs périphériques](external-graph-use-cases.md#advanced-graph-expansion) |
| Tous les Profils sur plusieurs périphériques | S.O. | Exclusif aux clients [des destinations](../destinations/people-based-destinations-overview.md) basées sur les personnes | Lot uniquement | Non | [Ciblage pour les destinations basées sur les personnes](merge-rule-targeting-options.md#all-cross-device) |

## Évaluation des segments de règle de fusion de Profils {#segment-evaluation}

Selon votre [!UICONTROL Profile Merge Rules] configuration, Audience Manager peut effectuer l’évaluation des segments en temps réel, par lot ou les deux.

* L’évaluation des segments en temps réel requiert que les visiteurs [!DNL DCS] puissent accéder à vos propriétés numériques en temps réel, afin de pouvoir bénéficier du segment.
* L’évaluation des segments par lot est effectuée par rapport aux caractéristiques précédemment qualifiées.
* [!UICONTROL Profile Merge Rules] qui prennent en charge l&#39;évaluation des segments en temps réel et par lots combinent l&#39;activité visiteur en temps réel avec des caractéristiques précédemment qualifiées.

## Latence du Rapports des règles de fusion de Profils {#reporting-latency}

L’évaluation des segments en temps réel est immédiatement prise en compte dans les [!UICONTROL Profile Merge Rules] rapports.

L’évaluation des segments par lot peut prendre jusqu’à 24 heures pour être prise en compte dans les rapports [Règles de fusion des](profile-link-metrics.md)Profils.

## Options sur plusieurs périphériques {#auth-options}

Elle [!UICONTROL Cross-Device Options] vous permet de sélectionner des utilisateurs authentifiés et non authentifiés et d’exploiter leur profil sur plusieurs périphériques pour la segmentation. Ces options vous aident à identifier et à atteindre des utilisateurs spécifiques sur un périphérique partagé. Pour plus d’informations sur les utilisateurs anonymes et authentifiés, voir Etats d’authentification des [Visiteurs dans Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option sur plusieurs périphériques </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aucun Profil sur plusieurs périphériques</span></b> </p> </td> 
   <td colname="col2"> <p>Indique au gestionnaire <span class="keyword"></span> d’Audiences de ne pas utiliser les données collectées auprès d’utilisateurs authentifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profils authentifiés actuels</span></b> </p> </td> 
   <td colname="col2"> <p>Indique au gestionnaire <span class="keyword"></span> d’Audiences de lire et d’écrire des données au profil authentifié si un visiteur s’est connecté à votre site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Derniers Profils authentifiés</span></b> </p> </td> 
   <td colname="col2"> <p>Indique <span class="keyword"> au Gestionnaire</span> des Audiences de lire les données du profil authentifié de l’utilisateur qui s’est connecté pour la dernière fois sur le périphérique. </p> <p>Lorsqu’elle est sélectionnée, <span class="keyword"> Audience Manager</span> n’écrit pas de nouvelles données de caractéristiques sur le profil authentifié si l’utilisateur est anonyme. Lors de l’authentification, les nouvelles données de caractéristiques sont écrites dans le profil authentifié de l’utilisateur. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tous les Profils sur plusieurs périphériques</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à Audience Manager de lire les données de tous les profils sur plusieurs périphériques, quel que soit l’état d’authentification. Cette option est disponible uniquement pour les clients du gestionnaire d’Audiences qui ont acheté le module complémentaire Destinations basées sur les personnes.</p> </td>
  </tr>
 </tbody>
</table>

## Options de Profil sur plusieurs périphériques {#profile-options}

La [!UICONTROL Cross-Device Profile Options] liste vos sources de données sur plusieurs périphériques. Ces options utilisent les noms que vous avez fournis lors de la création d’une source de données sur plusieurs périphériques (voir [Création d’une source](merge-rules-start.md#create-data-source)de données sur plusieurs périphériques). Vous pouvez sélectionner jusqu’à 3 sources de données sur plusieurs périphériques à utiliser avec chaque règle de profil. Ils [!UICONTROL Authenticated Profile Options] sont disponibles lorsque vous le souhaitez **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## Options de périphérique {#device-options}

Vous [!UICONTROL Device Options] pouvez sélectionner le type de *`device profile`* utilisé par un [!UICONTROL Profile Merge Rule]utilisateur. Un profil de périphérique est créé à partir de caractéristiques collectées à partir d’une activité de navigation anonyme. Au minimum, une règle de fusion de profil inclut une option authentifiée et une option de périphérique.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option du périphérique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aucun Profil de périphérique</span></b> </p> </td> 
   <td colname="col2"> <p>Indique au gestionnaire <span class="keyword"></span> d’Audiences de ne pas utiliser les caractéristiques contenues dans le profil anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profil de périphérique</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> d’utiliser le profil de périphérique anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Graphique du périphérique de lien de Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire les profils du périphérique actuel et jusqu’à 100 autres périphériques à partir desquels l’utilisateur s’est authentifié. Ce graphique de périphérique est créé à partir de vos propres données propriétaires dans <span class="keyword"> Audience Manager</span>. Il est idéal pour les clients qui disposent d’un niveau élevé d’authentification sur l’ensemble de leurs propriétés numériques. Le graphique du périphérique Lien <span class="wintitle"> de</span> Profil est mis à jour en temps réel. Cette option est disponible lorsque vous sélectionnez Profil <b><span class="uicontrol"> authentifié</span></b> actuel ou Profil <b><span class="uicontrol"></span></b>Dernière authentification. Lorsque vous utilisez cette option, vous ne pouvez choisir qu’un seul profil authentifié (<span class="keyword"> Audience Manager</span> grise automatiquement les autres). Voir aussi Cas <a href="profile-link-use-case.md"> d’utilisation du graphique de périphériques de lien de</a>Profil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Graphique des périphériques coopératifs</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire les profils du périphérique actuel et jusqu’à 100 autres périphériques à l’aide des liens fournis par <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> est une coopérative numérique au sein de laquelle les membres partagent des informations au sujet des liaisons de périphériques. La <span class="keyword"> Device Co-op</span> traite ces données dans un graphique <span class="term"></span>de périphérique. Un graphique de périphérique relie les périphériques à des grappes de périphériques. Ces liens sont construits à partir de données <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> probabilistes et déterministes</a>. Les grappes représentent un groupe de dispositifs utilisés par une personne inconnue. <span class="keyword">Device Co-op</span> partage ces grappes avec ses membres afin de les aider à proposer à leurs clients des contenus utiles et cohérents sur tous leurs périphériques. </p> <p> Pour plus d'informations sur <span class="wintitle"> Device Co-op</span>, consultez la section : </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Présentation de Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Conditions d’adhésion</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Graphique du périphérique : Processus internes et sortie</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Graphiques</a> de Audience Manager et de périphériques externes (téléchargement au format PDF). </li>
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

<!--Victor/Vlad: In the above table, you link to a .pdf file on marketing.adobe.com. Can you move that PDF into Git and link to it? This pdf might get blown away with the marketing.adobe.com decommission. -Bob-->

## Stratégies de fusion externe {#external-merge-policies}

Les segments d’Audience qui ont été automatiquement créés à partir d’autres solutions Experience Cloud, en fonction de règles de fusion définies en dehors d’Audience Manager, sont marqués comme utilisant une [!UICONTROL External Merge Policy]variable. Par exemple, voir Partage [d’Audiences entre Audience Manager et Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [FAQ sur les règles de fusion de Profils](../../faq/faq-profile-merge.md)

