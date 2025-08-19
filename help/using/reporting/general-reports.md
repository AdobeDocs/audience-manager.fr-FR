---
description: Un rapport Général renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-description: A General report in Audience Manager returns performance data on traits, segments, and destinations.
seo-title: General Reports in Audience Manager
solution: Audience Manager
title: Rapports généraux
uuid: 0cea75a0-969e-4ee3-971a-60b911711e52
feature: General & Trend Reports
exl-id: dc16a821-b776-4a04-af60-4b8c914253dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 0%

---

# Rapports généraux{#general-reports}

Un rapport [!UICONTROL General] renvoie des données de performances sur les caractéristiques, les segments et les destinations.

## Présentation {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations des groupes d’utilisateurs aux rapports [!UICONTROL General]. Les utilisateurs ne peuvent afficher que les caractéristiques et les segments dans les rapports qu’ils sont autorisés à consulter. [!UICONTROL RBAC] fonctionnalité vous permet de contrôler les données de rapport que les équipes internes peuvent afficher. Par exemple, une agence qui gère différents comptes d’annonceurs peut configurer des autorisations de groupe d’utilisateurs afin qu’une équipe qui gère le compte de l’annonceur A ne puisse pas voir les données de rapports de l’annonceur B.

Exécutez un rapport [!UICONTROL General] lorsque vous devez :

* Examinez les performances par caractéristique, segment ou destination.
* Effectuez le suivi des impressions (totales et uniques) à intervalles de 1, 7, 14, 30, 60 et 90 jours.
* Vérifier le nombre de chargements total et unique.
* Comparez les performances des caractéristiques et des segments.
* Identifiez les segments et les caractéristiques de performances forts ou faibles, analysez la demande ou comparez les données de chargement/déclenchement avec des rapports tiers.
* Exportez les données (format .csv) pour les analyser et les partager plus en détail.

L’illustration suivante présente de manière générale les éléments clés du rapport [!UICONTROL General].

![](assets/general_reports.png)

1. Configurez les options suivantes :

   * **Type de rapport :** sélectionnez le type de rapport souhaité (caractéristique, segment ou destination).

   * **De Dates à** : indiquez la période du rapport.

2. Rechercher une caractéristique, un segment ou une destination par nom ou par ID.
3. Dans la liste des dossiers, faites glisser et déposez les caractéristiques, les segments ou les destinations dont vous souhaitez créer un rapport dans le panneau [!UICONTROL Selections] sur le côté droit.
4. Générez le rapport à afficher dans un tableau exportable.

## Exécution d’un rapport général {#run-general-report}

Cette section décrit comment exécuter un rapport de [!UICONTROL General] et définir l’heure ainsi que d’autres options de performances.

<!-- 

t_run_general_report.xml

 -->

1. Dans le tableau de bord de la **[!UICONTROL Analytics]**, cliquez sur **[!UICONTROL General Reports]**.
1. Dans la liste déroulante **[!UICONTROL Report Type]** , sélectionnez le type souhaité : Caractéristique, Segment ou Destination.
1. *Conditionnel* Cliquez sur la zone de date pour afficher un calendrier, puis sélectionnez la date de fin de votre rapport si vous souhaitez spécifier une date autre qu&#39;aujourd&#39;hui.
1. Rechercher une caractéristique, un segment ou une destination par nom ou par ID.
1. Dans la liste des dossiers, faites glisser et déposez les caractéristiques, les segments ou les destinations dont vous souhaitez créer un rapport dans le panneau [!UICONTROL Selections] sur le côté droit.
1. Cliquez sur **[!UICONTROL Run Report]**.

   Les résultats s’affichent dans un tableau exportable. Cliquez sur les en-têtes des colonnes pour trier les résultats par ordre croissant ou décroissant.
1. Sélectionnez le bouton d’option de votre choix en haut du rapport pour filtrer les données par performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] ou [!UICONTROL Total Trait Population]) ou par heure (période de 1, 7, 14, 30, 60 ou 90 jours).

   >[!NOTE]
   >
   >Les [!UICONTROL Total Trait Realizations] sont calculés pour les [!UICONTROL Rule-based Traits] uniquement.

1. *Facultatif* Cliquez sur **[!UICONTROL Export to CSV]**. Cette opération exporte les [!UICONTROL Unique Trait Realizations], les [!UICONTROL Total Trait Realizations] et les [!UICONTROL Total Trait Population] pour toutes les périodes.

## Présentation des résultats des rapports généraux {#general-reports-explained}

Les nombres dans le [!UICONTROL General Reports] sont générés directement à partir de notre [!UICONTROL User Profile Store]. Les résultats reflètent le nombre d’utilisateurs qui [!DNL Audience Manager] contenus dans le serveur principal au moment où ces chiffres des rapports ont été générés.

* Ces nombres n’incluent pas les identifiants visiteur avec un trafic excessif. Le trafic provenant des robots est filtré avant d’atteindre notre système principal. En outre, une partie du trafic de robots est ignorée lors d’une exécution hebdomadaire de nettoyage sur le serveur principal.
* Si vous intégrez des données via le traitement entrant en désactivant l’UUID [!DNL Audience Manager] et que ces identifiants incluent des utilisateurs qui ne sont plus actifs dans notre système, ces UUID [!DNL Audience Manager] inactifs n’atteignent jamais l’[!UICONTROL User Profile Store] et ne sont pas signalés.
* Les [!UICONTROL Total Trait Realizations] sont calculés pour les [!UICONTROL Rule-based Traits] uniquement.

## Résultats des rapports généraux sur les caractéristiques {#general-report-results-traits}

Les filtres ci-dessous sont disponibles lorsque vous exécutez un rapport Général et sélectionnez **[!UICONTROL Trait]** comme type de rapport.

Lors du filtrage des résultats par [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs anonymes de votre appareil qui ont ajouté la caractéristique à leur profil au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques anonymes dans la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs anonymes de votre appareil qui ont cette caractéristique sur leur profil.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de vos visiteurs authentifiés qui ont ajouté la caractéristique à leur profil, au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques authentifiées au cours de la période sélectionnée.
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

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et sélectionnez **[!UICONTROL Segment]** comme type de rapport :

### Population de segments en temps réel

Cette mesure représente le nombre réel de visiteurs uniques vus en temps réel pour la période spécifiée et qui étaient qualifiés pour le segment au moment où ils ont été vus par Audience Manager.

### Population Totale Du Segment

Cette mesure représente le nombre total d’UUID Audience Manager qualifiés pour le segment au cours de la période d’analyse que vous avez sélectionnée. La population totale de segments sur 1 jour représente la base d’utilisateurs la plus précise pour le ciblage.

>[!NOTE]
>
>Sélectionnez **[!UICONTROL Include Destination Mappings]** pour afficher la répartition de la population de segments pour les destinations activées.

L’illustration ci-dessous montre les résultats de l’exécution d’un rapport général pour le type de rapport Segment .

![](assets/general_reports_segment_metrics.png)

## Résultats des rapports généraux pour les destinations {#general-report-results-destinations}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport Général et sélectionnez **[!UICONTROL Destination]** comme type de rapport :

**Population de segments en temps réel**

Cette mesure représente le nombre réel de visiteurs uniques vus en temps réel pour la période spécifiée et qui étaient qualifiés pour le segment au moment où ils ont été vus par Audience Manager.

**Population Totale De Segments**

Cette mesure représente le nombre total d’UUID Audience Manager appartenant à un segment au cours de la période d’analyse, qui ont été envoyés à une destination.

L’illustration ci-dessous montre les résultats de l’exécution d’un rapport général pour le type de rapport Destinations .

![](assets/general_reports_destinations.png)
