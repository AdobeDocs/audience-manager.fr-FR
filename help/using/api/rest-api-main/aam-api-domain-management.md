---
description: Méthodes de gestion des domaines qui vous permettent de créer et de gérer les domaines auxquels vous souhaitez envoyer des données (pour les destinations de cookies uniquement).
seo-description: Méthodes de gestion des domaines qui vous permettent de créer et de gérer les domaines auxquels vous souhaitez envoyer des données (pour les destinations de cookies uniquement).
seo-title: Méthodes de l'API Gestion des domaines
solution: Audience Manager
title: Méthodes de l'API Gestion des domaines
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Méthodes de l'API Gestion des domaines {#domain-management-api-methods}

Méthodes de gestion des domaines qui vous permettent de créer et de gérer les domaines auxquels vous souhaitez envoyer des données (pour les destinations de cookies uniquement).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

Méthode `POST` permettant de créer un domaine pour (destinations de cookies uniquement).

<!-- r_post_new_partner_site.xml -->

### Demande

`POST` `https://api.demdex.com/v1/partner-sites/`

### Exemple de requête

```
{
   "url":"example1.com"
}
```

### Réponse

Une réponse réussie renvoie `201 created` et le site partenaire, y compris son identifiant unique.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Suppression d’un domaine {#delete-domain}

Méthode `DELETE` permettant de supprimer un domaine (pour les destinations de cookies uniquement).

<!-- r_delete_partner_site.xml -->

### Demande

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Réponse

Une réponse réussie revient `204 no content`. Renvoie `404 not found` si le site partenaire est introuvable.

## Propriétés de retour pour un domaine {#return-props-domain}

Méthode `GET` qui renvoie des détails sur le domaine spécifié (pour les destinations de cookies uniquement).

<!-- r_get_partner_site.xml -->

### Demande

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Réponse

Une réponse réussie renvoie `200 OK` et des données comme illustré dans l’exemple ci-dessous. Renvoie `404 Not found` si l’identifiant ou le partenaire du site est introuvable.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Propriétés de retour pour tous les domaines {#return-props-all-domains}

Méthode `GET` qui renvoie des informations sur tous vos domaines (pour les destinations de cookies uniquement).

<!-- r_get_partner_sites.xml -->

### Demande

`GET https://api.demdex.com/v1/partner-sites/`

### Paramètres de requête facultatifs

Vous pouvez utiliser ces paramètres facultatifs avec [!DNL API] des méthodes qui renvoient *toutes les* propriétés d’un objet. Définissez ces options dans la chaîne de requête lors de la transmission de cette requête à la [!DNL API]. Voir Paramètres [](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)facultatifs.

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> Renvoie les résultats par numéro de page. La numérotation commence à 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Définit le nombre de résultats de réponse renvoyés par la requête (10 est la valeur par défaut). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Trie et renvoie les résultats selon la propriété JSON spécifiée. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> décroissant</code> </td>
   <td colname="col2"> Trie et renvoie les résultats dans l’ordre décroissant. L’option Croissant est utilisée par défaut. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> rechercher</code> </td>
   <td colname="col2">Renvoie les résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Supposons, par exemple, que vous souhaitiez rechercher des résultats pour tous les modèles qui contiennent le mot "Test" dans l’un des champs de valeur de cet élément. Votre exemple de requête peut ressembler à ceci : <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Vous pouvez rechercher n’importe quelle valeur renvoyée par une méthode "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Réponse

Une réponse réussie renvoie `200 OK` et des données dans un tableau, comme le montre l'exemple ci-dessous. Renvoie `404 Not found` si l’identifiant ou le partenaire du site est introuvable.

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
