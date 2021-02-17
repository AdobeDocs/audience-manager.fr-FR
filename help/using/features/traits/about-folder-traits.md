---
description: Les caractéristiques des dossiers vous permettent d’agrégat automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.
keywords: estimateur de taille de segment ; sse
seo-description: Les caractéristiques des dossiers vous permettent d’agrégat automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.
seo-title: Caractéristiques du dossier
solution: Audience Manager
title: Caractéristiques du dossier
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 1%

---


# À propos des caractéristiques de dossier {#folder-traits-about}

[!UICONTROL Folder traits] vous permet d’agrégat automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.

## Avantages de l&#39;utilisation de caractéristiques de dossier {#benefits}

Un [!UICONTROL folder trait] contient toutes les caractéristiques d&#39;un dossier parent et de ses dossiers enfants associés. Vous pouvez ainsi segmenter et cible automatiquement vos utilisateurs à différents niveaux de dossiers. Par exemple, supposons que vous ayez une structure de dossiers telle que celle-ci :

`*` Électronique (parent)

    Portables `*` (enfant)

        `*` Marques (petit-enfant)

[!UICONTROL Folder traits] qualifiez tous les utilisateurs de ces dossiers dans un dossier créé automatiquement  [!DNL Electronics] [!UICONTROL Folder Trait] (en fonction du nom du dossier parent). Et ce processus se répète au fur et à mesure que vous descendez dans la structure de fichiers. Dans ce cas, les caractéristiques de dossier capturent tous les utilisateurs des dossiers Portables et Marques dans des ordinateurs portables créés automatiquement [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sont sélectionnables dans les expressions de segments. La sélection d&#39;un [!UICONTROL folder trait] équivaut à sélectionner toutes les caractéristiques de ce dossier et de ses sous-dossiers avec un regroupement [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Réalisation des caractéristiques des dossiers - Récence et fréquence {#folder-traits-realization}

Le nombre de fréquence d’une caractéristique de dossier est la somme des réalisations des caractéristiques de son dossier et de ses dossiers enfants. L’illustration ci-dessous présente les caractéristiques A, B et C qui résident dans le dossier Automobile. Tenez compte du fait que chacune des caractéristiques a les réalisations suivantes :

* Caractéristique A : 5
* Caractéristique B : 1
* Caractéristique C : 3

Dans ce cas, [!DNL Automobile Folder Trait] comporte 7 réalisations.

![](assets/folder_traits_rollup_border.png)

## Rapports de caractéristiques du dossier {#folder-traits-reporting}

[!UICONTROL Folder traits] capturez tous les utilisateurs à partir des caractéristiques de la structure de dossiers sous eux. Si vous déplacez une caractéristique d’un dossier vers un autre dossier, la modification se propage à nos [serveurs de collecte de données](../../reference/system-components/components-data-collection.md), tout comme un changement de règle de caractéristique. Le rapports est mis à jour au cours de la prochaine rapports exécution pour refléter cette modification dans les plages de dates du rapports (1, 7, 14, 30, 60, 90). Les anciens numéros de rapports des jours précédents ne changeront pas.

## Autorisations des Contrôles d&#39;accès basés sur le rôle {#role-based-access-controls}

Pour les sociétés qui utilisent [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), les utilisateurs disposant des autorisations [!UICONTROL RBAC] appropriées peuvent modifier la source de données associée à [!UICONTROL folder trait]. Un utilisateur doit appartenir à un groupe avec l’un des éléments suivants :

* `READ` et les autorisations de  `WRITE` groupe sur une source de données de caractéristiques.
* `VIEW_ALL_TRAITS` et les autorisations  `EDIT_ALL_TRAITS` génériques pour les sources de données de caractéristiques.

Découvrez comment attribuer des autorisations [!UICONTROL RBAC] dans notre [documentation d&#39;administration](../../features/administration/administration-overview.md#create-group).

## Limites et autres considérations {#limits}

| Élément | Description |
|---|---|
| Type de caractéristique | [!UICONTROL Onboarded traits] et  [!UICONTROL algorithmic traits] contribuer au plus 1 à la réalisation de la fréquence  [!UICONTROL folder trait]d&#39;un. |
| Déplacement de caractéristiques entre des dossiers | Le déplacement d’une caractéristique d’un dossier vers un autre disqualifie cette caractéristique de la première caractéristique de dossier et la qualifie pour la seconde [!UICONTROL folder trait]. En d’autres termes, si vous supprimez ou déplacez une caractéristique du dossier, les utilisateurs de sa population ne seront pas segmentés par rapport aux segments en utilisant la caractéristique de dossier comme expression de segment. <br> Lors du mappage de segments Adobe Analytics ou de suites de rapports avec votre organisation Experience Cloud, l’Audience Manager crée automatiquement de nouveaux segments et caractéristiques correspondants en lecture seule. Vous ne pouvez pas modifier ou modifier l&#39;emplacement d&#39;enregistrement de ces caractéristiques à partir de l&#39;Audience Manager. Toutefois, toute modification que vous apportez à vos segments Adobe Analytics ou suites de rapports mappés est répercutée dans l’Audience Manager. |
| Variables système | [!UICONTROL Folder traits] ne peut pas être réalisé dans les appels de événement utilisant le  `d_sid` paramètre. |
| Création de rapports | [!UICONTROL Folder traits] sont des caractéristiques autocalculées et n’apparaissent pas dans  **[!UICONTROL Overlap Reports]**. |