---
description: Un rapport Général renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-description: Un rapport Général dans l’Audience Manager renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-title: Rapports généraux en Audience Manager
solution: Audience Manager
title: Rapports généraux
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: general & trend reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 0%

---


# Rapports généraux{#general-reports}

Un [!UICONTROL General] rapport renvoie des données de performances sur les caractéristiques, les segments et les destinations.

## Aperçu {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les permissions des groupes d&#39;utilisateurs aux [!UICONTROL General] rapports. Les utilisateurs ne peuvent afficher que les caractéristiques et segments dans le rapports pour lesquels ils disposent d’autorisations de vue. [!UICONTROL RBAC] permet de contrôler quelles données de rapports les équipes internes peuvent vue. Par exemple, une agence qui gère différents comptes d’annonceurs peut configurer des autorisations de groupe d’utilisateurs afin qu’une équipe qui gère le compte de l’annonceur A ne puisse pas afficher les données de rapports de l’annonceur B.

Exécutez un [!UICONTROL General] rapport lorsque vous devez :

* Examinez les performances par caractéristique, segment ou destination.
* Effectuez le suivi des impressions (totales et uniques) à des intervalles de 1, 7, 14, 30, 60 et 90 jours.
* Examiner les décomptes de charge totale et unique.
* Comparer les performances des caractéristiques et des segments.
* Identifiez les caractéristiques et les segments de performances fortes ou faibles, analysez la demande ou comparez les données de charge/feu aux rapports tiers.
* Exportez des données (format .csv) pour une analyse et un partage supplémentaires.

L’illustration suivante présente un aperçu général des éléments clés du [!UICONTROL General] rapport.

![](assets/general_reports.png)

1. Configurez les options suivantes :

   * **Type de rapport :** Sélectionnez le type de rapport souhaité (Caractéristique, Segment ou Destination).

   * **Pour les dates de passage à :** Spécifiez la plage de dates du rapport.

2. Recherchez une caractéristique, un segment ou une destination par nom ou par identifiant.
3. A partir de la liste de dossiers, faites glisser et déposez les caractéristiques, segments ou destinations que vous souhaitez rapporter dans le [!UICONTROL Selections] panneau de droite.
4. Générez le rapport à afficher dans un tableau exportable.

## Run a General Report {#run-general-report}

Cette section décrit comment exécuter un [!UICONTROL General] rapport et définir l’heure et d’autres options de performances.

<!-- 

t_run_general_report.xml

 -->

1. Dans le **[!UICONTROL Analytics]** tableau de bord, cliquez sur **[!UICONTROL General Reports]**.
1. Dans la liste **[!UICONTROL Report Type]** déroulante, sélectionnez le type de votre choix : Caractéristique, segment ou destination.
1. *Conditionnel* Cliquez sur la zone de date pour afficher un calendrier, puis sélectionnez la date de fin de votre rapport si vous souhaitez spécifier une date autre qu&#39;aujourd&#39;hui.
1. Recherchez une caractéristique, un segment ou une destination par nom ou par identifiant.
1. A partir de la liste de dossiers, faites glisser et déposez les caractéristiques, segments ou destinations que vous souhaitez rapporter dans le [!UICONTROL Selections] panneau de droite.
1. Cliquez sur **[!UICONTROL Run Report]**.

   Les résultats s’affichent dans un tableau exportable. Cliquez sur les en-têtes de colonne pour trier les résultats par ordre croissant ou décroissant.
1. Sélectionnez le bouton d’option de votre choix dans la partie supérieure du rapport pour filtrer les données par performances ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]ou [!UICONTROL Total Trait Population]) ou par heure (1, 7, 14, 30, 60 ou période de 90 jours).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sont calculées pour [!UICONTROL Rule-based Traits] uniquement.

1. *Facultatif* Cliquez sur **[!UICONTROL Export to CSV]**. Cette option exporte les données [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]et [!UICONTROL Total Trait Population] pour toutes les plages de jours.

## Rapports généraux Résultats expliqués {#general-reports-explained}

Les nombres dans le [!UICONTROL General Reports] sont générés directement à partir de notre [!UICONTROL User Profile Store]. Les résultats reflètent le nombre d’utilisateurs [!DNL Audience Manager] contenus dans le serveur principal au moment où ces numéros de rapports ont été générés.

* Ces nombres n’incluent pas les identifiants de visiteur avec un trafic excessif. Le trafic des robots est filtré avant d&#39;atteindre notre système principal. En outre, un certain trafic de robots est ignoré lors de l’exécution d’une tâche de nettoyage hebdomadaire en arrière-plan.
* Si vous embarquez des données via un traitement entrant ont désactivé l’ [!DNL Audience Manager] UUID et que ces ID incluent des utilisateurs qui ne sont plus actifs dans notre système, ces [!DNL Audience Manager] UUID inactifs n’atteignent jamais l’UUID [!UICONTROL User Profile Store] et ne sont pas signalés.
* [!UICONTROL Total Trait Realizations] sont calculées pour [!UICONTROL Rule-based Traits] uniquement.

## Rapports généraux Résultats pour les caractéristiques {#general-report-results-traits}

Les filtres ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Trait]** le type de rapport.

Lors du filtrage des résultats par [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] correspond au nombre de visiteurs anonymes de votre périphérique qui ont ajouté la caractéristique à leur profil au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques anonymes au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs anonymes de votre périphérique qui ont cette caractéristique sur leur profil.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] correspond au nombre de vos visiteurs authentifiés qui ont ajouté la caractéristique à leur profil, au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] représente le nombre total de réalisations de caractéristiques authentifiées au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de vos visiteurs authentifiés qui ont cette caractéristique sur leur profil.

![general-report-traits-cross-device](assets/general-report-traits-cross-device.png)

<!-- 
### Unique Trait Realizations

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. For example, if a user visited your homepage three times on 10/1, you would see one Unique Trait Realization.

### Total Trait Realizations

This metric represents the total amount of trait fires for the trait in your selected time range. For example, if a user visited your homepage, then navigated to your tech news and your sports news sections, they would appear in the General Report as three total trait realizations, and one unique trait realization.

### Total Trait Population

This metric represents the total amount of Audience Manager UUIDs that are currently qualified for the trait. Use this number to understand the total amount of users you could use for segmentation and targeting. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). For example, a user visiting your homepage three times today and never returning afterwards, would remain as a user in this population every day until 120 days from now. At the 120 day mark, they would be removed from the population. Read our [Trait and Segment Qualification Reference](../features/traits/trait-and-segment-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

The illustration below shows the results of running a general report for the Trait report type. -->
<!-- 
![](assets/general_reports_metrics.png) -->


## Résultats des rapports généraux pour les segments {#general-report-results-segments}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Segment]** le type de rapport :

### Population des segments en temps réel

Cette mesure représente le nombre réel de visiteurs uniques vus en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par Audience Manager.

### Population totale des segments

Cette mesure représente le nombre total d’UUID d’Audience Manager qui sont qualifiés pour le segment au cours de la période de recherche précédente que vous avez sélectionnée. Votre population totale de segments d’une journée représente votre base d’utilisateurs la plus précise pour le ciblage.

>[!NOTE]
>
>Sélectionnez cette option **[!UICONTROL Include Destination Mappings]** pour afficher la ventilation de la population de segments pour les destinations activées.

L&#39;illustration ci-dessous montre les résultats de l&#39;exécution d&#39;un rapport général pour le type de rapport Segment.

![](assets/general_reports_segment_metrics.png)

## Rapports généraux Résultats pour les destinations {#general-report-results-destinations}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et que vous sélectionnez **[!UICONTROL Destination]** le type de rapport :

**Population des segments en temps réel**

Cette mesure représente le nombre réel de visiteurs uniques vus en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par Audience Manager.

**Population totale des segments**

Cette mesure représente le nombre total d’UUID d’Audience Manager appartenant à un segment au cours de la période de recherche précédente, qui ont été envoyés à une destination.

L&#39;illustration ci-dessous montre les résultats de l&#39;exécution d&#39;un rapport général pour le type de rapport Destinations.

![](assets/general_reports_destinations.png)
