---
description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segment. Suivez ces instructions pour effectuer une requête d’estimation en bloc.
seo-description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segment. Suivez ces instructions pour effectuer une requête d’estimation en bloc.
seo-title: Estimations en bloc
solution: Audience Manager
title: Estimations en bloc
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Estimations en bloc{#bulk-estimates}

Une estimation en masse renvoie des données de taille de segment basées sur des règles de segment. Suivez ces instructions pour effectuer une requête d’estimation en bloc.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Les ](../../features/administration/administration-overview.md) autorisations de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont honorées dans le  [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en bloc, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l’onglet **[!UICONTROL Headers]** et copiez l’en-tête [!UICONTROL Estimate Segment Size].
2. Cliquez sur l’onglet **[!UICONTROL Estimate]** .
3. Collez l’en-tête d’estimation dans la première ligne de la feuille de calcul d’estimation.
4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d’outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l’élément que vous mettez à jour.
Cette action ouvre la boîte de dialogue [!UICONTROL Account Information].
6. Indiquez les [informations de connexion ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) requises, puis cliquez sur **[!UICONTROL Submit]**.

Cette action crée une colonne [!UICONTROL Response] dans la feuille de calcul qui contient les données de taille estimée du segment. Avant de saisir des données, votre feuille de calcul d’estimation en masse doit ressembler à ce qui suit :

![](assets/estimate.png)
Si votre mise à jour en bloc renvoie une erreur ou échoue, voir  [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
