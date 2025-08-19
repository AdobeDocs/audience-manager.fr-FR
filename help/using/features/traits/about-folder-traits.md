---
description: Les caractéristiques du dossier vous permettent d’agréger automatiquement les caractéristiques qui se trouvent dans le même dossier et tous les dossiers enfants dans un segment ciblable.
keywords: estimateur de taille de segment;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Caractéristiques du dossier Généralités
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Caractéristiques du dossier : À propos de {#folder-traits-about}

[!UICONTROL Folder traits] vous permettent d’agréger automatiquement les caractéristiques qui se trouvent dans le même dossier et tous les dossiers enfants dans un segment ciblable.

## Avantages de l’utilisation des caractéristiques de dossier {#benefits}

Une [!UICONTROL folder trait] contient toutes les caractéristiques d’un dossier parent et de ses dossiers enfants associés. Vous pouvez ainsi segmenter et cibler automatiquement vos utilisateurs à différents niveaux de dossier. Par exemple, supposons que vous ayez une structure de dossiers comme celle-ci :

`*` Electronics (parent)

    Ordinateurs portables `*` (enfant)

        `*` Brands (petit-enfant)

[!UICONTROL Folder traits] qualifier tous les utilisateurs de ces dossiers dans un [!DNL Electronics] de [!UICONTROL Folder Trait] créé automatiquement (en fonction du nom du dossier parent). Ce processus se répète à mesure que vous descendez dans la structure des fichiers. Dans ce cas, les caractéristiques du dossier capturent tous les utilisateurs dans les dossiers Ordinateurs portables et Marques dans un [!UICONTROL Folder Trait] Ordinateurs portables créé automatiquement.

Les [!UICONTROL Folder traits] peuvent être sélectionnés dans les expressions de segment. La sélection d’une [!UICONTROL folder trait] équivaut à sélectionner toutes les caractéristiques de ce dossier et de ses sous-dossiers avec un regroupement [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Réalisation des caractéristiques du dossier - Récence et fréquence {#folder-traits-realization}

Le nombre de fréquences d’une caractéristique de dossier est la somme des réalisations des caractéristiques dans son dossier et ses dossiers enfants. L’illustration ci-dessous présente les caractéristiques A, B et C, qui se trouvent dans le dossier Automobile . Tenez compte du fait que chacune des caractéristiques possède les réalisations suivantes :

* Caractéristique A : 5
* Caractéristique B : 1
* Caractéristique C : 1

Dans ce cas, le [!DNL Automobile Folder Trait] a 7 réalisations.

![](assets/folder_traits_rollup_border.png)

## Rapports sur les caractéristiques du dossier {#folder-traits-reporting}

[!UICONTROL Folder traits] capturer tous les utilisateurs à partir des caractéristiques de la structure de dossiers située sous eux. Si vous déplacez une caractéristique d’un dossier vers un autre dossier, la modification se propage à nos [ serveurs de collecte de données ](../../reference/system-components/components-data-collection.md) comme un changement de règle de caractéristique. Les mises à jour des rapports de la prochaine exécution de création de rapports reflètent cette modification sur les périodes de création de rapports (1, 7, 14, 30, 60, 90). Les anciens nombres de rapports des jours précédents ne changeront pas.

## Autorisations des contrôles d’accès basés sur les rôles {#role-based-access-controls}

Pour les sociétés qui utilisent [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), vos utilisateurs disposant des autorisations [!UICONTROL RBAC] appropriées peuvent modifier la source de données associée à la [!UICONTROL folder trait]. Un utilisateur doit appartenir à un groupe avec l’une des options suivantes :

* `READ` et `WRITE` les autorisations de groupe à une source de données de caractéristique.
* `VIEW_ALL_TRAITS` et `EDIT_ALL_TRAITS` des autorisations de caractères joker pour les sources de données des caractéristiques.

Découvrez comment attribuer des autorisations [!UICONTROL RBAC] dans notre [documentation d’administration](../../features/administration/administration-overview.md#create-group).

## Limites et autres considérations {#limits}

| Élément | Description |
|---|---|
| Type de caractéristique | [!UICONTROL Onboarded traits] et [!UICONTROL algorithmic traits] contribuent au plus 1 réalisation à la fréquence d&#39;un [!UICONTROL folder trait]. |
| Déplacement de caractéristiques entre des dossiers | Le déplacement d’une caractéristique d’un dossier à un autre disqualifie cette caractéristique du premier dossier et la qualifie pour le deuxième [!UICONTROL folder trait]. Cela signifie que si vous supprimez ou déplacez une caractéristique du dossier, les utilisateurs de la population de la caractéristique ne seront pas segmentés des segments en utilisant la caractéristique du dossier comme expression de segment. <br> Lors du mappage de segments ou de suites de rapports Adobe Analytics à votre organisation Experience Cloud, Audience Manager crée automatiquement de nouveaux segments et caractéristiques en lecture seule correspondants. Vous ne pouvez pas modifier ni changer l’emplacement de stockage de ces caractéristiques à partir d’Audience Manager. Cependant, toute modification que vous apportez à vos segments ou suites de rapports Adobe Analytics mappés est répercutée dans Audience Manager. |
| Variables système | [!UICONTROL Folder traits] ne peut pas être réalisée dans les appels d’événement à l’aide du paramètre `d_sid` . |
| Création de rapports   | [!UICONTROL Folder traits] caractéristiques sont calculées automatiquement et n’apparaissent pas dans les **[!UICONTROL Overlap Reports]**. |
