---
description: Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques, modèles, sources de données et éléments de dossier de segments ou de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en bloc.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Mises à jour en bloc
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Mises à jour en bloc{#bulk-updates}

Une mise à jour en bloc vous permet de modifier plusieurs segments, caractéristiques, modèles, sources de données et éléments de dossier de segments ou de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en bloc.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre d’Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[Autorisations des groupes RBAC](../../features/administration/administration-overview.md) affecté dans la variable [!DNL Audience Manager] L’interface utilisateur est honorée dans la [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en bloc, ouvrez le [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur le bouton **[!UICONTROL Headers]** et copiez les en-têtes de mise à jour de l’élément à modifier.
2. Cliquez sur le bouton **[!UICONTROL Update]** .
3. Collez les en-têtes de mise à jour dans la première ligne de la feuille de calcul de mise à jour. Notez les points suivants :

   * Lors de la mise à jour d’un dossier, tous les en-têtes sont requis.
   * Lors de la mise à jour de segments ou de caractéristiques, vous avez uniquement besoin de l’identifiant de segment (SID) et de l’élément d’en-tête qui doit être modifié. Supprimez les en-têtes inutilisés.

4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d’outils de la feuille de calcul, cliquez sur un bouton de mise à jour correspondant à l’élément que vous mettez à jour.
Cette action ouvre la fenêtre [!UICONTROL Account Information] de la boîte de dialogue

6. Fournissez les [informations de connexion](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) et cliquez sur **[!UICONTROL Submit]**.

   La feuille de calcul crée une [!UICONTROL Results] colonne . La variable [!UICONTROL Results] renvoie la réponse JSON pour une opération réussie. Voir [API REST](../../api/rest-api-main/rest-api-main.md) pour obtenir des exemples. Avant de saisir des données, votre feuille de calcul de mise à jour en masse doit ressembler à ce qui suit :

![](assets/update.png)

Si votre mise à jour en masse renvoie une erreur ou échoue, voir [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
