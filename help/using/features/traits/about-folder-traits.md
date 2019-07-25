---
description: Les caractéristiques de dossier vous permettent de regrouper automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.
keywords: estimateur de taille de segment ; sse
seo-description: Les caractéristiques de dossier vous permettent de regrouper automatiquement les caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.
seo-title: Caractéristiques du dossier à propos de
solution: Audience Manager
title: Caractéristiques du dossier à propos de
uuid: e 561 ce 8 f -6 c 90-44 a 7-b 034-685533 f 29030
translation-type: tm+mt
source-git-commit: c229bf71da5b07277811219cbf2794c3ca7bc89d

---


# Folder Traits: About {#folder-traits-about}

[!UICONTROL Folder traits] vous permet de regrouper automatiquement des caractéristiques qui résident dans le même dossier et tous les dossiers enfants dans un segment cible.

## Benefits of Using Folder Traits {#benefits}

A [!UICONTROL folder trait] contains all the traits in a parent folder and its associated child folders. Vous pouvez ainsi segmenter et cibler automatiquement vos utilisateurs à différents niveaux de dossier. Supposons, par exemple, que vous ayez une structure de dossiers telle que :

`*` Électronique (parent)

`*` Ordinateurs portables (enfant)

`*` Marques (grand enfant)

[!UICONTROL Folder traits] qualifier tous les utilisateurs dans ces dossiers dans une création [!DNL Electronics][!UICONTROL Folder Trait] automatique (en fonction du nom du dossier parent). Ce processus se répète alors lorsque vous déplacez la structure du fichier. In this case, folder traits capture all of the users in the Laptops and Brands folders in an automatically created Laptops [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] sont sélectionnables dans les expressions de segment. Selecting a [!UICONTROL folder trait] is equivalent to selecting all the traits within that folder and its subfolders with an [!UICONTROL OR] grouping.

![](assets/folder-traits-compare-border.jpg)

## Folder Traits Realization - Recency and Frequency {#folder-traits-realization}

Le nombre de fréquences d'une caractéristique de dossier est la somme des réexécutions des caractéristiques dans son dossier et ses dossiers enfants. L'illustration ci-dessous présente les caractéristiques A, B et C qui résident dans le dossier Automobile. Imaginons que chacune des caractéristiques comporte les réalizations suivantes :

* Caractéristique A : 5
* Caractéristique B : 1
* Caractéristique C : 1

In this case, the [!DNL ]Automobile [!UICONTROL Folder Trait] has 7 realizations.

![](assets/folder_traits_rollup_border.png)

## Folder Trait Reporting {#folder-traits-reporting}

[!UICONTROL Folder traits] capturer tous les utilisateurs des caractéristiques de la structure de dossiers sous-jacente. If you move a trait from a folder to another folder, the change propagates to our [data collection servers](../../reference/system-components/components-data-collection.md) just like a trait rule change. Les mises à jour des rapports lors de l'exécution des rapports suivants sont répercutées pour refléter cette modification dans les plages de dates des rapports (1, 7, 14, 30, 60, 90, durée de vie). Les anciens numéros de rapport des jours précédents ne changent pas.

## Role-Based Access Controls (RBAC) Permissions {#role-based-access-controls}

For companies using [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), your users with the appropriate [!UICONTROL RBAC] permissions are able to change the data source associated to the [!UICONTROL folder trait]. Un utilisateur doit appartenir à un groupe avec l'un des éléments suivants :

* `READ` et `WRITE` des autorisations de groupe à une source de données de caractéristiques.
* `VIEW_ALL_TRAITS` et `EDIT_ALL_TRAITS` des autorisations génériques pour les sources de données de caractéristiques.

Learn how to assign [!UICONTROL RBAC] permissions in our [administration documentation](../../features/administration/administration-overview.md#create-group).

## Limits and Other Considerations {#limits}

| Élément | Description |
|---|---|
| Type de caractéristique | [!UICONTROL Onboarded traits] et [!UICONTROL algorithmic traits] contribuer au maximum 1 à la fréquence d'une [!UICONTROL folder trait]fréquence. |
| Déplacement de caractéristiques entre les dossiers | Moving a trait from a folder to another will disqualify that trait from the first folder trait and qualify it for the second [!UICONTROL folder trait]. Cela signifie que si vous supprimez ou déplacez une caractéristique du dossier, les utilisateurs de la population de la caractéristique ne sont pas segmentés des segments à l'aide de la caractéristique de dossier comme expression de segment. <br> Lors du mappage des segments ou des suites de rapports Adobe Analytics à votre organisation Experience Cloud, Audience Manager crée automatiquement des segments et caractéristiques en lecture seule correspondants. Vous ne pouvez pas modifier ni modifier l'emplacement de stockage de ces caractéristiques depuis Audience Manager. Toutefois, toute modification que vous effectuez sur vos segments ou suites de rapports mappés est répercutée dans Audience Manager. |
| Variables système | [!UICONTROL Folder traits] ne peut pas être réalisé dans les appels d'événement à l'aide du `d_sid` paramètre. |
| Création de rapports   | [!UICONTROL Folder traits] sont des caractéristiques calculées automatiquement et n'apparaissent **[!UICONTROL Overlap Reports]** pas dans. |