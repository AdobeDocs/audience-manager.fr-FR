---
description: Décrit les étapes de configuration et les fonctionnalités propres au processus de création de caractéristiques algorithmiques.
seo-description: Décrit les étapes de configuration et les fonctionnalités propres au processus de création de caractéristiques algorithmiques.
seo-title: Créer des caractéristiques algorithmiques
solution: Audience Manager
title: Créer des caractéristiques algorithmiques
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Créer des caractéristiques algorithmiques {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Pour créer une caractéristique algorithmique, suivez [!UICONTROL Traits] les étapes ci-dessous :

1. Cliquez sur **[!UICONTROL Create New Trait]** puis sélectionnez **[!UICONTROL Algorithmic]** dans le menu déroulant.
1. Dans la section Informations [](../../features/traits/create-onboarded-rule-based-traits.md) de base
   * Nommez la caractéristique.
   * Sélectionnez une source de données.
   * Choisissez un dossier de stockage.
1. Développez le [!UICONTROL Configuration] volet et cliquez sur **[!UICONTROL Browse All Models]**.
Une nouvelle fenêtre s’ouvre, vous permettant de sélectionner le modèle à utiliser avec la caractéristique.
1. Sélectionnez un modèle et cliquez sur **[!UICONTROL Add Selected Model to Trait]**.
L’ajout du modèle expose les paramètres de portée et de précision.
1. Sélectionnez portée ou précision comme objectif et choisissez une valeur dans les menus déroulants respectifs. Click **[!UICONTROL Save]** when done.

>[!MORE_LIKE_This]
>
>* [Précision et portée](../../features/traits/trait-accuracy-reach.md)


## Paramètres de configuration pour les caractéristiques algorithmiques {#configure-settings}

Dans [!UICONTROL Trait Builder]la section [!UICONTROL Configuration] , vous pouvez associer un modèle algorithmique à une caractéristique. Pour terminer le processus de création de caractéristiques algorithmiques, sélectionnez un modèle et choisissez un objectif de portée ou de précision.

### Conditions préalables

<!-- r_algo_trait_config_section.xml -->

* [Créez un modèle](../../features/algorithmic-models/create-model.md#build-model)algorithmique.
* Attendez le courrier électronique de notification qui vous permet de savoir que l’exécution des données du modèle est terminée.
* Renseignez les champs obligatoires de la section Informations [](../../features/traits/create-onboarded-rule-based-traits.md) de base.

### Champs et paramètres de configuration

| Elément Interface | Description |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Cliquez sur le **[!UICONTROL Update]** bouton pour ouvrir la fenêtre des modèles. Dans la fenêtre, sélectionnez le modèle algorithmique à utiliser pour créer la caractéristique. |
| **[!UICONTROL Select Goal Accuracy]** | Sélectionnez cette option pour créer une caractéristique basée sur la précision. La précision est une valeur notée qui indique à quel point les utilisateurs potentiels sont proches de votre ligne de base. L’échelle de précision est comprise entre 0 (la moins précise) et 1 (la plus précise). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Située à droite, cette section affiche jusqu’à 21 lignes de données numériques qui affichent la précision et les valeurs de portée de votre modèle. |
| **[!UICONTROL Reach and Accuracy Slider]** | Situé au bas du graphique, le curseur vous permet de définir une valeur numérique pour vos objectifs de portée ou de précision. Vous pouvez définir le curseur, puis choisir le bouton d’objectif de portée ou de précision pour créer une caractéristique. |

>[!MORE_LIKE_This]
>
>* [Précision et portée](../../features/traits/trait-accuracy-reach.md)