---
description: Créez des segments de test mutuellement exclusifs dans les groupes de tests de segments afin de comparer et de mesurer l’efficacité de différentes destinations. Vous pouvez réserver une Population témoin et diviser votre segment en pourcentages entiers, afin de tester son efficacité.
seo-description: Créez des segments de test mutuellement exclusifs dans les groupes de tests de segments afin de comparer et de mesurer l’efficacité de différentes destinations. Vous pouvez réserver une Population témoin et diviser votre segment en pourcentages entiers, afin de tester son efficacité.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 3%

---


# [!UICONTROL Audience Lab] {#audience-lab}

Créez des segments de test mutuellement exclusifs dans [!UICONTROL Segment Test Groups] pour comparer et mesurer l&#39;efficacité de différentes destinations. Vous pouvez réserver une Population témoin et diviser votre segment en pourcentages entiers, afin de tester son efficacité.

## Aperçu {#audience-lab-overview}

[!UICONTROL Audience Lab] utilise [Profil Link](../../features/profile-merge-rules/merge-rules-overview.md) pour alimenter les tests sur plusieurs périphériques. Cela permet de s’assurer qu’un utilisateur est admissible pour le même segment de test et reçoit le même traitement sur tous les périphériques. Les segments de test des groupes de test héritent de la règle [de fusion](../../features/profile-merge-rules/merge-rules-dashboard.md) Profil que le segment de base lui a assignée.

La vue [!UICONTROL Audience Lab] par défaut affiche une carte pour chacun des groupes de tests. Cliquez sur une carte pour accéder à la **[!UICONTROL Test Group]** vue. Cette vue comprend les informations suivantes :

* **[Informations du groupe de tests](../../features/audience-lab/audience-lab-information-view.md)**
* **[Rapports du groupe de tests](../../features/audience-lab/audience-lab-reporting-view.md)**

Vous pouvez créer **jusqu’à 10 groupes** de tests, chacun avec **jusqu’à 15 segments** de test.

![](assets/test-groups-view.PNG)

## Recherche et filtrage de groupes de tests {#search-and-filter}

Une fois que vous avez début de créer plusieurs groupes de tests avec plusieurs segments de test, il peut être plus facile d&#39;utiliser la zone de recherche pour trouver un groupe de test spécifique. Vous pouvez rechercher un groupe de tests en procédant comme suit :

* le nom du groupe d&#39;essais ;
* nom de l’un des segments de test de votre groupe de tests ;
* Description du groupe de tests.

![](assets/search_and_filter_audience_lab.png)

Vous pouvez également filtrer vos groupes de tests par état. Tous les états disponibles sont décrits dans la section [Etat](../../features/audience-lab/audience-lab.md#status) ci-dessous.

## [!UICONTROL Status] {#status}

L&#39;état d&#39;un groupe de tests peut être actif, planifié, suspendu, préliminaire ou terminé. Pour plus d&#39;informations sur chacun d&#39;entre eux, consultez le tableau ci-dessous :

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
   <td colname="col2"> <p>Un groupe de test <i>actif</i> signifie que les données sont actuellement envoyées vers des destinations. Appuyez sur <b><span class="uicontrol"> Pause Test </span></b> dans la carte <b><span class="uicontrol"> Groupe de tests </span></b> pour suspendre l'envoi de données vers les destinations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Planifié </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de test <i>planifié</i> n’est pas encore actif mais ne peut plus être modifié. Il devient actif à la date de début que vous avez sélectionnée dans l'Assistant <b>Créer des groupes</b> de test. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> En pause </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de test <i>suspendu</i> n’envoie actuellement pas de données vers les destinations. Appuyez sur <b><span class="uicontrol"> Rendre actif </span></b> dans la carte <b><span class="uicontrol"> Groupe de tests </span></b> pour reprendre l'envoi des caractéristiques. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Version préliminaire </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de test <i>brouillon</i> n'est pas encore actif et peut toujours être modifié. Il n’envoie pas encore de données vers les destinations mappées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Terminé </span></b> </p> </td> 
   <td colname="col2"> <p>Un groupe de tests <i>terminé</i> a atteint la date de fin que vous avez sélectionnée dans l' <b><span class="uicontrol"> Assistant Créer des groupes de tests </span></b> et a cessé d'envoyer des données de rapports. </p> </td>
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
   <td colname="col2"> <p>Disponible <b>uniquement</b> pour les groupes de tests préliminaires. Permet de reprendre l' <b><span class="uicontrol"> assistant Créer un groupe de tests </span></b> . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pause </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les groupes de tests actifs. Permet de suspendre l’envoi des segments de test vers des destinations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Rendre actif </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les groupes de tests suspendus. Permet de reprendre l’envoi des segments de test vers les destinations. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Affichage </span></b> </p> </td>
   <td colname="col2"> <p>Disponible pour les groupes de tests terminés. Permet de vue les informations de rapports générées par le test. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Dupliquer </span></b> </p> </td>
   <td colname="col2"> <p>Permet de créer un nouveau groupe de tests avec la même configuration que celle que vous dupliquez. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Supprimer </span></b> </p> </td>
   <td colname="col2"> <p>Permet de supprimer un groupe de tests. Les segments de test seront démappés à partir des destinations, le segment de base et les caractéristiques de conversion associés au groupe de test sont entièrement modifiables. Une alerte vous invite à télécharger le fichier CSV lorsque vous supprimez un groupe de tests pour enregistrer le rapports si vous le souhaitez. </p> </td>
  </tr>
 </tbody>
</table>