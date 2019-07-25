---
description: Recommandations et cas d'utilisation pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct de Audience Manager. Cela inclut Adobe Experience Cloud Device Co-op et d'autres intégrations Adobe avec des sociétés de graphiques de périphériques tiers déterministes ou probabilistes.
seo-description: Recommandations et cas d'utilisation pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct de Audience Manager. Cela inclut Adobe Experience Cloud Device Co-op et d'autres intégrations Adobe avec des sociétés de graphiques de périphériques tiers déterministes ou probabilistes.
seo-title: Cas d’utilisation graphiques des périphériques externes
solution: Audience Manager
title: Cas d’utilisation graphiques des périphériques externes
uuid: f 4 bc 822 d -39 d 2-4680-90 ed -7 ee 2 ead 6 db 6 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Cas d’utilisation graphiques des périphériques externes {#external-device-graph-use-cases}

Recommandations et cas d'utilisation pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct de Audience Manager. This includes the [!DNL Adobe Experience Cloud Device Co-op] and other integrations Adobe has with third-party deterministic or probabilistic device graph companies.

## Recommandations {#recommendations}

Consider the [!DNL Experience Cloud Device Co-op] and third-party device graph options for campaigns that:

* Un faible niveau d'authentification dans leurs propriétés numériques. Use the [Profile Link device graph option](../../features/profile-merge-rules/merge-rule-definitions.md#device-options) if you have a large number of authenticated users.
* Ciblez les audiences volumineuses. The [!DNL Experience Cloud Device Co-op] and third-party device graphs contain authenticated and un-authenticated data.
* Segmenter les visiteurs authentifiés et/ou non authentifiés au niveau individuel et du foyer.

![](assets/merge-rule-triangle1.png)

## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

Une campagne de marque est conçue pour atteindre autant de personnes que possible. Elle limite quelques limites à la qualification des segments. Cependant, ces campagnes peuvent gaspiller le budget et les impressions en ciblant constamment les personnes qui visualisent votre contenu plusieurs fois et ne convertissent pas. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. Par exemple, vous pouvez ajouter ces utilisateurs inconnus à un segment « non marché » après leur affichage sur plusieurs périphériques pour votre quota de fréquence défini.

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
   <td colname="col2">Cette situation utilise les conditions suivantes : <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">Vous souhaitez fournir 10 impressions au maximum à un utilisateur anonyme pour une campagne publicitaire spécifique. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">Un utilisateur dispose de plusieurs périphériques et peut ou non s'être authentifié sur votre site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">Un utilisateur anonyme voit la publicité au total 10 fois lors de la navigation dans un état non authentifié sur son périphérique actuel et jusqu'à trois périphériques liés par un graphique de périphérique externe. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Fusionne l'activité anonyme non authentifiée collectée à partir du périphérique actuel et les 3 périphériques liés par le graphique de périphérique externe (les impressions publicitaires de chaque périphérique). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evalue l'utilisateur non authentifié pour la qualification des segments sur la base d'une combinaison d'activités anonymes sur les 3 périphériques liés par le graphique de périphérique externe et le périphérique actuel. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Envoie le segment à une destination en temps réel pour l'utiliser comme segment de suppression sur l'appareil actif et les 3 périphériques liés par le graphique de périphérique externe. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

Ces stratégies sont conçues pour amener un utilisateur non authentifié ou inconnu sur votre site ou pour personnaliser son expérience de navigation pendant qu'il est sur le site.

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
   <td colname="col2">Cette situation utilise les conditions suivantes : <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">Vous souhaitez fournir une expérience personnalisée sur site et/ou hors site à un utilisateur anonyme en fonction de son activité sur votre site pendant un état non authentifié. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">Un utilisateur dispose de plusieurs périphériques et peut ou non s'être authentifié sur votre site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">Un utilisateur consulte plusieurs pages de votre site en accédant à un état non authentifié sur son périphérique actuel et jusqu'à trois périphériques liés par un graphique de périphérique externe. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Résultats</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Fusionne l'activité anonyme non authentifiée collectée à partir des périphériques actuels et les 3 périphériques liés par le graphique de périphérique externe (les pages vues multiples de chaque périphérique). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evalue l'utilisateur non authentifié pour la qualification des segments sur la base d'une combinaison d'activités anonymes sur les 3 périphériques liés par le graphique de périphérique externe et le périphérique actuel. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Envoie le segment à une destination en temps réel afin de fournir une expérience personnalisée sur site et/ou hors site sur l'appareil actuel et les 3 périphériques liés par le graphique de périphérique externe. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

## Profile Merge Rule Options for External Device Graph Use Cases {#profile-merge}

Les options de règle de fusion pour ces cas d'utilisation ressemblent à celles présentées ci-dessous. The [!UICONTROL Authenticated Profile] options are deactivated because these settings are only available when you select **[!UICONTROL Current Authenticated Profile]** or **[!UICONTROL Last Authenticated Profile]**. Your [!UICONTROL Device Options] will vary depending on the type of device graph setting that you want to use or that is available to you.

![](assets/merge-rules-external.png)

For more information about how these device graph processes work, download our PDF, [Audience Manager and External Device Graphs](https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf).

>[!MORE_ LIKE_ THIS]
>
>* [Cas d'utilisation du graphique de périphérique de lien de profil](../../features/profile-merge-rules/profile-link-use-case.md)
>* [Cas d'utilisation général pour les règles de fusion de profils](../../features/profile-merge-rules/merge-rule-targeting-options.md)
>* [FAQ sur la fusion des profils](../../faq/faq-profile-merge.md)

