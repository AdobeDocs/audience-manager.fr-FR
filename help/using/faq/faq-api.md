---
description: Questions et problèmes courants liés à l’API.
seo-description: Questions et problèmes courants liés à l’API.
seo-title: FAQ sur l’API
solution: Audience Manager
title: FAQ sur l’API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---


# FAQ sur l’API{#api-faq}

Questions et problèmes courants liés à l’API.

<!-- 

faq_api.xml

 -->

La documentation de l’API [](../api/rest-api-main/rest-api-main.md) REST contient des détails sur des méthodes spécifiques et des exemples de code.

<br> 

**Pourquoi effectue-t-[!UICONTROL DIL]on des appels de événement avec[!UICONTROL GET]et[!UICONTROL POST]des méthodes ?**

[!UICONTROL DIL] transmet les données à [!DNL Audience Manager] l’aide d’une `GET` méthode ou `POST` d’une méthode basée sur la longueur de la chaîne de requête de l’appel de événement. Par défaut, ce comportement est intégré aux `GET` méthodes et `POST` aux méthodes. Il n&#39;est pas spécifique à [!DNL Audience Manager].

* [!UICONTROL DIL] effectue des appels de événement avec `GET` lorsqu’une URL contient 2 048 caractères ou moins. Un appel de `GET` événement inclut des données dans l’URL en tant que paramètres de chaîne de requête, qui sont transmis en tant que paires clé-valeur.

* [!UICONTROL DIL] effectue des appels de événement avec `POST` lorsqu’une URL contient plus de 2 048 caractères. Un appel de `POST` événement inclut des données dans le corps de la requête. [!UICONTROL DIL] place les données dans des paires clé-valeur et transmet les informations sous forme de données de formulaire plutôt que dans la chaîne de requête d’URL.

Bien que chaque méthode transmet les données d’une manière différente, cela n’affecte pas les fonctionnalités. Par exemple, avec l’une ou l’autre méthode, [!DNL Audience Manager] les données sont toujours envoyées vers les destinations, la synchronisation des identifiants fonctionne normalement et vous pouvez créer des caractéristiques à partir des signaux de données.

<br> 

**Qu&#39;est-ce que les[!UICONTROL REST API]s me permettent de faire ?**

Les [!UICONTROL REST API]s vous permettent de travailler par programmation avec la plupart des [!DNL Audience Manager] fonctions et fonctions disponibles dans l’interface utilisateur.

<br> 

**Comment puis-je obtenir un ID[!UICONTROL REST API]client et un secret ?**

Contactez votre représentant Solutions partenaires pour obtenir des informations d’ [!DNL API] accès. Nos API utilisent les normes [OAuth 2.0](https://oauth.net/2/) pour l’authentification, l’autorisation et le renouvellement des jetons. Voir [Authentification](../api/rest-api-main/aam-api-getting-started.md#oauth) OAuth pour plus d’informations.
