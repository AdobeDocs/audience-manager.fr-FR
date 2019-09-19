---
description: Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications liées à votre pratique d’Audience Manager. Les principales implications pour les partenaires qui procèdent à ces mises à jour sont le résultat du RMMD (Règlement général sur la protection des données), qui est entré en vigueur le 25 mai 2018 et du nouveau Cadre de transparence et de consentement du RMMD du CCI (Cadre du CCI).
seo-description: Cette page présente les informations fournies directement par nos partenaires, au fur et à mesure qu’elles deviennent disponibles, ainsi que les implications liées à votre pratique d’Audience Manager. Les principales implications pour les partenaires qui procèdent à ces mises à jour sont le résultat du RMMD (Règlement général sur la protection des données), qui est entré en vigueur le 25 mai 2018 et du nouveau Cadre de transparence et de consentement du RMMD du CCI (Cadre du CCI).
seo-title: Considérations sur le RMMD pour les destinations
solution: Audience Manager
title: Considérations sur le RMMD pour les destinations
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

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

Outre les mises à jour du Cadre IAB mentionnées ci-dessus, Yahoo/Oath/DataX a ajouté de nouveaux paramètres, **gdpr** et **gdpr_mode**, à leurs API de taxonomie et d’audience. Leurs paramètres indiquent à Yahoo/Oath/DataX qu’ils ont les droits de traiter un certain segment en tant que processeur de données ou en tant que contrôleur de données. Par conséquent, les clients d’Audience Manager qui envoient des segments à une destination Yahoo/Oath/DataX doivent désigner le paramètre approprié (Processeur ou Contrôleur), en fonction de leur accord avec Oath.

Contactez votre consultant ou le service à la clientèle pour définir le paramètre approprié. Adobe ne peut pas effectuer cette mise à jour pour le compte d’un client, sauf si nous recevons une correspondance écrite nous demandant cette mise à jour. Contactez votre représentant Yahoo/Oath/DataX pour comprendre la définition complète de ces paramètres.

## Partenaires Audience Manager Avec Des Fonctionnalités D’Unsegmentation {#aam-partners-with-unsegmentation}

Afin d’aider nos clients à automatiser les demandes GDPR, Audience Manager informe nos partenaires d’activation des demandes de suppression des objets de données en leur envoyant des informations de non-segmentation (ou de suppression de segment).

Cependant, certains de nos partenaires d’activation :

1. Impossible de prendre en charge les demandes de non-segmentation d’Adobe et/ou
1. Ne peuvent pas recevoir les mises à jour de nous plus d'une fois par 30 jours.

Dans ce cas, vous ne pouvez pas envoyer de demandes de suppression aux partenaires d’activation de manière automatisée via Audience Manager. Téléchargez notre feuille [Excel de](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) partenaire pour savoir quels partenaires d’activation d’Audience Manager prennent en charge le non-segmentation.
