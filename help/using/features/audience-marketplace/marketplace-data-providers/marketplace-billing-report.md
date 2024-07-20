---
description: Générez un rapport de facturation des Audiences Marketplace afin d’afficher l’utilisation des flux de données pour le mois précédent pour chacun de vos abonnés. Vous pouvez créer à tout moment un rapport pour le mois précédent. Toutefois, le rapport est plus précis lorsque vous le générez le ou après le 10e jour du mois en cours.
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

Générez un rapport de facturation [!DNL Audience Marketplace] afin d’afficher l’utilisation des flux de données pour le mois précédent pour chacun de vos abonnés. Vous pouvez créer à tout moment un rapport pour le mois précédent. Toutefois, le rapport est plus précis lorsque vous le générez le ou après le 10e jour du mois en cours.

## Téléchargement d’un rapport de facturation {#download-billing-report}

Pour télécharger un rapport :

1. Accédez à **[!UICONTROL Audience Marketplace > Receivables]**.
1. Cliquez sur **[!UICONTROL Generate Billing Report]**.

## Champs du rapport définis {#report-fields-defined}

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
   <td colname="col1"> <p><b><span class="uicontrol"> PID de fournisseur de données </span></b> </p> </td> 
   <td colname="col2"> <p>Votre identifiant de fournisseur de données <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nom du fournisseur de données </span></b> </p> </td> 
   <td colname="col2"> <p>Nom de votre société ou organisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID d’achat</span></b> </p> </td> 
   <td colname="col2"> <p>Identifiant de l'acheteur (abonné). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nom d’utilisateur</span></b> </p> </td> 
   <td colname="col2"> <p>Nom de la société ou de l’organisation de l’acheteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID de flux</span></b> </p> </td> 
   <td colname="col2"> <p>ID du flux de données </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nom du flux </span></b> </p> </td> 
   <td colname="col2"> <p>Nom du flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Cas d’utilisation du plan</span></b> </p> </td> 
   <td colname="col2"> <p>Les cas d’utilisation permettent aux vendeurs de contrôler la manière dont les acheteurs utilisent les données. Les options incluent : </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segments et chevauchement </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modélisation </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>Voir <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Types de plan pour les flux de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unité de mesure</span></b> </p> </td> 
   <td colname="col2"> <p>Indique la facturation CPM ou mensuelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prix </span></b> </p> </td> 
   <td colname="col2"> <p>Frais d’abonnement pour chaque flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prix réduit </span></b> </p> </td> 
   <td colname="col2"> <p>Frais d’abonnement pour un flux de données à prix réduit. Voir <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Remises pour les fournisseurs de données</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unités</span></b> </p> </td> 
   <td colname="col2"> <p>Varie en fonction du type de prix du flux : </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Flux de données à frais plats : renvoie 1 uniquement. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Flux de données CPM : renvoie le montant d’utilisation réel des flux de données CPM. Si un abonné n’a pas fourni de données d’impression pour un flux CPM, la cellule Unités est vide et la cellule Indicateur est définie sur 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Coût total</span></b> </p> </td> 
   <td colname="col2"> <p>La valeur <span class="keyword"> Audience Manager</span> facture un acheteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Période de facturation</span></b> </p> </td> 
   <td colname="col2"> <p> Dans le rapport, il s’agit du dernier jour du mois précédent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Date d’entrée</span></b> </p> </td> 
   <td colname="col2"> <p>Date à laquelle un acheteur a saisi des informations d’abonnement/d’utilisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Date de début d’abonnement </span></b> </p> </td> 
   <td colname="col2"> <p>Date à laquelle un acheteur a commencé son abonnement au flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Date de fin d’abonnement </span></b> </p> </td> 
   <td colname="col2"> <p>Date à laquelle un acheteur a mis fin à son abonnement au flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flag</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Pour les flux CPM uniquement</i>. Les options d’indicateur incluent : </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0 : indique qu’un abonné a signalé les informations d’utilisation à l’Audience Manager <span class="keyword"> </span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1 : indique qu’un abonné n’a pas signalé d’informations d’utilisation à l’Audience Manager <span class="keyword"></span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Affectation de facturation et d’impression pour les flux de données CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [ Affectation de facturation et d’impressions pour les flux de données de flux plats](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Comment signaler l’utilisation du CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
