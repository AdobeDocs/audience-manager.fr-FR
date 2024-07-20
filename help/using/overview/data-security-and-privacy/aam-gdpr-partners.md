---
description: Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications associées à votre utilisation d’Audience Manager. Les principales implications des partenaires qui procèdent à ces mises à jour sont les conséquences du RGPD (Règlement général sur la protection des données) entré en vigueur le 25 mai 2018 et du nouveau GDPR Transparency and Consent Framework de l’IAB.
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: Considérations relatives au RGPD pour les destinations
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 96%

---

# Considérations relatives au RGPD pour les destinations{#gdpr-considerations-for-destinations}

Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications associées à votre utilisation d’Audience Manager. Les principales implications des partenaires qui procèdent à ces mises à jour sont les conséquences du RGPD (Règlement général sur la protection des données) entré en vigueur le 25 mai 2018 et du nouveau GDPR Transparency and Consent Framework de l’IAB.

Les partenaires d’Adobe sont maîtres de leur gestion commerciale et peuvent décider de mettre à jour leurs exigences d’intégration dans Audience Manager de temps à autre. Nous travaillons de manière proactive avec notre écosystème de partenaires Audience Manager pour que nos clients soient prévenus de tels changements.

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

## Mise à jour de l’interface utilisateur de l’Audience Manager - Intégration Yahoo/Oath/DataX {#ui-update}

En plus des mises à jour apportées au framework de l’IAB mentionnées ci-dessus, Yahoo/Oath/DataX a ajouté de nouveaux paramètres, **gdpr** et **gdpr_mode**, à sa taxonomie et aux API Audience. Leurs paramètres informent Yahoo/Oath/DataX qu’ils disposent des droits de traiter un certain segment en tant que responsable du traitement des données ou contrôleur de données. Par conséquent, les clients d’Audience Manager qui envoient des segments vers une destination Yahoo/Oath/DataX doivent désigner le paramètre approprié (Responsable du traitement ou Contrôleur), en fonction de leur contrat avec Oath.

Contactez votre consultant ou le service clientèle pour définir le paramètre approprié. Adobe ne peut pas effectuer cette mise à jour au nom du client, sauf si nous recevons une demande de mise à jour par écrit. Contactez votre représentant Yahoo/Oath/DataX pour comprendre la définition complète de ces paramètres.
