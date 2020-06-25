---
description: Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu'elles deviennent disponibles, ainsi que les implications liées à votre pratique d'Audience Manager. Les principales implications pour les partenaires qui procèdent à ces mises à jour sont le résultat du RGPD (Règlement général sur la protection des données), qui est entré en vigueur le 25 mai 2018 et du nouveau Cadre de transparence et de consentement du RGGMD du CCI (Cadre du CCI).
seo-description: Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu'elles deviennent disponibles, ainsi que les implications liées à votre pratique d'Audience Manager. Les principales implications pour les partenaires qui procèdent à ces mises à jour sont le résultat du RGPD (Règlement général sur la protection des données), qui est entré en vigueur le 25 mai 2018 et du nouveau Cadre de transparence et de consentement du RGGMD du CCI (Cadre du CCI).
seo-title: Considérations relatives aux RMPD pour les destinations
solution: Audience Manager
title: Considérations relatives aux RMPD pour les destinations
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---


# Considérations relatives aux RMPD pour les destinations{#gdpr-considerations-for-destinations}

Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu&#39;elles deviennent disponibles, ainsi que les implications liées à votre pratique d&#39;Audience Manager. Les principales implications pour les partenaires qui procèdent à ces mises à jour sont le résultat du RGPD (Règlement général sur la protection des données), qui est entré en vigueur le 25 mai 2018 et du nouveau Cadre de transparence et de consentement du RGGMD du CCI (Cadre du CCI).

Les partenaires Adobe sont propriétaires de leurs processus d’entreprise et peuvent décider de mettre à jour leurs exigences d’intégration avec Audience Manager de temps à autre. Nous travaillons de façon proactive avec notre écosystème de partenaires d&#39;Audiences Manager pour tenir nos clients informés des changements.

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table> -->

## Mise à jour de l&#39;interface utilisateur de l&#39;Audience Manager - Intégration de Yahoo/Oath/DataX {#ui-update}

Outre les mises à jour apportées au cadre IAB mentionnées ci-dessus, Yahoo/Oath/DataX a ajouté de nouveaux paramètres, **gdpr** et **gdpr_mode**, à leurs API de taxonomie et d&#39;Audience. Leurs paramètres informent Yahoo/Oath/DataX qu&#39;ils ont les droits de traiter un segment donné comme processeur de données ou comme contrôleur de données. Par conséquent, les clients Audiences Manager qui envoient des segments vers une destination Yahoo/Oath/DataX doivent désigner le paramètre approprié (processeur ou contrôleur), en fonction de leur accord avec Oath.

Contactez votre consultant ou le service à la clientèle pour définir le paramètre approprié. Adobe ne peut pas effectuer cette mise à jour pour le compte d&#39;un client, à moins que nous ne recevions une correspondance écrite nous demandant cette mise à jour. Contactez votre représentant Yahoo/Oath/DataX pour comprendre la définition complète de ces paramètres.
