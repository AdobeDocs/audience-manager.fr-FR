---
description: Les caractéristiques de dossier vous permettent d’agréger automatiquement les caractéristiques qui se trouvent dans le même dossier et tous les dossiers enfants dans un segment pouvant être ciblé.
keywords: estimateur de taille de segment;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: À propos des caractéristiques de dossier
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# À propos des caractéristiques de dossier {#folder-traits-about}

[!UICONTROL Folder traits] vous permet d’agréger automatiquement les caractéristiques qui se trouvent dans le même dossier et tous les dossiers enfants dans un segment pouvant être ciblé.

## Avantages de l’utilisation des caractéristiques de dossier {#benefits}

Un [!UICONTROL folder trait] contient toutes les caractéristiques d’un dossier parent et de ses dossiers enfants associés. Vous pouvez ainsi segmenter et cibler automatiquement vos utilisateurs à différents niveaux de dossier. Par exemple, supposons que vous ayez une structure de dossiers comme celle-ci :

`*` Electronique (parent)

    `*` Ordinateurs portables (enfant)

        `*` Marques (petit-enfant)

[!UICONTROL Folder traits] qualifie tous les utilisateurs de ces dossiers dans un [!DNL Electronics] [!UICONTROL Folder Trait] créé automatiquement (en fonction du nom du dossier parent). Et ce processus se répète au fur et à mesure que vous descendez dans la structure du fichier. Dans ce cas, les caractéristiques de dossier capturent tous les utilisateurs dans les dossiers Ordinateurs portables et Marques dans des ordinateurs portables [!UICONTROL Folder Trait] créés automatiquement.

[!UICONTROL Folder traits] peuvent être sélectionnés dans les expressions de segment. Sélectionner un [!UICONTROL folder trait] équivaut à sélectionner toutes les caractéristiques de ce dossier et de ses sous-dossiers avec un regroupement [!UICONTROL OR].

![](assets/folder-traits-compare-border.jpg)

## Réalisation des caractéristiques de dossier - Récence et fréquence {#folder-traits-realization}

Le nombre de fréquences d’une caractéristique de dossier est la somme des réalisations des caractéristiques de son dossier et de ses dossiers enfants. L’illustration ci-dessous présente les caractéristiques A, B et C qui se trouvent dans le dossier Automobile. Considérez que chacune des caractéristiques a les réalisations suivantes :

* Caractéristique A : 5
* Caractéristique B : 1
* Caractéristique C : 1

Dans ce cas, le [!DNL Automobile Folder Trait] comporte 7 réalisations.

![](assets/folder_traits_rollup_border.png)

## Rapports sur les caractéristiques de dossier {#folder-traits-reporting}

[!UICONTROL Folder traits] capture tous les utilisateurs à partir des caractéristiques de la structure de dossiers sous eux. Si vous déplacez une caractéristique d’un dossier vers un autre dossier, la modification se propage à nos [serveurs de collecte de données](../../reference/system-components/components-data-collection.md) comme un changement de règle de caractéristique. Les mises à jour des rapports dans le prochain rapport s’exécutent pour refléter cette modification dans les plages de dates des rapports (1, 7, 14, 30, 60, 90). Les anciens nombres de rapports des jours précédents ne changeront pas.

## Autorisations des contrôles d’accès en fonction du rôle (RBAC) {#role-based-access-controls}

Pour les entreprises utilisant [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), vos utilisateurs disposant des autorisations [!UICONTROL RBAC] appropriées peuvent modifier la source de données associée à [!UICONTROL folder trait]. Un utilisateur doit appartenir à un groupe ayant l’une des caractéristiques suivantes :

* Autorisations des groupes `READ` et `WRITE` sur une source de données de caractéristiques.
* `VIEW_ALL_TRAITS` et `EDIT_ALL_TRAITS` autorisations génériques pour les sources de données de caractéristiques.

Découvrez comment attribuer des autorisations [!UICONTROL RBAC] dans notre [documentation d&#39;administration](../../features/administration/administration-overview.md#create-group).

## Limites et autres considérations {#limits}

| Élément | Description |
|---|---|
| Type de caractéristique | [!UICONTROL Onboarded traits] et [!UICONTROL algorithmic traits] contribuent au plus 1 réalisation à la fréquence de [!UICONTROL folder trait]. |
| Déplacement des caractéristiques entre les dossiers | Le déplacement d’une caractéristique d’un dossier vers un autre disqualifie cette caractéristique de la première caractéristique de dossier et la qualifie pour le second [!UICONTROL folder trait]. En d’autres termes, si vous supprimez ou déplacez une caractéristique du dossier, les utilisateurs de la population de cette caractéristique ne seront pas segmentés dans les segments à l’aide de la caractéristique du dossier comme expression de segment. <br> Lors du mappage de segments Adobe Analytics ou de suites de rapports à votre organisation Experience Cloud, l’Audience Manager crée automatiquement de nouveaux segments et caractéristiques correspondants en lecture seule. Vous ne pouvez pas modifier ni modifier l’emplacement de stockage de ces caractéristiques à partir d’Audience Manager. Toutefois, toute modification que vous effectuez sur vos segments Adobe Analytics ou suites de rapports mappés se reflète dans l’Audience Manager. |
| Variables système | [!UICONTROL Folder traits] ne peut pas être réalisé dans les appels d’événement à l’aide du paramètre `d_sid`. |
| Création de rapports   | [!UICONTROL Folder traits] sont des caractéristiques autocalculées et n’apparaissent pas dans **[!UICONTROL Overlap Reports]**. |
