---
description: Cette page décrit les informations fournies directement par nos partenaires, dès qu'elles sont disponibles, ainsi que toutes les implications liées à votre pratique Audience Manager. Les implications clés pour les partenaires effectuant ces mises à jour sont le résultat de GDPR (Règle générale de protection des données), qui a été mise en œuvre le 25 mai 2018 et le nouveau cadre de transparence et de consentement IAB GDPR (IAB Framework).
seo-description: Cette page décrit les informations fournies directement par nos partenaires, dès qu'elles sont disponibles, ainsi que toutes les implications liées à votre pratique Audience Manager. Les implications clés pour les partenaires effectuant ces mises à jour sont le résultat de GDPR (Règle générale de protection des données), qui a été mise en œuvre le 25 mai 2018 et le nouveau cadre de transparence et de consentement IAB GDPR (IAB Framework).
seo-title: Remarques concernant le GDPR pour les destinations
solution: Audience Manager
title: Remarques concernant le GDPR pour les destinations
uuid: e 8 a 40060-086 c -4 f 03-b 48 c -9 c 903 acb 7891
translation-type: tm+mt
source-git-commit: 69be038d0f2d31b6b5eda20041082c1890abc38f

---


# GDPR Considerations for Destinations{#gdpr-considerations-for-destinations}

Cette page décrit les informations fournies directement par nos partenaires, dès qu'elles sont disponibles, ainsi que toutes les implications liées à votre pratique Audience Manager. Les implications clés pour les partenaires effectuant ces mises à jour sont le résultat de GDPR (Règle générale de protection des données), qui a été mise en œuvre le 25 mai 2018 et le nouveau cadre de transparence et de consentement IAB GDPR (IAB Framework).

Les partenaires Adobe possèdent leurs processus métier et peuvent décider de mettre à jour leurs exigences d'intégration avec Audience Manager de temps à autres. Nous collaborons activement avec notre écosystème partenaires Audience Manager pour garder nos clients informés des modifications.

## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Certains partenaires, comme indiqué dans le tableau ci-dessous, ont modifié leurs exigences d'intégration avec Audience Manager pour inclure la prise en charge de la structure IAB, afin de se conformer aux normes GDPR.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Nom du partenaire </p> </th> 
   <th colname="col2" class="entry"> <p>Impact attendu </p> </th> 
   <th colname="col3" class="entry"> <p>État de la modification </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Serment/datax </p> </td> 
   <td colname="col2"> <p>Les synchronisations d'ID pour les utilisateurs de l'Union européenne sont ignorées par le partenaire </p> </td> 
   <td colname="col3"> <p>Live depuis le 22 mai 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Service administratif </p> </td> 
   <td colname="col2"> <p>Les synchronisations d'ID pour les utilisateurs de l'Union européenne sont ignorées par le partenaire </p> </td> 
   <td colname="col3"> <p>Pas encore en direct </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>Les synchronisations d'ID pour les utilisateurs de l'Union européenne sont ignorées par le partenaire </p> </td> 
   <td colname="col3"> <p>Pas encore en direct </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Liveramp </p> </td> 
   <td colname="col2"> <p>Les synchronisations d'ID pour les utilisateurs de l'Union européenne sont ignorées par le partenaire </p> </td> 
   <td colname="col3"> <p>Pas encore en direct </p> </td> 
  </tr> 
 </tbody> 
</table>

## Audience Manager UI Update - Yahoo/Oath/DataX Integration {#ui-update}

In addition to the updates to the IAB Framework mentioned above, Yahoo/Oath/DataX has added new parameters, **gdpr** and **gdpr_mode**, to their taxonomy and Audience APIs. Leurs paramètres informent Yahoo/Serment/datax qu'ils ont les droits de traiter un segment spécifique comme un processeur de données ou comme un contrôleur de données. Par conséquent, les clients Audience Manager qui envoient des segments à une destination Yahoo/Serment/datax doivent désigner le paramètre approprié (Processeur ou Contrôleur), en fonction de leur accord avec serment.

Contactez votre consultant ou le service à la clientèle pour définir le paramètre correct. Adobe ne peut pas effectuer cette mise à jour pour le compte d'un client, sauf si nous recevons une correspondance écrite, demandant cette mise à jour. Contactez votre représentant Yahoo/Serment/datax pour comprendre la définition complète de ces paramètres.

## Audience Manager Partners With Unsegmentation Capabilities {#aam-partners-with-unsegmentation}

Afin d'aider nos clients à automatiser les demandes GDPR, Audience Manager avertit nos partenaires d'activation au sujet des demandes de suppression à partir des sujets de données en les envoyant de manière non segmentée (ou en supprimant des segments).

Toutefois, certains de nos partenaires d'activation :

1. Ne peut pas prendre en charge les demandes de unsegment d'Adobe et/ou
1. Nous ne pouvons pas recevoir plus de mises à jour qu'une seule fois dans 30 jours.

Dans ce cas, vous ne pouvez pas envoyer de demandes de suppression aux partenaires d'activation de manière automatisée via Audience Manager. Download our [Partner Excel sheet](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx) to see which Audience Manager activation partners support unsegment.
