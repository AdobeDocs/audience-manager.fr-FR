---
description: Guide de préparation au RGPD pour les clients d’Audience Manager
seo-description: GDPR Readiness Guidance for Audience Manager Customers
seo-title: GDPR Readiness Guidance for Audience Manager Customers
solution: Audience Manager
title: Guide de préparation au RGPD pour les clients d’Audience Manager
feature: Data Governance & Privacy
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
TQID: https://experienceleague.adobe.com/K72pQ8Q6yILWexkG38Hc5W1roYObFvhLE5A0GSCyhYE
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: c814092e-2730-45e8-a12d-e084529f52cbid: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 461
ht-degree: 98%

---

# Guide de préparation au RGPD pour les clients Audience Manager (Contrôleurs de données) {#gdpr-readiness-guidance}

Audience Manager recommande d’être proactif dans les domaines de la gouvernance des données et de la préparation organisationnelle. Cela permet de vous assurer que les données relatives aux consommateurs sont organisées pour les processus liés aux requêtes d’accès ou de suppression, que vos équipes sont habilitées à gérer ces requêtes et que vos clients (titulaires de données) bénéficient d’une expérience positive et différenciée avec votre marque.

En tant que responsable du traitement des données, Adobe ne peut pas fournir d’avis juridique sur les exigences du RGPD et le processus d’obtention du consentement des titulaires de données. Veuillez consulter votre service juridique pour obtenir des conseils sur la conformité au RGPD pour votre organisation.

## Gouvernance des données : commencez à réfléchir à la manière dont les données relatives aux consommateurs sont gérées dans votre instance Audience Manager

* Examinez les différents identifiants de client utilisés par vos équipes marketing pour identifier les utilisateurs dans Audience Manager, ainsi que les sources de données dans lesquelles ils sont stockés. Cela permet de rationaliser le processus de requêtes (comme la suppression ou l’accès) puisque certains types de données sont hachés par vos équipes avant leur ingestion dans Audience Manager.
* Les identifiants d’appareil mobile IDFA/GAID sont utilisés pour plusieurs cas d’utilisation dans Audience Manager. Si vous utilisez le SDK Adobe Mobile, veillez à envoyer l’Experience Cloud ID (MID) avec IDFA/GAID pour vous assurer que les réponses du RGPD sont complètes.
* La définition des données personnelles étant de plus en plus étendue, les adresses IP peuvent être considérées comme des données personnelles dans votre région. Contactez Adobe Consulting de manière proactive pour obscurcir le dernier octet.
* Déterminez une stratégie et un processus de validation/d’authentification pour confirmer l’identité d’un titulaire de données lorsqu’il effectue une demande de RGPD.
* Envisagez d’utiliser les [contrôles des exportations de données](../../features/data-export-controls.md) pour bloquer l’activation des audiences aux technologies qui hébergent des données personnelles. Par exemple, les segments contenant des données tierces ne doivent pas être syndiqués aux fournisseurs de services de messagerie électronique. Définissez un [!UICONTROL Data Export Control] afin de vous assurer qu’aucun membre de votre organisation ne puisse accidentellement activer ces données.
* Commencez à utiliser les [Contrôles d’accès en fonction du rôle (RBAC)](../../features/administration/administration-overview.md) pour vous assurer que les bonnes équipes ont accès aux données prévues.
* Tenez compte des [périodes de rétention](../../faq/faq-privacy.md#data-retention-faq) appropriées pour les données.
* Examinez les politiques de confidentialité et de liaison et les exigences légales afin de déterminer le moment et le lieu où il convient de lier des ensembles d’identités ; utilisez-les de manière appropriée via les [stratégies de fusion de profils](../../features/profile-merge-rules/merge-rules-overview.md) d’Audience Manager.

## Préparation organisationnelle : établir un processus d’entreprise

* Identifiez un processus pour recevoir les requêtes des titulaires de données et y répondre. Pensez à créer un outil automatisé pour envoyer des requêtes à Audience Manager.
* Désignez un point de contact de confidentialité au sein de votre centre d’excellence DMP. Reliez le point de contact de confidentialité de votre organisation à votre équipe d’utilisation des produits d’Audience Manager pour comprendre comment vous pouvez gérer vos exigences d’identifiant d’entrée.
* Effectuez un examen des données avant de les partager avec le titulaire de données. Documentez les étapes que vous avez mises en place pour vous aider à déterminer les responsabilités.
