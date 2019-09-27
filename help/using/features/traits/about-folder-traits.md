---
description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
keywords: segment size estimator;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Folder Traits  About
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 9fa5a558c839da89286b1abdf77e835a92747c87

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

Dans ce cas, le [!DNL Automobile Folder Trait] compte a 7 réalisations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] capturez tous les utilisateurs à partir des caractéristiques de la structure de dossiers sous-jacente. Si vous déplacez une caractéristique d’un dossier vers un autre dossier, la modification se propage vers nos serveurs [de collecte de](../../reference/system-components/components-data-collection.md) données, tout comme une modification de règle de caractéristique. Les mises à jour des rapports dans le prochain rapport s’exécutent pour refléter cette modification dans les plages de dates des rapports (1, 7, 14, 30, 60, 90). Les anciens nombres de rapports des jours précédents ne changeront pas.

## Autorisations RBAC (Role-Based Access Controls) {#role-based-access-controls}

Pour les entreprises qui utilisent [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), les utilisateurs disposant des autorisations [!UICONTROL RBAC] appropriées peuvent modifier la source de données associée au [!UICONTROL folder trait]. Un utilisateur doit appartenir à un groupe avec l’un des éléments suivants :

* `READ` and  group permissions to a trait data source.`WRITE`
* `VIEW_ALL_TRAITS` and  wild card permissions for trait data sources.`EDIT_ALL_TRAITS`

Learn how to assign  permissions in our administration documentation.[!UICONTROL RBAC][](../../features/administration/administration-overview.md#create-group)

## Limits and Other Considerations {#limits}

| Élément | Description |
|---|---|
| Trait type | [!UICONTROL Onboarded traits] and  contribute at most 1 realization to a 's frequency.[!UICONTROL algorithmic traits][!UICONTROL folder trait] |
| Moving traits between folders | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second . [!UICONTROL folder trait] This means that if you delete or move a trait from the folder, the users in the trait's population will be unsegmented from the segments using the folder trait as a segment expression. <br> Lors du mappage de segments ou de suites de rapports Adobe Analytics avec votre organisation Experience Cloud, Audience Manager crée automatiquement de nouveaux segments et caractéristiques correspondants en lecture seule. Vous ne pouvez pas modifier ni modifier l’emplacement de stockage de ces caractéristiques à partir d’Audience Manager. Toutefois, toute modification que vous apportez à vos segments ou suites de rapports Adobe Analytics mappés est répercutée dans Audience Manager. |
| Variables système | [!UICONTROL Folder traits] ne peut pas être réalisée dans les appels d’événement utilisant le `d_sid` paramètre. |
| Création de rapports   | [!UICONTROL Folder traits] sont des caractéristiques autocalculées et n’apparaissent pas dans **[!UICONTROL Overlap Reports]**. |