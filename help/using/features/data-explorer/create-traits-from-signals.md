---
description: Créez de nouvelles caractéristiques à partir de tous les signaux, y compris ceux qui sont déjà utilisés dans les caractéristiques, et capturez les audiences futures qui remplissent les critères suivants.
seo-description: Créez de nouvelles caractéristiques à partir de tous les signaux, y compris ceux qui sont déjà utilisés dans les caractéristiques, et capturez les audiences futures qui remplissent les critères suivants.
seo-title: Création de caractéristiques à partir de signaux
title: Création de caractéristiques à partir de signaux
uuid: 4 f 324404-0 c 24-4 e 3 b -96 c 1-7 c 1 b 28 a 4536 d
translation-type: tm+mt
source-git-commit: f324838a5649722545ff36faba92bf3a13c2e805

---


# Création de caractéristiques à partir de signaux

Créez de nouvelles caractéristiques à partir de tous les signaux, y compris ceux qui sont déjà utilisés dans les caractéristiques, et capturez les audiences futures qui remplissent les critères suivants. Regardez la vidéo pour une démonstration rapide ou lisez-la pour obtenir des informations détaillées :

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12&captions=fre_fr)

## Create Traits from Signal Dashboard {#create-traits-from-signal-dashboard}

The [!UICONTROL Signal Dashboard] allows you to create new traits from the [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals], and your saved searches.

Lorsque vous créez une nouvelle caractéristique, le type de caractéristique est prédéfini en fonction du type de signal :

* **[!UICONTROL Rule-based]** caractéristiques pour les signaux en temps réel, les fichiers journaux et [!DNL Adobe Analytics] les signaux exploitables ;

* **[!UICONTROL Onboarded]** caractéristiques pour les signaux intégrés.

To create new traits from the **[!UICONTROL Signal Dashboard]**, identify the signal that you want to use in the trait, then click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.

![](assets/signals-create-trait.png)

You&#39;ll be redirected to the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new trait(s).

## Create Traits from Signal Search {#create-traits-from-signal-search}

Create traits based on used or unused signals that are not shown in the [!UICONTROL Signal Dashboard].

Recherchez des signaux spécifiques et créez des caractéristiques basées sur des règles ou des règles basées sur les résultats. Voici comment procéder :

1. Go to **[!UICONTROL Audience Data > Signals > Search]** and run a search based on the key-value pairs that you are looking for, or click **[!UICONTROL Search]** without entering any key-value pair to display all results.
2. Identifiez le ou les signaux à utiliser dans la caractéristique, dans la liste des résultats.
   * To create a trait from one signal, click the corresponding **[!UICONTROL Create Rule-Based Trait]** or **[!UICONTROL Create Onboarded Trait]** link.
   * To create a trait from multiple signals, click the corresponding check box of each signal, then click **[!UICONTROL Create Trait from Multiple Signals]**.
   >[!NOTE]
   >Vous pouvez uniquement créer des caractéristiques à partir de signaux du même type. Vous ne pouvez pas créer de caractéristique basée sur une combinaison d&#39;un signal en temps réel et d&#39;un caractère intégré.
   >
   > ![](assets/signals-create-trait-search.png)
   >Vous pouvez également créer des caractéristiques à partir des signaux utilisés. Signals that are already used in traits have the number of traits displayed in the **[!UICONTROL Included in Traits]** column. Cliquez sur la flèche pour afficher les caractéristiques qui incluent le signal.
   >
   >![](assets/signals-used-traits.png)

3. Use the **[Trait Builder](../../features/traits/about-trait-builder.md)** to create your new traits.
