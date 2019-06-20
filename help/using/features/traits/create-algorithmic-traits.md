---
description: Décrit les étapes de configuration et les fonctionnalités propres au processus de création de caractéristiques algorithmiques.
seo-description: Décrit les étapes de configuration et les fonctionnalités propres au processus de création de caractéristiques algorithmiques.
seo-title: Création de caractéristiques algorithmiques
solution: Audience Manager
title: Création de caractéristiques algorithmiques
uuid: 50 c 2 d 2 d 1-f 412-479 b-bb 70-4 f 139429 c 388
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create Algorithmic Traits {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

To create an algorithmic trait, go to [!UICONTROL Traits] and follow the steps below:

1. Click **[!UICONTROL Create New Trait]** and select **[!UICONTROL Algorithmic]** from the drop down menu.
1. In the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section
   * Nommez la caractéristique.
   * Sélectionnez une source de données.
   * Choisissez un dossier de stockage.
1. Expand the [!UICONTROL Configuration] pane and click **[!UICONTROL Browse All Models]**.
Cette fenêtre ouvre une nouvelle fenêtre qui vous permet de sélectionner le modèle à utiliser avec la caractéristique.
1. Select a model and click **[!UICONTROL Add Selected Model to Trait]**.
L&#39;ajout du modèle expose les paramètres de portée et de précision.
1. Sélectionnez la portée ou la précision comme objectif et choisissez une valeur dans les menus déroulants respectifs. Click **[!UICONTROL Save]** when done.

>[!MORE_ LIKE_ THIS]
>
>* [Précision et portée](../../features/traits/trait-accuracy-reach.md)


## Configuration Settings for Algorithmic Traits {#configure-settings}

In [!UICONTROL Trait Builder], the [!UICONTROL Configuration] section lets you associate an algorithmic model to a trait. Pour terminer le processus de création de caractéristiques algorithmiques, sélectionnez un modèle et choisissez un objectif de portée ou de précision.

### Conditions préalables

<!-- r_algo_trait_config_section.xml -->

* [Créez un modèle algorithmique](../../features/algorithmic-models/create-model.md#build-model).
* Attendez le courrier électronique de notification qui vous informe que l&#39;exécution des données du modèle est terminée.
* Complete the required fields in the [Basic Information](../../features/traits/create-onboarded-rule-based-traits.md) section.

### Champs et paramètres de configuration

| Elément de l&#39;interface | Description |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Click the **[!UICONTROL Update]** button to open the models window. Dans la fenêtre, sélectionnez le modèle algorithmique à utiliser pour créer la caractéristique. |
| **[!UICONTROL Select Goal Accuracy]** | Sélectionnez cette option pour créer une caractéristique basée sur la précision. Exactitude est une valeur notée qui indique la proximité des utilisateurs potentiels avec votre ligne de base. L&#39;échelle de précision est comprise entre 0 (moins précis) et 1 (la plus précise). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Situé à droite, cette section affiche jusqu&#39;à 21 lignes de données numériques qui affichent la précision et les valeurs de portée de votre modèle. |
| **[!UICONTROL Reach and Accuracy Slider]** | Situé au bas du graphique, le curseur vous permet de définir une valeur numérique pour vos objectifs de portée ou de précision. Vous pouvez définir le curseur, puis choisir le bouton d&#39;objectif de portée ou de précision pour créer une caractéristique. |

>[!MORE_ LIKE_ THIS]
>
>* [Précision et portée](../../features/traits/trait-accuracy-reach.md)