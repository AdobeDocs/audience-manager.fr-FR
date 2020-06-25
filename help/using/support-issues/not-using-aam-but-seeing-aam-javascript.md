---
description: Nous n’utilisons pas l’Audience Manager, mais nous voyons des appels Javascript d’Audience Manager dans le débogueur Javascript - Pourquoi ?
seo-description: Nous n’utilisons pas, mais nous voyons des appels Javascript d’Audience Manager dans le débogueur Javascript - Pourquoi ?
seo-title: Nous n’utilisons pas l’Audience Manager, mais nous voyons des appels Javascript d’Audience Manager dans le débogueur Javascript - Pourquoi ?
solution: Audience Manager
title: Nous n’utilisons pas l’Audience Manager, mais nous voyons des appels Javascript d’Audience Manager dans le débogueur Javascript - Pourquoi ?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 1%

---


# Nous ne sommes pas clients d’Audience Manager, mais nous voyons les appels Javascript d’Audience Manager sur notre site.

## Question

Nous n’utilisons pas d’Adobe Audience Manager, mais nous voyons des appels Javascript d’Audience Manager dans le débogueur Javascript.

Pourquoi cela se produit-il ?

## Réponse

Il est probable que vous exécutez le service [d&#39;identité](https://docs.adobe.com/content/help/en/id-service/using/home.html) Experience Cloud sur votre propriété. Si tel est le cas, la référence à cette Audience Manager ne fait pas nécessairement référence à la propriété exécutant l’Audience Manager. Au lieu de cela, cela signifie que l&#39;Audience Manager alimente ce service.

L’appel du serveur d’Audiences Manager est généralement effectué pour [synchroniser les identifiants](https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/setcustomerids.html)des clients.
