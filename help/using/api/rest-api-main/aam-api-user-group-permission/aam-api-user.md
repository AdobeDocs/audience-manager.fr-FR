---
description: Méthodes de l’API REST pour gérer les utilisateurs, notamment la création, la mise à jour, la liste, la suppression et le renvoi d’objets utilisateur.
seo-description: Méthodes de l’API REST pour gérer les utilisateurs, notamment la création, la mise à jour, la liste, la suppression et le renvoi d’objets utilisateur.
seo-title: Méthodes de l’API de gestion des utilisateurs
solution: Audience Manager
title: Méthodes de l’API de gestion des utilisateurs
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Méthodes de l’API de gestion des utilisateurs {#user-management-api-methods}

Redéfinissez [!DNL API] les méthodes de gestion des utilisateurs, notamment la création, la mise à jour, la liste, la suppression et le renvoi d’objets utilisateur.

<!-- c_rest_api_user_man_user.xml -->

## Create a User {#create-user}

Méthode `POST` de création d’un utilisateur.

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

Si `isAdmin` est défini sur true, l’utilisateur est créé en tant qu’administrateur partenaire. Cette propriété vous permet également de savoir si un utilisateur est un administrateur partenaire.

Renvoie `409 Conflict` si le nom d’utilisateur est déjà utilisé.

## Mettre à jour un utilisateur {#update-user}

Méthode `PUT` de mise à jour d’un utilisateur.

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

Renvoie `409 Conflict` si le nom d’utilisateur est déjà utilisé.

## Mettre à jour l’utilisateur connecté {#update-logged-in-user}

Méthode `PUT` permettant de mettre à jour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Alors que la plupart des [!DNL API] méthodes ne peuvent être appelées que par des administrateurs de partenaires, cette méthode peut l’être par des utilisateurs non administrateurs.

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

Renvoie `409 Conflict` si le nom d’utilisateur est déjà utilisé.

## Mettre à jour le mot de passe utilisateur connecté {#update-logged-in-user-pw}

Méthode `PUT` permettant de mettre à jour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Alors que la plupart des [!DNL API] méthodes ne peuvent être appelées que par des administrateurs de partenaires, cette méthode peut l’être par des utilisateurs non administrateurs.

### Demande

`POST /users/self/update-password`

### Exemple de corps de requête

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Renvoie `200 OK` en cas de réussite. Renvoie `400 Bad Request` si quelque chose ne va pas avec l’un ou l’autre mot de passe.

## Réinitialiser le mot de passe utilisateur connecté {#reset-logged-in-user-pw}

Méthode `PUT` permettant de réinitialiser l’utilisateur actuellement connecté. [!UICONTROL Audience Management] envoie à l’utilisateur un mot de passe généré par le système.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Alors que la plupart des [!DNL API] méthodes ne peuvent être appelées que par des administrateurs de partenaires, cette méthode peut l’être par des utilisateurs non administrateurs.

### Demande

`POST /self/reset-password`

Renvoie `200 OK` en cas de réussite.

## Renvoie un objet utilisateur pour un ID utilisateur {#return-user-object-for-id}

Méthode `Get` de renvoi de l’objet utilisateur pour un ID utilisateur.

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

## Objet utilisateur de retour pour l’utilisateur connecté {#return-user-object-for-logged-in-user}

Méthode `Get` de renvoi de l’objet user pour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Alors que la plupart des [!DNL API] méthodes ne peuvent être appelées que par des administrateurs de partenaires, cette méthode peut l’être par des utilisateurs non administrateurs.

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

## Répertorier les utilisateurs {#list-users}

Méthode `GET` permettant de répertorier les utilisateurs.

<!-- r_rest_api_user_list.xml -->

### Demande

`GET /api/v1/users/`

Vous pouvez spécifier plusieurs ID de groupe dans les paramètres de requête :

`GET /api/v1/users/?groupId=343&groupdId=12`

Cette requête renvoie une liste de tous les utilisateurs des groupes spécifiés.

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

Méthode `DELETE` de suppression d’un utilisateur.

<!-- r_rest_api_user_delete.xml -->

### Demande

`DELETE /api/v1/users/`*`<user_id>`*

Renvoie `204 No Content` en cas de réussite. En cas de conflit revient `409 Conflict`.

## Suppression d’utilisateurs en bloc {#delete-users-bulk}

Une `POST` méthode pour supprimer plusieurs utilisateurs en bloc.

<!-- r_rest_api_user_delete_bulk.xml -->

### Demande

`POST /api/v1/users/bulk-delete`

### Exemple de corps de requête

```
{[<user_id_1>, <user_id_2>, ...]}
```
