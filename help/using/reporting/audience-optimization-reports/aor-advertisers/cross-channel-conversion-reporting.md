---
description: L’option Cross Channel Conversion (Conversion cross-canal) dans les rapports d’Audience Optimization vous permet d’attribuer des conversions hors ligne aux impressions ou clics en ligne diffusés.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Conversion cross-canal
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Conversion cross-canal{#cross-channel-conversion}

L’option Cross Channel Conversion (Conversion cross-canal) dans les rapports d’Audience Optimization vous permet d’attribuer des conversions hors ligne aux impressions ou clics en ligne diffusés.

Les rapports [!UICONTROL Cross Channel Conversion] combinent les résultats de la plateforme [!DNL Google Campaign Manager] avec des caractéristiques de conversion [!DNL Audience Manager]. Vous pouvez ainsi lier des conversions hors ligne à des impressions ou des clics en ligne.

Vous pouvez utiliser le [!UICONTROL Cross Channel Conversion] pour les rapports [ Performance de segment](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) et [Fréquence optimale](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Pour afficher les rapports [!UICONTROL Cross Channel Conversion], sélectionnez l’élément **[!UICONTROL AAM + Ad Server Name]** dans la liste déroulante **[!UICONTROL Platform]**.

Le tableau suivant répertorie les points importants à prendre en compte lors de la configuration de [!UICONTROL Cross Channel Conversion] :

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
   <td colname="col1"> <p>Au moins une caractéristique de conversion doit être affectée à une source de données pour que les rapports <span class="wintitle"> Cross Channel Conversion</span> s’exécutent. Pour plus d’informations sur les caractéristiques, voir <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Informations de base sur les caractéristiques</a> . </p> </td> 
  </tr>
  <tr> 
   <td> <p>Fenêtre d’attribution </p> </td> 
   <td> <p> <b><span class="uicontrol"> La fenêtre d’attribution AAM+Google Campaign Manager</span></b> est de 14 jours, ce qui signifie que seules les caractéristiques de conversion exposées au cours des deux dernières semaines sont prises en compte. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Méthodologie de Dernière touche </p> </td> 
   <td> <p>Le créatif que l’utilisateur a vu avant la conversion est celui qui a reçu la conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics et impressions </p> </td> 
   <td> <p>Un clic a la priorité sur une impression lors du choix de l’attribution s’il se produit exactement en même temps. Par exemple, sur une page où plusieurs éléments créatifs sont affichés, celui sur lequel l’utilisateur clique se voit attribuer la conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Récence des données </p> </td> 
   <td> <p>Les rapports sont toujours calculés pour les données disponibles le jour précédent. </p> </td> 
  </tr> 
 </tbody> 
</table>
