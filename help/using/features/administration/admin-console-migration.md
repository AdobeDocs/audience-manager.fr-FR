---
description: La gestion des utilisateurs d’Audience Manager est transférée vers Adobe Admin Console. Cet article explique ce que vous devez faire pour préparer la migration des utilisateurs et ce qui changera une fois la migration terminée.
keywords: rbac;RBAC;basé sur les rôles;basé sur les rôles;contrôles d’accès basés sur les rôles
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Migration des utilisateurs d’Audience Manager vers Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# [!DNL Audience Manager] la migration des utilisateurs vers [!DNL Admin Console] {#user-migration}

## Présentation {#overview}

[!DNL Audience Manager] gestion des comptes d’utilisateurs est transférée vers [Adobe Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html), pour une expérience simplifiée sur l’ensemble de vos solutions Adobe.

Les avantages de l’utilisation de l’[!DNL Admin Console] sont les suivants :

| Avantage | Description |
|---|---|
| Authentification unique pour toutes les solutions | [!DNL Audience Manager] utilisateurs peuvent se connecter à [!DNL Experience Cloud] et à toutes les autres solutions à l’aide de leurs [!DNL Adobe ID] ou [!DNL Enterprise ID]. Cette connexion permet d’accéder à des solutions intégrées et à des services principaux dans toutes les [!DNL Experience Cloud]. Après la migration, les utilisateurs qui tentent de se connecter au moyen des comptes hérités (`bank.demdex.com`) sont redirigés vers `experiencecloud.adobe.com`. |
| Gestion des utilisateurs et des groupes | Une fois la migration terminée, [!DNL Audience Manager] administrateurs géreront les utilisateurs et les groupes exclusivement dans le [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Gestion des produits et services | À partir du [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), les administrateurs peuvent : <ul><li>Créer, mettre à jour et supprimer des utilisateurs</li><li>Accorder l’accès aux solutions et services</li></ul> |

Pour faciliter la migration des utilisateurs, nous demandons à tous les administrateurs [!DNL Audience Manager] de commencer à migrer leurs comptes d&#39;utilisateurs vers [Adobe Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html) dès que possible, en suivant les étapes décrites dans cet article.

## Ce que les utilisateurs doivent faire {#what-to-do-users}

En tant qu’utilisateur Audience Manager, il vous suffit de contacter votre administrateur [!DNL Audience Manager] et de lui demander de créer un compte utilisateur pour vous dans [!DNL Admin Console].

## Ce que les administrateurs doivent faire {#what-to-do-admins}

Les administrateurs Audience Manager doivent suivre les étapes ci-dessous pour migrer les utilisateurs vers [!DNL Admin Console].

1. Accédez à [https://adminconsole.adobe.com](https://adminconsole.adobe.com) et connectez-vous à l’aide de votre Adobe ID ou Enterprise ID. Si vous n’avez pas accès au [!DNL Admin Console], contactez l’assistance clientèle ou votre consultant Adobe.
2. Consultez le [!DNL Adobe Admin Console] [guide d’aide](https://helpx.adobe.com/fr/enterprise/admin-guide.html/enterprise/using/users.ug.html) pour obtenir des instructions détaillées sur la création et la gestion des comptes utilisateur.
3. Créez des comptes d’utilisateurs pour tous vos utilisateurs Audience Manager existants.
4. Informez vos utilisateurs des comptes utilisateur nouvellement créés. Une fois les utilisateurs migrés vers [!DNL Admin Console], ils doivent cesser d’utiliser les comptes hérités.

## Considérations relatives à la migration des utilisateurs {#considerations}

Les utilisateurs et les administrateurs doivent garder à l’esprit les points suivants concernant la migration des utilisateurs d’Audience Manager :

* Une fois les nouveaux comptes utilisateur créés dans Admin Console, leurs autorisations existantes de leurs comptes utilisateur hérités s’appliquent toujours.
* Les mises à jour des autorisations utilisateur seront toujours gérées à partir de [!DNL Audience Manager]. La [!DNL Admin Console] ne couvre que la gestion des utilisateurs et des groupes.
* Les administrateurs n’ont pas besoin de désactiver les comptes utilisateur hérités. Les anciens comptes d’utilisateurs seront automatiquement fusionnés avec les comptes migrés.
