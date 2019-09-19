---
description: Envoyez des données à l’API DCS à l’aide des méthodes GET ou POST.
seo-description: Envoyez des données à l’API DCS à l’aide des méthodes GET ou POST.
seo-title: ' Méthodes de l’API DCS'
solution: Audience Manager
title: ' Méthodes de l’API DCS'
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# Méthodes de l’API DCS {#dcs-api-methods}

Envoyez des données à l’utilisateur [!UICONTROL DCS] à l’aide [!DNL API] ou `GET` `POST` de méthodes.

Vous pouvez envoyer des données à l’ [!UICONTROL DCS] utilisateur à l’aide de l’une des méthodes `GET` ou `POST` . Examinez les exemples d’appels ci-dessous, à l’aide de [curl](https://curl.haxx.se/). Dans les trois exemples d’appels, nous ajoutons les signaux `c_likes = famous popstar` et `c_loves = famous actress` au profil du périphérique `12345678901234567890123456789012345678`.


## Envoyer des données via GET {#send-data-via-get}

Notez que la taille maximale autorisée pour les `GET` appels est de 8 Ko.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Envoyer des données via POST {#send-data-via-post}

Notez les conditions requises pour envoyer des données à l’aide de la `POST` méthode :

* La taille maximale autorisée est de 32 Ko.
* Définissez le type de contenu sur `application/x-www-form-urlencoded`.

### Exemple d’appel

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
