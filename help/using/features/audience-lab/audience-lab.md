---
description: Créez de manière collective des segments de test exclusifs dans les groupes de test de segments afin de comparer et mesurer l'efficacité de différentes destinations. Vous pouvez définir un groupe de contrôle et diviser votre segment en pourcentages d'un ensemble afin de tester l'efficacité.
seo-description: Créez de manière collective des segments de test exclusifs dans les groupes de test de segments afin de comparer et mesurer l'efficacité de différentes destinations. Vous pouvez définir un groupe de contrôle et diviser votre segment en pourcentages d'un ensemble afin de tester l'efficacité.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: API DIL
uuid: aaee 820 c -1 e 78-4 fd 4-bd 8 f -2629085 d 78 e 9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Create mutually exclusive test segments in [!UICONTROL Segment Test Groups] to compare and measure effectiveness of different destinations. Vous pouvez définir un groupe de contrôle et diviser votre segment en pourcentages d'un ensemble afin de tester l'efficacité.

## Aperçu {#audience-lab-overview}

[!UICONTROL Audience Lab] utilise [le lien de profil](../../features/profile-merge-rules/merge-rules-overview.md) pour effectuer le test entre plusieurs périphériques. Cela permet de s'assurer qu'un utilisateur est admissible pour le même segment de test et reçoit le même traitement sur tous les appareils. The test segments in test groups will inherit the [Profile Merge Rule](../../features/profile-merge-rules/merge-rules-dashboard.md) the base segment has assigned to it.

The [!UICONTROL Audience Lab] default view displays a card for each of the test groups. Click a card to access the **[!UICONTROL Test Group]** view. Cette vue comprend les informations suivantes :

* **[Test des informations du groupe](../../features/audience-lab/audience-lab-information-view.md)**
* **[Création de rapports de groupe de test](../../features/audience-lab/audience-lab-reporting-view.md)**

You are able to create **up to 10 test groups**, each one with **up to 15 test segments**.

![](assets/test-groups-view.PNG)

## Search and Filter Test Groups {#search-and-filter}

Lorsque vous commencez à créer plusieurs groupes de test avec plusieurs segments de test, il peut être plus facile d'utiliser la zone de recherche pour trouver un groupe de test spécifique. Vous pouvez rechercher un groupe de test par :

* Nom du groupe de test ;
* nom de l'un des segments de test dans votre groupe de test ;
* Description du groupe de test.

![](assets/search_and_filter_audience_lab.png)

Vous pouvez également filtrer les groupes de tests par état. All available statuses are described in the [Status](../../features/audience-lab/audience-lab.md#status) section below.

## État {#status}

L'état d'un groupe de test peut être actif, planifié, suspendu, brouillon ou terminé. Plus d'informations sur chacune d'elles dans le tableau ci-dessous :

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
   <td colname="col2"> <p>An <i>active</i> test group means that data is currently being sent to destinations. Press <b><span class="uicontrol"> Pause Test </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to suspend sending data to destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Planifié </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>scheduled</i> test group is not yet active but cannot be edited anymore. It will become active at the start date you selected in the <b>Create Test Groups</b> wizard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> En pause </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>paused</i> test group does not currently send data to destinations. Press <b><span class="uicontrol"> Make Active </span></b> in the <b><span class="uicontrol"> Test Group </span></b> card to resume sending traits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Version préliminaire </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>draft</i> test group is not yet active and can still be edited. Il n'envoie pas encore de données aux destinations mappées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Terminé </span></b> </p> </td> 
   <td colname="col2"> <p>A <i>completed</i> test group has reached the end date you selected in the <b><span class="uicontrol"> Create Test Groups </span></b> wizard and has stopped sending reporting data. </p> </td>
  </tr>
 </tbody>
</table>

## Actions {#actions}

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
   <td colname="col2"> <p>Available <b>only</b> for draft test groups. Allows you to resume the <b><span class="uicontrol"> Create New Test Group </span></b> wizard. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les groupes de test actifs. Permet de suspendre l'envoi des segments de test vers les destinations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rendre actif </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les groupes de test en pause. Permet de reprendre l'envoi des segments de test vers les destinations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Affichage </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les groupes de test terminés. Permet d'afficher les informations de rapport que le test a générées. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Dupliquer </span></b> </p> </td>
   <td colname="col2"> <p>Permet de créer un groupe de test avec la même configuration que celle que vous dupliquez. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Supprimer </span></b> </p> </td>
   <td colname="col2"> <p>Permet de supprimer un groupe de test. Les segments de test ne sont pas mappés à partir des destinations, le segment de ligne de base et les caractéristiques de conversion associées au groupe de test sont entièrement modifiables. Une alerte vous invite à télécharger le fichier CSV lorsque vous supprimerez un groupe de tests pour enregistrer les rapports si vous le souhaitez. </p> </td>
  </tr>
 </tbody>
</table>