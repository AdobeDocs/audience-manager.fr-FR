---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: Gestion des Audiences prédictives
solution: Audience Manager
title: Audiences prédictives d’Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 48bf17a2899fd06c525ba6b4fddb9ec805efb5c3
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 7%

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

## Clonage et modification de modèles d’Audience prédictifs {#clone-predictive-audiences}

L&#39;Audience Manager ne prend pas en charge la modification des [!UICONTROL Predictive Audiences] modèles existants. Pour modifier la configuration d&#39;un modèle, vous pouvez créer un clone d&#39;un modèle existant et le modifier. Voici comment procéder :

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Cliquez sur le nom du [!UICONTROL Predictive Audiences] modèle à cloner.
3. Cliquez sur le **[!UICONTROL Clone]** bouton dans l’angle supérieur gauche de l’écran.
   ![prédictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Une fois le modèle cloné, vous accédez à la [!DNL Save & Configure] page du modèle cloné. Dans cette page, vous pouvez modifier le modèle [!UICONTROL data source] et l&#39;assignation[!UICONTROL Profile Merge Rule] du modèle. Pour modifier les personnages et l’audience de cible du modèle cloné, utilisez les boutons [!UICONTROL Back] et [!UICONTROL Next] pour naviguer entre les trois onglets ou cliquez sur les trois noms d’onglets.

   ![prédictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Lorsque vous avez terminé de modifier un modèle, cliquez sur **[!UICONTROL Save]**.

## Suppression des Audiences prédictives {#delete-predictive-audiences}

Pour supprimer un [!UICONTROL Predictive Audiences] modèle, cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, recherchez le modèle à supprimer, puis cliquez sur l&#39; **[!UICONTROL Delete]** icône .
