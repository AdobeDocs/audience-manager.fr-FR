---
description: Guide de préparation au RGPD pour les clients d’Audience Manager
seo-description: Guide de préparation au RGPD pour les clients d’Audience Manager
seo-title: Guide de préparation au RGPD pour les clients d’Audience Manager
solution: Audience Manager
title: Guide de préparation au RGPD pour les clients d’Audience Manager
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---


# Guide de préparation au RGPD pour les clients d’Audience Manager (contrôleurs de données) {#gdpr-readiness-guidance}

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
