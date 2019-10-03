---
description: Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications liées à votre pratique d’Audience Manager. Les principales implications pour les partenaires qui procèdent à ces mises à jour sont le résultat du RMMD (Règlement général sur la protection des données), qui est entré en vigueur le 25 mai 2018 et du nouveau Cadre de transparence et de consentement du RMMD du CCI (Cadre du CCI).
seo-description: Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications liées à votre pratique d’Audience Manager. Les principales implications pour les partenaires qui procèdent à ces mises à jour sont le résultat du RMMD (Règlement général sur la protection des données), qui est entré en vigueur le 25 mai 2018 et du nouveau Cadre de transparence et de consentement du RMMD du CCI (Cadre du CCI).
seo-title: Considérations sur le RMMD pour les destinations
solution: Audience Manager
title: Considérations sur le RMMD pour les destinations
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# Considérations sur le RMMD pour les destinations{#gdpr-considerations-for-destinations}

Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications liées à votre pratique d’Audience Manager. Les principales implications pour les partenaires qui procèdent à ces mises à jour sont le résultat du RMMD (Règlement général sur la protection des données), qui est entré en vigueur le 25 mai 2018 et du nouveau Cadre de transparence et de consentement du RMMD du CCI (Cadre du CCI).

Les partenaires Adobe sont propriétaires de leurs processus d’entreprise et peuvent décider de mettre à jour leurs exigences d’intégration avec Audience Manager de temps à autre. Nous travaillons de manière proactive avec notre écosystème partenaire Audience Manager pour tenir nos clients informés des changements.

## Mises à jour des partenaires d’Audience Manager - Synchronisations des identifiants {#partner-updates-id-syncs}

Certains partenaires, comme indiqué dans le tableau ci-dessous, ont modifié leurs exigences d’intégration avec Audience Manager afin d’inclure un soutien basé sur le Cadre du CCI, afin de se conformer aux normes du RMPC.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nom du partenaire </p> </th> 
   <th colname="col2" class="entry"> <p>Impact attendu </p> </th> 
   <th colname="col3" class="entry"> <p>État du changement </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>Les synchronisations d’ID pour les utilisateurs de l’Union européenne sont ignorées par le partenaire </p> </td> 
   <td colname="col3"> <p>En direct depuis le 22 mai 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Service commercial </p> </td> 
   <td colname="col2"> <p>Les synchronisations d’ID pour les utilisateurs de l’Union européenne sont ignorées par le partenaire </p> </td> 
   <td colname="col3"> <p>Pas encore vivant </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>Les synchronisations d’ID pour les utilisateurs de l’Union européenne sont ignorées par le partenaire </p> </td> 
   <td colname="col3"> <p>Pas encore vivant </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>Les synchronisations d’ID pour les utilisateurs de l’Union européenne sont ignorées par le partenaire </p> </td> 
   <td colname="col3"> <p>Pas encore vivant </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mise à jour de l’interface utilisateur d’Audience Manager - Intégration de Yahoo/Oath/DataX {#ui-update}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, gdpr and gdpr_mode, to their taxonomy and Audience APIs. ******** Leurs paramètres indiquent à Yahoo/Oath/DataX qu’ils ont les droits de traiter un certain segment en tant que processeur de données ou en tant que contrôleur de données. Par conséquent, les clients d’Audience Manager qui envoient des segments à une destination Yahoo/Oath/DataX doivent désigner le paramètre approprié (Processeur ou Contrôleur), en fonction de leur accord avec Oath.

Please reach out to your Consultant or Client Care to set the correct parameter. Adobe cannot make this update on behalf of a customer unless we receive written correspondence, requesting this update. Please reach out to your Yahoo/Oath/DataX representative to understand the full definition of these parameters.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

In order to help our customers automate GDPR requests, Audience Manager notifies our activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

However, some of our activation partners:

1. Cannot support unsegment requests from Adobe and/or
1. Are not able to receive updates from us more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx) to see which Audience Manager activation partners support unsegment.
