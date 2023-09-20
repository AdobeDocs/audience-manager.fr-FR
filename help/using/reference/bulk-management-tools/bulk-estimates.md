---
description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segment. Suivez ces instructions pour effectuer une requête d’estimation en bloc.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Estimations en bloc
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 2%

---

# Estimations en bloc{#bulk-estimates}

Une estimation en masse renvoie des données de taille de segment basées sur des règles de segment. Suivez ces instructions pour effectuer une requête d’estimation en bloc.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre d’Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Autorisations des groupes RBAC](../../features/administration/administration-overview.md) affecté dans la variable [!DNL Audience Manager] L’interface utilisateur est honorée dans la [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en bloc, ouvrez le [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur le bouton **[!UICONTROL Headers]** et copiez la variable [!UICONTROL Estimate Segment Size] en-tête .
2. Cliquez sur le bouton **[!UICONTROL Estimate]** .
3. Collez l’en-tête d’estimation dans la première ligne de la feuille de calcul d’estimation.
4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d’outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l’élément que vous mettez à jour.
Cette action ouvre la fenêtre [!UICONTROL Account Information] de la boîte de dialogue
6. Fournissez les [informations de connexion](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) et cliquez sur **[!UICONTROL Submit]**.

Cette action crée une [!UICONTROL Response] dans la feuille de calcul qui contient les données de taille estimée du segment. Avant de saisir des données, votre feuille de calcul d’estimation en masse doit ressembler à ce qui suit :

![](assets/estimate.png)
Si votre mise à jour en masse renvoie une erreur ou échoue, voir [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
