---
description: La gestion des utilisateurs de l’Audience Manager passe à Adobe Admin Console. Cet article explique ce que vous devez faire pour préparer la migration des utilisateurs et ce qui va changer une fois la migration terminée.
keywords: rbac;RBAC;basé sur les rôles;basé sur les rôles;contrôle d’accès basé sur les rôles
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Audience Manager de la migration des utilisateurs vers Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 1%

---

# [!DNL Audience Manager] migration des utilisateurs vers [!DNL Admin Console] {#user-migration}

## Présentation {#overview}

[!DNL Audience Manager] La gestion des comptes d’utilisateurs se déplace vers [Adobe Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html), pour une expérience plus simplifiée dans l’ensemble de vos solutions d’Adobe.

Les avantages de l’utilisation de [!DNL Admin Console] incluent :

| Avantage | Description |
|---|---|
| Authentification unique dans toutes les solutions | Les utilisateurs de [!DNL Audience Manager] peuvent se connecter à [!DNL Experience Cloud] et à toutes les autres solutions à l’aide de leurs [!DNL Adobe ID] ou [!DNL Enterprise ID]. Cette connexion permet d’accéder aux solutions intégrées et aux services principaux sur [!DNL Experience Cloud]. Après la migration, les utilisateurs qui tentent de se connecter via des comptes hérités (`bank.demdex.com`) seront redirigés vers `experiencecloud.adobe.com`. |
| Gestion des utilisateurs et des groupes | Une fois la migration terminée, [!DNL Audience Manager] administrateurs gèrent les utilisateurs et les groupes exclusivement dans le [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Gestion des produits et des services | À partir de [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/), les administrateurs peuvent : <ul><li>Créer, mettre à jour et supprimer des utilisateurs</li><li>Accorder l’accès aux solutions et services</li></ul> |

Pour faciliter la migration des utilisateurs, nous demandons à tous les administrateurs de [!DNL Audience Manager] de commencer à migrer leurs comptes d’utilisateurs vers [Adobe Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html) dès que possible, en suivant les étapes décrites dans cet article.

## Ce que les utilisateurs doivent faire {#what-to-do-users}

En tant qu&#39;utilisateur d&#39;Audience Manager, il vous suffit de contacter votre administrateur [!DNL Audience Manager] et de lui demander de créer un compte d&#39;utilisateur pour vous dans [!DNL Admin Console].

## Ce que les administrateurs doivent faire {#what-to-do-admins}

Les administrateurs d’Audience Manager doivent suivre les étapes ci-dessous pour migrer les utilisateurs vers [!DNL Admin Console].

1. Accédez à [https://adminconsole.adobe.com](https://adminconsole.adobe.com) et connectez-vous à l’aide de votre Adobe ID ou de votre Enterprise ID. Si vous n&#39;avez pas accès à [!DNL Admin Console], contactez l&#39;assistance clientèle ou votre consultant d&#39;Adobe.
2. Consultez le [!DNL Adobe Admin Console] [guide d’aide](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) pour obtenir des instructions détaillées sur la création et la gestion des comptes d’utilisateurs.
3. Créez de nouveaux comptes utilisateur pour tous vos utilisateurs d’Audience Manager existants.
4. Informez vos utilisateurs au sujet des comptes d’utilisateurs nouvellement créés. Une fois que les utilisateurs sont migrés vers [!DNL Admin Console], ils doivent cesser d’utiliser les comptes hérités.

## Considérations relatives à la migration des utilisateurs {#considerations}

Les utilisateurs et les administrateurs doivent tenir compte des points suivants pour la migration des utilisateurs d’Audience Manager :

* Une fois de nouveaux comptes d’utilisateurs créés dans Admin Console, leurs autorisations existantes à partir de leurs comptes d’utilisateurs hérités s’appliquent toujours.
* Les mises à jour des autorisations utilisateur seront toujours gérées à partir de [!DNL Audience Manager]. Le [!DNL Admin Console] couvre uniquement la gestion des utilisateurs et des groupes.
* Les administrateurs n’ont pas besoin de désactiver les comptes d’utilisateurs hérités. Les anciens comptes utilisateur seront automatiquement fusionnés dans les comptes migrés.
