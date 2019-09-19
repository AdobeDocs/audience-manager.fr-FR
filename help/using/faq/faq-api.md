---
description: Questions et problèmes courants liés aux API.
seo-description: Questions et problèmes courants liés aux API.
seo-title: FAQ sur l’API
solution: Audience Manager
title: FAQ sur l’API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# FAQ sur l’API{#api-faq}

Questions et problèmes courants liés aux API.

<!-- 

faq_api.xml

 -->

La documentation de l’API [](../api/rest-api-main/rest-api-main.md) REST contient des détails sur des méthodes spécifiques et des exemples de code.

<br> 

**Pourquoi[!UICONTROL DIL]appelle-t-on des événements avec[!UICONTROL GET]et[!UICONTROL POST]des méthodes ?**

[!UICONTROL DIL] transmet les données à [!DNL Audience Manager] l’aide d’une `GET` ou d’une méthode `POST` en fonction de la longueur de la chaîne de requête de l’appel d’événement. Ce comportement est intégré par défaut aux méthodes `GET` et `POST` aux méthodes. Il n'est pas spécifique à [!DNL Audience Manager].

* [!UICONTROL DIL] effectue des appels d’événement avec `GET` lorsqu’une URL contient 2 048 caractères ou moins. Un appel `GET` d’événement inclut des données dans l’URL sous forme de paramètres de chaîne de requête, qui sont transmis sous forme de paires clé-valeur.

* [!UICONTROL DIL] effectue des appels d’événement avec `POST` lorsqu’une URL contient plus de 2 048 caractères. Un appel `POST` d’événement inclut des données dans le corps de la requête. [!UICONTROL DIL] place les données dans des paires clé-valeur et transmet les informations sous forme de données de formulaire plutôt que dans la chaîne de requête d’URL.

Bien que chaque méthode transmet les données d’une manière différente, cela n’affecte pas la fonctionnalité. Par exemple, avec l’une ou l’autre méthode, envoie toujours [!DNL Audience Manager] des données vers des destinations, la synchronisation des identifiants fonctionne normalement et vous pouvez créer des caractéristiques à partir de signaux de données.

<br> 

**Qu'est-ce que[!UICONTROL REST API]nous me permettons de faire ?**

Les [!UICONTROL REST API]s vous permettent de travailler par programmation avec la plupart des [!DNL Audience Manager] fonctionnalités et fonctions disponibles dans l’interface utilisateur.

<br> 

**Comment obtenir un ID[!UICONTROL REST API]client et un secret ?**

Contactez votre représentant Solutions partenaires pour obtenir des informations d’identification d’ [!DNL API] accès. Nos API utilisent les normes [OAuth 2.0](https://oauth.net/2/) pour l’authentification, l’autorisation et le renouvellement des jetons. Voir [Authentification](../api/rest-api-main/aam-api-getting-started.md#oauth) OAuth pour plus d’informations.
