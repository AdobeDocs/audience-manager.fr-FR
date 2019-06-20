---
description: Questions et problèmes courants sur l'API.
seo-description: Questions et problèmes courants sur l'API.
seo-title: FAQ sur l'API
solution: Audience Manager
title: FAQ sur l'API
uuid: 8222 ebf 0-b 50 e -4 f 48-8021-dbfca 2828 b 7 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API FAQ{#api-faq}

Questions et problèmes courants sur l&#39;API.

<!-- 

faq_api.xml

 -->

The [REST API](../api/rest-api-main/rest-api-main.md) documentation contains details about specific methods and code samples.

<br> 

**Pourquoi[!UICONTROL DIL]les appels d&#39;événement et[!UICONTROL GET][!UICONTROL POST]les méthodes sont-ils effectués ?**

[!UICONTROL DIL] transmet les données [!DNL Audience Manager] à une `GET``POST` ou à plusieurs méthodes en fonction de la longueur de la chaîne de requête de l&#39;appel d&#39;événement. This behavior is built in to `GET` and `POST` methods by default. It is not specific to [!DNL Audience Manager].

* [!UICONTROL DIL] effectue des appels d&#39;événement avec `GET` lorsqu&#39;une URL contient 2 048 caractères ou moins. A `GET` event call includes data in the URL as query string parameters, which are passed in as key-value pairs.

* [!UICONTROL DIL] effectue des appels d&#39;événement avec `POST` lorsqu&#39;une URL contient plus de 2 048 caractères. A `POST` event call includes data in the body of the request. [!UICONTROL DIL] place les données dans des paires clé-valeur et transmet les informations sous forme de données de formulaire plutôt que dans la chaîne de requête d&#39;URL.

Bien que chaque méthode transmette les données d&#39;une manière différente, cela n&#39;a aucune incidence sur les fonctionnalités. For example, with either method, [!DNL Audience Manager] still sends data to destinations, ID syncs works normally, and you can create traits from data signals.

<br> 

**Que me[!UICONTROL REST API]permet-il de faire ?**

The [!UICONTROL REST API]s let you work programmatically with most [!DNL Audience Manager] features and functions that are available in the user interface.

<br> 

**Comment obtenir un ID[!UICONTROL REST API]client et un secret ?**

Contact your Partner Solutions representative to obtain [!DNL API] access credentials. Our APIs use [OAuth 2.0](https://oauth.net/2/) standards for token authentication, authorization, and renewal. See [OAuth Authentication](../api/rest-api-main/aam-api-getting-started.md#oauth) for more information.
