---
description: La suppression en bloc vous permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés, sources de données, modèles et destinations à l’aide d’une seule opération. Suivez ces instructions pour effectuer une requête de suppression en bloc.
seo-description: La suppression en bloc vous permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés, sources de données, modèles et destinations à l’aide d’une seule opération. Suivez ces instructions pour effectuer une requête de suppression en bloc.
seo-title: Suppression en bloc
solution: Audience Manager
title: Suppression en bloc
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Suppression en bloc{#bulk-delete}

La suppression en bloc vous permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés, sources de données, modèles et destinations à l’aide d’une seule opération. Suivez ces instructions pour effectuer une requête de suppression en bloc.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Les ](../../features/administration/administration-overview.md) autorisations de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont honorées dans le  [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Une suppression en bloc des mappages de destination échoue si des segments sont mappés à la destination. Supprimez vos segments de cette destination dans l’interface utilisateur avant de tenter de supprimer des destinations en masse. En outre, les dossiers de caractéristiques et de segments doivent être vides avant de pouvoir les supprimer.

Pour supprimer plusieurs éléments, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l’onglet **[!UICONTROL Headers]** et copiez les en-têtes de création de l’élément à ajouter.
2. Cliquez sur l’onglet **[!UICONTROL Delete]** .
3. Collez les en-têtes de suppression dans la première ligne de la feuille de calcul de mise à jour.
4. Collez ou saisissez les identifiants des objets que vous souhaitez supprimer dans la colonne située sous l’en-tête.
5. Indiquez les [informations de connexion ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) requises, puis cliquez sur **[!UICONTROL Submit]**.

   La feuille de calcul crée une colonne [!UICONTROL Results]. La colonne [!UICONTROL Results] renvoie un message indiquant si l’élément a été supprimé ou un message d’erreur.
Avant de saisir des données, votre feuille de calcul de mise à jour en masse doit ressembler à ce qui suit :

![](assets/delete.png)

Si votre mise à jour en bloc renvoie une erreur ou échoue, voir [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
