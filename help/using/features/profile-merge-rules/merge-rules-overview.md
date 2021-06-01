---
description: Grâce aux règles de fusion de profils, vous contrôlez les jeux de données utilisés pour la segmentation et pouvez cibler une personne avec précision sur plusieurs périphériques.
seo-description: Grâce aux règles de fusion de profils, vous contrôlez les jeux de données utilisés pour la segmentation et pouvez cibler une personne avec précision sur plusieurs périphériques.
seo-title: Présentation des stratégies de fusion de profils
solution: Audience Manager
title: Présentation des stratégies de fusion de profils
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Fusion des profils
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 4%

---

# [!UICONTROL Profile Merge Rules] Présentation {#profile-merge-rules-overview}

Avec [!UICONTROL Profile Merge Rules], vous pouvez contrôler quels jeux de données sont utilisés pour la segmentation et cibler précisément les utilisateurs sur plusieurs appareils.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Collecte de données et ciblage avec profils anonymes et authentifiés {#data-collection-targeting}

En règle générale, la segmentation et le ciblage de l’audience reposent sur les données collectées par tous les utilisateurs sur un appareil. La collecte et le ciblage des données en fonction des données au niveau de l’appareil présentent certains inconvénients. Par exemple, vous ne pouvez pas distinguer plusieurs utilisateurs qui partagent un appareil ou ciblent précisément des utilisateurs sur plusieurs appareils. La collecte de données centrée sur les appareils ne suffit plus pour les campagnes marketing numériques ou le ciblage entre appareils.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] modifie fondamentalement la manière dont  [!DNL Audience Manager] collecte des données et segmente les utilisateurs pour le ciblage. Il vous permet de travailler avec 2 types de profils distincts, un profil d’appareil et un [profil authentifié](../../reference/visitor-authentication-states.md).

| Type de profil | Description |
|---|---|
| [!UICONTROL Device Profile] | Un [!UICONTROL device profile] est lié à un ID pour un appareil donné, tel qu’un [!UICONTROL cookie] ID ou un ID d’appareil mobile.<br><br>Il inclut :<ul><li>[!UICONTROL Rule-based traits] réalisée lorsqu’un utilisateur n’est pas authentifié.</li><li>[!UICONTROL Onboarded traits] liés à un identifiant d’appareil tel que  [!UICONTROL cookie-based], des données tierces.</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile] est lié à un ID utilisateur transmis lorsqu’une personne se connecte à votre site.<br><br>Il inclut :<ul><li>[!UICONTROL Rule-based traits] collectés sur plusieurs appareils lorsqu’un utilisateur est authentifié.</li><li>[!UICONTROL Onboarded traits] dans un fichier hors ligne lié au même ID utilisateur.</li></ul> |

Ces différents profils contrôlent les données que vous pouvez utiliser pour la segmentation. Par exemple, avec un [profil authentifié](../../reference/visitor-authentication-states.md), vous pouvez créer une [!UICONTROL segments] précise en fonction des données provenant de plusieurs périphériques pour un seul utilisateur. Cela signifie que vous pouvez offrir une expérience de marque cohérente aux clients sur plusieurs appareils. [!DNL Audience Manager] pour ce faire, stockez le mappage des différents appareils qu’une personne utilise pour ses activités en ligne sur son profil [ ](../../reference/visitor-authentication-states.md)authentifié. Ces mappages sont appelés [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Avantages {#advantages}

Avec [!UICONTROL Profile Merge Rules] vous pouvez :

* Ciblez les utilisateurs en fonction du [profil authentifié](../../reference/visitor-authentication-states.md), des profils anonymes ou des combinaisons des deux.
* Ciblez un client spécifique sur l’ensemble de ses appareils.
* Créez une représentation graphique des appareils basée sur des données déterministes.
* Ajustez les données de votre [!UICONTROL segments] en fonction de différents profils.
* Obtenez des informations supplémentaires sur votre audience.
