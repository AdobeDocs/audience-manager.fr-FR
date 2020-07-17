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

Vous [!UICONTROL Profile Merge Rules] pouvez ainsi contrôler quels jeux de données sont utilisés pour la segmentation et cible précisément les utilisateurs sur plusieurs périphériques.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Collecte et ciblage de données avec des profils anonymes et authentifiés {#data-collection-targeting}

En règle générale, la segmentation et le ciblage des audiences reposent sur les données collectées auprès de tous les utilisateurs sur un périphérique. La collecte et le ciblage des données basés sur les données au niveau du périphérique présentent certains inconvénients. Par exemple, vous ne pouvez pas faire la distinction entre plusieurs utilisateurs qui partagent un périphérique ou qui cible avec précision des utilisateurs sur plusieurs périphériques. La collecte de données centrée sur le périphérique ne suffit plus pour les campagnes de marketing numérique ou le ciblage inter-périphériques.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] modifie fondamentalement la manière de [!DNL Audience Manager] collecter des données et de segmenter les utilisateurs pour le ciblage. Il vous permet de travailler avec deux types de profils distincts, un profil de périphérique et un profil [](../../reference/visitor-authentication-states.md)authentifié.

| Type de Profil | Description |
|---|---|
| [!UICONTROL Device Profile] | Un [!UICONTROL device profile] est lié à un identifiant pour un périphérique donné, tel qu’un [!UICONTROL cookie] identifiant ou un identifiant de périphérique mobile.<br><br>Il inclut :<ul><li>[!UICONTROL Rule-based traits] réalisé lorsqu’un utilisateur n’est pas authentifié.</li><li>[!UICONTROL Onboarded traits] lié à un ID de périphérique tel que [!UICONTROL cookie-based]des données tierces.</li></ul> |
| [!UICONTROL Authenticated Profile] | Le [!UICONTROL authenticated profile] lien est lié à un ID utilisateur transmis lorsqu’une personne se connecte à votre site.<br><br>Il inclut :<ul><li>[!UICONTROL Rule-based traits] collectées sur plusieurs périphériques lorsqu’un utilisateur est authentifié.</li><li>[!UICONTROL Onboarded traits] dans un fichier hors ligne lié au même ID utilisateur.</li></ul> |

Ces différents profils contrôlent les données que vous pouvez utiliser pour la segmentation. Par exemple, avec un profil [](../../reference/visitor-authentication-states.md)authentifié, vous pouvez créer des données précises [!UICONTROL segments] basées sur des données provenant de plusieurs périphériques pour un utilisateur unique. Cela signifie que vous pouvez offrir une expérience cohérente de la marque aux clients sur plusieurs périphériques. [!DNL Audience Manager] pour ce faire, il stocke le mappage des différents périphériques qu&#39;une personne utilise pour ses activités en ligne sur son profil [](../../reference/visitor-authentication-states.md)authentifié. Ces mappages sont appelés le [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Avantages {#advantages}

Avec [!UICONTROL Profile Merge Rules] vous pouvez :

* Utilisateurs de Cible en fonction d’un profil [](../../reference/visitor-authentication-states.md)authentifié, de profils anonymes ou de combinaisons des deux.
* Cible d’un client spécifique sur l’ensemble de ses périphériques.
* Créez un graphique de périphérique basé sur des données déterministes.
* Ajustez les données dans votre fichier [!UICONTROL segments] en fonction de différents profils.
* Obtenez des informations supplémentaires sur votre audience.
