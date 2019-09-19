---
description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segment. Suivez ces instructions pour effectuer une demande d’estimation en masse.
seo-description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segment. Suivez ces instructions pour effectuer une demande d’estimation en masse.
seo-title: Estimations en masse
solution: Audience Manager
title: Estimations en masse
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Estimations en masse{#bulk-estimates}

Une estimation en masse renvoie des données de taille de segment basées sur des règles de segment. Suivez ces instructions pour effectuer une demande d’estimation en masse.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>Les variables ne [!UICONTROL Bulk Management Tools] sont pas *prises en charge par* [!DNL Audience Manager]. Cet outil est fourni à titre pratique et à titre de courtoisie seulement. Pour les modifications en masse, nous vous recommandons de travailler avec les API [Audience Manager](../../api/rest-api-main/aam-api-getting-started.md) à la place. [Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en masse, ouvrez la [!UICONTROL Bulk Management Tools] feuille de calcul et procédez comme suit :

1. Cliquez sur l’ **[!UICONTROL Headers]** onglet et copiez l’ [!UICONTROL Estimate Segment Size] en-tête.
1. Click the **[!UICONTROL Estimate]** tab.
1. Collez l'en-tête d'estimation dans la première ligne de la feuille de calcul d'estimation.
1. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
1. Dans la barre d'outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l'élément que vous mettez à jour.
Cette action ouvre la boîte de dialogue [!UICONTROL Account Information] .

1. Fournissez les informations [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) connexion requises et cliquez sur **[!UICONTROL Submit]**.

Cette action crée une [!UICONTROL Response] colonne dans la feuille de calcul qui contient une estimation de la taille du segment. Avant de saisir des données, votre feuille de calcul d’estimation en masse doit ressembler à ce qui suit :

![](assets/estimate.png)Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gestion en bloc.

