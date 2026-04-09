---
description: La création en masse vous permet de construire plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments en une seule opération. Suivez ces instructions pour effectuer une requête de création en bloc.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Création en bloc
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
TQID: https://experienceleague.adobe.com/EbavgrTOfC5Wjx4IwGxt4Gi3-d-EkOSQjG3WaRAionU
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: c2c33729-f309-4bc2-92ba-87c475259df3id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 0%

---

# Création en bloc{#bulk-create}

La création en masse vous permet de construire plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments en une seule opération. Suivez ces instructions pour effectuer une requête de création en bloc.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>Les [autorisations de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans l’interface utilisateur de [!DNL Audience Manager] sont respectées dans la [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Ne mélangez pas les types d’objet dans une demande de création en bloc. Les en-têtes de chaque objet sont uniques et ne peuvent pas être combinés. Effacez la feuille de calcul et effectuez une demande distincte pour différents éléments.

Pour créer des objets en bloc, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l’onglet **[!UICONTROL Headers]** et copiez les en-têtes de création pour l’élément que vous souhaitez ajouter.
2. Cliquez sur l’onglet **[!UICONTROL Create]** .
3. Collez les en-têtes de création dans la première ligne de la feuille de calcul de mise à jour.
4. Collez ou saisissez les données à modifier dans une colonne correspondante en fonction du libellé de l’en-tête.
5. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l&#39;élément que vous mettez à jour.
Cette action ouvre la boîte de dialogue [!UICONTROL Account Information].
6. Fournissez les [informations de connexion](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) requises, puis cliquez sur **[!UICONTROL Submit]**.

La feuille de calcul crée une colonne [!UICONTROL Results]. La colonne [!UICONTROL Results] renvoie la réponse JSON pour une opération réussie. Voir les [API REST](../../api/rest-api-main/rest-api-main.md) pour obtenir des exemples. Avant de saisir des données, votre feuille de calcul de création en bloc doit ressembler à l’exemple suivant. Notez que toutes les différentes options de création ne sont pas affichées ici. Cela vous aide à comprendre à quoi pourrait ressembler une feuille de calcul remplie.

![](assets/cretetraits.png)

Si votre mise à jour en bloc renvoie une erreur ou échoue, consultez [Dépannage pour les outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
