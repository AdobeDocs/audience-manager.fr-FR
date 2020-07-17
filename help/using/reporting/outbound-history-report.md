---
description: Vue des informations d'historique des lots sortants pour une destination et une période spécifiées.
seo-description: Vue des informations d'historique des lots sortants pour une destination et une période spécifiées.
seo-title: Historique des fichiers sortants
solution: Audience Manager
title: Historique des fichiers sortants
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 7%

---


# Historique des fichiers sortants {#outbound-file-history}

Vue des informations d&#39;historique des lots sortants pour une destination et une période spécifiées.

<!-- 

t_reports_outbound_history.xml

 -->

1. Cliquez sur **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Résultat de l’étape](assets/outbound_history.png)

1. Dans la **[!UICONTROL Search for a Destination]** zone, tapez un début et sélectionnez la destination souhaitée.
1. Dans la **[!UICONTROL Select a Date Range]** zone, indiquez les dates de début et de fin du rapport, puis cliquez sur **[!UICONTROL Apply Date Filter]**.

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
   <td colname="col2"> <p>Liste de tous les fichiers sortants que Adobe <span class="keyword"></span> a générés pour cette destination et qui ont été traités ensemble. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Réussite </td> 
   <td colname="col2"> <p>Nombre d'enregistrements qui ont été correctement envoyés d' <span class="keyword"> Audience Manager</span> à la destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Echec </td> 
   <td colname="col2"> <p>Nombre d'enregistrements qui n'ont pas pu être envoyés à la destination. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements reçus </td> 
   <td colname="col2"> <p>Nombre total d'enregistrements <span class="keyword"> Adobe</span> générés dans les fichiers et tentés d'envoyer vers la destination. Dans la plupart des cas, il doit s’agir du nombre total de fichiers réussis et de fichiers ayant échoué. </p> </td> 
  </tr> 
 </tbody> 
</table>
