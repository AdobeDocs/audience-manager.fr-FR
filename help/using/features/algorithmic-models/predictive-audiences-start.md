---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-title: Gestion des audiences prédictives
solution: Audience Manager
title: Prise en main des audiences prédictives
feature: Modèles algorithmiques
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 7%

---

# Prise en main des audiences prédictives {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

## Création d’un modèle d’audiences prédictives {#create-predictive-audiences}

Avant de créer un modèle [!UICONTROL Predictive Audiences], vous devez déterminer la source de données propriétaire à laquelle vous souhaitez affecter vos caractéristiques et segments [!UICONTROL Predictive Audiences]. Vous pouvez utiliser une source de données propriétaire existante ou en créer une nouvelle. Voir [Gestion des sources de données](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) pour plus d’informations sur la création d’une source de données propriétaire.

Une fois que vous aurez su quelle source de données vous allez utiliser, procédez comme suit.

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Dans la section [!UICONTROL Predictive Audiences], cliquez sur **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Définissez ensuite les personas selon lesquelles vous souhaitez classer votre audience. Pour ce faire, sélectionnez les caractéristiques ou les segments à partir desquels créer des personnages. Utilisez les onglets [!UICONTROL Traits] et [!UICONTROL Segments] dans le coin supérieur gauche de l’écran pour basculer entre votre caractéristique et votre catalogue de segments. Une fois que vous avez identifié les caractéristiques ou les segments que vous souhaitez utiliser comme personas, cliquez sur l’icône **[!UICONTROL Add]** correspondante dans la colonne [!UICONTROL Action].
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Vous devez choisir au moins deux caractéristiques ou deux segments pour vos personnages de base. Vous ne pouvez pas utiliser une combinaison de caractéristiques et de segments.
1. Cliquez sur **[!UICONTROL Next]** après avoir défini vos personas.
1. Sélectionnez ensuite l’audience propriétaire que vous souhaitez classer en choisissant une caractéristique ou un segment propriétaire pour cette audience. Utilisez les onglets [!UICONTROL Traits] et [!UICONTROL Segments] dans le coin supérieur gauche de l’écran pour basculer entre vos caractéristiques et votre catalogue de segments. Sélectionnez la caractéristique ou le segment propriétaire que vous souhaitez utiliser comme audience pour l’ajouter au modèle.
   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)
1. Cliquez sur **[!UICONTROL Next]** après avoir choisi votre audience.
1. Renseignez les détails du modèle :
   * **[!UICONTROL Model Name]**: Saisissez un nom explicite pour le modèle, qui vous aidera à l’identifier ultérieurement. Les noms des segments générés par le modèle commencent par le nom du modèle.
   * **[!UICONTROL Description]**: Saisissez une description du modèle qui vous aidera à identifier son cas d’utilisation.
   * **[!UICONTROL Data Source]**: Sélectionnez la source de données propriétaire à laquelle vous souhaitez affecter les  [!UICONTROL Predictive Audiences] segments de ce modèle.
   * **[!UICONTROL Profile Merge Rule]**: Sélectionnez le  [!UICONTROL Profile Merge Rule] à attribuer pour tous les prédictifs  [!UICONTROL segments] créés par ce modèle. Si l&#39;audience cible sélectionnée est [!UICONTROL segment], il est recommandé de sélectionner la même [!UICONTROL Profile Merge Rule] audience cible.
      ![predictive-audiences-save](assets/predictive-audiences-save.png)
1. Cliquez sur **[!UICONTROL Save]**.

## Clonage et modification des modèles d’audience prédictive {#clone-predictive-audiences}

L’Audience Manager ne prend pas en charge la modification des modèles [!UICONTROL Predictive Audiences] existants. Pour modifier la configuration d’un modèle, vous pouvez créer un clone d’un modèle existant et le modifier. Pour ce faire, procédez comme suit :

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Cliquez sur le nom du modèle [!UICONTROL Predictive Audiences] que vous souhaitez cloner.
3. Cliquez sur le bouton **[!UICONTROL Clone]** dans la partie supérieure gauche de l’écran.
   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)
4. Une fois le modèle cloné, vous accédez à la page [!DNL Save & Configure] du modèle cloné. Dans cette page, vous pouvez modifier la balise [!UICONTROL data source] et la balise [!UICONTROL Profile Merge Rule] affectée du modèle. Pour éditer les personnages et l’audience cible du modèle cloné, utilisez les boutons [!UICONTROL Back] et [!UICONTROL Next] pour naviguer entre les trois onglets, ou cliquez sur les trois noms d’onglets.

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. Lorsque vous avez terminé de modifier un modèle, cliquez sur **[!UICONTROL Save]**.

## Suppression d’audiences prédictives {#delete-predictive-audiences}

Pour supprimer un modèle [!UICONTROL Predictive Audiences], accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, recherchez le modèle à supprimer, puis cliquez sur l’icône **[!UICONTROL Delete]**.
