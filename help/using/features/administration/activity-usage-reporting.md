---
description: Les rapports d’utilisation des activités vous permettent d’afficher et de suivre l’utilisation des activités pour votre instance d’Audience Manager, de sorte que vous puissiez comparer votre utilisation réelle à votre engagement contractuel.
keywords: activity, usage, reporting, commitment
seo-description: Les rapports d’utilisation des activités vous permettent d’afficher et de suivre l’utilisation des activités pour votre instance d’Audience Manager, de sorte que vous puissiez comparer votre utilisation réelle à votre engagement contractuel.
seo-title: Rapports d’utilisation des activités
solution: Audience Manager
title: Rapports d’utilisation des activités
topic: Activity Usage Reporting
translation-type: tm+mt
source-git-commit: 7a3914af8fb225508f57724a75fe2547aac3f241

---


# Rapports d’utilisation des activités

## Aperçu {#overview}

L’ [!UICONTROL Activity Usage Report] outil vous permet d’afficher et de suivre l’utilisation de l’activité de votre instance d’Audience Manager, ce qui vous donne une idée claire de la comparaison entre l’utilisation de l’activité et votre engagement contractuel.

De plus, vous pouvez télécharger le [!UICONTROL Activity Usage Report] fichier au besoin, pour la conservation des enregistrements et l’analyse personnalisée.

## Considérations {#considerations}

Elle [!UICONTROL Activity Usage Report] est accessible à tous les utilisateurs d’Audience Manager disposant de droits [d’](edit-account-settings.md)administrateur.

> [!IMPORTANT]
>
> Le [!UICONTROL Activity Usage Report] montre les statistiques d’utilisation des activités de votre instance Audience Manager. Pour toute demande de facturation liée à l’utilisation de votre activité, contactez votre représentant Adobe.

## Cas d’utilisation {#use-cases}

Il existe deux principaux cas d’utilisation du [!UICONTROL Activity Usage Report]:

* **Suivi de l’utilisation réelle de l’activité d’instance par rapport à votre engagement** d’utilisation de l’activité : La plupart des clients ont un engagement d’activité estimé mensuellement par instance d’Audience Manager, qui est ensuite cumulé dans un engagement d’activité annuel pour toutes les instances. Bien que ce rapport ne soit pas un rapport de facturation, il peut vous aider à déterminer si vous dépassez l’utilisation de l’activité engagée.
* **Validation des modifications** d’implémentation : Si vous avez récemment mis à jour votre implémentation, par exemple en configurant le transfert côté serveur d’Analytics ou en modifiant les paramètres d’appel au serveur Target, ce rapport peut vous aider à vérifier si le nouveau volume d’activité est conforme au volume d’activité attendu.

## Utilisation du rapport d’utilisation des activités {#using}

Pour voir le [!UICONTROL Activity Usage Report], connectez-vous à votre compte Audience Manager, puis cliquez sur **[!UICONTROL Administration]**>**[!UICONTROL Usage]**.

![aur-ui](assets/aur-ui.png)

Ensuite, utilisez le **[!UICONTROL Reporting Interval]**filtre pour sélectionner l&#39;intervalle de génération du rapport. Vous pouvez choisir entre 30, 60, 90 jours ou une plage de dates personnalisée.

Une fois le rapport chargé, vous pouvez voir la ventilation de votre rapport [!UICONTROL Activities] pour la période sélectionnée.

[!UICONTROL Activities] définissez le total global de toutes les interactions sur site et hors site avec Audience Manager, fractionnées en catégories suivantes :

* **[!UICONTROL Server Calls]**: Tout événement de collecte ou de récupération de données envoyé à Audience Manager à partir de sites Web, de serveurs, de courriers électroniques, d’applications mobiles ou d’autres systèmes.
* **[!UICONTROL Pixel Calls](anciennement[!UICONTROL Impression Server Calls])**: Données collectées à partir de publicités (telles que le volume d’impression d’une plateforme de ciblage) ou appels d’impression par courrier électronique envoyés à Audience Manager. Pour ce faire, le `d_event` paramètre doit être présent dans la chaîne de requête.
* **[!UICONTROL On-Boarded Records]**: Enregistrements uniques assimilés à partir de votre propre système de gestion de la relation client (CRM) ou d’autres fichiers de données hors ligne, tels que les enregistrements du centre d’appels, les ID de périphérique et les flux de données personnalisés provenant de fournisseurs de données externes.
* **[!UICONTROL Log File Records]**: Enregistrements uniques des fichiers journaux assimilés à Audience Manager à partir d’une plateforme de ciblage.

> [!NOTE]
> Un enregistrement unique définit chaque enregistrement individuel de données dans un fichier stocké par Adobe au nom d’un client d’Audience Manager.

De plus, vous pouvez utiliser les types de [!UICONTROL Activity Usage Trends] graphique pour basculer entre deux types de graphiques.

![aur-ui-graphes](assets/aur-ui-graphs.png)

Vous pouvez également placer le curseur sur une date spécifique du plan de montage chronologique pour voir l’utilisation détaillée de cette date.

![aur-hover](assets/aur-hover.png)

## Exportation des rapports d’utilisation des activités {#export}

Pour une meilleure vue d’ensemble du niveau d’utilisation de l’activité d’Audience Manager, vous pouvez exporter le fichier [!UICONTROL Activity Usage Report] en fonction du type d’enregistrement à inclure.

![aur-export](assets/aur-export.png)

Les **[!UICONTROL Onboarded Records Breakdown]**rapports et**[!UICONTROL Onsite Server Calls Breakdown]** les rapports fournissent une vue d’ensemble des données source disponibles pour ces activités. Le volume attribué à ces ventilations est basé sur votre implémentation.

### Ventilation des enregistrements intégrés {#onboarded-breakdown}

Ce rapport contient des enregistrements intégrés ventilés par source de données.

### Ventilation des appels au serveur Onsite {#onsite-breakdown}

Ce rapport contient une ventilation des appels serveur provenant de trois sources : [!UICONTROL Analytics], [!UICONTROL Target]et [!UICONTROL Other].

* **[!UICONTROL Analytics]**: Il s’agit d’appels serveur facturables transmis de toutes les instances Adobe Analytics à Audience Manager, y compris le transfert côté serveur. Les appels serveur secondaires ou les appels serveur en double (comme dans le cas du transfert côté serveur à partir de plusieurs suites de rapports) ne sont pas facturables. Ils ne sont donc pas inclus dans cette ventilation.
* **[!UICONTROL Target]**: Il s’agit d’appels côté serveur d’Adobe Target vers Audience Manager, pour récupérer les données de segments d’Audience Manager dans le cadre d’une intégration serveur à serveur.
* **[!UICONTROL Other]**: Inclut les appels en provenance de tout autre site Web ou système (sites partenaires, appels directs au serveur, etc.), les appels de navigateur/application mobile via les[!DNL SDK],[!DNL DIL], les appels d’événement et[!DNL DCS]les appels. Inclut également les appels de[!DNL Target]s’ils sont configurés en tant qu’intégration de cookie (plutôt que de serveur à serveur).
