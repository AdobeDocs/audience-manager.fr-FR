---
description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segmentation. Suivez ces instructions pour effectuer une demande d’estimation en masse.
seo-description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segmentation. Suivez ces instructions pour effectuer une demande d’estimation en masse.
seo-title: Estimations en masse
solution: Audience Manager
title: Estimations en masse
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: 3051ca9f7c4039dafdfa01b89226c1fa8717e610

---


# Estimations en masse{#bulk-estimates}

Une estimation en masse renvoie des données de taille de segment basées sur des règles de segmentation. Suivez ces instructions pour effectuer une demande d’estimation en masse.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en masse, ouvrez la [!UICONTROL Bulk Management Tools] feuille de calcul et procédez comme suit :

1. Cliquez sur l’ **[!UICONTROL Headers]** onglet et copiez l’ [!UICONTROL Estimate Segment Size] en-tête.
2. Click the **[!UICONTROL Estimate]** tab.
3. Collez l&#39;en-tête d&#39;estimation dans la première ligne de la feuille de calcul d&#39;estimation.
4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l&#39;élément que vous mettez à jour.
Cette action ouvre la boîte de [!UICONTROL Account Information] dialogue.
6. Fournissez les informations [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) connexion requises et cliquez sur **[!UICONTROL Submit]**.

Cette action crée une [!UICONTROL Response] colonne dans la feuille de calcul qui contient une estimation de la taille du segment. Avant de saisir des données, votre feuille de calcul d’estimation en masse doit ressembler à ce qui suit :

![](assets/estimate.png)
Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gestion en bloc.

