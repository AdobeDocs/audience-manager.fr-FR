---
description: Méthodes API REST pour gérer les utilisateurs, notamment la création, la mise à jour, la liste, la suppression et le retour d'objets utilisateur.
seo-description: Méthodes API REST pour gérer les utilisateurs, notamment la création, la mise à jour, la liste, la suppression et le retour d'objets utilisateur.
seo-title: Méthodes de l'API Gestion des utilisateurs
solution: Audience Manager
title: Méthodes de l'API Gestion des utilisateurs
uuid: 6 e 1 f 2 c 35-bb 9 d -4166-b 7 d 4-d 9 c 5518 a 61 ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# User Management API Methods {#user-management-api-methods}

Rest [!DNL API] methods to manage users, including creating, updating, listing, deleting, and returning user objects.

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

`POST` Méthode de création d'un utilisateur.

<!-- r_rest_api_user_create.xml -->

### Demande

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

If `isAdmin` is set to true, the user is created as a partner admin. Cette propriété vous permet également de savoir si un utilisateur est un administrateur.

Returns `409 Conflict` if the username is already taken.

## Update a User {#update-user}

`PUT` Méthode de mise à jour d'un utilisateur.

<!-- r_rest_api_user_update.xml -->

### Demande

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User {#update-logged-in-user}

`PUT` Méthode de mise à jour de l'utilisateur actuellement connecté.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Demande

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

Returns `409 Conflict` if the username is already taken.

## Update Logged-In User Password {#update-logged-in-user-pw}

`PUT` Méthode de mise à jour de l'utilisateur actuellement connecté.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Demande

`POST /users/self/update-password`

### Exemple de corps de requête

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Returns `200 OK` if successful. Returns `400 Bad Request` if something is wrong with either password.

## Reset Logged-In User Password {#reset-logged-in-user-pw}

`PUT` Méthode permettant de réinitialiser l'utilisateur actuellement connecté. [!UICONTROL Audience Management] lui envoie un mot de passe généré par le système.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Demande

`POST /self/reset-password`

Returns `200 OK` if successful.

## Return User Object for a User ID {#return-user-object-for-id}

`Get` Méthode permettant de renvoyer l'objet utilisateur pour un utilisateur - id.

<!-- r_rest_api_user_get_user_obj.xml -->

### Demande

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

## Return User Object for Logged-In User {#return-user-object-for-logged-in-user}

`Get` Méthode permettant de renvoyer l'objet utilisateur pour l'utilisateur actuellement connecté.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Whereas most [!DNL API] methods are only callable by partner admins, this method is callable by non-admin users.

### Demande

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

## List Users {#list-users}

`GET` Méthode permettant de répertorier les utilisateurs.

<!-- r_rest_api_user_list.xml -->

### Demande

`GET /api/v1/users/`

Vous pouvez spécifier plusieurs ID de groupe dans les paramètres de requête :

`GET /api/v1/users/?groupId=343&groupdId=12`

Cette requête renvoie la liste de tous les utilisateurs des groupes spécifiés.

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

## Delete a User {#delete-users}

`DELETE` Méthode de suppression d'un utilisateur.

<!-- r_rest_api_user_delete.xml -->

### Demande

`DELETE /api/v1/users/`*`<user_id>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Users in Bulk {#delete-users-bulk}

`POST` Méthode permettant de supprimer plusieurs utilisateurs par lot.

<!-- r_rest_api_user_delete_bulk.xml -->

### Demande

`POST /api/v1/users/bulk-delete`

### Exemple de corps de requête

```
{[<user_id_1>, <user_id_2>, ...]}
```
