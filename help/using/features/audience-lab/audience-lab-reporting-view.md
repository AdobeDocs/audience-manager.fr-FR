---
description: La section rapports du groupe de test renvoie des informations sur les conversions du groupe de test, ce qui permet de comparer facilement l'efficacité du segment de test. De nombreux filtres et dimensions sont disponibles pour la visualisation des données.
seo-description: La section rapports du groupe de test renvoie des informations sur les conversions du groupe de test, ce qui permet de comparer facilement l'efficacité du segment de test. De nombreux filtres et dimensions sont disponibles pour la visualisation des données.
seo-title: Rapports sur les groupes de test
solution: Audience Manager
title: Rapports sur les groupes de test
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: 'Audience Lab '
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 3%

---

# Rapports sur les groupes de test {#test-group-reporting}

La section rapports du groupe de test renvoie des informations sur les conversions du groupe de test, ce qui permet de comparer facilement l&#39;efficacité du segment de test. De nombreux filtres et dimensions sont disponibles pour la visualisation des données.

[!UICONTROL Audience Lab] renvoie des informations détaillées sur le rapports des segments de test que vous avez créés et vous permet d&#39;enregistrer les données du rapports sous forme de  [!DNL CSV] fichiers. Vous pouvez choisir entre **[!UICONTROL Aggregate Reporting]** et **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** renvoie les nombres absolus pour vos segments de test. **[!UICONTROL Trend Reporting]** renvoie un graphique de la tendance  *sur une période* spécifique. Quatre onglets vous permettent de personnaliser les rapports :

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Taux de conversion de la population</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le pourcentage de périphériques appartenant à un segment de test particulier, qui ont été convertis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Convertisseurs</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de périphériques ayant présenté les caractéristiques de conversion sélectionnées dans les groupes de tests. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Regardez cette </a> vidéo pour découvrir comment créer des caractéristiques de conversion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Total des conversions</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de conversions générées par les segments de test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Test des populations de segments</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de périphériques appartenant aux segments de test. Basculer entre <b><span class="uicontrol"> Population totale</span></b> ou <b><span class="uicontrol"> Population en temps réel </span></b>. La différence est expliquée dans le <a href="../../faq/faq-reporting.md"> Rapports FAQ</a> . </p> </td>
  </tr>
 </tbody>
</table>

Vous pouvez sélectionner un trait de conversion spécifique pour lequel générer le rapport ou sélectionner toutes les caractéristiques combinées. Vous pouvez définir une plage de dates pour laquelle les informations doivent être renvoyées et exporter le rapport sous la forme d&#39;un fichier [!DNL CSV].

>[!NOTE]
>
>* Le rapports d’un groupe de test est renseigné le jour suivant sa date de début.
>* Une conversion n’est comptabilisée pour un périphérique qu’après la date de début d’un test et après l’ajout du périphérique à un segment de test. Si une conversion survient pour ce périphérique avant qu’un groupe de test ne lui soit affecté, la conversion ne sera pas comptabilisée.


Un graphique **[!UICONTROL Aggregate Reporting]** renvoyé peut se présenter comme suit :

![](assets/aggregate-reporting.PNG)

Un graphique **[!UICONTROL Trend Reporting]** renvoyé peut ressembler à celui ci-dessous. Cochez la case **[!UICONTROL Normalized]** si vous souhaitez ignorer les chiffres absolus et vous concentrer simplement sur les tendances des segments de test.

![](assets/trend-reporting.PNG)
