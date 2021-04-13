---
description: Recommendations et utilisation de cas pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct de l’Audience Manager. Cela inclut le Adobe Experience Cloud Device Co-op et d'autres Adobes d'intégration avec des sociétés de graphiques de dispositifs déterministes ou probabilistes tierces.
seo-description: Recommendations et utilisation de cas pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct de l’Audience Manager. Cela inclut le Adobe Experience Cloud Device Co-op et d'autres Adobes d'intégration avec des sociétés de graphiques de dispositifs déterministes ou probabilistes tierces.
seo-title: Cas d’utilisation des représentations graphiques externes des appareils
solution: Audience Manager
title: Cas d’utilisation des représentations graphiques externes des appareils
uuid: f4bc822d-39d2-4680-90ed-7ee2ead6db6f
feature: Fusion de profil
exl-id: 657aecfd-7fa3-466e-8331-c49cc921e3a9
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 5%

---

# Cas d’utilisation des représentations graphiques externes des appareils {#external-device-graph-use-cases}

Recommendations et utilisation de cas pour la prospection, le reciblage et la personnalisation pour les utilisateurs inconnus avec un graphique de périphérique externe. Un graphique de périphérique externe est défini comme un graphique de périphérique distinct de l’Audience Manager. Cela inclut l&#39;Adobe [!DNL Adobe Experience Cloud Device Co-op] et d&#39;autres intégrations avec des sociétés de graphiques de dispositifs déterministes ou probabilistes tierces.

## Recommandations {#recommendations}

Examinez les options [!DNL Experience Cloud Device Co-op] et les options de graphique de périphérique tiers pour les campagnes qui :

* Posséder un faible niveau d’authentification sur l’ensemble de leurs propriétés numériques. Utilisez [!UICONTROL Profile Link Device Graph option] si vous avez un grand nombre d’utilisateurs authentifiés.
* Cible de grandes audiences. Les graphiques [!DNL Experience Cloud Device Co-op] et de périphériques tiers contiennent des données authentifiées et non authentifiées.
* Segmenter les visiteurs authentifiés et/ou non authentifiés au niveau individuel et familial.

![](assets/merge-rule-triangle1.png)
<!-- 
## Prospecting/Branding Use Case {#prospecting-branding-use-cases}

A branding campaign is designed to reach as many people as possible. It places few limits on segment qualification. But, these campaigns can waste budget and impressions by constantly targeting people who see your content multiple times and don't convert. A [!UICONTROL Profile Merge] rule that uses the [!DNL Device Co-op] or third-party option can help you create an efficient branding campaign. For example, you can add these unknown users to a "not in-market" segment after seeing them across multiple devices for your set frequency cap.

<table id="table_00F6EED172574E80A38CADA8A92A23B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_F5CA7EE525774F7EBA5FBB5F94E4EDC8"> 
      <li id="li_81AE304924724146A24FAB5B6533AD8E">You want to deliver a maximum of 10 impressions to an anonymous user for a specific ad campaign. </li> 
      <li id="li_E371F989735245B0B82433DE240D56D0">A user has 4 devices and may or may not have authenticated on your site. </li> 
      <li id="li_9231ABE15CA249E6B79D8BF0E511FD33">An anonymous user sees the ad a total of 10 times while browsing in an unauthenticated state on their current device and 3 devices linked to the current device by an external device graph. </li> 
      <li id="li_8C276C07019C49EFA3A0D0D54CF73C31">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify anonymous users after they have seen 10 impressions. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_8E988B1005324526BC6DC6637BBACCFB"> 
      <li id="li_C9DD546754914BACB8F4C92C7D4ED70E">Merges the anonymous, unauthenticated activity collected from the current device and the 3 devices linked by the external device graph (the ad impressions from each device). </li> 
      <li id="li_FB55CB9116074525BA30FF062D1136AE">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_B28EB32F718145A7ABBDAC0AF75E2AFC">Sends the segment to any real-time destination for use as a suppression segment on the current device and all 3 devices linked by the external device graph. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Retargeting or Site Personalization Use Case {#retargeting-use-case}

These strategies are designed to bring an unauthenticated or unknown user back to your site or personalize their browsing experience while they're on-site.

<table id="table_0EE2052AA3E744B3B76036FC06B5A453"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Conditions</b> </p> </td> 
   <td colname="col2">This use case assumes these conditions: <p> 
     <ul id="ul_FD0B869B4AF3453FAEC9BA3A45ABF039"> 
      <li id="li_8E30BAED42E94AB3B81FCB1C7464E5FC">You want to deliver a personalized on-site and/or off-site experience to an anonymous user based on their activity on your site while in an unauthenticated state. </li> 
      <li id="li_3DBE53BA94324F1BA1C52A37AD4E426C">A user has multiple devices and may or may not have authenticated to your site. </li> 
      <li id="li_F867AFBDC1A54CD6A68AB0EC196E27C9">A user views multiple pages on your site while browsing in an unauthenticated state on their current device and 3 other devices linked by an external device graph. </li> 
      <li id="li_7E35D77949CE4E69BD51655AA4C40BEE">You have defined an <span class="keyword"> Audience Manager</span> segment to qualify users after they have viewed multiple pages on your site while browsing in an unauthenticated state.</li>
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Results</b> </p> </td> 
   <td colname="col2"> <p>Given these conditions, <span class="wintitle"> Audience Manager</span>: </p> <p> 
     <ul id="ul_301339426B0643B295DC5B17E1939CFB"> 
      <li id="li_7E8BC3B179804F4A929497DE81E76911">Merges the anonymous, unauthenticated activity collected from the current devices and the 3 devices linked by the external device graph (the multiple page views from each device). </li> 
      <li id="li_803EFD58AA124A5BBC8279C4DC695544">Evaluates the unauthenticated user for segment qualification based on a combination of anonymous activity across all 3 devices linked by the external device graph and the current device. </li> 
      <li id="li_98D749268CC5456CBC9CF3BF5EB91BA8">Sends the segment to any real-time destination to deliver a personalized on-site and/or off-site experience across the current device and all 3 devices linked by the external device graph. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table> -->

## Ciblage étendu des périphériques {#audience-expansion}

Ce cas d&#39;utilisation illustre comment vous pouvez augmenter la taille de votre audience adressable avec une personnalisation inter-périphériques précise, via [!DNL Adobe Co-Op Device Graph] ou autre [!DNL External Device Graphs].

Disons que Jane possède trois appareils qu&#39;elle utilise régulièrement pour rechercher des forfaits vacances : son ordinateur portable ([!DNL Device 1]), son smartphone ([!DNL Device 2]) et sa tablette ([!DNL Device 3]). En utilisant l&#39;ordinateur portable, Jane a recherché des vols, des hôtels et des visites guidées. En utilisant son smartphone et sa tablette, elle n&#39;a visité que la page d&#39;accueil de l&#39;agence de voyages.

En utilisant la règle [!UICONTROL No Cross-Device Profile] + [!UICONTROL Adobe Co-op Device Graph], l&#39;agence de voyages peut fusionner les trois profils de périphériques, puisqu&#39;ils sont liés au même propriétaire par l&#39;intermédiaire de [!UICONTROL Adobe Co-op Device Graph].

![audience-expansion-règle](assets/audience-expansion-rule.png)

Dans notre exemple, les caractéristiques requises pour être incluses dans le segment ont toutes été collectées sur [!DNL Device 1]. Comme l&#39;Audience Manager qualifie chaque profil d&#39;appareil qui a participé à la fusion de profils pour un segment, les trois profils d&#39;appareil de Jane sont maintenant segmentés.

Grâce à cette règle, le graphique de périphériques a augmenté le nombre de profils de périphériques admissibles au segment de un à trois et a permis à l’agence de voyages de diffuser un message cohérent aux trois périphériques appartenant à Jane.

![audience-expansion](assets/audience-expansion.png)

## Ciblage avancé sur plusieurs périphériques {#advanced-graph-expansion}

Ce cas d’utilisation montre comment développer le ciblage des audiences pour les visiteurs authentifiés à l’aide de périphériques à partir d’un graphique de périphérique externe ou de [!DNL Adobe Co-Op Device Graph], en utilisant la règle **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Adobe Co-Op Device Graph]**.

![dernier-dispositif-graphique](assets/last-device-coop.png)

Dans l&#39;exemple ci-dessous, la société Acme Inc. veut cible à tous les ménages ayant un revenu supérieur à 100 000 $ par année, qui ont [!DNL Acme Inc.] abonnés sur [!DNL Data Plan A], qui utilisent un dispositif [!DNL iPhone 7].

John utilise son iPhone 7 sur le plan de données A pour s’authentifier sur le site Web d’Acme Inc. Dans le même temps, la grappe [!DNL Co-Op Device Graph] de John contient deux périphériques supplémentaires qu&#39;il utilise régulièrement : son ordinateur portable ([!DNL Device 1]) et son smartphone secondaire, [!DNL Device 2] (a [!DNL Samsung S7] sur [!DNL Data Plan B]).

En utilisant **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Adobe Co-Op Device Graph]**, [!DNL Acme Inc.] est en mesure de fournir des messages personnalisés aux trois périphériques à partir du cluster graphique de John, même si l&#39;un d&#39;eux seulement est initialement admissible pour le segment.

![expansion-graphique avancée](assets/advanced-device-graph-expansion.png)

>[!MORELIKETHIS]
>
>* [Cas d’utilisation des représentations graphiques des appareils Profile Link](profile-link-use-case.md)
>* [Cas d’utilisation généraux des stratégies de fusion de profils](merge-rule-targeting-options.md)
>* [FAQ sur les règles de fusion de profils](../../faq/faq-profile-merge.md)

