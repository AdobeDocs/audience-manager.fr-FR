---
description: Grâce aux règles de fusion de Profils, vous contrôlez les jeux de données utilisés pour la segmentation et pouvez cible une personne avec précision sur plusieurs périphériques.
seo-description: Grâce aux règles de fusion de Profils, vous contrôlez les jeux de données utilisés pour la segmentation et pouvez cible une personne avec précision sur plusieurs périphériques.
seo-title: Présentation des stratégies de fusion de profils
solution: Audience Manager
title: Présentation des stratégies de fusion de profils
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---


# [!UICONTROL Profile Merge Rules] Présentation {#profile-merge-rules-overview}

[!UICONTROL Profile Merge Rules] permet de contrôler quels jeux de données sont utilisés pour la segmentation et de cible précise des utilisateurs sur plusieurs périphériques.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Collecte et ciblage de données avec des profils anonymes et authentifiés {#data-collection-targeting}

En règle générale, la segmentation et le ciblage des audiences reposent sur les données collectées auprès de tous les utilisateurs sur un périphérique. La collecte et le ciblage des données basés sur les données au niveau du périphérique présentent certains inconvénients. Par exemple, vous ne pouvez pas faire la distinction entre plusieurs utilisateurs qui partagent un périphérique ou qui cible avec précision des utilisateurs sur plusieurs périphériques. La collecte de données centrée sur le périphérique ne suffit plus pour les campagnes de marketing numérique ou le ciblage inter-périphériques.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] modifie fondamentalement la manière dont  [!DNL Audience Manager] les données sont collectées et segmente les utilisateurs pour le ciblage. Il vous permet de travailler avec 2 types de profils distincts, un profil de périphérique et un [profil authentifié](../../reference/visitor-authentication-states.md).

| Type de profil | Description |
|---|---|
| [!UICONTROL Device Profile] | Un [!UICONTROL device profile] est lié à un ID pour un périphérique donné, tel qu&#39;un [!UICONTROL cookie] ID ou un ID de périphérique mobile.<br><br>Il inclut :<ul><li>[!UICONTROL Rule-based traits] réalisé lorsqu’un utilisateur n’est pas authentifié.</li><li>[!UICONTROL Onboarded traits] lié à un ID de périphérique tel que  [!UICONTROL cookie-based]des données tierces.</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile] est lié à un ID utilisateur transmis lorsqu’une personne se connecte à votre site.<br><br>Il inclut :<ul><li>[!UICONTROL Rule-based traits] collectées sur plusieurs périphériques lorsqu’un utilisateur est authentifié.</li><li>[!UICONTROL Onboarded traits] dans un fichier hors ligne lié au même ID utilisateur.</li></ul> |

Ces différents profils contrôlent les données que vous pouvez utiliser pour la segmentation. Par exemple, avec un [profil authentifié](../../reference/visitor-authentication-states.md), vous pouvez créer [!UICONTROL segments] précis sur la base de données provenant de plusieurs périphériques pour un utilisateur unique. Cela signifie que vous pouvez offrir une expérience cohérente de la marque aux clients sur plusieurs périphériques. [!DNL Audience Manager] pour ce faire, il stocke le mappage des différents périphériques qu&#39;une personne utilise pour ses activités en ligne sur son profil [ ](../../reference/visitor-authentication-states.md)authentifié. Ces mappages sont appelés [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Avantages {#advantages}

Avec [!UICONTROL Profile Merge Rules], vous pouvez :

* Utilisateurs de cible basés sur [profil authentifié](../../reference/visitor-authentication-states.md), profils anonymes ou combinaisons des deux.
* Cible d’un client spécifique sur l’ensemble de ses périphériques.
* Créez un graphique de périphérique basé sur des données déterministes.
* Ajustez les données de votre [!UICONTROL segments] en fonction de différents profils.
* Obtenez des informations supplémentaires sur votre audience.
