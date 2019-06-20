---
description: Une requête en masse renvoie les données que vous pouvez utiliser avec les différents en-têtes dans les feuilles de calcul Mettre à jour, Créer, Estimation et Supprimer.
seo-description: Une requête en masse renvoie les données que vous pouvez utiliser avec les différents en-têtes dans les feuilles de calcul Mettre à jour, Créer, Estimation et Supprimer.
seo-title: Demandes en masse
solution: Audience Manager
title: Demandes en masse
uuid: 0192 d 26 a -4 cea -4 e 12-9 fea -388 b 92 b 382 f 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Requests{#bulk-requests}

Une requête en masse renvoie les données que vous pouvez utiliser avec les différents en-têtes dans les feuilles de calcul Mettre à jour, Créer, Estimation et Supprimer.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l&#39;interface utilisateur sont respectées dans l&#39; [!UICONTROL Bulk Management Tools]interface.

The [!UICONTROL Request] worksheet does not have its own set of column headers and you don&#39;t need to copy IDs to any of the columns. Il renvoie plutôt des données sur la base du bouton d&#39;action que vous cliquez sur la barre d&#39;outils. De plus, une fonction de création de rapports facultative renvoie un nombre de fréquence pour les déclenchements de pixels et le nombre d&#39;utilisateurs uniques pendant plusieurs intervalles fixes.

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Request]** tab.
2. Dans la barre d&#39;outils située en haut de la feuille de calcul, cliquez sur un bouton de demande correspondant aux données que vous souhaitez utiliser. Vous pouvez demander :

   * ID des fournisseurs de données
   * Signaux dérivés
   * Correspondances de destination
   * Caractéristiques articulées autour des règles et intégrées
   * Segments
   * ID des dossiers de caractéristiques et de segments
   The [!DNL Audience Manager] API writes bulk data back to the [!UICONTROL Request] worksheet.

>[!NOTE]
>
>In your results, the `createTime` and `updateTime` columns return data in exponential notation. Les tampons date/heure sous-jacents sont enregistrés sous UNIX UTC heure. Actuellement, la feuille de calcul ne peut pas renvoyer les horodatages de date/heure dans un format lisible.

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
