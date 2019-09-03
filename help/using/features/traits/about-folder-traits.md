---
description: Les caractéristiques de dossier vous permettent de regrouper automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.
keywords: estimateur de taille de segment ; sse
seo-description: Les caractéristiques de dossier vous permettent de regrouper automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.
seo-title: Caractéristiques du dossier à propos de
solution: Audience Manager
title: Caractéristiques du dossier à propos de
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: 263c55e6bd2c9ad7159306fc889b048d800c59da

---


# Caractéristiques du dossier : A propos de {#folder-traits-about}

[!UICONTROL Folder traits] vous permet de regrouper automatiquement des caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.

## Avantages de l'utilisation des caractéristiques de dossier {#benefits}

A [!UICONTROL folder trait] contient toutes les caractéristiques d'un dossier parent et des dossiers enfants associés. Vous pouvez ainsi segmenter et cibler automatiquement vos utilisateurs à différents niveaux de dossier. Supposons, par exemple, que vous ayez une structure de dossiers telle que :

`*` Électronique (parent)

`*` Ordinateurs portables (enfant)

`*` Marques (grand enfant)

[!UICONTROL Folder traits] qualifier tous les utilisateurs dans ces dossiers dans une création [!DNL Electronics][!UICONTROL Folder Trait] automatique (en fonction du nom du dossier parent). Ce processus se répète alors lorsque vous déplacez la structure du fichier. Dans ce cas, les caractéristiques de dossier capturent tous les utilisateurs dans les dossiers portables et portables dans des ordinateurs portables [!UICONTROL Folder Trait]créés automatiquement.

[!UICONTROL Folder traits] sont sélectionnables dans les expressions de segment. La sélection d'une [!UICONTROL folder trait] valeur équivaut à sélectionner toutes les caractéristiques de ce dossier et ses sous-dossiers avec [!UICONTROL OR] un regroupement.

![](assets/folder-traits-compare-border.jpg)

## Concrétisation des caractéristiques du dossier - Récence et fréquence {#folder-traits-realization}

Le nombre de fréquences d'une caractéristique de dossier est la somme des réexécutions des caractéristiques dans son dossier et ses dossiers enfants. L'illustration ci-dessous présente les caractéristiques A, B et C qui résident dans le dossier Automobile. Imaginons que chacune des caractéristiques comporte les réalizations suivantes :

* Caractéristique A : 5
* Caractéristique B : 1
* Caractéristique C : 1

Dans ce cas, [!DNL ]l'automobile [!UICONTROL Folder Trait] dispose de 7 réalizations.

![](assets/folder_traits_rollup_border.png)

## Rapport Caractéristiques de dossier {#folder-traits-reporting}

[!UICONTROL Folder traits] capturer tous les utilisateurs des caractéristiques de la structure de dossiers sous-jacente. Si vous déplacez une caractéristique d'un dossier vers un autre dossier, la modification se propage sur nos [serveurs de collecte de données](../../reference/system-components/components-data-collection.md) tout comme un changement de règle de caractéristique. Les mises à jour des rapports lors de l'exécution des rapports suivants sont répercutées pour refléter cette modification dans les plages de dates des rapports (1, 7, 14, 30, 60, 90). Les anciens numéros de rapport des jours précédents ne changent pas.

## Permissions RBAC (Role-Based Access Controls) {#role-based-access-controls}

Pour les entreprises qui utilisent [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), vos utilisateurs disposant des [!UICONTROL RBAC] autorisations appropriées peuvent modifier la source de données associée à [!UICONTROL folder trait]la variable. Un utilisateur doit appartenir à un groupe avec l'un des éléments suivants :

* `READ` et `WRITE` des autorisations de groupe à une source de données de caractéristiques.
* `VIEW_ALL_TRAITS` et `EDIT_ALL_TRAITS` des autorisations génériques pour les sources de données de caractéristiques.

Découvrez comment attribuer [!UICONTROL RBAC] des autorisations à notre [documentation d'administration](../../features/administration/administration-overview.md#create-group).

## Limites et autres considérations {#limits}

| Élément | Description |
|---|---|
| Type de caractéristique | [!UICONTROL Onboarded traits] et [!UICONTROL algorithmic traits] contribuer au maximum 1 à la fréquence d'une [!UICONTROL folder trait]fréquence. |
| Déplacement de caractéristiques entre les dossiers | Le déplacement d'une caractéristique d'un dossier vers un autre permet d'exclure cette caractéristique de la caractéristique de premier dossier et de la qualifier pour la seconde [!UICONTROL folder trait]. Cela signifie que si vous supprimez ou déplacez une caractéristique du dossier, les utilisateurs de la population de la caractéristique ne sont pas segmentés des segments à l'aide de la caractéristique de dossier comme expression de segment. <br> Lors du mappage des segments ou des suites de rapports Adobe Analytics à votre organisation Experience Cloud, Audience Manager crée automatiquement des segments et caractéristiques en lecture seule correspondants. Vous ne pouvez pas modifier ni modifier l'emplacement de stockage de ces caractéristiques depuis Audience Manager. Toutefois, toute modification que vous effectuez sur vos segments ou suites de rapports mappés est répercutée dans Audience Manager. |
| Variables système | [!UICONTROL Folder traits] ne peut pas être réalisé dans les appels d'événement à l'aide du `d_sid` paramètre. |
| Création de rapports   | [!UICONTROL Folder traits] sont des caractéristiques calculées automatiquement et n'apparaissent **[!UICONTROL Overlap Reports]** pas dans. |