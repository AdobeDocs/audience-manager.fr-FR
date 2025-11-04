---
description: Les audiences prédictives vous aident à classer les audiences inconnues en personas distinctes en temps réel à l’aide de la science des données.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: Prise en main des audiences prédictives
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 2%

---

# Prise en main des audiences prédictives {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

## Création d’un modèle d’audiences prédictives {#create-predictive-audiences}

Avant de créer un modèle de [!UICONTROL Predictive Audiences], vous devez décider à quelle source de données propriétaire vous souhaitez affecter vos caractéristiques et segments de [!UICONTROL Predictive Audiences]. Vous pouvez utiliser une source de données propriétaire existante ou en créer une nouvelle. Consultez [Gérer les sources de données](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) pour plus d’informations sur la création d’une source de données propriétaire.

Une fois que vous savez quelle source de données vous allez utiliser, procédez comme suit.

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Dans la section [!UICONTROL Predictive Audiences], cliquez sur **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Définissez ensuite les personnes en fonction desquelles vous souhaitez classer votre audience. Pour ce faire, choisissez des caractéristiques ou des segments à partir desquels créer des rôles. Utilisez les onglets [!UICONTROL Traits] et [!UICONTROL Segments] dans le coin supérieur gauche de l’écran pour basculer entre votre caractéristique et votre catalogue de segments. Une fois que vous avez identifié les caractéristiques ou les segments que vous souhaitez utiliser en tant que personnes, cliquez sur l’icône de **[!UICONTROL Add]** correspondante dans la colonne [!UICONTROL Action].

   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)

   >[!NOTE]
   >
   >Vous devez choisir au minimum deux caractéristiques ou deux segments pour vos personnages de base. Vous ne pouvez pas utiliser une combinaison de caractéristiques et de segments.

1. Cliquez sur **[!UICONTROL Next]** après avoir défini vos rôles.
1. Sélectionnez ensuite l’audience propriétaire que vous souhaitez classer en choisissant une caractéristique ou un segment propriétaire pour cette audience. Utilisez les onglets [!UICONTROL Traits] et [!UICONTROL Segments] dans le coin supérieur gauche de l’écran pour basculer entre vos caractéristiques et votre catalogue de segments. Sélectionnez la caractéristique ou le segment propriétaire que vous souhaitez utiliser comme audience pour l’ajouter au modèle.

   ![smart-persona-select-audience](assets/predictive-audiences-audience.png)

1. Cliquez sur **[!UICONTROL Next]** après avoir choisi votre audience.
1. Renseignez les détails du modèle :

   * **[!UICONTROL Model Name]** : saisissez un nom explicite pour le modèle, qui vous aidera à l’identifier ultérieurement. Les noms des segments générés par le modèle commencent par le nom du modèle.
   * **[!UICONTROL Description]** : saisissez une description du modèle qui vous aidera à identifier son cas d’utilisation.
   * **[!UICONTROL Data Source]** : sélectionnez la source de données propriétaire à laquelle vous souhaitez affecter les segments de [!UICONTROL Predictive Audiences] de ce modèle.
   * **[!UICONTROL Profile Merge Rule]** : sélectionnez les [!UICONTROL Profile Merge Rule] à affecter à toutes les [!UICONTROL segments] prédictives créées par ce modèle. Si l’audience cible sélectionnée est une [!UICONTROL segment], nous vous recommandons de sélectionner la même [!UICONTROL Profile Merge Rule] de l’audience cible.

   ![predictive-audiences-save](assets/predictive-audiences-save.png)

1. Cliquez sur **[!UICONTROL Save]**.

## Clonage et modification de modèles d’audience prédictifs {#clone-predictive-audiences}

Audience Manager ne prend pas en charge la modification des modèles de [!UICONTROL Predictive Audiences] existants. Pour modifier la configuration d’un modèle, vous pouvez créer un clone d’un modèle existant et le modifier. Voici comment procéder :

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Cliquez sur le nom du modèle de [!UICONTROL Predictive Audiences] à cloner.
1. Cliquez sur le bouton **[!UICONTROL Clone]** dans la partie supérieure gauche de l’écran.

   ![predictive-audiences-clone](assets/predictive-audiences-clone.png)

1. Une fois le modèle cloné, vous accédez à la page [!DNL Save & Configure] du modèle cloné. Dans cette page, vous pouvez modifier le [!UICONTROL data source] et l’affecté[!UICONTROL Profile Merge Rule] du modèle. Pour modifier les rôles et l’audience cible du modèle cloné, utilisez les boutons [!UICONTROL Back] et [!UICONTROL Next] pour naviguer entre les trois onglets, ou cliquez sur les trois noms d’onglets

   ![predictive-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

1. Une fois la modification du modèle terminée, cliquez sur **[!UICONTROL Save]**.

## Suppression d’audiences prédictives {#delete-predictive-audiences}

Pour supprimer un modèle de [!UICONTROL Predictive Audiences], accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, recherchez le modèle à supprimer, puis cliquez sur l’icône **[!UICONTROL Delete]**.
