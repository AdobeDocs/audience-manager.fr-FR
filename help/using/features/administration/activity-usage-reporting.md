---
description: Le rapport d’utilisation des activités vous permet d’afficher et de suivre l’utilisation des activités de votre instance Audience Manager, afin que vous puissiez comparer votre utilisation réelle à votre engagement contractuel.
keywords: activité, utilisation, reporting, engagement
seo-description: Activity Usage Reporting helps you view and track the activity usage for your Audience Manager instance, so you can compare your actual usage to your contractual commitment.
seo-title: Activity Usage Reporting
solution: Audience Manager
title: Rapports d’utilisation des activités
feature: Usage and Billing
exl-id: 0c5f04c6-d008-4817-9c67-cd39350b3aaf
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 5%

---

# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Présentation {#overview}

L’[!UICONTROL Activity Usage Report] vous aide à visualiser et à effectuer le suivi de l’utilisation des activités de votre instance Audience Manager, ce qui vous donne une idée claire de votre utilisation des activités comparée à votre engagement contractuel.

De plus, vous pouvez télécharger le [!UICONTROL Activity Usage Report] quand vous en avez besoin, pour la conservation des enregistrements et l’analyse personnalisée.

## Considérations {#considerations}

Le [!UICONTROL Activity Usage Report] est disponible pour tous les utilisateurs d’Audience Manager disposant de [ privilèges d’administrateur ](edit-account-settings.md).

>[!IMPORTANT]
>
>La [!UICONTROL Activity Usage Report] présente les statistiques d’utilisation des activités de votre instance Audience Manager. Pour toute demande de facturation liée à l’utilisation de votre activité, contactez votre représentant Adobe.

## Cas d’utilisation {#use-cases}

Il existe deux cas d’utilisation principaux du [!UICONTROL Activity Usage Report] :

* **Suivi de l’utilisation réelle de l’activité de l’instance par rapport à votre engagement d’utilisation des activités** : la plupart des clients ont un engagement estimé mensuel pour chaque instance Audience Manager, qui est ensuite cumulé dans un engagement annuel pour toutes les instances. Bien que ce rapport ne soit pas un rapport de facturation, il peut fournir des conseils utiles pour savoir si vous dépassez l’utilisation des activités validées.
* **Validation des modifications d’implémentation** : si vous avez récemment mis à jour votre implémentation, par exemple en configurant [!DNL Adobe Analytics] transfert côté serveur, ou en modifiant les paramètres d’appel au serveur [!DNL Adobe Target], ce rapport peut vous aider à vérifier si le nouveau volume d’activité est conforme à votre volume d’activité attendu.

## Utilisation de l’[!UICONTROL Activity Usage Report] {#using}

Pour voir le [!UICONTROL Activity Usage Report], connectez-vous à votre compte Audience Manager, puis accédez à **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Ensuite, utilisez le filtre **[!UICONTROL Reporting Interval]** pour sélectionner l’intervalle de temps pour lequel générer le rapport. Vous pouvez choisir entre 30, 60, 90 jours ou une période personnalisée.

Une fois votre rapport chargé, vous pouvez voir une répartition de vos [!UICONTROL Activities] pour la période sélectionnée.

[!UICONTROL Activities] définir le total agrégé de toutes les interactions sur site et hors site avec Audience Manager, divisé en les catégories suivantes :

* **[!UICONTROL Server Calls]** : tout événement de collecte ou de récupération de données envoyé à Audience Manager à partir de sites web, de serveurs, d’e-mails, d’applications mobiles ou d’autres systèmes.
* **[!UICONTROL Pixel Calls] (anciennement appelé [!UICONTROL Impression Server Calls])** : données collectées à partir d’annonces (telles que le volume d’impression d’une plateforme de ciblage) ou d’appels d’impressions d’e-mail effectués vers Audience Manager. Ceux-ci nécessitent la présence du paramètre `d_event` dans la chaîne de requête.
* **[!UICONTROL On-Boarded Records]** : enregistrements uniques ingérés à partir de votre propre système de gestion de la relation client (CRM) ou d’autres fichiers de données hors ligne, tels que les enregistrements du centre d’appels, les identifiants d’appareil et les flux de données personnalisés de fournisseurs de données externes.
* **[!UICONTROL Log File Records]** : enregistrements uniques de fichiers journaux ingérés dans Audience Manager à partir d’une plateforme de ciblage.

>[!NOTE]
>
>Un enregistrement unique définit chaque enregistrement individuel de données dans un fichier stocké par Adobe pour le compte d’un client Audience Manager.

De plus, vous pouvez utiliser les types de graphiques [!UICONTROL Activity Usage Trends] pour basculer entre deux types de graphiques.

![aur-ui-graph](assets/aur-ui-graphs.png)

Vous pouvez également placer le pointeur de la souris sur une date spécifique de la chronologie pour afficher l’utilisation détaillée de cette date.

![vol stationnaire](assets/aur-hover.png)

## Exportation de [!UICONTROL Activity Usage Reports] {#export}

Pour une meilleure vue d’ensemble de votre niveau d’utilisation des activités Audience Manager, vous pouvez exporter les [!UICONTROL Activity Usage Report] en fonction du type d’enregistrements que vous souhaitez inclure.

![aur-export](assets/aur-export.png)

Les rapports **[!UICONTROL Onboarded Records Breakdown]** et **[!UICONTROL Onsite Server Calls Breakdown]** fournissent l’insight le plus granulaire de données source disponibles pour ces activités. Le volume attribué à ces répartitions dépend de votre implémentation.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Ce rapport contient des enregistrements intégrés répartis par source de données.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Ce rapport contient une répartition des appels au serveur provenant de trois sources : [!UICONTROL Analytics], [!UICONTROL Target] et [!UICONTROL Other].

* **[!UICONTROL Analytics]** : il s’agit d’appels au serveur facturables transmis de toutes les instances [!UICONTROL Adobe Analytics] à Audience Manager, y compris le transfert côté serveur. Les appels au serveur Secondaire ou les appels au serveur en double (comme dans le cas du transfert côté serveur à partir de plusieurs suites de rapports) ne sont pas des activités facturables. Ils ne sont donc pas inclus dans cette répartition.
* **[!UICONTROL Target]** : il s’agit d’appels côté serveur de [!UICONTROL Adobe Target] à Audience Manager, pour récupérer les données de segment Audience Manager dans le cadre d’une intégration serveur à serveur.
* **[!UICONTROL Other]** : inclut les appels provenant de tout autre site web ou système (sites partenaires, appels directs au serveur, etc.), les appels au navigateur/à l’application mobile via les [!DNL SDK], les [!DNL DIL], les appels d’événement et les appels [!DNL DCS]. Inclut également les appels de [!DNL Target] s’ils sont configurés en tant qu’intégration de cookies (plutôt que de serveur à serveur).
