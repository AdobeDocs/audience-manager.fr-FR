---
description: Créez de nouvelles caractéristiques à partir de tous les signaux, y compris ceux qui sont déjà utilisés dans les caractéristiques, et capturez les audiences futures qui seront qualifiées après la création de caractéristiques.
seo-description: Créez de nouvelles caractéristiques à partir de tous les signaux, y compris ceux qui sont déjà utilisés dans les caractéristiques, et capturez les audiences futures qui seront qualifiées après la création de caractéristiques.
seo-title: Créer des caractéristiques à partir de signaux
title: Créer des caractéristiques à partir de signaux
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Créer des caractéristiques à partir de signaux

Créez de nouvelles caractéristiques à partir de tous les signaux, y compris ceux qui sont déjà utilisés dans les caractéristiques, et capturez les audiences futures qui seront qualifiées après la création de caractéristiques. Regardez la vidéo pour une démonstration rapide ou lisez-la pour obtenir des informations détaillées :

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=fre_fr)

## Créer des caractéristiques à partir du tableau de bord Signal {#create-traits-from-signal-dashboard}

Le [!UICONTROL Signal Dashboard] permet de créer de nouvelles caractéristiques à partir des [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals]et des recherches enregistrées.

Lorsque vous créez une nouvelle caractéristique, le type de caractéristique est prédéfini en fonction du type de signal :

* **[!UICONTROL Rule-based]** caractéristiques des signaux en temps réel, des fichiers journaux exploitables et des [!DNL Adobe Analytics] signaux;

* **[!UICONTROL Onboarded]** caractéristiques des signaux embarqués.

Pour créer de nouvelles caractéristiques à partir de la **[!UICONTROL Signal Dashboard]** caractéristique, identifiez le signal que vous souhaitez utiliser dans la caractéristique, puis cliquez sur le lien correspondant **[!UICONTROL Create Rule-Based Trait]** ou **[!UICONTROL Create Onboarded Trait]** .

![](assets/signals-create-trait.png)

Vous serez redirigé vers le Créateur de **[caractéristiques](../../features/traits/about-trait-builder.md)** pour créer vos nouvelles caractéristiques.

## Créer des caractéristiques à partir de la recherche de signaux {#create-traits-from-signal-search}

Créez des caractéristiques basées sur des signaux utilisés ou inutilisés qui ne sont pas affichés dans le [!UICONTROL Signal Dashboard].

Recherchez des signaux spécifiques et créez des caractéristiques basées sur des règles ou des caractéristiques intégrées en fonction des résultats. Voici comment procéder :

1. Accédez à **[!UICONTROL Audience Data > Signals > Search]** et exécutez une recherche en fonction des paires clé-valeur recherchées, ou cliquez **[!UICONTROL Search]** sans entrer de paire clé-valeur pour afficher tous les résultats.
2. Identifiez le ou les signaux que vous souhaitez utiliser dans la caractéristique, dans la liste des résultats.
   * Pour créer une caractéristique à partir d’un signal, cliquez sur le lien correspondant **[!UICONTROL Create Rule-Based Trait]** ou **[!UICONTROL Create Onboarded Trait]** .
   * Pour créer une caractéristique à partir de plusieurs signaux, cochez la case correspondante de chaque signal, puis cliquez sur **[!UICONTROL Create Trait from Multiple Signals]**.
   >[!NOTE]
   >Vous pouvez uniquement créer des caractéristiques à partir de signaux du même type. Vous ne pouvez pas créer de caractéristique basée sur une combinaison d’un signal en temps réel et d’un signal intégré.
   >
   > ![](assets/signals-create-trait-search.png)
   >Vous pouvez également créer des caractéristiques à partir de signaux d'occasion. Le nombre de caractéristiques affichées dans la **[!UICONTROL Included in Traits]** colonne correspond aux signaux déjà utilisés dans les caractéristiques. Cliquez sur la flèche pour afficher les caractéristiques qui incluent le signal.
   >
   >![](assets/signals-used-traits.png)

3. Utilisez le Créateur de **[caractéristiques](../../features/traits/about-trait-builder.md)** pour créer vos nouvelles caractéristiques.