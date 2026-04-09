---
description: Questions et problématiques courantes liées à l’API.
seo-description: Common API questions and issues.
seo-title: API FAQ
solution: Audience Manager
title: FAQ sur l’API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
exl-id: 9a51220e-3f53-4911-876b-16e968d44d0f
TQID: https://experienceleague.adobe.com/IKztfem2G3SCH36c-2Qe5cJWVhPWRLQXjU5TEgF9Cgs
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 100%

---

# FAQ sur l’API{#api-faq}

Questions et problématiques courantes liées à l’API.

<!-- 

faq_api.xml

 -->

La documentation de l’[API REST](../api/rest-api-main/rest-api-main.md) contient des informations sur des méthodes spécifiques et des exemples de code.

<br> 

**Pourquoi [!UICONTROL DIL] effectue-t-il des appels d’événement au moyen de méthodes [!UICONTROL GET] et [!UICONTROL POST] ?**

[!UICONTROL DIL] transmet les données à [!DNL Audience Manager] au moyen d’une méthode `GET` ou `POST` selon la longueur de la chaîne de requête de l’appel d’événement. Par défaut, ce comportement est intégré aux méthodes `GET` et `POST`. Il n’est pas spécifique à [!DNL Audience Manager].

* [!UICONTROL DIL] effectue des appels d’événement avec `GET` lorsqu’une URL contient 2 048 caractères ou moins. Un appel d’événement `GET` inclut des données dans l’URL en tant que paramètres de chaîne de requête, qui sont transmis en tant que paires clé-valeur.

* [!UICONTROL DIL] effectue des appels d’événement avec `POST` lorsqu’une URL contient plus de 2 048 caractères. Un appel d’événement `POST` inclut des données dans le corps de la requête. [!UICONTROL DIL] transforme les données en paires clé-valeur et transmet les informations en tant que données de formulaire plutôt que dans la chaîne de requête de l’URL.

Bien que chaque méthode transmette les données d’une manière différente, cela n’a aucune incidence sur la fonctionnalité. Par exemple, [!DNL Audience Manager] envoie toujours des données vers les destinations, les identifiants se synchronisent normalement et vous pouvez créer des caractéristiques à partir des signaux de données, et ce quelle que soit la méthode employée.

<br> 

**Qu’est-ce que les [!UICONTROL REST API] me permettent de faire ?**

Les [!UICONTROL REST API] vous permettent de travailler par programmation avec la plupart des fonctionnalités d’[!DNL Audience Manager] disponibles dans l’interface utilisateur.

<br> 

**Comment puis-je obtenir un [!UICONTROL REST API] identifiant client et un secret client  ?**

Prenez contact avec votre représentant Partenaires en solution pour obtenir des identifiants d’accès [!DNL API]. Nos API utilisent les normes [OAuth 2.0](https://oauth.net/2/) pour l’authentification, l’autorisation et le renouvellement des jetons. Pour plus d’informations, consultez l’[Authentification OAuth](../api/rest-api-main/aam-api-getting-started.md#oauth).
