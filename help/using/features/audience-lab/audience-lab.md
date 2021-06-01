---
description: Créez des segments de test mutuellement exclusifs dans des groupes de test de segment pour comparer et mesurer l’efficacité de différentes destinations. Vous pouvez mettre de côté une population témoin et diviser votre segment en pourcentages d’un tout, afin de tester l’efficacité.
seo-description: Créez des segments de test mutuellement exclusifs dans des groupes de test de segment pour comparer et mesurer l’efficacité de différentes destinations. Vous pouvez mettre de côté une population témoin et diviser votre segment en pourcentages d’un tout, afin de tester l’efficacité.
seo-title: 'Audience Lab '
solution: Audience Manager
title: 'Audience Lab '
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: 'Audience Lab '
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 4%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Créez des segments de test mutuellement exclusifs dans [!UICONTROL Segment Test Groups] pour comparer et mesurer l’efficacité de différentes destinations. Vous pouvez mettre de côté une population témoin et diviser votre segment en pourcentages d’un tout, afin de tester l’efficacité.

## Présentation {#audience-lab-overview}

[!UICONTROL Audience Lab] utilise  [Profile ](../../features/profile-merge-rules/merge-rules-overview.md) Linkto pour effectuer des tests sur plusieurs appareils. Cela permet de s’assurer qu’un utilisateur est admissible pour le même segment de test et reçoit le même traitement sur tous les appareils. Les segments de test des groupes de test hériteront de la [stratégie de fusion de profils](../../features/profile-merge-rules/merge-rules-dashboard.md) que le segment de base lui a attribuée.

La vue [!UICONTROL Audience Lab] par défaut affiche une carte pour chacun des groupes de test. Cliquez sur une carte pour accéder à la vue **[!UICONTROL Test Group]**. Cette vue comprend les informations suivantes :

* **[Informations sur le groupe de test](../../features/audience-lab/audience-lab-information-view.md)**
* **[Rapports sur les groupes de test](../../features/audience-lab/audience-lab-reporting-view.md)**

Vous pouvez créer **jusqu’à 10 groupes de test**, chacun avec **jusqu’à 15 segments de test**.

![](assets/test-groups-view.PNG)

## Rechercher et filtrer des groupes de test {#search-and-filter}

Une fois que vous avez commencé à créer plusieurs groupes de test avec plusieurs segments de test, il peut être plus facile d’utiliser la zone de recherche pour trouver un groupe de test spécifique. Vous pouvez rechercher un groupe de tests en procédant comme suit :

* le nom du groupe test ;
* Le nom de l’un des segments de test de votre groupe de tests ;
* Description du groupe de test.

![](assets/search_and_filter_audience_lab.png)

Vous pouvez également filtrer vos groupes de test par état. Tous les états disponibles sont décrits dans la section [État](../../features/audience-lab/audience-lab.md#status) ci-dessous.

## [!UICONTROL Status] {#status}

L’état d’un groupe de test peut être principal, planifié, en pause, en version préliminaire ou terminé. Vous trouverez plus d’informations sur chacune d’elles dans le tableau ci-dessous :

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> État </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Actif </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de test <i>principal</i> signifie que les données sont actuellement envoyées vers les destinations. Appuyez sur <b><span class="uicontrol"> Pause Test </span></b> dans la carte <b><span class="uicontrol"> Groupe de tests </span></b> pour suspendre l’envoi de données aux destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Planifié </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de test <i>planifié</i> n’est pas encore principal, mais ne peut plus être modifié. Elle deviendra principale à la date de début que vous avez sélectionnée dans l’assistant <b>Créer des groupes test</b>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> En pause </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de test <i>paused</i> n’envoie actuellement pas de données vers les destinations. Appuyez sur <b><span class="uicontrol"> Rendre Principal </span></b> dans la carte <b><span class="uicontrol"> Groupe de tests </span></b> pour reprendre l’envoi des caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Version préliminaire </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de test <i>draft</i> n’est pas encore principal et peut être modifié. Il n’envoie pas encore de données vers les destinations mappées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Terminé </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de test <i>terminé</i> a atteint la date de fin que vous avez sélectionnée dans l’assistant <b><span class="uicontrol"> Créer des groupes de test </span></b> et a cessé d’envoyer des données de rapport. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Actions </th> 
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Modifier </span></b> </p> </td>
   <td colname="col2"> <p>Disponible <b>uniquement</b> pour les groupes de test de brouillon. Permet de reprendre l’assistant <b><span class="uicontrol"> Créer un groupe de test </span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les principaux groupes de test. Permet de suspendre l’envoi des segments de test vers des destinations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rendre Principal  </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les groupes de test en pause. Permet de reprendre l’envoi des segments de test aux destinations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Affichage </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les groupes de test terminés. Permet d'afficher les informations de rapport générées par le test. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Dupliquer </span></b> </p> </td>
   <td colname="col2"> <p>Permet de créer un nouveau groupe de test avec la même configuration que celle que vous dupliquez. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Supprimer </span></b> </p> </td>
   <td colname="col2"> <p>Permet de supprimer un groupe de tests. Les segments de test seront démappés des destinations, le segment de ligne de base et les caractéristiques de conversion associés au groupe de test sont entièrement modifiables. Une alerte vous invite à télécharger le fichier CSV lorsque vous supprimez un groupe de test pour enregistrer le rapport si vous le souhaitez. </p> </td>
  </tr>
 </tbody>
</table>
