---
description: Décrit les étapes et les fonctionnalités de configuration propres au processus de création de caractéristiques algorithmiques.
seo-description: Décrit les étapes et les fonctionnalités de configuration propres au processus de création de caractéristiques algorithmiques.
seo-title: Création de caractéristiques algorithmiques
solution: Audience Manager
title: Création de caractéristiques algorithmiques
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 5%

---


# Création de caractéristiques algorithmiques {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Pour créer une caractéristique algorithmique, accédez à [!UICONTROL Traits] et procédez comme suit :

1. Cliquez sur **[!UICONTROL Create New Trait]** puis sélectionnez **[!UICONTROL Algorithmic]** dans le menu déroulant.
1. Dans la section Informations [](../../features/traits/create-onboarded-rule-based-traits.md) de base
   * Nommez la caractéristique.
   * Sélectionnez une source de données.
   * Sélectionnez un dossier d’enregistrement.
1. Développez le [!UICONTROL Configuration] volet et cliquez sur **[!UICONTROL Browse All Models]**.
Une nouvelle fenêtre s’ouvre, vous permettant de sélectionner le modèle à utiliser avec la caractéristique.
1. Sélectionnez un modèle, puis cliquez sur **[!UICONTROL Add Selected Model to Trait]**.
Ajouter le modèle expose les paramètres de portée et de précision.
1. Sélectionnez la portée ou la précision de votre objectif et choisissez une valeur dans les menus déroulants respectifs. Cliquez **[!UICONTROL Save]** une fois terminé.

## Paramètres de configuration pour les caractéristiques algorithmiques {#configure-settings}

Dans [!UICONTROL Trait Builder]la section [!UICONTROL Configuration] , vous pouvez associer un modèle algorithmique à une caractéristique. Pour terminer le processus de création de caractéristiques algorithmiques, sélectionnez un modèle et choisissez un objectif de portée ou de précision.

### Conditions préalables

<!-- r_algo_trait_config_section.xml -->

* [Création d’un modèle analogue](../../features/algorithmic-models/create-model.md).
* Attendez que le courrier électronique de notification vous permette de savoir que l&#39;exécution des données du modèle est terminée.
* Renseignez les champs obligatoires de la section Informations [](../../features/traits/create-onboarded-rule-based-traits.md) de base.

### Champs et paramètres de configuration

| Elément Interface | Description |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Cliquez sur le **[!UICONTROL Update]** bouton pour ouvrir la fenêtre des modèles. Dans la fenêtre, sélectionnez le modèle algorithmique à utiliser pour créer la caractéristique. |
| **[!UICONTROL Select Goal Accuracy]** | Sélectionnez cette option pour créer une caractéristique basée sur la précision. La précision est une valeur notée qui indique à quel point les utilisateurs potentiels sont proches de votre ligne de base. L&#39;échelle de précision est comprise entre 0 (la moins précise) et 1 (la plus précise). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Située à droite, cette section affiche jusqu’à 21 lignes de données numériques qui affichent la précision et les valeurs de portée de votre modèle. |
| **[!UICONTROL Reach and Accuracy Slider]** | Situé au bas du graphique, le curseur vous permet de définir une valeur numérique pour vos objectifs de portée ou de précision. Vous pouvez définir le curseur, puis choisir le bouton d’objectif de portée ou de précision pour créer une caractéristique. |

>[!MORELIKETHIS]
>
>* [Précision et portée](../../features/traits/trait-accuracy-reach.md)

