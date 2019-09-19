---
description: Recommandations et cas d’utilisation pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct d’Audience Manager. Cela inclut Adobe Experience Cloud Device Co-op et d’autres intégrations d’Adobe avec des sociétés tierces de graphes de périphériques déterministes ou probabilistes.
seo-description: Recommandations et cas d’utilisation pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct d’Audience Manager. Cela inclut Adobe Experience Cloud Device Co-op et d’autres intégrations d’Adobe avec des sociétés tierces de graphes de périphériques déterministes ou probabilistes.
seo-title: Cas d’utilisation graphiques des périphériques externes
solution: Audience Manager
title: Cas d’utilisation graphiques des périphériques externes
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Cas d’utilisation graphiques des périphériques externes {#external-device-graph-use-cases}

Recommandations et cas d’utilisation pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct d’Audience Manager. Cela inclut les intégrations [!DNL Adobe Experience Cloud Device Co-op] et autres d’Adobe avec des sociétés tierces de graphiques de périphériques déterministes ou probabilistes.

## Recommandations {#recommendations}

Tenez compte des options de graphique de périphériques [!DNL Experience Cloud Device Co-op] et tiers pour les campagnes qui :

* Posséder un faible niveau d’authentification sur l’ensemble de leurs propriétés numériques. Utilisez l’option [de graphique Lien de](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) profil si vous avez un grand nombre d’utilisateurs authentifiés.
* Ciblez les publics importants. Les graphiques de périphériques [!DNL Experience Cloud Device Co-op] et tiers contiennent des données authentifiées et non authentifiées.
* Segmentez les visiteurs authentifiés et/ou non authentifiés au niveau individuel et familial.

![](assets/merge-rule-triangle1.png)

## Cas d’utilisation de la prospection/de la marque {#prospecting-branding-use-cases}

Une campagne d’image de marque est conçue pour toucher le plus grand nombre possible de personnes. Il limite peu la qualification des segments. Mais ces campagnes peuvent gâcher le budget et les impressions en ciblant constamment les personnes qui voient votre contenu plusieurs fois et ne le convertissent pas. Une [!UICONTROL Profile Merge] règle qui utilise l’option [!DNL Device Co-op] ou tierce peut vous aider à créer une campagne d’image de marque efficace. Par exemple, vous pouvez ajouter ces utilisateurs inconnus à un segment "non commercialisé" après les avoir vus sur plusieurs périphériques pour votre limite de fréquence définie.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">Ce cas d’utilisation suppose les conditions suivantes : <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Vous souhaitez transmettre un maximum de 10 impressions à un utilisateur anonyme pour une campagne publicitaire spécifique. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Un utilisateur possède plusieurs périphériques et peut s’être authentifié ou non sur votre site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Un utilisateur anonyme voit la publicité au total 10 fois lors de sa navigation dans un état non authentifié sur son périphérique actuel et jusqu’à 3 périphériques liés par un graphique de périphérique externe. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">Vous avez défini un segment <span class="keyword"> Audience Manager</span> pour qualifier les utilisateurs anonymes après avoir vu 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Dans ces conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Fusionne l’activité anonyme non authentifiée collectée à partir du périphérique actuel et les 3 périphériques liés par le graphique du périphérique externe (impressions publicitaires de chaque périphérique). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evalue l’utilisateur non authentifié pour la qualification de segment en fonction d’une combinaison d’activité anonyme sur les 3 périphériques liés par le graphique de périphérique externe et le périphérique actuel. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Envoie le segment à une destination en temps réel pour l’utiliser comme segment de suppression sur le périphérique actuel et sur les 3 périphériques liés par le graphique de périphérique externe. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cas d’utilisation du ciblage ou de la personnalisation de site {#retargeting-use-case}

Ces stratégies sont conçues pour ramener un utilisateur inconnu ou non authentifié sur votre site ou personnaliser son expérience de navigation lorsqu’il est sur site.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">Ce cas d’utilisation suppose les conditions suivantes : <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Vous souhaitez fournir une expérience personnalisée sur site et/ou hors site à un utilisateur anonyme en fonction de son activité sur votre site alors qu’il n’est pas authentifié. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Un utilisateur possède plusieurs périphériques et peut s’être authentifié ou non sur votre site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Un utilisateur affiche plusieurs pages de votre site alors qu’il navigue dans un état non authentifié sur son périphérique actuel et jusqu’à 3 périphériques liés par un graphique de périphérique externe. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">Vous avez défini un segment <span class="keyword"> Audience Manager</span> pour qualifier les utilisateurs après avoir consulté plusieurs pages de votre site pendant leur navigation dans un état non authentifié. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Dans ces conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Fusionne l’activité anonyme et non authentifiée collectée à partir des périphériques actuels et des 3 périphériques liés par le graphique du périphérique externe (les pages vues multiples de chaque périphérique). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evalue l’utilisateur non authentifié pour la qualification de segment en fonction d’une combinaison d’activité anonyme sur les 3 périphériques liés par le graphique de périphérique externe et le périphérique actuel. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Envoie le segment à une destination en temps réel afin de fournir une expérience personnalisée sur site et/ou hors site sur le périphérique actuel et sur les 3 périphériques liés par le graphique du périphérique externe. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Options des règles de fusion de profils pour les cas d'utilisation de graphiques de périphériques externes {#profile-merge}

Les options de règles de fusion pour ces cas d’utilisation ressemblent aux options disponibles présentées ci-dessous. Les [!UICONTROL Authenticated Profile] options sont désactivées car ces paramètres ne sont disponibles que lorsque vous sélectionnez **[!UICONTROL Current Authenticated Profile]** ou **[!UICONTROL Last Authenticated Profile]**. Votre [!UICONTROL Device Options] valeur varie selon le type de paramètre de graphique de périphérique que vous souhaitez utiliser ou qui est disponible pour vous.

![](assets/merge-rules-external.png)

Pour plus d’informations sur le fonctionnement de ces graphiques de périphériques, téléchargez nos graphiques [PDF,](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf)Audience Manager et externes.

>[!MORE_LIKE_This]
>
>* [Cas d’utilisation de graphiques de périphériques de lien de profil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Cas d’utilisation généraux des règles de fusion de profils](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

