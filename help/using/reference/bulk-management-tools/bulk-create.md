---
description: La création en bloc vous permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments à l’aide d’une seule opération. Suivez ces instructions pour effectuer une demande de création en masse.
seo-description: La création en bloc vous permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments à l’aide d’une seule opération. Suivez ces instructions pour effectuer une demande de création en masse.
seo-title: Création en masse
solution: Audience Manager
title: Création en masse
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
translation-type: tm+mt
source-git-commit: 3051ca9f7c4039dafdfa01b89226c1fa8717e610

---


# Création en masse{#bulk-create}

La création en bloc vous permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments à l’aide d’une seule opération. Suivez ces instructions pour effectuer une demande de création en masse.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Ne mélangez pas les types d’objet dans une requête de création en bloc. Les en-têtes de chaque objet sont uniques et ne peuvent pas être combinés. Effacez la feuille de calcul et effectuez une requête distincte pour différents éléments.

Pour créer des objets en bloc, ouvrez la [!UICONTROL Bulk Management Tools] feuille de calcul et procédez comme suit :

1. Cliquez sur l’ **[!UICONTROL Headers]** onglet et copiez les en-têtes de création de l’élément à ajouter.
2. Click the **[!UICONTROL Create]** tab.
3. Collez les en-têtes de création dans la première ligne de la feuille de calcul de mise à jour.
4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l&#39;élément que vous mettez à jour.
Cette action ouvre la boîte de [!UICONTROL Account Information] dialogue.
6. Fournissez les informations [de](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) connexion requises et cliquez sur **[!UICONTROL Submit]**.

La feuille de calcul crée une [!UICONTROL Results] colonne. La [!UICONTROL Results] colonne renvoie la réponse JSON pour une opération réussie. Voir les API [](../../api/rest-api-main/rest-api-main.md) REST pour obtenir des exemples. Avant de saisir des données, votre feuille de calcul de création en masse doit ressembler à l&#39;exemple suivant. Notez que toutes les différentes options de création ne sont pas affichées ici. Cette section vous aide à comprendre à quoi pourrait ressembler une feuille de calcul remplie.

![](assets/cretetraits.png)

Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md)de gestion en bloc.
