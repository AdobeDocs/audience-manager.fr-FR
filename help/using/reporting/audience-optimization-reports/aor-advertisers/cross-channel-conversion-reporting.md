---
description: L’option Conversion entre Canaux des rapports d’Audience Optimization vous permet d’attribuer des conversions hors ligne aux impressions ou clics en ligne diffusés.
seo-description: L’option Conversion entre Canaux des rapports d’Audience Optimization vous permet d’attribuer des conversions hors ligne aux impressions ou clics en ligne diffusés.
seo-title: Conversion inter-canaux
solution: Audience Manager
title: Conversion inter-canaux
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 97129b435ab8e13def14bc85dcaab8254b2c4bda
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---


# Conversion inter-canaux{#cross-channel-conversion}

L’option Conversion entre Canaux des rapports d’Audience Optimization vous permet d’attribuer des conversions hors ligne aux impressions ou clics en ligne diffusés.

Les rapports [!UICONTROL Cross Channel Conversion] combinent les résultats de la plateforme [!DNL Google Campaign Manager] avec les caractéristiques de conversion [!DNL Audience Manager]. Vous pouvez ainsi lier des conversions hors ligne à des impressions ou des clics en ligne.

Vous pouvez utiliser [!UICONTROL Cross Channel Conversion] pour les rapports [Performances du segment](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) et [Fréquence optimale](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Pour vue des rapports [!UICONTROL Cross Channel Conversion], sélectionnez l&#39;élément **[!UICONTROL AAM + Ad Server Name]** dans la liste déroulante **[!UICONTROL Platform]**.

Le tableau suivant liste les points importants à prendre en compte lors de la configuration de [!UICONTROL Cross Channel Conversion] :

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
   <td colname="col1"> <p>Au moins une caractéristique de conversion doit être attribuée à une source de données pour que les rapports de conversion <span class="wintitle"> inter-Canaux</span> s'exécutent. Voir <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Informations de base sur les caractéristiques</a> pour plus d'informations sur les caractéristiques. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Fenêtre Attribution </p> </td> 
   <td> <p> <b><span class="uicontrol"> La fenêtre d’attribution AAM+Google Campaign </span></b> Manager est de 14 jours, ce qui signifie que seules les caractéristiques de conversion exposées au cours des deux dernières semaines sont prises en compte. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Méthodologie Dernière touche </p> </td> 
   <td> <p>Le créatif que l’utilisateur a vu en dernier avant la conversion est celui qui a attribué la conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics versus impressions </p> </td> 
   <td> <p>Un clic prévaut sur une impression lors du choix de l’attribution s’il se produit exactement au même moment. Par exemple, sur une page où plusieurs éléments créatifs sont affichés, celui sur lequel l’utilisateur clique obtient la conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Récence des données </p> </td> 
   <td> <p>Les rapports sont toujours calculés pour les données disponibles la veille. </p> </td> 
  </tr> 
 </tbody> 
</table>
