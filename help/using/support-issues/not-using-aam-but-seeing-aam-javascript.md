---
description: Nous n’utilisons pas Audience Manager, mais nous voyons des appels JavaScript Audience Manager dans le débogueur de JavaScript. Pourquoi ?
seo-description: We are not using  but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
seo-title: We are not using Audience Manager but we are seeing Audience Manager Javascript calls in the Javascript debugger - Why?
solution: Audience Manager
title: Nous n’utilisons pas Audience Manager, mais nous voyons des appels JavaScript Audience Manager dans le débogueur de JavaScript. Pourquoi ?
feature: Support
exl-id: f409e326-17b3-40ee-8570-8d99119fe337
TQID: https://experienceleague.adobe.com/Zpe6ML-WJ5tu4x-gYuPJfAn4IklOxFw2bW8E7ys8YSc
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 136
ht-degree: 98%

---

# Nous ne sommes pas client d’Audience Manager, mais nous pouvons voir des appels JavaScript d’Audience Manager sur notre site

## Question

Nous n’utilisons pas Adobe Audience Manager, mais nous voyons des appels JavaScript Audience Manager dans le débogueur de JavaScript.

Pourquoi cela se produit-il ?

## Réponse

Il est probable que vous exécutiez [Experience Cloud Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr) sur votre propriété. Si tel est le cas, cette référence Audience Manager ne fait pas forcément référence à la propriété exécutant Audience Manager. Cela signifie plutôt qu’Audience Manager alimente ce service.

L’appel au serveur Audience Manager est généralement passé pour [synchroniser les identifiants du client](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=fr).
