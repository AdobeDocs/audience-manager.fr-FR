---
description: Méthodes de gestion des domaines qui vous permettent de créer et de gérer les domaines sur lesquels vous souhaitez envoyer des données (pour les destinations de cookie uniquement).
seo-description: Méthodes de gestion des domaines qui vous permettent de créer et de gérer les domaines sur lesquels vous souhaitez envoyer des données (pour les destinations de cookie uniquement).
seo-title: Méthodes de l'API Gestion des domaines
solution: Audience Manager
title: Méthodes de l'API Gestion des domaines
uuid: f 2 f 08 bc 5-ea 42-4171-9 a 43-0 b 20976 f 0 cb 0
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Domain Management API Methods {#domain-management-api-methods}

Méthodes de gestion des domaines qui vous permettent de créer et de gérer les domaines sur lesquels vous souhaitez envoyer des données (pour les destinations de cookie uniquement).

<!-- c_partner_site.xml -->

## Create a New Domain {#create-new-domain}

`POST` Méthode qui permet de créer un domaine pour (destinations de cookie uniquement).

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

A successful response returns `201 created` and the partner site, including its unique ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Delete a Domain {#delete-domain}

`DELETE` Méthode qui permet de supprimer un domaine (pour les destinations de cookie uniquement).

<!-- r_delete_partner_site.xml -->

### Demande

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Réponse

A successful response returns `204 no content`. Returns `404 not found` if the partner site cannot be found.

## Return Properties for a Domain {#return-props-domain}

`GET` Méthode qui renvoie des détails sur le domaine spécifié (pour les destinations de cookie uniquement).

<!-- r_get_partner_site.xml -->

### Demande

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Réponse

A successful response returns `200 OK` and data as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Return Properties for all Domains {#return-props-all-domains}

`GET` Méthode qui renvoie des informations sur tous les domaines (pour les destinations de cookie uniquement).

<!-- r_get_partner_sites.xml -->

### Demande

`GET https://api.demdex.com/v1/partner-sites/`

### Paramètres de requête facultatifs

You can use these optional parameters with [!DNL API] methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col1"><code> Pagesize</code> </td> 
   <td colname="col2"> Définit le nombre de résultats de réponse renvoyés par la requête (10 est par défaut). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td> 
   <td colname="col2"> Trie et renvoie les résultats selon la propriété JSON spécifiée. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> décroissant</code> </td>
   <td colname="col2"> Trie et renvoie les résultats par ordre décroissant. L'ordre croissant est par défaut. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> recherche</code> </td>
   <td colname="col2">Renvoie les résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Par exemple, supposons que vous souhaitiez obtenir des résultats pour tous les modèles qui contiennent le mot « Test » dans l'un des champs de valeur de cet élément. Voici un exemple de demande : <p><code> ' GET ''https://api.demdex.com/v1/models/?search=Test '</code>. </p> <p>Vous pouvez rechercher une valeur renvoyée par une méthode « get all ». </p> </td>
  </tr> 
 </tbody> 
</table>

### Réponse

A successful response returns `200 OK` and data in an array as shown in the sample below. Returns `404 Not found` if the site ID or partner is not found.

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
