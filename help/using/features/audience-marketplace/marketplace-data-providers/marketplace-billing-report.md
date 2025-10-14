---
description: Générez un rapport de facturation Audience Marketplace pour afficher l’utilisation des flux de données du mois précédent pour chacun de vos abonnés. Vous pouvez à tout moment créer un rapport pour le mois précédent. Cependant, le rapport est plus précis lorsque vous le générez le ou après le 10e jour du mois en cours.
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: Facturation pour les fournisseurs de flux de données
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Facturation pour les fournisseurs de flux de données {#billing-for-data-feed-providers}

Générez un rapport de facturation [!DNL Audience Marketplace] pour afficher l’utilisation des flux de données pour le mois précédent pour chacun de vos abonnés. Vous pouvez à tout moment créer un rapport pour le mois précédent. Cependant, le rapport est plus précis lorsque vous le générez le ou après le 10e jour du mois en cours.

## Télécharger un rapport de facturation {#download-billing-report}

Pour télécharger un rapport :

1. Accédez à **[!UICONTROL Audience Marketplace > Receivables]**.
1. Cliquez sur **[!UICONTROL Generate Billing Report]**.

## Champs de rapport définis {#report-fields-defined}

Un rapport de facturation contient les informations suivantes.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ de rapport </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID du fournisseur de données</span></b> </p> </td> 
   <td colname="col2"> <p>Identifiant <span class="keyword"> fournisseur de données Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nom <b><span class="uicontrol"> fournisseur de données </span></b> </p> </td> 
   <td colname="col2"> <p>Nom de votre société ou organisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID de l'acheteur </span></b> </p> </td> 
   <td colname="col2"> <p>ID d'acheteur (abonné). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> nom de l'acheteur</span></b> </p> </td> 
   <td colname="col2"> <p>Nom de la société ou de l'organisation de l'acheteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de flux <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p>Identifiant du flux de données </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> le flux</span></b> </p> </td> 
   <td colname="col2"> <p>Nom du flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> des cas d’utilisation de plan d’utilisation</span></b> </p> </td> 
   <td colname="col2"> <p>Les cas d’utilisation permettent aux vendeurs de contrôler la manière dont les acheteurs utilisent les données. Les options incluent : </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segments et chevauchement </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modélisation </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>Voir Types de plan <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> pour les flux de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> unité de mesure</span></b> </p> </td> 
   <td colname="col2"> <p>Indique la facturation de frais CPM ou forfaitaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> prix catalogue </span></b> </p> </td> 
   <td colname="col2"> <p>Frais d’abonnement pour chaque flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> prix réduit</span></b> </p> </td> 
   <td colname="col2"> <p>Frais d’abonnement pour un flux de données à prix réduit. Voir <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> des remises pour les fournisseurs de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unités</span></b> </p> </td> 
   <td colname="col2"> <p>Varie selon le type de prix de l’alimentation : </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Flux de données à frais fixes : renvoie 1 uniquement. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Flux de données CPM : renvoie le volume d’utilisation réel des flux de données CPM. Si un abonné n’a pas fourni de données d’impression pour un flux CPM, la cellule Unités est vide et la cellule Indicateur est définie sur 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> coût total</span></b> </p> </td> 
   <td colname="col2"> <p>Montant <span class="keyword"> facture Audience Manager</span> à un acheteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> période de facturation</span></b> </p> </td> 
   <td colname="col2"> <p> Dans le rapport, il s’agit du dernier jour du mois précédent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Date D’Entrée </span></b> </p> </td> 
   <td colname="col2"> <p>Date à laquelle un acheteur a saisi les informations d'abonnement/d'utilisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Date De Début D’Abonnement</span></b> </p> </td> 
   <td colname="col2"> <p>Date à laquelle un acheteur a commencé son abonnement au flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> la date de fin de l’abonnement</span></b> </p> </td> 
   <td colname="col2"> <p>Date à laquelle un acheteur a mis fin à son abonnement au flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indicateur de <b><span class="uicontrol"></span></b> </p> </td> 
   <td colname="col2"> <p> <i>Pour les flux CPM uniquement</i>. Les options d’indicateur incluent : </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0 : indique qu’un abonné a signalé des informations d’utilisation à <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1 : indique qu’un abonné n’a pas signalé d’informations d’utilisation à <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Facturation et affectation des impressions pour les flux de données CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Facturation et affectation d’impressions pour les flux de données à frais fixes](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Comment signaler l’utilisation de CPM &#x200B;](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
