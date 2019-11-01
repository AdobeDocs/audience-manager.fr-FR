---
description: Générez un rapport de facturation Audience Marketplace pour afficher l’utilisation des flux de données pour le mois précédent pour chacun de vos abonnés. Vous pouvez créer un rapport pour le mois précédent à tout moment. Toutefois, le rapport est plus précis lorsque vous le générez le ou après le 10e jour du mois en cours.
seo-description: Générez un rapport de facturation Audience Marketplace pour afficher l’utilisation des flux de données pour le mois précédent pour chacun de vos abonnés. Vous pouvez créer un rapport pour le mois précédent à tout moment. Toutefois, le rapport est plus précis lorsque vous le générez le ou après le 10e jour du mois en cours.
seo-title: Facturation pour les fournisseurs de flux de données
solution: Audience Manager
title: Facturation pour les fournisseurs de flux de données
topic: API DIL
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Facturation pour les fournisseurs de flux de données {#billing-for-data-feed-providers}

Générez un rapport [!DNL Audience Marketplace] de facturation pour afficher l’utilisation des flux de données pour le mois précédent pour chacun de vos abonnés. Vous pouvez créer un rapport pour le mois précédent à tout moment. Toutefois, le rapport est plus précis lorsque vous le générez le ou après le 10e jour du mois en cours.

## Télécharger un rapport de facturation {#download-billing-report}

Pour télécharger un rapport :

1. Allez-y **[!UICONTROL Audience Marketplace > Receivables]**.
1. Cliquez sur **[!UICONTROL Generate Billing Report]**.

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
   <td colname="col1"> <p><b><span class="uicontrol"> PID du fournisseur de données</span></b> </p> </td> 
   <td colname="col2"> <p>Your <span class="keyword"> Audience Manager</span> data provider ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nom du fournisseur de données</span></b> </p> </td> 
   <td colname="col2"> <p>Nom de votre société ou organisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID d'acheteur</span></b> </p> </td> 
   <td colname="col2"> <p>ID de l'acheteur (abonné). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nom de l'acheteur</span></b> </p> </td> 
   <td colname="col2"> <p>Nom de la société ou de l’organisation de l’acheteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Identifiant du flux</span></b> </p> </td> 
   <td colname="col2"> <p>ID du flux de données </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Nom du flux</span></b> </p> </td> 
   <td colname="col2"> <p>Nom du flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Cas d’utilisation du plan</span></b> </p> </td> 
   <td colname="col2"> <p>Les cas d’utilisation permettent aux vendeurs de contrôler la manière dont les acheteurs utilisent les données. Les options incluent : </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segments et chevauchement </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modélisation </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>Voir Types de <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> plan pour les flux</a>de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unité de mesure</span></b> </p> </td> 
   <td colname="col2"> <p>Indique la facturation CPM ou à frais fixes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prix de la liste</span></b> </p> </td> 
   <td colname="col2"> <p>Frais d’abonnement pour chaque flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Prix réduit</span></b> </p> </td> 
   <td colname="col2"> <p>Frais d’abonnement pour un flux de données à tarif réduit. Voir <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Remises pour les fournisseurs</a>de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Unités</span></b> </p> </td> 
   <td colname="col2"> <p>Varie selon le type de prix du flux : </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Flux de données à frais fixes : Renvoie 1 uniquement. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">Flux de données CPM : Renvoie le montant d’utilisation réel pour les flux de données CPM. Si un abonné n’a pas fourni de données d’impression pour un flux CPM, la cellule Unités est vide et la cellule Indicateur est définie sur 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Coût total</span></b> </p> </td> 
   <td colname="col2"> <p>Montant que <span class="keyword"> Audience Manager</span> facture à un acheteur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Période de facturation</span></b> </p> </td> 
   <td colname="col2"> <p> Dans le rapport, il s’agit du dernier jour du mois précédent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Date d’accès</span></b> </p> </td> 
   <td colname="col2"> <p>date à laquelle un acheteur a saisi des informations d’abonnement/d’utilisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Date de début de l’abonnement</span></b> </p> </td> 
   <td colname="col2"> <p>date à laquelle un acheteur a commencé son abonnement au flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Date de fin d’abonnement</span></b> </p> </td> 
   <td colname="col2"> <p>date à laquelle un acheteur a mis fin à son abonnement au flux de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Indicateur</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Pour les flux CPM uniquement</i>. Les options d’indicateur incluent : </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0 : Indique qu’un abonné a signalé des informations d’utilisation à <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1 : Indique qu’un abonné n’a pas signalé d’informations d’utilisation à <span class="keyword"> Audience Manager</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Attribution de facturation et d’impression pour les flux de données CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Attribution de la facturation et de l’impression pour les flux de données à frais fixes](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Comment signaler l'utilisation du CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

