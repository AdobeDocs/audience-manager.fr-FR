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

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations des groupes d’utilisateurs aux rapports [!UICONTROL General]. Les utilisateurs ne peuvent afficher que les caractéristiques et les segments dans les rapports qu’ils sont autorisés à afficher. La fonctionnalité [!UICONTROL RBAC] vous permet de contrôler les données de rapport que les équipes internes peuvent afficher. Par exemple, une agence qui gère différents comptes publicitaires peut configurer des autorisations de groupe d’utilisateurs de sorte qu’une équipe qui gère le compte de l’annonceur A ne puisse pas consulter les données de rapport de l’annonceur B.

Exécutez un rapport [!UICONTROL General] lorsque vous devez :

* Examinez les performances par caractéristique, segment ou destination.
* Effectuez le suivi des impressions (total et unique) à des intervalles de 1, 7, 14, 30, 60 et 90 jours.
* Vérifiez le nombre total et le nombre de chargements uniques.
* Comparer les performances des caractéristiques et des segments.
* Identifiez les segments et les caractéristiques de performances fortes ou médiocres, analysez la demande ou comparez les données de charge/feu à des rapports tiers.
* Exportez des données (format .csv) pour une analyse et un partage plus approfondis.

L’illustration suivante présente un aperçu général des éléments clés du rapport [!UICONTROL General].

![](assets/general_reports.png)

1. Configurez les options suivantes :

   * **Type de rapport :** Sélectionnez le type de rapport souhaité (Caractéristique, Segment ou Destination).

   * **Pour les dates de clôture :** Spécifiez la période du rapport.

2. Recherchez une caractéristique, un segment ou une destination par nom ou par identifiant.
3. Dans la liste des dossiers, effectuez un glisser-déposer des caractéristiques, des segments ou des destinations à signaler dans le panneau [!UICONTROL Selections] sur le côté droit.
4. Générez le rapport à afficher dans une table exportable.

## Exécution d’un rapport général {#run-general-report}

Cette section décrit comment exécuter un rapport [!UICONTROL General] et définir l’heure et d’autres options de performances.

<!-- 

t_run_general_report.xml

 -->

1. Dans le tableau de bord **[!UICONTROL Analytics]**, cliquez sur **[!UICONTROL General Reports]**.
1. Dans la liste déroulante **[!UICONTROL Report Type]**, sélectionnez le type souhaité : Caractéristique, Segment ou Destination.
1. *Conditionnel* Cliquez sur la zone de date pour afficher un calendrier, puis sélectionnez la date de fin de votre rapport si vous souhaitez spécifier une date autre qu’aujourd’hui.
1. Recherchez une caractéristique, un segment ou une destination par nom ou par identifiant.
1. Dans la liste des dossiers, effectuez un glisser-déposer des caractéristiques, des segments ou des destinations à signaler dans le panneau [!UICONTROL Selections] sur le côté droit.
1. Cliquez sur **[!UICONTROL Run Report]**.

   Les résultats s’affichent dans un tableau exportable. Cliquez sur les en-têtes de colonne pour trier les résultats par ordre croissant ou décroissant.
1. Sélectionnez le bouton d’option de votre choix en haut du rapport pour filtrer les données par performances ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] ou [!UICONTROL Total Trait Population]) ou par heure (1, 7, 14, 30, 60 ou période de 90 jours).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sont calculés pour [!UICONTROL Rule-based Traits] uniquement.

1. *Facultatif* Cliquez sur **[!UICONTROL Export to CSV]**. Cette opération exporte les [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] et [!UICONTROL Total Trait Population] pour toutes les plages de jours.

## Explication des résultats des rapports généraux {#general-reports-explained}

Les nombres de [!UICONTROL General Reports] sont générés directement à partir de notre [!UICONTROL User Profile Store]. Les résultats reflètent le nombre d’utilisateurs contenus dans le serveur principal au moment de la génération de ces chiffres de rapport. [!DNL Audience Manager]

* Ces chiffres n’incluent pas les identifiants visiteur avec un trafic excessif. Le trafic des robots est filtré avant d’atteindre notre système principal. En outre, un certain trafic de robots est ignoré lors d’une exécution de tâche de nettoyage hebdomadaire dans le serveur principal.
* Si vous intégrez des données par le biais d’un traitement entrant clé en dehors de l’UUID [!DNL Audience Manager] et que ces identifiants incluent des utilisateurs qui ne sont plus actifs dans notre système, ces UUID [!DNL Audience Manager] inactifs n’atteignent jamais l’UUID [!UICONTROL User Profile Store] et ne sont pas signalés.
* [!UICONTROL Total Trait Realizations] sont calculés pour [!UICONTROL Rule-based Traits] uniquement.

## Résultats généraux des rapports pour les caractéristiques {#general-report-results-traits}

Les filtres ci-dessous sont disponibles lorsque vous exécutez un rapport général et que vous sélectionnez **[!UICONTROL Trait]** comme type de rapport.

Lors du filtrage des résultats par [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs de votre appareil anonyme ayant ajouté la caractéristique à leur profil au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques anonymes au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs de votre appareil anonyme ayant cette caractéristique sur leur profil.

![general-report-traits-device](assets/general-report-traits-deviceid.png)

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs authentifiés qui ont ajouté la caractéristique à leur profil, au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques authentifiées au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs authentifiés ayant cette caractéristique sur leur profil.

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


## Résultats généraux des rapports pour les segments {#general-report-results-segments}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport général et que vous sélectionnez **[!UICONTROL Segment]** comme type de rapport :

### Population des segments en temps réel

Cette mesure représente le nombre réel de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par l’Audience Manager.

### Population totale de segments

Cette mesure représente le nombre total d’UUID d’Audience Manager qualifiés pour le segment au cours de la période d’analyse que vous avez sélectionnée. Votre population totale de segments d’un jour représente votre base d’utilisateurs la plus précise pour le ciblage.

>[!NOTE]
>
>Sélectionnez **[!UICONTROL Include Destination Mappings]** pour afficher la ventilation de la population de segments pour les destinations activées.

L’illustration ci-dessous présente les résultats de l’exécution d’un rapport général pour le type de rapport Segment .

![](assets/general_reports_segment_metrics.png)

## Résultats des rapports généraux pour les destinations {#general-report-results-destinations}

Les mesures ci-dessous sont disponibles lorsque vous exécutez un rapport général et que vous sélectionnez **[!UICONTROL Destination]** comme type de rapport :

**Population des segments en temps réel**

Cette mesure représente le nombre réel de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par l’Audience Manager.

**Population totale de segments**

Cette mesure représente le nombre total d’UUID d’Audience Manager appartenant à un segment au cours de la période d’analyse, qui ont été envoyés à une destination.

L’illustration ci-dessous présente les résultats de l’exécution d’un rapport général pour le type de rapport Destinations .

![](assets/general_reports_destinations.png)
