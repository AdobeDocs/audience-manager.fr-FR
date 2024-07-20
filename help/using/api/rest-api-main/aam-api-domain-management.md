---
description: Méthodes de gestion des domaines qui vous permettent de créer et gérer les domaines auxquels vous souhaitez envoyer des données (pour les destinations de cookies uniquement).
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: Méthodes d’API de gestion de domaine
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 2%

---

# Méthodes d’API de gestion de domaine {#domain-management-api-methods}

Méthodes de gestion des domaines qui vous permettent de créer et gérer les domaines auxquels vous souhaitez envoyer des données (pour les destinations de cookies uniquement).

<!-- c_partner_site.xml -->

## Création d’un domaine {#create-new-domain}

Une méthode `POST` qui vous permet de créer un domaine pour (destinations de cookie uniquement).

<!-- r_post_new_partner_site.xml -->

### Requête

`POST` `https://api.demdex.com/v1/partner-sites/`

### Exemple de requête

```
{
   "url":"example1.com"
}
```

### Réponse

Une réponse réussie renvoie `201 created` et le site du partenaire, y compris son identifiant unique.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Suppression d’un domaine {#delete-domain}

Méthode `DELETE` qui permet de supprimer un domaine (pour les destinations de cookie uniquement).

<!-- r_delete_partner_site.xml -->

### Requête

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Réponse

Une réponse réussie renvoie `204 no content`. Renvoie `404 not found` si le site du partenaire est introuvable.

## Propriétés de retour pour un domaine {#return-props-domain}

Une méthode `GET` qui renvoie des détails sur le domaine spécifié (pour les destinations de cookie uniquement).

<!-- r_get_partner_site.xml -->

### Requête

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Réponse

Une réponse réussie renvoie `200 OK` et des données comme illustré dans l’exemple ci-dessous. Renvoie `404 Not found` si l&#39;identifiant du site ou le partenaire est introuvable.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Propriétés de retour pour tous les domaines {#return-props-all-domains}

Une méthode `GET` qui renvoie des informations sur tous vos domaines (pour les destinations de cookie uniquement).

<!-- r_get_partner_sites.xml -->

### Requête

`GET https://api.demdex.com/v1/partner-sites/`

### Paramètres de requête facultatifs

Vous pouvez utiliser ces paramètres facultatifs avec des méthodes [!DNL API] qui renvoient *toutes* propriétés pour un objet. Définissez ces options dans la chaîne de requête lors de la transmission de cette requête à [!DNL API]. Voir [Paramètres facultatifs](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Trie et renvoie les résultats en fonction de la propriété JSON spécifiée. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Trie et renvoie les résultats dans l’ordre décroissant. La valeur ascendante est la valeur par défaut. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Renvoie des résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Par exemple, supposons que vous souhaitiez trouver des résultats pour tous les modèles ayant le mot "Test" dans l’un des champs de valeur de cet élément. Votre exemple de requête peut ressembler à ceci : <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Vous pouvez effectuer une recherche sur n’importe quelle valeur renvoyée par une méthode "get all". </p> </td>
  </tr> 
 </tbody> 
</table>

### Réponse

Une réponse réussie renvoie `200 OK` et des données dans un tableau comme illustré dans l’exemple ci-dessous. Renvoie `404 Not found` si l&#39;identifiant du site ou le partenaire est introuvable.

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
