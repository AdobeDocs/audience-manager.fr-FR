---
description: Les options de règle de fusion vous permettent de contrôler le type d’Audience Manager de données utilisé pour la segmentation. Une règle de fusion peut inclure des profils de périphérique mappés par le graphique de périphérique Profile Link et/ou d’autres fournisseurs de graphiques de périphérique tiers intégrés à Audience Manager. Vous pouvez créer un maximum de 4 règles de fusion de profils.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Définition des options des règles de fusion de profils
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] Options définies {#profile-merge-rule-options-defined}

Les options [!UICONTROL profile merge rule] vous permettent de contrôler le type de données utilisé par [!DNL Audience Manager] pour la segmentation. Un [!UICONTROL profile merge rule] peut inclure des profils d’appareil mappés par le graphique d’appareil [!UICONTROL Profile Link] et/ou d’autres fournisseurs de graphiques d’appareil tiers intégrés à [!DNL Audience Manager]. Vous pouvez créer un maximum de 4 [!UICONTROL Profile Merge Rules]. Le quatrième [!UICONTROL Profile Merge Rule] est disponible exclusivement pour les clients qui ont acheté le module complémentaire [!UICONTROL People-Based Destinations].

Vous créez un [!UICONTROL Profile Merge Rule] en effectuant une sélection à partir des options décrites ci-dessous, dans [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Options - Aperçu {#overview}

[!UICONTROL Profile Merge Rules] autorise un certain nombre de combinaisons de règles, chacune étant orientée vers des cas d’utilisation spécifiques. Consultez le tableau ci-dessous pour savoir quand utiliser chaque combinaison de règles.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Disponibilité | Type d’évaluation | Assistance [!UICONTROL Audience Lab] | Cas d’utilisation |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Tous les clients | Temps réel et lot | Oui | [Ciblage de périphérique](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Tous les clients | Temps réel et lot | Non | [Ciblage de périphérique étendu](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Tous les clients | Temps réel uniquement | Non | [Ciblage d’appareil partagé](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Tous les clients | Temps réel et lot | Oui | [Ciblage en ligne/hors ligne](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Tous les clients | Temps réel et lot | Oui | [Ciblage sur plusieurs appareils](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Tous les clients | Temps réel et lot | Non | [Ciblage avancé sur plusieurs appareils](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | S.O. | Exclusif aux clients [Destinations basées sur les personnes](../destinations/people-based-destinations-overview.md) | Lot uniquement | Non | [Ciblage pour les destinations basées sur les personnes](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Évaluation {#segment-evaluation}

Selon votre configuration [!UICONTROL Profile Merge Rules], [!DNL Audience Manager] peut effectuer l’évaluation [!UICONTROL segment] en temps réel, par lot ou les deux.

* L’évaluation [!UICONTROL segment] en temps réel nécessite que [!DNL DCS] visualise les visiteurs qui accèdent à vos propriétés numériques en temps réel, afin de remplir les conditions requises pour l’ [!UICONTROL segment].
* L’évaluation du lot [!UICONTROL segment] est effectuée par rapport aux [!UICONTROL traits] précédemment qualifiés.
* [!UICONTROL Profile Merge Rules] qui prennent en charge l’évaluation en temps réel et par lot [!UICONTROL segment] combine l’activité des visiteurs en temps réel avec les [!UICONTROL traits] précédemment qualifiés.

## [!UICONTROL Profile Merge Rules] Latence des rapports {#reporting-latency}

L’évaluation [!UICONTROL segment] en temps réel se reflète immédiatement dans les rapports [!UICONTROL Profile Merge Rules].

L’évaluation du lot [!UICONTROL segment] peut prendre jusqu’à 24 heures pour se refléter dans les [ rapports de règles de fusion de profils](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

L’ [!UICONTROL Cross-Device Options] vous permet de sélectionner des utilisateurs authentifiés et non authentifiés et d’exploiter leur profil multi-appareils pour la segmentation. Ces options vous aident à identifier et à atteindre des utilisateurs spécifiques sur un appareil partagé. Pour plus d’informations sur les utilisateurs anonymes et authentifiés, voir [États d’authentification du visiteur en Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option multi-appareils </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aucun profil multi-appareils</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> Audience Manager</span> de ne pas utiliser les données collectées auprès des utilisateurs authentifiés. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profils authentifiés actuels</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> de lire et d’écrire des données dans le profil authentifié si un visiteur s’est connecté à votre site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Derniers profils authentifiés</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> de lire les données du profil authentifié de l’utilisateur qui s’est connecté pour la dernière fois à l’appareil. </p> <p>Lorsqu’elle est sélectionnée, l’Audience Manager <span class="keyword"> n’écrira pas de nouvelles données de caractéristiques dans le profil authentifié si l’utilisateur est anonyme. </span> Lors de l’authentification, les nouvelles données de caractéristique sont écrites dans le profil authentifié de l’utilisateur. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tous les profils multi-appareils</span></b> </p> </td> 
   <td colname="col2"> <p>Indique à l’Audience Manager de lire les données de tous les profils multi-appareils, quel que soit l’état d’authentification. Cette option est disponible uniquement pour les clients d’Audience Manager qui ont acheté le module complémentaire Destinations basées sur les personnes .</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

Le [!UICONTROL Cross-Device Profile Options] répertorie votre [!UICONTROL cross-device data sources]. Ces options utilisent les noms que vous avez fournis lors de la création d’un [!UICONTROL cross-device] [!UICONTROL data source] (voir [Création d’une Source de données multi-appareils](merge-rules-start.md#create-data-source)). Vous pouvez sélectionner jusqu’à 3 [!UICONTROL cross-device data sources] à utiliser avec chaque règle de profil. Les [!UICONTROL Authenticated Profile Options] sont disponibles lorsque vous choisissez **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

Le [!UICONTROL Device Options] vous permet de sélectionner le type de *`device profile`* utilisé par un [!UICONTROL Profile Merge Rule]. Un profil d’appareil est créé à partir de [!UICONTROL traits] collecté à partir d’une activité de navigation anonyme. Au minimum, un [!UICONTROL profile merge rule] comprend un [!UICONTROL authenticated option] et un [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option du périphérique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aucun profil de périphérique </span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> de ne pas utiliser les caractéristiques contenues dans le profil anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profil de périphérique </span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> d’utiliser le profil d’appareil anonyme pour la segmentation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Graphique du périphérique du lien de profil </span></b> </p> </td> 
   <td colname="col2"> <p>Indique à <span class="keyword"> l’Audience Manager</span> de lire les profils de l’appareil actuel et jusqu’à 100 autres appareils à partir desquels l’utilisateur s’est authentifié. Ce graphique d’appareil est créé sur vos propres données propriétaires dans l’ <span class="keyword"> Audience Manager</span>. Il est idéal pour les clients qui disposent d’un niveau élevé d’authentification dans leurs propriétés numériques. Le graphique d’appareil <span class="wintitle"> Profile Link</span> est mis à jour en temps réel. Cette option est disponible lorsque vous sélectionnez <b><span class="uicontrol"> Profil authentifié actuel</span></b> ou <b><span class="uicontrol"> Dernier profil authentifié</span></b>. Lorsque vous utilisez cette option, vous ne pouvez choisir qu’un seul profil authentifié (<span class="keyword"> Audience Manager</span> grise automatiquement les autres). Voir aussi <a href="profile-link-use-case.md"> Cas d’utilisation des représentations graphiques des appareils Profile Link</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Options graphiques d’appareil tiers</b> (personne et foyer) </p> </td>
   <td colname="col2"> <p>Ces options vous permettent de créer des règles de fusion basées sur la technologie de représentation graphique des appareils fournie par un fournisseur tiers. Une représentation graphique tierce des appareils fournit les éléments suivants : </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Données probabilistes ou déterministes. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Données au niveau de la personne ou du foyer. </li> 
     </ul> </p> <p>Pour utiliser ces options, vous devez être client d’une représentation graphique des appareils qui est déjà intégrée à <span class="keyword"> Audience Manager</span>. Contactez votre gestionnaire de compte pour plus d’informations ou pour commencer. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Les segments d’audience automatiquement créés à partir d’autres solutions [!DNL Experience Cloud], basés sur des règles de fusion définies en dehors de [!DNL Audience Manager], sont marqués comme utilisant un [!UICONTROL External Merge Policy]. Par exemple, voir [Partage d’audiences entre Audience Manager et Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)
