---
description: Questions et problématiques courantes liées à l’API.
seo-description: Questions et problématiques courantes liées à l’API.
seo-title: FAQ sur l’API
solution: Audience Manager
title: FAQ sur l’API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 100%

---


# FAQ sur l’API {#api-faq}

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
