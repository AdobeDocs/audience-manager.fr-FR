---
description: Les règles de fusion de profil vous permettent de contrôler les jeux de données utilisés pour la segmentation et de cibler une personne avec précision sur plusieurs appareils.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: Présentation des règles de fusion de profil
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# Présentation de [!UICONTROL Profile Merge Rules] {#profile-merge-rules-overview}

Avec [!UICONTROL Profile Merge Rules], vous pouvez contrôler les jeux de données utilisés pour la segmentation et cibler les utilisateurs avec précision sur plusieurs appareils.

>[!VIDEO](https://video.tv.adobe.com/v/32184?captions=fre_fr)

## Collecte de données et ciblage avec des profils anonymes et authentifiés {#data-collection-targeting}

En règle générale, la segmentation et le ciblage des audiences reposent sur les données collectées auprès de tous les utilisateurs d’un appareil. La collecte et le ciblage de données basés sur les données au niveau de l’appareil présentent certains inconvénients. Par exemple, vous ne pouvez pas faire la distinction entre plusieurs utilisateurs qui partagent un appareil ou ciblent précisément les utilisateurs sur plusieurs appareils. La collecte de données centrée sur l’appareil ne suffit plus pour les campagnes marketing numériques ou le ciblage sur plusieurs appareils.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] modifie fondamentalement la manière dont [!DNL Audience Manager] collecte les données et segmente les utilisateurs pour le ciblage. Il vous permet de travailler avec 2 types de profils distincts, un profil d’appareil et un [ profil authentifié ](../../reference/visitor-authentication-states.md).

| Type de profil | Description |
|---|---|
| [!UICONTROL Device Profile] | Un [!UICONTROL device profile] est lié à un ID pour un appareil donné, tel qu’un ID de [!UICONTROL cookie] ou un ID d’appareil mobile.<br><br> Il comprend :<ul><li>[!UICONTROL Rule-based traits] réalisé lorsqu’un utilisateur n’est pas authentifié.</li><li>[!UICONTROL Onboarded traits] liées à un ID d’appareil tel que des [!UICONTROL cookie-based], des données tierces.</li></ul> |
| [!UICONTROL Authenticated Profile] | Le [!UICONTROL authenticated profile] est lié à un ID utilisateur transmis lorsqu’une personne se connecte à votre site.<br><br>Il comprend :<ul><li>[!UICONTROL Rule-based traits] collectées sur plusieurs appareils lorsqu’un utilisateur est authentifié.</li><li>[!UICONTROL Onboarded traits] dans un fichier hors ligne lié au même identifiant utilisateur.</li></ul> |

Ces différents profils contrôlent les données que vous pouvez utiliser pour la segmentation. Par exemple, avec un [profil authentifié](../../reference/visitor-authentication-states.md), vous pouvez créer des [!UICONTROL segments] précis basés sur des données provenant de plusieurs appareils pour un seul utilisateur. Cela signifie que vous pouvez offrir une expérience de marque cohérente aux clients sur plusieurs appareils. [!DNL Audience Manager] y parvient en stockant le mappage des différents appareils qu’une personne utilise pour ses activités en ligne sur son [ profil authentifié ](../../reference/visitor-authentication-states.md). Ces mappages sont appelés [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Avantages {#advantages}

Avec [!UICONTROL Profile Merge Rules], vous pouvez :

* Ciblez les utilisateurs en fonction du [profil authentifié](../../reference/visitor-authentication-states.md), des profils anonymes ou des combinaisons des deux.
* Cibler un client spécifique sur tous ses appareils.
* Créez un graphique d’appareil basé sur des données déterministes.
* Ajustez les données de votre [!UICONTROL segments] en fonction de différents profils.
* Obtenez des insight supplémentaires dans votre audience.
