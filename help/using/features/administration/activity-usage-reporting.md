---
description: Le Rapports d’utilisation des Activités vous aide à vue et à suivre l’utilisation des activités pour votre instance d’Audience Manager, afin que vous puissiez comparer votre utilisation réelle à votre engagement contractuel.
keywords: activity, usage, reporting, commitment
seo-description: Le Rapports d’utilisation des Activités vous aide à vue et à suivre l’utilisation des activités pour votre instance d’Audience Manager, afin que vous puissiez comparer votre utilisation réelle à votre engagement contractuel.
seo-title: Rapports d’utilisation des activités
solution: Audience Manager
title: Rapports d’utilisation des activités
topic: Activity Usage Reporting
feature: Usage and Billing
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 6%

---


# [!UICONTROL Activity Usage Reporting] {#activity-usage-reporting}

## Présentation {#overview}

L’[!UICONTROL Activity Usage Report] vous aide à visualiser et à effectuer le suivi de l’utilisation des activités de votre instance Audience Manager, ce qui vous donne une idée claire de votre utilisation des activités comparée à votre engagement contractuel.

De plus, vous pouvez télécharger les [!UICONTROL Activity Usage Report] fichiers au besoin, pour la tenue de dossiers et l&#39;analyse personnalisée.

## Considérations {#considerations}

Elle [!UICONTROL Activity Usage Report] est accessible à tous les utilisateurs d’Audience Manager disposant de droits [d’](edit-account-settings.md)administrateur.

>[!IMPORTANT]
>
>Le [!UICONTROL Activity Usage Report] montre les statistiques d&#39;utilisation des activités de votre instance d&#39;Audience Manager. Pour toute demande de facturation liée à l&#39;utilisation de votre activité, contactez votre représentant Adobe.

## Cas d’utilisation {#use-cases}

Il existe deux principaux cas d&#39;utilisation du [!UICONTROL Activity Usage Report]:

* **Suivi de l’utilisation réelle des activités d’instance par rapport à votre engagement** d’utilisation des activités : La plupart des clients ont un engagement d’activité estimé mensuellement par instance d’Audience Manager, qui est ensuite cumulé en un engagement d’activité annuel dans toutes les instances. Bien que ce rapport ne soit pas un rapport de facturation, il peut vous aider à déterminer si vous dépassez l’utilisation d’activités engagée.
* **Validation des modifications** d’implémentation : Si vous avez récemment mis à jour votre mise en oeuvre, par exemple en configurant le transfert côté [!DNL Adobe Analytics] serveur ou en modifiant les paramètres d’appel au [!DNL Adobe Target] serveur, ce rapport peut vous aider à vérifier si le nouveau volume d’activité correspond au volume d’activité attendu.

## L’utilisation de l’identification [!UICONTROL Activity Usage Report] {#using}

Pour afficher le [!UICONTROL Activity Usage Report]rapport, connectez-vous à votre compte d’Audience Manager, puis cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Ensuite, utilisez le **[!UICONTROL Reporting Interval]** filtre pour sélectionner l&#39;intervalle de temps pour lequel générer le rapport. Vous pouvez choisir entre 30, 60, 90 jours ou une plage de dates personnalisée.

Une fois le rapport chargé, vous pouvez voir la ventilation de votre rapport [!UICONTROL Activities] pour la période sélectionnée.

[!UICONTROL Activities] définissez le total des agrégats de toutes les interactions sur site et hors site avec l’Audience Manager, fractionnées en catégories suivantes :

* **[!UICONTROL Server Calls]**: Tout événement de collecte ou de récupération de données envoyé à l&#39;Audience Manager à partir de sites Web, de serveurs, de courriels, d&#39;applications mobiles ou d&#39;autres systèmes.
* **[!UICONTROL Pixel Calls](anciennement appelé[!UICONTROL Impression Server Calls])**: Données collectées à partir de publicités (telles que le volume d’impression provenant d’une plateforme de ciblage) ou appels d’impression par courrier électronique envoyés à l’Audience Manager. Pour ce faire, le`d_event`paramètre doit être présent dans la chaîne de requête.
* **[!UICONTROL On-Boarded Records]**: Enregistrements uniques ingérés à partir de votre propre système de gestion de la relation client (CRM) ou d’autres fichiers de données hors ligne, tels que les enregistrements du centre d’appels, les ID de périphérique et les flux de données personnalisés provenant de fournisseurs de données externes.
* **[!UICONTROL Log File Records]**: Enregistrements uniques des fichiers journaux assimilés à l’Audience Manager à partir d’une plateforme de ciblage.

>[!NOTE]
>
>Un enregistrement unique définit chaque enregistrement individuel de données dans un fichier stocké par Adobe pour le compte d’un client d’Audience Manager.

De plus, vous pouvez utiliser les types de [!UICONTROL Activity Usage Trends] graphique pour basculer entre deux types de graphiques.

![aur-ui-graphes](assets/aur-ui-graphs.png)

Vous pouvez également placer le curseur sur une date spécifique du plan de montage chronologique pour afficher l’utilisation détaillée de cette date.

![aur-hover](assets/aur-hover.png)

## Exportation [!UICONTROL Activity Usage Reports] {#export}

Pour une meilleure vue d’ensemble du niveau d’utilisation de vos activités d’Audience Manager, vous pouvez exporter les données [!UICONTROL Activity Usage Report] en fonction du type d’enregistrements à inclure.

![aur-export](assets/aur-export.png)

Les **[!UICONTROL Onboarded Records Breakdown]** rapports et **[!UICONTROL Onsite Server Calls Breakdown]** les rapports fournissent les informations les plus granulaires sur les données source disponibles pour ces activités. Le volume attribué à ces ventilations dépend de votre implémentation.

### [!UICONTROL Onboarded Records Breakdown] {#onboarded-breakdown}

Ce rapport contient des enregistrements intégrés ventilés par source de données.

### [!UICONTROL Onsite Server Calls Breakdown] {#onsite-breakdown}

Ce rapport contient une ventilation des appels serveur provenant de trois sources : [!UICONTROL Analytics], [!UICONTROL Target]et [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Il s’agit d’appels serveur facturables transmis de toutes les instances à l’Audience Manager, y compris le transfert côté serveur. [!UICONTROL Adobe Analytics] Les appels de serveur Secondaire ou de serveur de duplicata (comme dans le cas du transfert côté serveur depuis plusieurs suites de rapports) ne sont pas des activités facturables, elles ne sont donc pas incluses dans cette ventilation.
* **[!UICONTROL Target]**: Il s’agit d’appels côté serveur de [!UICONTROL Adobe Target] vers l’Audience Manager, pour récupérer les données de segment d’Audience Manager dans le cadre d’une intégration serveur à serveur.
* **[!UICONTROL Other]**: Inclut les appels en provenance de tout autre site Web ou système (sites partenaires, appels directs au serveur, etc.), les appels de navigateur mobile/d’application via les [!DNL SDK], [!DNL DIL], les appels de événement et les [!DNL DCS] appels. Inclut également les appels de [!DNL Target] si configuré comme intégration de cookie (plutôt que de serveur à serveur).
