---
description: La suppression en bloc vous permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés, sources de données, modèles et destinations à l’aide d’une seule opération. Suivez ces instructions pour effectuer une requête de suppression en bloc.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Suppression en bloc
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 1%

---

# Suppression en bloc{#bulk-delete}

La suppression en bloc vous permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés, sources de données, modèles et destinations à l’aide d’une seule opération. Suivez ces instructions pour effectuer une requête de suppression en bloc.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre d’Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[Autorisations des groupes RBAC](../../features/administration/administration-overview.md) affecté dans la variable [!DNL Audience Manager] L’interface utilisateur est honorée dans la [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>Une suppression en bloc des mappages de destination échoue si des segments sont mappés à la destination. Supprimez vos segments de cette destination dans l’interface utilisateur avant de tenter de supprimer des destinations en masse. En outre, les dossiers de caractéristiques et de segments doivent être vides avant de pouvoir les supprimer.

Pour supprimer plusieurs éléments, ouvrez le [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur le bouton **[!UICONTROL Headers]** et copiez les en-têtes de création de l’élément à ajouter.
2. Cliquez sur le bouton **[!UICONTROL Delete]** .
3. Collez les en-têtes de suppression dans la première ligne de la feuille de calcul de mise à jour.
4. Collez ou saisissez les identifiants des objets que vous souhaitez supprimer dans la colonne située sous l’en-tête.
5. Fournissez les [informations de connexion](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) et cliquez sur **[!UICONTROL Submit]**.

   La feuille de calcul crée une [!UICONTROL Results] colonne . La variable [!UICONTROL Results] renvoie un message indiquant si l’élément a été supprimé ou un message d’erreur.
Avant de saisir des données, votre feuille de calcul de mise à jour en masse doit ressembler à ce qui suit :

![](assets/delete.png)

Si votre mise à jour en masse renvoie une erreur ou échoue, voir [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
