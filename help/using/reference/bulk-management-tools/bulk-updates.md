---
description: Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques, modèles, sources de données et éléments de segments ou de dossiers de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en masse.
keywords: baaam
seo-description: Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques, modèles, sources de données et éléments de segments ou de dossiers de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en masse.
seo-title: Mises à jour en masse
solution: Audience Manager
title: Mises à jour en masse
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Mises à jour en masse{#bulk-updates}

Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques, modèles, sources de données et éléments de segments ou de dossiers de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en masse.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en masse, ouvrez la [!UICONTROL Bulk Management Tools] feuille de calcul et procédez comme suit :

1. Cliquez sur l’ **[!UICONTROL Headers]** onglet et copiez les en-têtes de mise à jour de l’élément à modifier.
2. Click the **[!UICONTROL Update]** tab.
3. Collez les en-têtes de mise à jour dans la première ligne de la feuille de calcul de mise à jour. Tenez compte des points suivants :

   * Lors de la mise à jour d’un dossier, tous les en-têtes sont obligatoires.
   * Lors de la mise à jour de segments ou de caractéristiques, vous avez uniquement besoin de l’ID de segment (SID) et de l’élément d’en-tête qui doit être modifié. Supprimez les en-têtes inutilisés.

4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur un bouton de mise à jour correspondant à l&#39;élément que vous mettez à jour.
Cette action ouvre la boîte de [!UICONTROL Account Information] dialogue.

6. Fournissez les informations [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) connexion requises et cliquez sur **[!UICONTROL Submit]**.

   La feuille de calcul crée une [!UICONTROL Results] colonne. La [!UICONTROL Results] colonne renvoie la réponse JSON pour une opération réussie. Voir les API [](../../api/rest-api-main/rest-api-main.md) REST pour obtenir des exemples. Avant de saisir des données, votre feuille de calcul de mise à jour en masse doit ressembler à ce qui suit :

![](assets/update.png)

Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gestion en bloc.
