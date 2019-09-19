---
description: La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment dans Audience Manager, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.
keywords: qualification de caractéristique;réalisation de caractéristiques;Réalisations de caractéristiques uniques;UTR;Population totale de caractéristiques;TTP
seo-description: La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment dans Audience Manager, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.
seo-title: Référence de qualification des traits
solution: Audience Manager
title: Référence de qualification des traits
uuid: 07e0a639-2fb2-45d8-bad7-10fb46b08ba9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Référence de qualification des traits {#trait-qualification-reference}

La qualification des caractéristiques, ou réalisation des caractéristiques, est traitée différemment dans Audience Manager, selon le type de caractéristique. Consultez le tableau ci-dessous pour obtenir des informations détaillées sur la qualification des caractéristiques.

## Qualification des caractéristiques par type de caractéristiques {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de trait </th> 
   <th colname="col2" class="entry"> Critères de qualification </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques basées sur des règles </p> </td> 
   <td colname="col2"> <p>La qualification des caractéristiques se produit en temps réel, car les utilisateurs remplissent les conditions requises pour obtenir une caractéristique dans leur navigateur. Les utilisateurs commenceront à bénéficier de la qualification pour une caractéristique basée sur des règles environ 4 heures après avoir <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> créé la caractéristique</a> dans l’interface utilisateur. </p> <p>Les caractéristiques basées sur des règles vous permettent d’utiliser des contrôles de <a href="../../features/segments/recency-and-frequency.md"> récence et de fréquence</a> pour le plafonnement de la fréquence des annonces et d’autres cas d’utilisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques intégrées </p> </td> 
   <td colname="col2"> <p>La qualification des caractéristiques se produit après le traitement d’un fichier entrant, c’est-à-dire lorsque le fichier entrant est <a href="../../faq/faq-inbound-data-ingestion.md"> importé dans Audience Manager</a> et que la qualification des caractéristiques se produit. </p> <p> Pour les caractéristiques intégrées, le nombre maximal de qualifications pour un profil utilisateur est 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques algorithmiques </p> </td> 
   <td colname="col2"> <p>Pour les caractéristiques algorithmiques, le nombre maximal de qualifications pour un profil utilisateur est 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques des dossiers </p> </td> 
   <td colname="col2"> <p>Une caractéristique de dossier résume les qualités des caractéristiques qu’elle contient. </p> <p>Caractéristiques <a href="../../features/traits/about-folder-traits.md"> des dossiers de lecture : À propos</a> de. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Caractéristiques d’audience actives et caractéristiques synchronisées de la source de données </p> </td> 
   <td colname="col2"> <p>Une caractéristique Audience <span class="wintitle"></span> active contient tous les périphériques sous gestion dans votre <span class="wintitle"> compte Audience Manager</span> . </p> <p><span class="wintitle"> Les caractéristiques</span> synchronisées de la source de données effectuent le suivi de tous les utilisateurs associés à une source de données. </p> <p>En savoir plus sur les caractéristiques <a href="../../features/traits/client-activity-synced-audience-traits.md"> d’audience actives et les caractéristiques</a>synchronisées de source de données. </p> </td>
  </tr>
 </tbody>
</table>

## Valorisation des caractéristiques uniques et population totale des caractéristiques {#unique-trait-realizations}

![](assets/utr-ttp1.png)

Le **[!UICONTROL Unique Trait Realizations]** compte du nombre de visiteurs qui ont ajouté la caractéristique à leur profil, au cours de différentes périodes.

Le **[!UICONTROL Total Trait Population]** représente le nombre de visiteurs qui ont cette caractéristique sur leur profil.

Pensez aux chiffres de cette façon. Dans l’image ci-dessus, dans la vue Détails [des](../../features/traits/trait-details-page.md) caractéristiques, 181 représente le nombre de périphériques actifs qui ont visité vos propriétés hier. Le nombre [!UICONTROL Total Trait Population] de 1 595 représente le nombre d’utilisateurs actuellement qualifiés pour cette caractéristique. La [!UICONTROL Total Trait Population] figure indique le nombre total d’utilisateurs pouvant être utilisés pour la segmentation/le ciblage. En règle générale, les utilisateurs restent une caractéristique pendant 120 jours.

Parce que nous exécutons deux tâches de calcul différentes pour calculer les deux populations, le [!UICONTROL Total Trait Population] reste en retard par rapport au [!UICONTROL Unique Trait Realizations] de 24 heures. Dans le graphique ci-dessus, vous pouvez voir 175 [!UICONTROL Unique Trait Realizations] et un [!UICONTROL Total Trait Population] de 6 pour le 11 février. Les 175 profils sont ajoutés au [!UICONTROL Total Trait Population] jour suivant.

Pour continuer sur le point de rentrer chez vous, si vous avez connu un pic de 10 000 visiteurs en ce moment, ils apparaîtraient dans le demain [!UICONTROL Unique Trait Realizations], mais seulement 24 heures plus tard dans le [!UICONTROL Total Trait Population].

## Limite de qualification des caractéristiques {#trait-qualification-limit}

Nous imposons une limite de 150 000 qualifications de caractéristiques pour chaque profil utilisateur, qu’il s’agisse d’un profil authentifié ( [DPUUID](../../reference/ids-in-aam.md)) ou d’un ID d’appareil ( [UUID](../../reference/ids-in-aam.md)). Notez que si les DPUUID sont propres à une instance spécifique de [!DNL Audience Manager], les UUID sont partagés sur la [!DNL Audience Manager] plateforme. Pour [!UICONTROL UUID]nous, nous imposons une politique d’équité dans le stockage des qualifications relatives aux caractéristiques. Un algorithme garantit qu’une part égale du [!UICONTROL UUID] profil est rendue disponible pour chaque instance de [!DNL Audience Manager].
