---
description: La suppression en bloc permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés et destinations avec une seule opération. Suivez ces instructions pour effectuer une demande de suppression en bloc.
seo-description: La suppression en bloc permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés et destinations avec une seule opération. Suivez ces instructions pour effectuer une demande de suppression en bloc.
seo-title: Suppression en masse
solution: Audience Manager
title: Suppression en masse
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Suppression en masse{#bulk-delete}

La suppression en bloc permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés et destinations avec une seule opération. Suivez ces instructions pour effectuer une demande de suppression en bloc.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>Les variables ne [!UICONTROL Bulk Management Tools] sont pas *prises en charge par* [!DNL Audience Manager]. Cet outil est fourni à titre pratique et à titre de courtoisie seulement. Pour les modifications en masse, nous vous recommandons de travailler avec les API [Audience Manager](../../api/rest-api-main/aam-api-getting-started.md) à la place. [Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Une suppression en bloc pour les mappages de destination échoue si des segments sont mappés sur la destination. Supprimez vos segments de cette destination dans l’interface utilisateur avant d’essayer de supprimer des destinations en bloc. En outre, les dossiers de caractéristiques et de segments doivent être vides avant de pouvoir les supprimer.

Pour supprimer plusieurs éléments, ouvrez la [!UICONTROL Bulk Management Tools] feuille de calcul et procédez comme suit :

1. Cliquez sur l’ **[!UICONTROL Headers]** onglet et copiez les en-têtes de création de l’élément à ajouter.
2. Click the **[!UICONTROL Delete]** tab.
3. Collez les en-têtes de suppression dans la première ligne de la feuille de calcul de mise à jour.
4. Collez ou saisissez les ID des objets à supprimer dans la colonne située sous l’en-tête.
5. Fournissez les informations [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) connexion requises et cliquez sur **[!UICONTROL Submit]**.

   La feuille de calcul crée une [!UICONTROL Results] colonne. La [!UICONTROL Results] colonne renvoie un message indiquant si l’élément a été supprimé ou un message d’erreur.
Avant de saisir des données, votre feuille de calcul de mise à jour en masse doit ressembler à ce qui suit :

![](assets/delete.png)

Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gestion en bloc.
