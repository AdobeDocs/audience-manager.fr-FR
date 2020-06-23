---
description: Les options de règle de fusion vous permettent de contrôler le type d’Audience Manager de données utilisé pour la segmentation. Une règle de fusion peut inclure des profils de périphérique mappés par le graphique de périphérique Lien de Profil, Adobe Experience Cloud Device Co-op et/ou d’autres fournisseurs de graphiques de périphériques tiers intégrés à l’Audience Manager. Vous pouvez créer un maximum de 4 règles de fusion de Profils.
seo-description: Les options de règle de fusion vous permettent de contrôler le type d’Audience Manager de données utilisé pour la segmentation. Une règle de fusion peut inclure des profils de périphérique mappés par le graphique de périphérique Lien de Profil, Adobe Experience Cloud Device Co-op et/ou d’autres fournisseurs de graphiques de périphériques tiers intégrés à l’Audience Manager. Vous pouvez créer un maximum de 4 règles de fusion de Profils.
seo-title: Définition des options de règle de fusion de Profil
solution: Audience Manager
title: Définition des options de règle de fusion de Profil
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 4%

---


# [!UICONTROL Profile Merge Rules] Options définies {#profile-merge-rule-options-defined}

The [!UICONTROL profile merge rule] options let you control the type of data [!DNL Audience Manager] uses for segmentation. Un [!UICONTROL profile merge rule] peut inclure les profils de périphérique mappés par le graphique de [!UICONTROL Profile Link] périphérique, les fournisseurs [!UICONTROL Adobe Experience Cloud Device Co-op]et/ou autres fournisseurs de graphiques de périphérique tiers intégrés à [!DNL Audience Manager]. Vous pouvez créer un maximum de 4 [!UICONTROL Profile Merge Rules]. Le quatrième [!UICONTROL Profile Merge Rule] est disponible exclusivement aux clients qui ont acheté le [!UICONTROL People-Based Destinations] module complémentaire.

Vous créez un [!UICONTROL Profile Merge Rule] formulaire en effectuant une sélection à partir des options décrites ci-dessous, dans [!UICONTROL Profile Merge Rule Setup].

![profil-fusion-règle-configuration](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Présentation des options {#overview}

[!UICONTROL Profile Merge Rules] permettent un certain nombre de combinaisons de règles, chacune étant orientée vers des cas d’utilisation spécifiques. Consultez le tableau ci-dessous pour savoir quand utiliser chaque combinaison de règles.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilité | Type d’évaluation | [!UICONTROL Audience Lab] Assistance | Cas d’utilisation |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Tous les clients | Temps réel et par lot | Oui | [Ciblage de périphérique](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (inclut [!UICONTROL Co-op Device Graph]) | Tous les clients | Temps réel et par lot | Non | [Ciblage étendu des périphériques](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Tous les clients | Temps réel uniquement | Non | [Ciblage de périphériques partagés](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Tous les clients | Temps réel et par lot | Oui | [Ciblage en ligne/hors ligne](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Tous les clients | Temps réel et par lot | Oui | [Ciblage sur plusieurs périphériques](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (inclut [!UICONTROL Co-op Device Graph]) | Tous les clients | Temps réel et par lot | Non | [Ciblage avancé sur plusieurs périphériques](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | S.O. | Exclusif aux clients [des destinations](../destinations/people-based-destinations-overview.md) basées sur les personnes | Lot uniquement | Non | [Ciblage pour les destinations basées sur les personnes](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Evaluation {#segment-evaluation}

Selon votre [!UICONTROL Profile Merge Rules] configuration, [!DNL Audience Manager] peut effectuer l’ [!UICONTROL segment] évaluation en temps réel, par lot ou les deux.

* L’ [!UICONTROL segment] évaluation en temps réel nécessite que les visiteurs [!DNL DCS] puissent accéder à vos propriétés numériques en temps réel, pour être admissibles au [!UICONTROL segment]programme.
* L’ [!UICONTROL segment] évaluation du lot est effectuée par rapport à [!UICONTROL traits]la valeur précédemment qualifiée.
* [!UICONTROL Profile Merge Rules] qui prennent en charge à la fois l&#39;évaluation en temps réel et l&#39;évaluation par lots [!UICONTROL segment] combinent l&#39;activité d&#39;visiteur en temps réel avec l&#39;évaluation par lots [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Latence du Rapports {#reporting-latency}

L&#39; [!UICONTROL segment] évaluation en temps réel est immédiatement prise en compte dans les [!UICONTROL Profile Merge Rules] rapports.

L’ [!UICONTROL segment] évaluation du lot peut prendre jusqu’à 24 heures pour être prise en compte dans les rapports [Règles de fusion des](profile-link-metrics.md)Profils.

## [!UICONTROL Cross-Device Options] {#auth-options}

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
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> de ne pas utiliser les données collectées auprès d’utilisateurs authentifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profils authentifiés actuels</span></b> </p> </td> 
   <td colname="col2"> <p>Indique <span class="keyword"> à l’Audience Manager</span> de lire et d’écrire des données au profil authentifié si un visiteur s’est connecté à votre site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Derniers Profils authentifiés</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> de lire les données issues du profil authentifié de l’utilisateur qui s’est connecté pour la dernière fois sur le périphérique. </p> <p>Lorsqu’elle est sélectionnée, <span class="keyword"> l’Audience Manager</span> n’écrit pas de nouvelles données de caractéristiques sur le profil authentifié si l’utilisateur est anonyme. Lors de l’authentification, les nouvelles données de caractéristiques sont écrites dans le profil authentifié de l’utilisateur. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tous les Profils sur plusieurs périphériques</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à l’Audience Manager de lire les données de tous les profils sur plusieurs périphériques, quel que soit l’état d’authentification. Cette option est disponible uniquement pour les clients d’Audience Manager qui ont acheté le module complémentaire Destinations basées sur les personnes.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

Les [!UICONTROL Cross-Device Profile Options] listes vous [!UICONTROL cross-device data sources]. Ces options utilisent les noms que vous avez fournis lors de la création d’une [!UICONTROL cross-device][!UICONTROL data source] (voir [Création d’une source](merge-rules-start.md#create-data-source)de données sur plusieurs périphériques). Vous pouvez sélectionner jusqu’à 3 [!UICONTROL cross-device data sources] à utiliser avec chaque règle de profil. Ils [!UICONTROL Authenticated Profile Options] sont disponibles lorsque vous le souhaitez **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

Vous [!UICONTROL Device Options] pouvez sélectionner le type de *`device profile`* utilisé par un [!UICONTROL Profile Merge Rule]utilisateur. Un profil de périphérique est créé à partir [!UICONTROL traits] d’une activité de navigation anonyme. Au minimum, un [!UICONTROL profile merge rule] comprend un [!UICONTROL authenticated option] et un [!UICONTROL device option].

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
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> de ne pas utiliser les caractéristiques contenues dans le profil anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profil de périphérique</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> d’utiliser le profil de périphérique anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Graphique du périphérique de lien de Profil</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> de lire les profils du périphérique actuel et jusqu’à 100 autres périphériques à partir desquels l’utilisateur s’est authentifié. Ce graphique de périphérique est créé sur vos propres données propriétaires en <span class="keyword"> Audience Manager</span>. Il est idéal pour les clients qui disposent d’un niveau élevé d’authentification sur l’ensemble de leurs propriétés numériques. Le graphique du périphérique Lien <span class="wintitle"> de</span> Profil est mis à jour en temps réel. Cette option est disponible lorsque vous sélectionnez Profil <b><span class="uicontrol"> authentifié</span></b> actuel ou Profil <b><span class="uicontrol"></span></b>Dernière authentification. Lorsque vous utilisez cette option, vous ne pouvez choisir qu’un seul profil authentifié (<span class="keyword"> l’Audience Manager</span> grise automatiquement les autres). Voir aussi Cas <a href="profile-link-use-case.md"> d’utilisation du graphique de périphériques de lien de</a>Profil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Graphique des périphériques coopératifs</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l'Audience Manager</span> de lire les profils de l'appareil actuel et jusqu'à 100 autres appareils en utilisant les liens fournis par la <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p><span class="keyword"> Device Co-op</span> est une coopérative numérique au sein de laquelle les membres partagent des informations au sujet des liaisons de périphériques. La <span class="keyword"> Device Co-op</span> traite ces données dans un graphique <span class="term"></span>de périphérique. Un graphique de périphérique relie les périphériques à des grappes de périphériques. Ces liens sont construits à partir de données <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> probabilistes et déterministes</a>. Les grappes représentent un groupe de dispositifs utilisés par une personne inconnue. <span class="keyword">Device Co-op</span> partage ces grappes avec ses membres afin de les aider à proposer à leurs clients des contenus utiles et cohérents sur tous leurs périphériques. </p> <p> Pour plus d'informations sur <span class="wintitle"> Device Co-op</span>, consultez la section : </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Présentation de Device Co-op</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Conditions d’adhésion</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Graphique du périphérique : Processus internes et sortie</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Options</b> graphiques de périphériques tiers (personne et foyer) </p> </td>
   <td colname="col2"> <p>Ces options vous permettent de créer des règles de fusion basées sur la technologie de graphique de périphérique fournie par un fournisseur tiers. Un graphique de périphériques tiers fournit les éléments suivants : </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Données probabilistes et/ou déterministes. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Données au niveau de la personne ou du ménage. </li> 
     </ul> </p> <p>Pour utiliser ces options, vous devez être client d’un graphique de périphérique qui est déjà intégré à <span class="keyword"> l’Audience Manager</span>. Contactez votre gestionnaire de compte pour en savoir plus ou pour commencer. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Les segments d’Audience qui ont été automatiquement créés à partir d’autres [!DNL Experience Cloud] solutions, en fonction de règles de fusion définies en dehors de [!DNL Audience Manager], sont marqués comme utilisant un [!UICONTROL External Merge Policy]. Par exemple, voir Partage des [Audiences entre Audience Manager et Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [FAQ sur les règles de fusion de Profils](../../faq/faq-profile-merge.md)

