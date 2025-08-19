---
description: Décrit les étapes et les fonctionnalités de configuration propres au processus de création de caractéristiques algorithmiques.
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: Créer des caractéristiques algorithmiques
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# Créer des caractéristiques algorithmiques {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Pour créer une caractéristique algorithmique, accédez à [!UICONTROL Traits] et procédez comme suit :

1. Cliquez sur **[!UICONTROL Create New Trait]** et sélectionnez **[!UICONTROL Algorithmic]** dans le menu déroulant.
1. Dans la section [ Informations de base ](../../features/traits/create-onboarded-rule-based-traits.md)
   * Nommez la caractéristique.
   * Sélectionnez une source de données.
   * Choisissez un dossier de stockage.
1. Développez le volet [!UICONTROL Configuration] et cliquez sur **[!UICONTROL Browse All Models]**.
Une nouvelle fenêtre s’ouvre, qui vous permet de sélectionner le modèle à utiliser avec la caractéristique.
1. Sélectionnez un modèle et cliquez sur **[!UICONTROL Add Selected Model to Trait]**.
L’ajout du modèle expose les paramètres de portée et de précision.
1. Sélectionnez la portée ou la précision comme objectif et choisissez une valeur dans les menus déroulants respectifs. Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

## Paramètres de configuration des caractéristiques algorithmiques {#configure-settings}

Dans [!UICONTROL Trait Builder], la section [!UICONTROL Configuration] vous permet d’associer un modèle algorithmique à une caractéristique. Pour terminer le processus de création de caractéristiques algorithmiques, sélectionnez un modèle et choisissez un objectif de portée ou de précision.

### Conditions préalables

<!-- r_algo_trait_config_section.xml -->

* [Créer un modèle analogue](../../features/algorithmic-models/create-model.md).
* Attendez la fin de l’e-mail de notification qui vous permet de savoir que l’exécution des données du modèle est terminée.
* Renseignez les champs obligatoires de la section [Informations de base](../../features/traits/create-onboarded-rule-based-traits.md).

### Champs et paramètres de configuration

| Élément d’interface | Description |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Cliquez sur le bouton **[!UICONTROL Update]** pour ouvrir la fenêtre des modèles. Dans la fenêtre, sélectionnez le modèle algorithmique que vous souhaitez utiliser pour créer la caractéristique. |
| **[!UICONTROL Select Goal Accuracy]** | Sélectionnez cette option pour créer une caractéristique basée sur la précision. La précision est une valeur notée qui indique la proximité entre les utilisateurs potentiels et votre ligne de base. L’échelle de précision va de 0 (la moins précise) à 1 (la plus précise). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Située à droite, cette section affiche jusqu’à 21 lignes de données numériques qui affichent la précision et les valeurs d’atteinte de votre modèle. |
| **[!UICONTROL Reach and Accuracy Slider]** | Situé au bas du graphique, le curseur permet de définir une valeur numérique pour vos objectifs d’atteinte ou de précision. Vous pouvez définir le curseur, puis choisir le bouton d’objectif de portée ou de précision pour créer une caractéristique. |

>[!MORELIKETHIS]
>
>* [Précision et portée](../../features/traits/trait-accuracy-reach.md)
