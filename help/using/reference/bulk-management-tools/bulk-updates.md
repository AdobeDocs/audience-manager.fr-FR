---
description: Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques, modèles, sources de données et éléments de dossier de segments ou de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en bloc.
keywords: baaam
seo-description: Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques, modèles, sources de données et éléments de dossier de segments ou de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en bloc.
seo-title: Mises à jour en bloc
solution: Audience Manager
title: Mises à jour en bloc
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# Mises à jour en bloc{#bulk-updates}

Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques, modèles, sources de données et éléments de dossier de segments ou de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en bloc.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Les ](../../features/administration/administration-overview.md) autorisations de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont honorées dans le  [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en bloc, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l’onglet **[!UICONTROL Headers]** et copiez les en-têtes de mise à jour de l’élément à modifier.
2. Cliquez sur l’onglet **[!UICONTROL Update]** .
3. Collez les en-têtes de mise à jour dans la première ligne de la feuille de calcul de mise à jour. Notez les points suivants :

   * Lors de la mise à jour d’un dossier, tous les en-têtes sont requis.
   * Lors de la mise à jour de segments ou de caractéristiques, vous avez uniquement besoin de l’identifiant de segment (SID) et de l’élément d’en-tête qui doit être modifié. Supprimez les en-têtes inutilisés.

4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d’outils de la feuille de calcul, cliquez sur un bouton de mise à jour correspondant au        élément que vous mettez à jour.
Cette action ouvre la boîte de dialogue [!UICONTROL Account Information].

6. Indiquez les [informations de connexion ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) requises, puis cliquez sur **[!UICONTROL Submit]**.

   La feuille de calcul crée une colonne [!UICONTROL Results]. La colonne [!UICONTROL Results] renvoie la réponse JSON pour une opération réussie. Voir les [API REST](../../api/rest-api-main/rest-api-main.md) pour consulter des exemples. Avant de saisir des données, votre feuille de calcul de mise à jour en masse doit ressembler à ce qui suit :

![](assets/update.png)

Si votre mise à jour en bloc renvoie une erreur ou échoue, voir [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
