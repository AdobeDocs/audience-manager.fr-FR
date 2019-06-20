---
description: La section de création de rapports du groupe de test renvoie des informations sur les conversions des groupes de test, ce qui permet une comparaison facile de l'efficacité du segment de test. De nombreux filtres et dimensions sont disponibles pour la visualisation des données.
seo-description: La section de création de rapports du groupe de test renvoie des informations sur les conversions des groupes de test, ce qui permet une comparaison facile de l'efficacité du segment de test. De nombreux filtres et dimensions sont disponibles pour la visualisation des données.
seo-title: Création de rapports de groupe de test
solution: Audience Manager
title: Création de rapports de groupe de test
topic: API DIL
uuid: 21303 c 3 e -4 c 05-4728-a 759-96 c 2 a 1 d 99 b 69
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Test Group Reporting {#test-group-reporting}

La section de création de rapports du groupe de test renvoie des informations sur les conversions des groupes de test, ce qui permet une comparaison facile de l&#39;efficacité du segment de test. De nombreux filtres et dimensions sont disponibles pour la visualisation des données.

[!UICONTROL Audience Lab] renvoie des informations de rapport détaillées pour les segments de test que vous avez créés et vous permet d&#39;enregistrer les données de rapport sous forme [!DNL CSV] de fichiers. You can select between **[!UICONTROL Aggregate Reporting]** and **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** renvoie les chiffres absolus des segments de test. **[!UICONTROL Trend Reporting]** renvoie un graphique de la tendance *sur une période spécifique*. Quatre onglets permettent de personnaliser les rapports :

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Taux de conversion de population</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le pourcentage des périphériques appartenant à un segment de test spécifique qui ont été convertis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Convertisseurs</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de périphériques qui ont affiché la ou les caractéristiques de conversion sélectionnées dans les groupes de test. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> Regardez cette vidéo</a> pour apprendre à créer des caractéristiques de conversion. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Conversions totales</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de conversions générées par les segments de test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Tester les populations de segments</span></b> </p> </td> 
   <td colname="col2"> <p>Renvoie le nombre de périphériques appartenant aux segments de test. Toggle between <b><span class="uicontrol"> Total Population</span></b> or <b><span class="uicontrol"> Real-time Population</span></b>. The difference is explained in the <a href="../../faq/faq-reporting.md"> Reporting FAQ</a> . </p> </td>
  </tr>
 </tbody>
</table>

Vous pouvez sélectionner une caractéristique de conversion spécifique pour laquelle générer le rapport ou sélectionner toutes les caractéristiques combinées. You can define a date range for which the information should be returned and export the report as a [!DNL CSV] file.

>[!NOTE]
>
>* La création de rapports pour un groupe de test remplit le jour suivant sa date de début.
>* Une conversion est comptée uniquement pour un périphérique après la date de début d&#39;un test et une fois que le périphérique a été ajouté à un segment de test. Si une conversion se produit pour ce périphérique avant d&#39;être affectée à un groupe de test, la conversion n&#39;est pas comptabilisée.


A returned **[!UICONTROL Aggregate Reporting]** chart could look like this:

![](assets/aggregate-reporting.PNG)

A returned **[!UICONTROL Trend Reporting]** chart could look like the one below. Select **[!UICONTROL Normalized]** in the check box if you want to ignore the absolute numbers and simply focus on the test segments trends.

![](assets/trend-reporting.PNG)