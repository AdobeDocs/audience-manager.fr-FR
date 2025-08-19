---
description: La section de rapport sur le groupe de test renvoie des informations sur les conversions de groupe de test, ce qui permet de comparer facilement l’efficacité du segment de test. De nombreux filtres et dimensions sont disponibles pour la visualisation des données.
seo-description: The test group reporting section returns information on test group conversions, allowing an easy comparison of test segment efficacy. Numerous filters and dimensions are available for data visualization.
seo-title: Test Group Reporting
solution: Audience Manager
title: Rapports de groupe de test
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: Audience Lab
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Rapports de groupe de test {#test-group-reporting}

La section de rapport sur le groupe de test renvoie des informations sur les conversions de groupe de test, ce qui permet de comparer facilement l’efficacité du segment de test. De nombreux filtres et dimensions sont disponibles pour la visualisation des données.

[!UICONTROL Audience Lab] renvoie des informations de rapport détaillées pour les segments de test que vous avez créés et vous permet d’enregistrer les données de rapport sous forme de fichiers [!DNL CSV]. Vous pouvez choisir entre **[!UICONTROL Aggregate Reporting]** et **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** renvoie les nombres absolus pour vos segments de test. **[!UICONTROL Trend Reporting]** renvoie un graphique de la tendance *sur une période spécifique*. Quatre onglets permettent de personnaliser les rapports :

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Taux De Conversion De Population</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le pourcentage d’appareils appartenant à un segment de test particulier qui ont été convertis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Convertisseurs</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre d’appareils qui ont présenté la ou les caractéristiques de conversion sélectionnées dans les groupes de test. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Regardez cette vidéo</a> pour savoir comment créer des caractéristiques de conversion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Total Des Conversions</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de conversions générées par les segments de test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> les populations de segments de test</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre d’appareils appartenant aux segments de test. Basculez entre <b><span class="uicontrol"> population totale</span></b> ou <b><span class="uicontrol"> population en temps réel</span></b>. La différence est expliquée dans la FAQ sur les rapports d’<a href="../../faq/faq-reporting.md"></a> . </p> </td>
  </tr>
 </tbody>
</table>

Vous pouvez sélectionner une caractéristique de conversion spécifique pour laquelle générer le rapport ou sélectionner toutes les caractéristiques combinées. Vous pouvez définir une période pour laquelle les informations doivent être renvoyées et exporter le rapport sous la forme d’un fichier [!DNL CSV].

>[!NOTE]
>
>* La création de rapports pour un groupe de test sera renseignée le jour suivant sa date de début.
>* Une conversion n’est comptabilisée pour un appareil qu’après la date de début d’un test et après l’ajout de l’appareil à un segment de test. Si une conversion se produit pour cet appareil avant qu’un groupe de test ne lui soit attribué, elle n’est pas comptabilisée.

Voici à quoi pourrait ressembler un graphique **[!UICONTROL Aggregate Reporting]** renvoyé :

![](assets/aggregate-reporting.PNG)

Un graphique **[!UICONTROL Trend Reporting]** renvoyé peut ressembler à celui ci-dessous. Cochez la case **[!UICONTROL Normalized]** si vous souhaitez ignorer les nombres absolus et vous concentrer simplement sur les tendances des segments de test.

![](assets/trend-reporting.PNG)
