---
description: La création en bloc vous permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments à l’aide d’une seule opération. Suivez ces instructions pour effectuer une requête de création en bloc.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Création en bloc
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Création en bloc{#bulk-create}

La création en bloc vous permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments à l’aide d’une seule opération. Suivez ces instructions pour effectuer une requête de création en bloc.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre d’Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Les autorisations de groupe RBAC ](../../features/administration/administration-overview.md) attribuées dans l’interface utilisateur de [!DNL Audience Manager] sont honorées dans le [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Ne mélangez pas les types d’objet dans une requête de création en bloc. Les en-têtes de chaque objet sont uniques et ne peuvent pas être combinés. Effacez la feuille de calcul et effectuez une requête distincte pour différents éléments.

Pour créer des objets en bloc, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l’onglet **[!UICONTROL Headers]** et copiez les en-têtes de création de l’élément à ajouter.
2. Cliquez sur l’onglet **[!UICONTROL Create]** .
3. Collez les en-têtes de création dans la première ligne de la feuille de calcul de mise à jour.
4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d’outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l’élément que vous mettez à jour.
Cette action ouvre la boîte de dialogue [!UICONTROL Account Information].
6. Fournissez les [informations de connexion](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) requises et cliquez sur **[!UICONTROL Submit]**.

La feuille de calcul crée une colonne [!UICONTROL Results]. La colonne [!UICONTROL Results] renvoie la réponse JSON pour une opération réussie. Voir les [API REST](../../api/rest-api-main/rest-api-main.md) pour obtenir des exemples. Avant de saisir des données, la feuille de calcul de création en masse doit ressembler à l’exemple suivant. Notez que toutes les différentes options de création ne s’affichent pas ici. Cela permet de vous aider à comprendre à quoi pourrait ressembler une feuille de calcul terminée.

![](assets/cretetraits.png)

Si votre mise à jour en masse renvoie une erreur ou échoue, reportez-vous à la section [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
