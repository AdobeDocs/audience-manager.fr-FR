---
description: Méthodes de l’API REST pour gérer les utilisateurs, y compris la création, la mise à jour, la liste, la suppression et le renvoi d’objets utilisateur.
seo-description: Méthodes de l’API REST pour gérer les utilisateurs, y compris la création, la mise à jour, la liste, la suppression et le renvoi d’objets utilisateur.
seo-title: Méthodes d’API de gestion des utilisateurs
solution: Audience Manager
title: Méthodes d’API de gestion des utilisateurs
uuid: 6e1f2c35-bb9d-4166-b7d4-d9c5518a61ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 7%

---


# Méthodes d’API de gestion des utilisateurs {#user-management-api-methods}

Restez [!DNL API] aux méthodes de gestion des utilisateurs, y compris la création, la mise à jour, la liste, la suppression et le renvoi d’objets utilisateur.

<!-- c_rest_api_user_man_user.xml -->

## Créer un utilisateur {#create-user}

Méthode `POST` permettant de créer un utilisateur.

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

Renvoie `409 Conflict` si le nom d&#39;utilisateur est déjà utilisé.

## Mettre à jour un utilisateur {#update-user}

Méthode `PUT` permettant de mettre à jour un utilisateur.

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

Renvoie `409 Conflict` si le nom d&#39;utilisateur est déjà utilisé.

## Mettre à jour l&#39;utilisateur connecté {#update-logged-in-user}

Méthode `PUT` pour mettre à jour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_update_self.xml -->

>[!NOTE]
>
>Alors que la plupart des méthodes [!DNL API] ne sont appelables que par les administrateurs partenaires, cette méthode est appelable par les utilisateurs non-administrateurs.

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

Renvoie `409 Conflict` si le nom d&#39;utilisateur est déjà utilisé.

## Mettre à jour le mot de passe utilisateur connecté {#update-logged-in-user-pw}

Méthode `PUT` pour mettre à jour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_password.xml -->

>[!NOTE]
>
>Alors que la plupart des méthodes [!DNL API] ne sont appelables que par les administrateurs partenaires, cette méthode est appelable par les utilisateurs non-administrateurs.

### Demande

`POST /users/self/update-password`

### Exemple de corps de requête

```
{ "oldPassword" : "old password", "newPassword" : "new password" }
```

Renvoie `200 OK` en cas de réussite. Renvoie `400 Bad Request` si un problème survient avec l&#39;un des mots de passe.

## Réinitialiser le mot de passe utilisateur connecté {#reset-logged-in-user-pw}

Méthode `PUT` pour réinitialiser l&#39;utilisateur actuellement connecté. [!UICONTROL Audience Management] envoie à l’utilisateur un mot de passe généré par le système.

<!-- r_rest_api_user_password_reset.xml -->

>[!NOTE]
>
>Alors que la plupart des méthodes [!DNL API] ne sont appelables que par les administrateurs partenaires, cette méthode est appelable par les utilisateurs non-administrateurs.

### Demande

`POST /self/reset-password`

Renvoie `200 OK` en cas de réussite.

## Renvoie un objet utilisateur pour un ID utilisateur {#return-user-object-for-id}

Méthode `Get` pour renvoyer l’objet utilisateur pour un ID utilisateur.

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

## Renvoie l’objet utilisateur pour l’utilisateur connecté {#return-user-object-for-logged-in-user}

Méthode `Get` pour renvoyer l’objet utilisateur pour l’utilisateur actuellement connecté.

<!-- r_rest_api_user_get_self.xml -->

>[!NOTE]
>
>Alors que la plupart des méthodes [!DNL API] ne sont appelables que par les administrateurs partenaires, cette méthode est appelable par les utilisateurs non-administrateurs.

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

## Utilisateurs de liste {#list-users}

Méthode `GET` destinée aux utilisateurs de la liste.

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

## Supprimer un utilisateur {#delete-users}

Méthode `DELETE` de suppression d’un utilisateur.

<!-- r_rest_api_user_delete.xml -->

### Demande

`DELETE /api/v1/users/`*`<user_id>`*

Renvoie `204 No Content` en cas de réussite. En cas de conflit renvoie `409 Conflict`.

## Supprimer des utilisateurs en bloc {#delete-users-bulk}

Une méthode `POST` pour supprimer plusieurs utilisateurs en bloc.

<!-- r_rest_api_user_delete_bulk.xml -->

### Demande

`POST /api/v1/users/bulk-delete`

### Exemple de corps de requête

```
{[<user_id_1>, <user_id_2>, ...]}
```
