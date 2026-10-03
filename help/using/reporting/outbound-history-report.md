---
description: Affichez les informations d’historique des traitements par lots sortants pour une destination et une période spécifiées.
seo-description: View outbound batch job history information for a specified destination and time period.
seo-title: Outbound File History
solution: Audience Manager
title: Historique des fichiers sortants
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: Inbound and Outbound Reports
exl-id: 8072c44f-bc9a-4b40-99d9-8cb87bb58d98
TQID: 'https://experienceleague.adobe.com/bAoUgntw3hZBsEuyPQV6yX2ftNRFV9HIv9QbierOgmA'
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
    internal-label: Reporting
subfeature_v2:
  - id: bacaf04d-fec1-4cf9-a97e-cb1b36e40b07
    internal-label: Inbound and outbound reports
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 1%
---
# Historique des fichiers sortants {#outbound-file-history}

Affichez les informations d’historique des traitements par lots sortants pour une destination et une période spécifiées.

<!-- 

t_reports_outbound_history.xml

 -->

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Résultat de l’étape](assets/outbound_history.png)

1. Dans la zone de **[!UICONTROL Search for a Destination]**, commencez la saisie et sélectionnez la destination souhaitée.
1. Dans la zone de **[!UICONTROL Select a Date Range]**, indiquez les dates de début et de fin de votre rapport, puis cliquez sur **[!UICONTROL Apply Date Filter]**.

   ![Résultat de l’étape](assets/outbound_history_stats.png)

   Le tableau suivant contient des informations correspondant aux colonnes du rapport :

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ligne </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom du fichier de synchronisation des données </td> 
   <td colname="col2"> <p>Liste de tous les fichiers sortants générés <span class="keyword"> Adobe</span> pour cette destination et traités ensemble. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Succès </td> 
   <td colname="col2"> <p>Nombre d’enregistrements envoyés avec succès d’<span class="keyword"> Audience Manager</span> vers la destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Echec </td> 
   <td colname="col2"> <p>Nombre d'enregistrements qui n'ont pas pu être envoyés à la destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements reçus </td> 
   <td colname="col2"> <p>Nombre total d’enregistrements <span class="keyword"> Adobe</span> générés dans les fichiers et ayant tenté d’être envoyés à la destination. Dans la plupart des cas, il s’agit du nombre total de fichiers réussis et en échec. </p> </td> 
  </tr> 
 </tbody> 
</table>
