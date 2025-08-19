---
description: Les options des règles de fusion vous permettent de contrôler le type de données qu’Audience Manager utilise pour la segmentation. Une règle de fusion peut inclure des profils d’appareil mappés par le graphique d’appareil Profile Link et/ou d’autres fournisseurs tiers de graphique d’appareil intégrés à Audience Manager. Vous pouvez créer un maximum de 4 règles de fusion de profil.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Options De Règle De Fusion De Profil Définies
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# Options de [!UICONTROL Profile Merge Rules] définies {#profile-merge-rule-options-defined}

Les options [!UICONTROL profile merge rule] vous permettent de contrôler le type de données que [!DNL Audience Manager] utilisez pour la segmentation. Un [!UICONTROL profile merge rule] peut inclure des profils d’appareil mappés par le graphique d’appareil [!UICONTROL Profile Link] et/ou d’autres fournisseurs tiers de graphique d’appareil intégrés à [!DNL Audience Manager]. Vous pouvez créer 4 [!UICONTROL Profile Merge Rules] maximum. Le quatrième [!UICONTROL Profile Merge Rule] est disponible exclusivement pour les clients qui ont acheté le module complémentaire [!UICONTROL People-Based Destinations].

Vous créez un [!UICONTROL Profile Merge Rule] en effectuant une sélection parmi les options décrites ci-dessous, dans [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Présentation des options de [!UICONTROL Profile Merge Rule] {#overview}

[!UICONTROL Profile Merge Rules] permettent un certain nombre de combinaisons de règles, chacune orientée vers des cas d’utilisation spécifiques. Pour plus d’informations sur l’utilisation de chaque combinaison de règles, consultez le tableau ci-dessous.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilité | Type d’évaluation | Assistance [!UICONTROL Audience Lab] | Cas d’utilisation |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Tous les clients | Temps réel et par lots | Oui | [Ciblage des appareils](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Tous les clients | Temps réel et par lots | Non | [Ciblage d’appareil étendu](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Tous les clients | Temps réel uniquement | Non | [Ciblage des appareils partagés](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Tous les clients | Temps réel et par lots | Oui | [ Ciblage en ligne/hors ligne ](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Tous les clients | Temps réel et par lots | Oui | [Ciblage inter-appareils](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Tous les clients | Temps réel et par lots | Non | [Ciblage avancé sur l’ensemble des appareils](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | S.O. | Exclusif aux clients [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md) | Lot uniquement | Non | [Ciblage des destinations basées sur les personnes](merge-rule-targeting-options.md#all-cross-device) |

## Évaluation [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] {#segment-evaluation}

Selon la configuration de votre [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] pouvez effectuer l’évaluation [!UICONTROL segment] en temps réel, par lots, ou les deux.

* L’évaluation des [!UICONTROL segment] en temps réel nécessite que le [!DNL DCS] voie les visiteurs accéder à vos propriétés numériques en temps réel, pour être qualifiés pour le [!UICONTROL segment].
* L’évaluation du [!UICONTROL segment] par lots est effectuée par rapport aux [!UICONTROL traits] qualifiés précédemment.
* Les [!UICONTROL Profile Merge Rules] qui prennent en charge l’évaluation des [!UICONTROL segment] en temps réel et par lots combinent l’activité visiteur en temps réel avec des [!UICONTROL traits] qualifiés précédemment.

## Latence de création de rapports [!UICONTROL Profile Merge Rules] {#reporting-latency}

L’évaluation des [!UICONTROL segment] en temps réel se reflète immédiatement dans les rapports [!UICONTROL Profile Merge Rules].

L’évaluation des [!UICONTROL segment] par lots peut prendre jusqu’à 24 heures dans les rapports [Règles de fusion de profil](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

Les [!UICONTROL Cross-Device Options] vous permettent de sélectionner des utilisateurs authentifiés et non authentifiés et d’exploiter leur profil sur l’ensemble des appareils pour la segmentation. Ces options vous aident à identifier et à atteindre des utilisateurs et utilisatrices spécifiques sur un appareil partagé. Pour plus d’informations sur les utilisateurs anonymes et authentifiés, voir [États de l’authentification des visiteurs dans Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option Sur Plusieurs Appareils </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aucun Profil Sur L’Ensemble Des Appareils </span></b> </p> </td> 
   <td colname="col2"> <p>Indique <span class="keyword"> Audience Manager </span> ne pas utiliser les données collectées auprès des utilisateurs authentifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> les profils authentifiés actuels</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire et d’écrire des données dans le profil authentifié si un visiteur s’est connecté à votre site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> derniers profils authentifiés</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire les données du profil authentifié de la dernière personne connectée à l’appareil. </p> <p>Lorsque cette option est sélectionnée, <span class="keyword"> Audience Manager</span> n’écrit pas de nouvelles données de caractéristiques dans le profil authentifié si l’utilisateur est anonyme. Lors de l’authentification, les nouvelles données de caractéristique sont écrites dans le profil authentifié de l’utilisateur. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tous Les Profils Sur Plusieurs Appareils</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à Audience Manager de lire les données de tous les profils sur l’ensemble des appareils, quel que soit l’état d’authentification. Cette option n’est disponible que pour les clients Audience Manager qui ont acheté le module complémentaire Destinations basées sur les personnes .</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

La [!UICONTROL Cross-Device Profile Options] répertorie vos [!UICONTROL cross-device data sources]. Ces options utilisent les noms que vous avez fournis lors de la création d’une [!UICONTROL cross-device] de [!UICONTROL data source] (voir [Création d’une Source de données entre appareils](merge-rules-start.md#create-data-source)). Vous pouvez sélectionner jusqu’à 3 [!UICONTROL cross-device data sources] à utiliser avec chaque règle de profil. Les [!UICONTROL Authenticated Profile Options] sont disponibles lorsque vous choisissez **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

Les [!UICONTROL Device Options] vous permettent de sélectionner le type de *`device profile`* utilisé par un [!UICONTROL Profile Merge Rule]. Un profil d’appareil est créé à partir des [!UICONTROL traits] collectées lors d’une activité de navigation anonyme. Au minimum, un [!UICONTROL profile merge rule] comprend un [!UICONTROL authenticated option] et un [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option d’appareil </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aucun Profil D’Appareil</span></b> </p> </td> 
   <td colname="col2"> <p>Indique <span class="keyword"> Audience Manager </span> ne pas utiliser les caractéristiques contenues dans le profil anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> profil d’appareil</span></b> </p> </td> 
   <td colname="col2"> <p>Indique <span class="keyword"> Audience Manager</span> d’utiliser le profil d’appareil anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> graphique d’appareil Profile Link</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de lire les profils de l’appareil actuel et de 100 autres appareils à partir desquels l’utilisateur s’est authentifié. Ce graphique d’appareil est créé sur vos propres données propriétaires dans <span class="keyword"> Audience Manager</span>. Il est idéal pour les clients qui disposent d’un niveau élevé d’authentification sur leurs propriétés numériques. Le graphique d’appareil <span class="wintitle"> Profile Link</span> est mis à jour en temps réel. Cette option est disponible lorsque vous sélectionnez <b><span class="uicontrol"> profil authentifié actuel</span></b> ou <b><span class="uicontrol"> dernier profil authentifié</span></b>. Lorsque vous utilisez cette option, vous ne pouvez choisir qu’un seul profil authentifié (<span class="keyword"> Audience Manager</span> grise automatiquement les autres). Voir aussi Cas d’utilisation du graphique d’appareil <a href="profile-link-use-case.md"> Profile Link</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Options graphiques d’appareils tiers</b> (personne et ménage) </p> </td>
   <td colname="col2"> <p>Ces options vous permettent de créer des règles de fusion basées sur la technologie de graphique d’appareil fournie par un fournisseur tiers. Un graphique d’appareil tiers fournit les éléments suivants : </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Données probabilistes et/ou déterministes. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Données au niveau de la personne ou du ménage. </li> 
     </ul> </p> <p>Pour utiliser ces options, vous devez être client d’un fournisseur de graphique d’appareils déjà intégré à <span class="keyword"> Audience Manager</span>. Contactez votre gestionnaire de compte pour plus d’informations ou pour commencer. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Les segments d’audience qui ont été automatiquement créés à partir d’autres solutions [!DNL Experience Cloud], en fonction de règles de fusion définies en dehors de [!DNL Audience Manager], sont marqués comme utilisant un [!UICONTROL External Merge Policy] . Par exemple, consultez la section [Partage d’audiences entre Audience Manager et Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [FAQ sur les règles de fusion de profil](../../faq/faq-profile-merge.md)
