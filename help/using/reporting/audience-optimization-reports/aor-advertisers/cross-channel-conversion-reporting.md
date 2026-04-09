---
description: L’option Conversion cross-canal dans les rapports Audience Optimization vous permet d’attribuer des conversions hors ligne aux impressions ou clics diffusés en ligne.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Conversion cross-canal
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
TQID: https://experienceleague.adobe.com/oP3jo2IVz2w0ExYE00wHo19nelOfOf4iAN84pgF64fU
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 238
ht-degree: 0%

---

# Conversion cross-canal{#cross-channel-conversion}

L’option Conversion cross-canal dans les rapports Audience Optimization vous permet d’attribuer des conversions hors ligne aux impressions ou clics diffusés en ligne.

Les rapports [!UICONTROL Cross Channel Conversion] combinent les résultats de la plateforme [!DNL Google Campaign Manager] avec des caractéristiques de conversion [!DNL Audience Manager]. Vous pouvez ainsi lier les conversions hors ligne aux impressions ou clics en ligne.

Vous pouvez utiliser le [!UICONTROL Cross Channel Conversion] pour les rapports [Performance des segments](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) et [Fréquence optimale](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Pour afficher les rapports [!UICONTROL Cross Channel Conversion], sélectionnez l’élément **[!UICONTROL AAM + Ad Server Name]** dans la liste déroulante **[!UICONTROL Platform]** .

Le tableau suivant répertorie les points importants à prendre en compte lors de la configuration d’[!UICONTROL Cross Channel Conversion] :

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
   <td colname="col1"> <p>Au moins une caractéristique de conversion doit être affectée à une source de données pour que les rapports <span class="wintitle"> Conversion cross</span>canal s’exécutent. Voir <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> des informations de base sur les caractéristiques </a> pour plus d’informations sur les caractéristiques. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Fenêtre d’attribution </p> </td> 
   <td> <p> <b><span class="uicontrol"> La fenêtre d’attribution du gestionnaire de campagne AAM+Google</span></b> est de 14 jours, ce qui signifie que seules les caractéristiques de conversion présentées au cours des deux dernières semaines sont prises en compte. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Méthodologie Dernière touche </p> </td> 
   <td> <p>Le contenu créatif que l’utilisateur ou l’utilisatrice a vu en dernier avant la conversion est celui qui a obtenu la conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Clics et impressions </p> </td> 
   <td> <p>Un clic est prioritaire sur une impression lors de la décision d’attribution s’il se produit exactement au même moment. Par exemple, sur une page où plusieurs contenus publicitaires sont affichés, celui sur lequel l’utilisateur clique se voit attribuer la conversion. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Récence des données </p> </td> 
   <td> <p>Les rapports sont toujours calculés pour les données disponibles la veille. </p> </td> 
  </tr> 
 </tbody> 
</table>
