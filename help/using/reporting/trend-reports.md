---
description: Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.
seo-description: Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.
seo-title: Rapports de tendances
solution: Audience Manager
title: Rapports de tendances
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: Rapports généraux et de tendances
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 1%

---

# Rapports de tendances{#trend-reports}

Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.

## Présentation {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utilise  [!UICONTROL Role Based Access Control]  ([!UICONTROL RBAC]) pour étendre les autorisations des groupes d’utilisateurs aux  [!UICONTROL Trend] rapports. Les utilisateurs ne peuvent afficher que les caractéristiques et les segments dans les rapports qu’ils sont autorisés à afficher. [!UICONTROL RBAC] permet de contrôler les données de rapport que les équipes internes peuvent afficher.

Par exemple, une agence qui gère différents comptes publicitaires peut configurer des autorisations de groupe d’utilisateurs de sorte qu’une équipe qui gère le compte de l’annonceur A ne puisse pas consulter les données de rapport de l’annonceur B.

Exécutez un rapport [!UICONTROL Trend] lorsque vous devez :

* Examinez les données de tendance par caractéristiques et par segments.
* Effectuez le suivi des tendances par intervalles de 1, 7, 14, 30, 60 et 90 jours.
* Comparer les tendances des caractéristiques et des segments au fil du temps.
* Identifiez les caractéristiques et les segments de performances forts ou médiocres.
* Exportez des données (format .csv) pour une analyse et un partage plus approfondis.

L’illustration suivante présente un aperçu général des éléments clés du rapport [!UICONTROL Trend].

![](assets/trend_reports.png)

1. Configurez les options suivantes :
   **Type de rapport :** sélectionnez le type de rapport souhaité (Caractéristique ou segment).
   **Période :** spécifiez la période du rapport (date de début et date de fin).
   **Intervalle d’affichage :** spécifiez l’intervalle d’affichage (intervalles de 1, 7, 14, 30, 60 et 90 jours).
1. Recherchez une caractéristique ou un segment par nom ou par identifiant.
1. Dans la liste des dossiers, faites glisser les caractéristiques ou les segments à signaler dans le panneau [!UICONTROL Selections] sur le côté droit.
1. Générez le rapport afin d&#39;afficher les données sous forme graphique ou exportez le rapport au format CSV.

## Exécution d’un rapport de tendance {#run-trend-report}

Cette procédure décrit l’exécution d’un rapport [!UICONTROL Trend].

<!-- 

t_working_with_trend_reports.xml

 -->

1. Dans le tableau de bord **[!UICONTROL Analytics]**, cliquez sur **[!UICONTROL Trend Reports]**.
1. Dans la liste déroulante **[!UICONTROL Report Type]**, sélectionnez le type de votre choix : **[!UICONTROL Trait]** ou **[!UICONTROL Segment]**.
1. Cliquez sur les zones de date pour afficher un calendrier, puis sélectionnez les dates de début et de fin du rapport.
1. Spécifiez l’intervalle d’affichage : par 1, 7, 14, 30, 60 ou 90 jours.
1. Recherchez une caractéristique ou un segment par nom ou par identifiant.
1. Dans la liste des dossiers, faites glisser les caractéristiques ou les segments à signaler dans le panneau [!UICONTROL Selections] sur le côté droit.
   * Pour de meilleures performances, exécutez un rapport [!UICONTROL Trend] sur moins de 20 caractéristiques ou segments à la fois.
1. Cliquez sur **[!UICONTROL Graph Traits]** ou **[!UICONTROL Graph Segments]**, selon le type de rapport que vous affichez (Caractéristiques ou Segments). Ces options ignorent tous les dossiers et graphiques uniquement les caractéristiques ou segments sélectionnés individuellement.

   OU

   Cliquez sur **[!UICONTROL Export to CSV]** pour exporter les données de caractéristique ou de segment et tous les dossiers au format CSV en vue d’une analyse et d’un partage plus approfondis. Cela exporte les valeurs [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations] et [!UICONTROL Total Trait Population] pour toutes les plages de jours.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sont calculées  [!UICONTROL Rule-based Traits] uniquement pour .

1. (Facultatif) Placez le pointeur de la souris sur des caractéristiques ou des segments individuels pour afficher le nombre de visites et la date de chaque point de données. Vous pouvez cliquer sur les en-têtes de colonne du tableau pour trier les résultats par ordre croissant ou décroissant.

## Résultats des rapports de tendances pour les caractéristiques {#trend-report-results-traits}

Les filtres ci-dessous sont disponibles lorsque vous exécutez un [!UICONTROL Trend Report] et sélectionnez **[!UICONTROL Trait]** comme type de rapport.

Lors du filtrage des résultats par [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs de votre appareil anonyme qui ont ajouté la caractéristique à leur profil au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques anonymes au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs de votre appareil anonyme qui ont cette caractéristique sur leur profil.

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs authentifiés qui ont ajouté la caractéristique à leur profil, au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques authentifiées au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de vos visiteurs authentifiés présentant cette caractéristique sur leur profil.

![tend-report-traits](assets/trend-report-traits.png)

Les zéros indiquent que [!DNL Audience Manager] n’a pas collecté de données pour cette journée. Les entrées vides indiquent que la caractéristique n’existait pas.

Regardez la vidéo ci-dessous pour une vue détaillée du fonctionnement des mesures sur plusieurs appareils.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Résultats des rapports de tendances pour les segments {#segment-report-results-traits}

Les filtres ci-dessous sont disponibles lorsque vous exécutez un [!UICONTROL Trend Report] et sélectionnez **[!UICONTROL Segments]** comme type de rapport.

* **[!UICONTROL Real-time Segment Population]**: le nombre de visiteurs qualifiés pour le segment au cours de la période sélectionnée.
* **[!UICONTROL Total Segment Population]**: le nombre total de visiteurs qualifiés pour le segment.

![tend-report-segments](assets/trend-report-segments.png)
