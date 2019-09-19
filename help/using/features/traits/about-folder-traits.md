---
description: Les caractéristiques des dossiers vous permettent d’agréger automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.
keywords: estimateur de taille de segment;sse
seo-description: Les caractéristiques des dossiers vous permettent d’agréger automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.
seo-title: Caractéristiques des dossiers
solution: Audience Manager
title: Caractéristiques des dossiers
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# Caractéristiques des dossiers : À propos de {#folder-traits-about}

[!UICONTROL Folder traits] vous permet d’agréger automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.

## Avantages de l’utilisation des caractéristiques des dossiers {#benefits}

Un [!UICONTROL folder trait] contient toutes les caractéristiques d’un dossier parent et des dossiers enfants associés. Vous pouvez ainsi segmenter et cibler automatiquement vos utilisateurs à différents niveaux de dossier. Supposons, par exemple, que vous ayez une structure de dossiers comme celle-ci :

`*` Électronique (parent)

    Ordinateurs`*` portables (enfant)

        `*` Marques (petit-enfant)

[!UICONTROL Folder traits] qualifiez tous les utilisateurs de ces dossiers dans un dossier créé automatiquement [!DNL Electronics] [!UICONTROL Folder Trait] (en fonction du nom du dossier parent). Et ce processus se répète au fur et à mesure que vous descendez dans la structure de fichiers. Dans ce cas, les caractéristiques des dossiers capturent tous les utilisateurs des dossiers Ordinateurs portables et Marques dans des ordinateurs portables créés automatiquement [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] peuvent être sélectionnées dans les expressions de segment. La sélection d’un [!UICONTROL folder trait] groupe équivaut à sélectionner toutes les caractéristiques de ce dossier et de ses sous-dossiers avec un [!UICONTROL OR] regroupement.

![](assets/folder-traits-compare-border.jpg)

## Réalisation des caractéristiques des dossiers - Récence et fréquence {#folder-traits-realization}

Le nombre de fréquences d’une caractéristique de dossier est la somme des réalisations des caractéristiques de son dossier et de ses dossiers enfants. L'illustration ci-dessous présente les caractéristiques A, B et C, qui résident dans le dossier Automobile. Tenez compte du fait que chacune des caractéristiques a les réalisations suivantes :

* Caractéristique A : 5
* Caractéristique B : 1
* Caractéristique C : 1

Dans ce cas, l' [!DNL ]Automobile [!UICONTROL Folder Trait] a 7 réalisations.

![](assets/folder_traits_rollup_border.png)

## Rapports de caractéristiques du dossier {#folder-traits-reporting}

[!UICONTROL Folder traits] capturez tous les utilisateurs à partir des caractéristiques de la structure de dossiers sous-jacente. Si vous déplacez une caractéristique d’un dossier vers un autre dossier, la modification se propage vers nos serveurs [de collecte de](../../reference/system-components/components-data-collection.md) données, tout comme une modification de règle de caractéristique. Les mises à jour des rapports dans le prochain rapport s’exécutent pour refléter cette modification dans les plages de dates des rapports (1, 7, 14, 30, 60, 90). Les anciens nombres de rapports des jours précédents ne changeront pas.

## Autorisations RBAC (Role-Based Access Controls) {#role-based-access-controls}

Pour les entreprises qui utilisent [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), les utilisateurs disposant des autorisations [!UICONTROL RBAC] appropriées peuvent modifier la source de données associée au [!UICONTROL folder trait]. Un utilisateur doit appartenir à un groupe avec l’un des éléments suivants :

* `READ` et `WRITE` regrouper les autorisations sur une source de données de caractéristiques.
* `VIEW_ALL_TRAITS` et les autorisations `EDIT_ALL_TRAITS` génériques pour les sources de données de caractéristiques.

Découvrez comment attribuer [!UICONTROL RBAC] des autorisations dans notre documentation [d’](../../features/administration/administration-overview.md#create-group)administration.

## Limites et autres considérations {#limits}

| Élément | Description |
|---|---|
| Type de trait | [!UICONTROL Onboarded traits] et [!UICONTROL algorithmic traits] contribuer au plus 1 à la réalisation de [!UICONTROL folder trait]la fréquence d'un. |
| Déplacement de caractéristiques entre des dossiers | Le déplacement d’une caractéristique d’un dossier vers un autre disqualifie cette caractéristique de la première caractéristique de dossier et la qualifie pour la seconde [!UICONTROL folder trait]. En d’autres termes, si vous supprimez ou déplacez une caractéristique du dossier, les utilisateurs de sa population ne seront pas segmentés des segments à l’aide de la caractéristique de dossier en tant qu’expression de segment. <br> Lors du mappage de segments ou de suites de rapports Adobe Analytics avec votre organisation Experience Cloud, Audience Manager crée automatiquement de nouveaux segments et caractéristiques correspondants en lecture seule. Vous ne pouvez pas modifier ni modifier l’emplacement de stockage de ces caractéristiques à partir d’Audience Manager. Toutefois, toute modification que vous apportez à vos segments ou suites de rapports Adobe Analytics mappés est répercutée dans Audience Manager. |
| Variables système | [!UICONTROL Folder traits] ne peut pas être réalisée dans les appels d’événement utilisant le `d_sid` paramètre. |
| Création de rapports   | [!UICONTROL Folder traits] sont des caractéristiques autocalculées et n’apparaissent pas dans **[!UICONTROL Overlap Reports]**. |