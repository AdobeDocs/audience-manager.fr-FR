---
description: Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications associées à votre utilisation d’Audience Manager. Les principales implications des partenaires qui procèdent à ces mises à jour sont les conséquences du RGPD (Règlement général sur la protection des données) entré en vigueur le 25 mai 2018 et du nouveau GDPR Transparency and Consent Framework de l’IAB.
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: Considérations relatives au RGPD pour les destinations
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
TQID: https://experienceleague.adobe.com/QJr4SR9ZcwBH-xkX-0CJ23GQ09SDmkgTeN7Vl4djSb4
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0id: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 3c88464c2249b7848c9ae80ca4c0ed58fcb81070
workflow-type: tm+mt
source-wordcount: 298
ht-degree: 96%

---

# Considérations relatives au RGPD pour les destinations{#gdpr-considerations-for-destinations}

Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications associées à votre utilisation d’Audience Manager. Les principales implications des partenaires qui procèdent à ces mises à jour sont les conséquences du RGPD (Règlement général sur la protection des données) entré en vigueur le 25 mai 2018 et du nouveau GDPR Transparency and Consent Framework de l’IAB.

Les partenaires d’Adobe sont maîtres de leur gestion commerciale et peuvent décider de mettre à jour leurs exigences d’intégration dans Audience Manager de temps à autre. Nous travaillons de manière proactive avec notre écosystème de partenaires Audience Manager pour que nos clients soient prévenus de tels changements.

<!--
## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

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
</table>
-->

## Mise à jour de l’interface utilisateur d’Audience Manager - Intégration Yahoo/Oath/DataX {#ui-update}

En plus des mises à jour apportées au framework de l’IAB mentionnées ci-dessus, Yahoo/Oath/DataX a ajouté de nouveaux paramètres, **gdpr** et **gdpr_mode**, à sa taxonomie et aux API Audience. Leurs paramètres informent Yahoo/Oath/DataX qu’ils disposent des droits de traiter un certain segment en tant que responsable du traitement des données ou contrôleur de données. Par conséquent, les clients d’Audience Manager qui envoient des segments vers une destination Yahoo/Oath/DataX doivent désigner le paramètre approprié (Responsable du traitement ou Contrôleur), en fonction de leur contrat avec Oath.

Contactez votre consultant ou le service clientèle pour définir le paramètre approprié. Adobe ne peut pas effectuer cette mise à jour au nom du client, sauf si nous recevons une demande de mise à jour par écrit. Contactez votre représentant Yahoo/Oath/DataX pour comprendre la définition complète de ces paramètres.
