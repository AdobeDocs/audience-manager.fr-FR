---
description: Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques et éléments de dossiers de segments ou caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en masse.
keywords: baaam
seo-description: Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques et éléments de dossiers de segments ou caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en masse.
seo-title: Mises à jour en masse
solution: Audience Manager
title: Mises à jour en masse
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Mises à jour en masse{#bulk-updates}

Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques et éléments de dossiers de segments ou caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en masse.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>Les variables ne [!UICONTROL Bulk Management Tools] sont pas *prises en charge par* [!DNL Audience Manager]. Cet outil est fourni à titre pratique et à titre de courtoisie seulement. Pour les modifications en masse, nous vous recommandons de travailler avec les API [Audience Manager](../../api/rest-api-main/aam-api-getting-started.md) à la place. [Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en masse, ouvrez la [!UICONTROL Bulk Management Tools] feuille de calcul et procédez comme suit :

1. Cliquez sur l’ **[!UICONTROL Headers]** onglet et copiez les en-têtes de mise à jour de l’élément à modifier.
1. Click the **[!UICONTROL Update]** tab.
1. Collez les en-têtes de mise à jour dans la première ligne de la feuille de calcul de mise à jour. Notez les points suivants :

   * Lors de la mise à jour d’un dossier, tous les en-têtes sont obligatoires.
   * Lors de la mise à jour de segments ou de caractéristiques, vous avez uniquement besoin de l’ID de segment (SID) et de l’élément d’en-tête qui doit être modifié. Supprimez les en-têtes inutilisés.

1. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
1. Dans la barre d'outils de la feuille de calcul, cliquez sur un bouton de mise à jour correspondant à l'élément que vous mettez à jour.
Cette action ouvre la boîte de dialogue [!UICONTROL Account Information] .

1. Fournissez les informations [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) connexion requises et cliquez sur **[!UICONTROL Submit]**.

   La feuille de calcul crée une [!UICONTROL Results] colonne. La [!UICONTROL Results] colonne renvoie la réponse JSON pour une opération réussie. Voir les API [](../../api/rest-api-main/rest-api-main.md) REST pour obtenir des exemples. Avant de saisir des données, votre feuille de calcul de mise à jour en masse doit ressembler à ce qui suit :

![](assets/update.png)

Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gestion en bloc.
