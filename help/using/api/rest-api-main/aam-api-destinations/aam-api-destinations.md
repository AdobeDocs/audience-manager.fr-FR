---
description: Méthodes qui vous permettent de travailler par programmation avec les fonctionnalités de destination.
seo-description: Méthodes qui vous permettent de travailler par programmation avec les fonctionnalités de destination.
seo-title: Méthodes de l’API de destination
solution: Audience Manager
title: Méthodes de l’API de destination
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Méthodes de l’API de destination {#destination-api-methods}

Méthodes qui vous permettent de travailler par programmation avec les fonctionnalités de destination.

<!-- c_destinations_api.xml -->

Dans Audience Manager, une destination correspond à tout autre système (serveur publicitaire, [!DNL DSP]réseau publicitaire, échange, cookie propriétaire, etc.). que vous souhaitez partager avec.

## Types de destination : URL et cookie {#destination-types}

Répertorie les variables utilisées par le `destinationType` paramètre. Spécifiez `push` ou `ADS` pour travailler avec un [!UICONTROL URL] ou [!UICONTROL cookie destination]. Vous ne pouvez pas créer [!UICONTROL server-to-server destinations] avec les [!DNL API] méthodes de destination disponibles.

<!-- r_destination_types.xml -->

| Type de destination de l'API | Type de destination de l’interface utilisateur |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Comment choisir un type de destination](../../../features/destinations/destinations.md)

