---
description: L'option Cross Channel Conversion (Conversion multicanaux) des rapports Optimisation d'audience vous permet d'attribuer des conversions hors ligne aux impressions ou aux clics en ligne diffusés.
seo-description: L'option Cross Channel Conversion (Conversion multicanaux) des rapports Optimisation d'audience vous permet d'attribuer des conversions hors ligne aux impressions ou aux clics en ligne diffusés.
seo-title: Conversion inter-canaux
solution: Audience Manager
title: Conversion inter-canaux
uuid: 0 fecec 23-e 502-490 b-b 7 dd -47 a 3753 a 3 f 75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Conversion inter-canaux{#cross-channel-conversion}

L&#39;option Cross Channel Conversion (Conversion multicanaux) des rapports Optimisation d&#39;audience vous permet d&#39;attribuer des conversions hors ligne aux impressions ou aux clics en ligne diffusés.

[!UICONTROL Cross Channel Conversion] Les rapports combinent les résultats de la plateforme [!DNL DoubleClick Campaign Manager] (DCM) avec des caractéristiques [!DNL Audience Manager] de conversion. Vous pouvez ainsi lier les conversions hors ligne aux impressions ou aux clics en ligne.

You can use the [!UICONTROL Cross Channel Conversion] for the [Segment Performance](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) and [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) reports.

To view the [!UICONTROL Cross Channel Conversion] reports, select the **[!UICONTROL AAM+DCM]** item in the **[!UICONTROL Platform]** drop-down list.

The following table lists important considerations when setting up [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Considération </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Nombre minimum de caractéristiques de conversion </p> </td> 
   <td colname="col1"> <p>At least one conversion trait must be assigned to a data source in order for the <span class="wintitle"> Cross Channel Conversion</span> reports to run. See <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Basic Information for Traits</a> for more information on traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Nombre maximum de caractéristiques de conversion </p> </td> 
   <td colname="col1"> <p>The reports pull in a <i>maximum</i> of 50 conversion traits from the user. Si vous atteignez le maximum, les rapports utilisent les 50 premières caractéristiques de conversion basées sur l'identifiant de caractéristique, dans l'ordre croissant. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Fenêtre Attribution </p> </td> 
   <td> <p> <b><span class="uicontrol"> La fenêtre</span></b> d'attribution AAM + DCM est 14 jours, ce qui signifie que seules les caractéristiques de conversion affichées au cours des deux dernières semaines sont prises en compte. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Méthodologie Dernière touche </p> </td> 
   <td> <p>Le créatif affiché par l'utilisateur avant la conversion est celui qui a obtenu la conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics par rapport aux impressions </p> </td> 
   <td> <p>Un clic est prioritaire sur une impression lors de la décision d'attribution si elles se produisent exactement à la même heure. Par exemple, sur une page sur laquelle plusieurs éléments créatifs sont affichés, celle sur laquelle on clique reçoit la conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Récence des données </p> </td> 
   <td> <p>Les rapports sont toujours calculés pour les données disponibles le jour précédent. </p> </td> 
  </tr> 
 </tbody> 
</table>
