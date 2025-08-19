---
description: Méthodes d’API REST pour gérer les utilisateurs, notamment la création, la mise à jour, la mise en liste, la suppression et le renvoi d’objets utilisateur.
seo-description: Rest API methods to manage users, including creating, updating, listing, deleting, and returning user objects.
seo-title: User Management API Methods
solution: Audience Manager
title: Méthodes d’API User Management
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
exl-id: c015c42c-63c7-4392-9fef-f48dc787a56f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 1%

---

# Méthodes d’API User Management {#user-management-api-methods}

Méthodes de [!DNL API] Rest pour gérer les utilisateurs, notamment la création, la mise à jour, la mise en liste, la suppression et le renvoi d’objets utilisateur.

<!-- c_rest_api_user_man_user.xml -->

## Création d’un utilisateur {#create-user}

Méthode `POST` pour créer un nouvel utilisateur.

<!-- r_rest_api_user_create.xml -->

### Requête

`POST /api/v1/users/`

### Exemple de corps de requête

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : true | false 
}
```

### Réponse

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...], 
  "isAdmin" : <"true"|"false"> 
 
}
```

Si `isAdmin` est défini sur true, l’utilisateur est créé en tant qu’administrateur de partenaire. Cette propriété vous permet également de savoir si un utilisateur est un administrateur partenaire.

Renvoie `409 Conflict` si le nom d’utilisateur est déjà utilisé.

## Mettre à jour un utilisateur {#update-user}

Méthode `PUT` pour mettre à jour un utilisateur.

<!-- r_rest_api_user_update.xml -->

### Requête

`PUT /api/v1/users/`*`<userId>`*

### Exemple de corps de requête

```
{ 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
}
```

### Réponse

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

Renvoie `409 Conflict` si le nom d’utilisateur est déjà utilisé.

## Mettre à jour l&#39;utilisateur connecté {#update-logged-in-user}

Méthode `PUT` pour mettre à jour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Alors que la plupart des méthodes [!DNL API] ne peuvent être appelées que par les administrateurs partenaires, cette méthode est appelée par les utilisateurs non administrateurs.

### Requête

`PUT /self/update`

### Exemple de corps de requête

```
{  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

### Réponse

```
{ 
  "userId": <integer>,,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string> 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null> 
}
```

Renvoie `409 Conflict` si le nom d’utilisateur est déjà utilisé.

## Mettre à jour le mot de passe de l&#39;utilisateur connecté {#update-logged-in-user-pw}

Méthode `PUT` pour mettre à jour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Alors que la plupart des méthodes [!DNL API] ne peuvent être appelées que par les administrateurs partenaires, cette méthode est appelée par les utilisateurs non administrateurs.

### Requête

`POST /users/self/update-password`

### Exemple de corps de requête

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Renvoie `200 OK` en cas de réussite. Renvoie `400 Bad Request` si un problème se produit avec l’un ou l’autre mot de passe.

## Réinitialiser le mot de passe de l&#39;utilisateur connecté {#reset-logged-in-user-pw}

Méthode `PUT` pour réinitialiser l’utilisateur actuellement connecté. [!UICONTROL Audience Management] envoie à l’utilisateur un mot de passe généré par le système.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Alors que la plupart des méthodes [!DNL API] ne peuvent être appelées que par les administrateurs partenaires, cette méthode est appelée par les utilisateurs non administrateurs.

### Requête

`POST /self/reset-password`

Renvoie `200 OK` en cas de réussite.

## Renvoyer l’objet utilisateur pour un ID utilisateur {#return-user-object-for-id}

Une méthode `Get` pour renvoyer l’objet utilisateur pour un ID utilisateur.

<!-- r_rest_api_user_get_user_obj.xml -->

### Requête

`GET /api/v1/users/`*`<userId>`*

### Réponse

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Renvoyer l&#39;objet utilisateur pour l&#39;utilisateur connecté {#return-user-object-for-logged-in-user}

Une méthode `Get` pour renvoyer l’objet utilisateur pour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Alors que la plupart des méthodes [!DNL API] ne peuvent être appelées que par les administrateurs partenaires, cette méthode est appelée par les utilisateurs non administrateurs.

### Requête

`GET /api/v1/users/self`

### Réponse

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email" : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<groupd_id_1>, ...] 
 
}
```

## Liste des utilisateurs {#list-users}

Méthode `GET` pour répertorier les utilisateurs.

<!-- r_rest_api_user_list.xml -->

### Requête

`GET /api/v1/users/`

Vous pouvez spécifier plusieurs identifiants de groupe dans les paramètres de requête :

`GET /api/v1/users/?groupId=343&groupdId=12`

Cette requête renvoie une liste de tous les utilisateurs appartenant aux groupes spécifiés.

### Réponse

```
{ 
  "pid" : <integer>, 
  "userId": <integer>, 
  "username" : <string>,  
  "status" : <"ACTIVE"|"INACTIVE"|"LOCKED"> 
  "firstName" : <string>, 
  "lastName" : <string>, 
  "email : <string>, 
  "title" : <string_may_be_null>, 
  "phoneNumber" : <string_may_be_null>, 
  "groups" : [<group_1_id>, ...] 
 
}
```

## Suppression d’un utilisateur {#delete-users}

Méthode `DELETE` pour supprimer un utilisateur.

<!-- r_rest_api_user_delete.xml -->

### Requête

`DELETE /api/v1/users/`*`<user_id>`*

Renvoie `204 No Content` en cas de réussite. En cas de conflit, renvoie `409 Conflict`.

## Supprimer des utilisateurs en bloc {#delete-users-bulk}

Une méthode `POST` pour supprimer plusieurs utilisateurs en bloc.

<!-- r_rest_api_user_delete_bulk.xml -->

### Requête

`POST /api/v1/users/bulk-delete`

### Exemple de corps de requête

```
{[<user_id_1>, <user_id_2>, ...]}
```
