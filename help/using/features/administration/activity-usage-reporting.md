---
description: Les rapports d’utilisation des activités vous aident à visualiser et à suivre l’utilisation des activités pour votre instance d’Audience Manager, afin que vous puissiez comparer votre utilisation réelle à votre engagement contractuel.
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

De plus, vous pouvez télécharger le [!UICONTROL Activity Usage Report] si besoin, pour la conservation des enregistrements et l’analyse personnalisée.

## Considérations {#considerations}

[!UICONTROL Activity Usage Report] est disponible pour tous les utilisateurs d&#39;Audience Manager disposant de [ privilèges d&#39;administrateur](edit-account-settings.md).

>[!IMPORTANT]
>
>Le [!UICONTROL Activity Usage Report] présente les statistiques d’utilisation des activités de votre instance d’Audience Manager. Pour toute question de facturation relative à l’utilisation de votre activité, contactez votre représentant d’Adobe.

## Cas d’utilisation {#use-cases}

Il existe deux principaux cas d’utilisation de [!UICONTROL Activity Usage Report] :

* **Suivi de l’utilisation réelle de l’activité de l’instance par rapport à votre engagement d’utilisation de l’activité** : la plupart des clients ont un engagement d’activité estimé mensuellement par instance d’Audience Manager, qui est ensuite cumulé dans un engagement d’activité annuel sur toutes les instances. Bien que ce rapport ne soit pas un rapport de facturation, il peut vous aider à déterminer si vous dépassez l’utilisation de l’activité engagée.
* **Validation des modifications de mise en oeuvre** : si vous avez récemment mis à jour votre mise en oeuvre, par exemple en configurant le transfert côté serveur [!DNL Adobe Analytics] ou en modifiant les paramètres d’appel au serveur [!DNL Adobe Target], ce rapport peut vous aider à vérifier si le nouveau volume d’activité correspond au volume d’activité attendu.

## Utilisation de la fonction [!UICONTROL Activity Usage Report] {#using}

Pour voir le [!UICONTROL Activity Usage Report], connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Ensuite, utilisez le filtre **[!UICONTROL Reporting Interval]** pour sélectionner l’intervalle de temps pour lequel générer le rapport. Vous pouvez choisir entre 30, 60, 90 jours ou une période personnalisée.

Une fois votre rapport chargé, vous pouvez afficher la ventilation de votre [!UICONTROL Activities] pour la période sélectionnée.

[!UICONTROL Activities] définit le total agrégé de toutes les interactions sur site et hors site avec l’Audience Manager, divisé en catégories suivantes :

* **[!UICONTROL Server Calls]** : tout événement de collecte ou de récupération de données envoyé à l’Audience Manager à partir de sites web, de serveurs, de courriers électroniques, d’applications mobiles ou d’autres systèmes.
* **[!UICONTROL Pixel Calls] (anciennement [!UICONTROL Impression Server Calls])** : données collectées à partir de publicités (telles que le volume d’impression d’une plateforme de ciblage) ou appels d’impression de courrier électronique effectués à l’Audience Manager. Elles nécessitent la présence du paramètre `d_event` dans la chaîne de requête.
* **[!UICONTROL On-Boarded Records]** : enregistrements uniques ingérés à partir de votre propre système de gestion de la relation client (CRM) ou d’autres fichiers de données hors ligne, tels que les enregistrements du centre d’appel, les identifiants d’appareil et les flux de données personnalisés provenant de fournisseurs de données externes.
* **[!UICONTROL Log File Records]** : enregistrements uniques à partir de fichiers journaux ingérés dans l’Audience Manager à partir d’une plateforme de ciblage.

>[!NOTE]
>
>Un enregistrement unique définit chaque enregistrement individuel de données dans un fichier stocké par Adobe au nom d’un client d’Audience Manager.

De plus, vous pouvez utiliser les types de graphiques [!UICONTROL Activity Usage Trends] pour basculer entre deux types de graphiques.

![aur-ui-graph](assets/aur-ui-graphs.png)

Vous pouvez également placer le curseur sur une date spécifique de la chronologie pour afficher l’utilisation détaillée de cette date.

![aur-hover](assets/aur-hover.png)

## Export [!UICONTROL Activity Usage Reports] {#export}

Pour un meilleur aperçu du niveau d’utilisation de l’activité d’Audience Manager, vous pouvez exporter le [!UICONTROL Activity Usage Report] en fonction du type d’enregistrements que vous souhaitez inclure.

![aur-export](assets/aur-export.png)

Les rapports **[!UICONTROL Onboarded Records Breakdown]** et **[!UICONTROL Onsite Server Calls Breakdown]** fournissent les informations les plus granulaires sur les données source disponibles pour ces activités. Le volume attribué à ces ventilations dépend de votre mise en oeuvre.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Ce rapport contient des enregistrements intégrés ventilés par source de données.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Ce rapport contient une ventilation des appels au serveur provenant de trois sources : [!UICONTROL Analytics], [!UICONTROL Target] et [!UICONTROL Other].

* **[!UICONTROL Analytics]** : il s’agit d’appels serveur facturables transmis de toutes les instances [!UICONTROL Adobe Analytics] à l’Audience Manager, y compris le transfert côté serveur. Les appels au serveur Secondaire ou les appels au serveur en double (comme dans le cas du transfert côté serveur depuis plusieurs suites de rapports) ne sont pas facturables. Ils ne sont donc pas inclus dans cette ventilation.
* **[!UICONTROL Target]** : il s’agit d’appels côté serveur de [!UICONTROL Adobe Target] vers l’Audience Manager, pour récupérer les données de segment d’Audience Manager dans le cadre d’une intégration serveur à serveur.
* **[!UICONTROL Other]** : comprend les appels en provenance d’autres sites web ou systèmes (sites partenaires, appels directs au serveur, etc.), les appels de navigateur/d’application mobile via les appels [!DNL SDK], [!DNL DIL], d’événement et [!DNL DCS]. Inclut également les appels de [!DNL Target] s’ils sont configurés en tant qu’intégration de cookie (plutôt que de serveur à serveur).
