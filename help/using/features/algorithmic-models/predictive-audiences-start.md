---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: Gestion des Audiences prédictives
solution: Audience Manager
title: Audiences prédictives d’Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 71e129a39cf85d5f07979ede8f3aa862f93b6512
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 8%

---


# Prise en main des audiences prédictives {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

## Créer un modèle d’Audiences prédictives {#create-predictive-audiences}

Avant de créer un [!UICONTROL Predictive Audiences] modèle, vous devez choisir la source de données propriétaire à laquelle vous souhaitez affecter vos [!UICONTROL Predictive Audiences] caractéristiques et segments. Vous pouvez utiliser une source de données propriétaire existante ou en créer une nouvelle. Voir [Gérer les sources](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) de données pour en savoir plus sur la création d’une source de données propriétaire.

Une fois que vous avez identifié la source de données que vous allez utiliser, suivez les étapes ci-dessous.

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Dans la [!UICONTROL Predictive Audiences] section, cliquez sur **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Ensuite, définissez les personnes dont vous souhaitez classifier l’audience. Pour ce faire, sélectionnez les caractéristiques ou les segments à partir desquels créer des personnages. Utilisez les [!UICONTROL Traits] onglets et [!UICONTROL Segments] dans le coin supérieur gauche de l’écran pour basculer entre votre catalogue de caractéristiques et de segments. Une fois que vous avez identifié les caractéristiques ou les segments que vous souhaitez utiliser comme personnages, cliquez sur l’ **[!UICONTROL Add]** icône correspondante dans la [!UICONTROL Action] colonne.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Vous devez choisir un minimum de deux caractéristiques ou deux segments pour vos personnages de base. Vous ne pouvez pas utiliser une combinaison de caractéristiques et de segments.
1. Cliquez **[!UICONTROL Next]** après avoir défini vos personnages.
1. Ensuite, sélectionnez l’audience propriétaire à classifier en choisissant une caractéristique ou un segment propriétaire pour cette audience. Utilisez les [!UICONTROL Traits] onglets et [!UICONTROL Segments] dans le coin supérieur gauche de l’écran pour passer d’un catalogue de caractéristiques à un catalogue de segments. Sélectionnez la caractéristique ou le segment propriétaire que vous souhaitez utiliser comme audience pour l’ajouter au modèle.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Cliquez **[!UICONTROL Next]** après avoir choisi votre audience.
1. Renseignez les détails du modèle :
   * **[!UICONTROL Model Name]**: Entrez un nom descriptif pour le modèle, qui vous aidera à l&#39;identifier plus tard. Les noms des segments générés par le modèle s’début avec le nom du modèle.
   * **[!UICONTROL Description]**: Entrez une description du modèle qui vous aidera à identifier son cas d&#39;utilisation.
   * **[!UICONTROL Data Source]**: Sélectionnez la source de données propriétaire à laquelle vous souhaitez affecter les [!UICONTROL Predictive Audiences] segments de ce modèle.
   * **[!UICONTROL Profile Merge Rule]**: Sélectionnez le [!UICONTROL Profile Merge Rule] à attribuer pour tous les prédictifs [!UICONTROL segments] créés par ce modèle. Si votre audience de cible sélectionnée est une [!UICONTROL segment], nous vous recommandons de sélectionner la même [!UICONTROL Profile Merge Rule] audience de cible.
      ![prédictive-audiences-save](assets/predictive-audiences-save.png)
1. Cliquez sur **[!UICONTROL Save]**.

## Modification des Audiences prédictives {#edit-predictive-audiences}

L&#39;Audience Manager ne prend pas en charge la modification des [!UICONTROL Predictive Audiences] modèles existants. Pour modifier la configuration d&#39;un modèle, vous devez créer un nouveau modèle. Si vous avez atteint la limite de 10 [!UICONTROL Predictive Audiences] modèles et devez modifier l&#39;un de vos modèles, vous devez supprimer un modèle et en créer un nouveau.

## Suppression des Audiences prédictives {#delete-predictive-audiences}

Pour supprimer un [!UICONTROL Predictive Audiences] modèle, cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, recherchez le modèle à supprimer, puis cliquez sur l&#39; **[!UICONTROL Delete]** icône .
