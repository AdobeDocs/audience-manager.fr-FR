---
description: Créez de nouvelles caractéristiques à partir de tous les signaux, y compris celles qui sont déjà utilisées dans les caractéristiques, et capturez les futures audiences qui remplissent les critères après la création d’une caractéristique.
seo-description: Créez de nouvelles caractéristiques à partir de tous les signaux, y compris celles qui sont déjà utilisées dans les caractéristiques, et capturez les futures audiences qui remplissent les critères après la création d’une caractéristique.
seo-title: Création de caractéristiques à partir de signaux
title: Création de caractéristiques à partir de signaux
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: 'Explorateur de données '
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# Création de caractéristiques à partir de signaux

Créez de nouvelles caractéristiques à partir de tous les signaux, y compris celles qui sont déjà utilisées dans les caractéristiques, et capturez les futures audiences qui remplissent les critères après la création d’une caractéristique. Regardez la vidéo pour une démonstration rapide ou lisez la vidéo pour plus d’informations :

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Créer des caractéristiques à partir du tableau de bord des signaux {#create-traits-from-signal-dashboard}

[!UICONTROL Signal Dashboard] permet de créer de nouvelles caractéristiques à partir de [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals] et de vos recherches enregistrées.

Lorsque vous créez une nouvelle caractéristique, le type de caractéristique est prédéfini en fonction du type de signal :

* **[!UICONTROL Rule-based]** caractéristiques pour les signaux en temps réel, les fichiers journaux exploitables et les  [!DNL Adobe Analytics] signaux ;

* **[!UICONTROL Onboarded]** caractéristiques pour les signaux intégrés.

Pour créer de nouvelles caractéristiques à partir de **[!UICONTROL Signal Dashboard]**, identifiez le signal que vous souhaitez utiliser dans la caractéristique, puis cliquez sur le lien **[!UICONTROL Create Rule-Based Trait]** ou **[!UICONTROL Create Onboarded Trait]** correspondant.

![](assets/signals-create-trait.png)

Vous serez redirigé vers le **[créateur de caractéristiques](../../features/traits/about-trait-builder.md)** pour créer vos caractéristiques.

## Créer des caractéristiques à partir de la recherche de signaux {#create-traits-from-signal-search}

Créez des caractéristiques basées sur des signaux utilisés ou inutilisés qui ne sont pas affichés dans la balise [!UICONTROL Signal Dashboard].

Recherchez des signaux spécifiques et créez des caractéristiques basées sur des règles ou intégrées en fonction des résultats. Procédez comme suit :

1. Accédez à **[!UICONTROL Audience Data > Signals > Search]** et exécutez une recherche en fonction des paires clé-valeur que vous recherchez, ou cliquez sur **[!UICONTROL Search]** sans saisir de paire clé-valeur pour afficher tous les résultats.
2. Identifiez le ou les signaux que vous souhaitez utiliser dans la caractéristique, dans la liste des résultats.
   * Pour créer une caractéristique à partir d’un signal, cliquez sur le lien **[!UICONTROL Create Rule-Based Trait]** ou **[!UICONTROL Create Onboarded Trait]** correspondant.
   * Pour créer une caractéristique à partir de plusieurs signaux, cochez la case correspondante de chaque signal, puis cliquez sur **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >Vous pouvez uniquement créer des caractéristiques à partir de signaux du même type. Vous ne pouvez pas créer de caractéristique basée sur une combinaison d’un signal en temps réel et d’un signal intégré.
   >
   > ![](assets/signals-create-trait-search.png)
   >Vous pouvez également créer des caractéristiques à partir de signaux utilisés. Les signaux déjà utilisés dans les caractéristiques ont le nombre de caractéristiques affichées dans la colonne **[!UICONTROL Included in Traits]**. Cliquez sur la flèche pour afficher les caractéristiques qui incluent le signal.
   >
   >![](assets/signals-used-traits.png)

3. Utilisez le **[créateur de caractéristiques](../../features/traits/about-trait-builder.md)** pour créer vos nouvelles caractéristiques.
