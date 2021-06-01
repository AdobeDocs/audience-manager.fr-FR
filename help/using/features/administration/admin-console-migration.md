---
description: La gestion des utilisateurs de l’Audience Manager passe à Adobe Admin Console. Cet article explique ce que vous devez faire pour préparer la migration des utilisateurs et ce qui va changer une fois la migration terminée.
keywords: rbac;RBAC;basé sur les rôles;basé sur les rôles;contrôle d’accès basé sur les rôles
seo-description: La gestion des utilisateurs de l’Audience Manager passe à Adobe Admin Console. Cet article explique ce que vous devez faire pour préparer la migration des utilisateurs et ce qui va changer une fois la migration terminée.
seo-title: Audience Manager de la migration des utilisateurs vers Admin Console
solution: Audience Manager
title: Audience Manager de la migration des utilisateurs vers Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 3%

---

# [!DNL Audience Manager] migration des utilisateurs vers  [!DNL Admin Console] {#user-migration}

## Présentation {#overview}

[!DNL Audience Manager] la gestion des comptes d’utilisateurs se déplace vers  [Adobe Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html), ce qui vous permet d’offrir une expérience plus simplifiée dans vos solutions d’Adobe.

Les avantages de l’utilisation de [!DNL Admin Console] incluent :

| Avantage | Description |
|---|---|
| Authentification unique à travers les solutions | [!DNL Audience Manager] les utilisateurs peuvent se connecter à  [!DNL Experience Cloud] et à toutes les autres solutions à l’aide de leur  [!DNL Adobe ID] ou  [!DNL Enterprise ID]. Cette connexion permet d’accéder aux solutions intégrées et aux services principaux sur [!DNL Experience Cloud]. Après la migration, les utilisateurs qui tentent de se connecter via des comptes hérités (`bank.demdex.com`) seront redirigés vers `experiencecloud.adobe.com`. |
| Gestion des utilisateurs et des groupes | Une fois la migration terminée, les administrateurs [!DNL Audience Manager] gèrent les utilisateurs et les groupes exclusivement dans les [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Gestion des produits et des services | À partir de [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/), les administrateurs peuvent : <ul><li>Créer, mettre à jour et supprimer des utilisateurs</li><li>Accorder l’accès aux solutions et services</li></ul> |

Pour faciliter la migration des utilisateurs, nous demandons à tous les [!DNL Audience Manager] administrateurs de commencer dès que possible la migration de leurs comptes d’utilisateurs vers [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) en suivant les étapes décrites dans cet article.

## Ce que les utilisateurs doivent faire {#what-to-do-users}

En tant qu’utilisateur d’Audience Manager, il vous suffit de contacter votre administrateur [!DNL Audience Manager] et de lui demander de créer un compte d’utilisateur pour vous dans [!DNL Admin Console].

## Ce que les administrateurs doivent faire {#what-to-do-admins}

Les administrateurs d’Audience Manager doivent suivre les étapes ci-dessous pour migrer les utilisateurs vers [!DNL Admin Console].

1. Accédez à [https://adminconsole.adobe.com](https://adminconsole.adobe.com) et connectez-vous à l’aide de votre Adobe ID ou de votre Enterprise ID. Si vous n’avez pas accès à [!DNL Admin Console], contactez l’assistance clientèle ou votre consultant d’Adobe.
2. Consultez le [!DNL Adobe Admin Console] [guide d’aide](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) pour obtenir des instructions détaillées sur la création et la gestion des comptes d’utilisateurs.
3. Créez de nouveaux comptes utilisateur pour tous vos utilisateurs d’Audience Manager existants.
4. Informez vos utilisateurs au sujet des comptes d’utilisateurs nouvellement créés. Une fois que les utilisateurs sont migrés vers [!DNL Admin Console], ils doivent cesser d’utiliser les comptes hérités.

## Considérations relatives à la migration des utilisateurs {#considerations}

Les utilisateurs et les administrateurs doivent tenir compte des points suivants pour la migration des utilisateurs d’Audience Manager :

* Une fois de nouveaux comptes d’utilisateurs créés dans Admin Console, leurs autorisations existantes à partir de leurs comptes d’utilisateurs hérités s’appliquent toujours.
* Les mises à jour des autorisations utilisateur seront toujours gérées à partir de [!DNL Audience Manager]. [!DNL Admin Console] couvre uniquement la gestion des utilisateurs et des groupes.
* Les administrateurs n’ont pas besoin de désactiver les comptes d’utilisateurs hérités. Les anciens comptes utilisateur seront automatiquement fusionnés dans les comptes migrés.
