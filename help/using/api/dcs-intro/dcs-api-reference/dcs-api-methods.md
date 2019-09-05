---
description: Envoyez des données à l'API DCS à l'aide des méthodes GET ou POST.
seo-description: Envoyez des données à l'API DCS à l'aide des méthodes GET ou POST.
seo-title: Méthodes de l'API DCS
solution: Audience Manager
title: Méthodes de l'API DCS
uuid: 6 e 407458-11 d 4-4342-a 84 a -512 afa 5 fc 183
translation-type: tm+mt
source-git-commit: bdea2609b84d7f80d67452b4c43e11cbef01a368

---


# Méthodes de l'API DCS {#dcs-api-methods}

Envoyer des données à [!UICONTROL DCS][!DNL API] l'utilisation `GET` ou `POST` aux méthodes.

Vous pouvez envoyer des données à l [!UICONTROL DCS] 'aide de l'une ou l'autre des `GET``POST` méthodes. Examinez les exemples d'appels ci-dessous, à l'aide [de curl](https://curl.haxx.se/). Dans les trois exemples d'appel, nous ajoutons les signaux `c_likes = famous popstar` et `c_loves = famous actress` le profil `12345678901234567890123456789012345678`du périphérique.


## Envoyer des données via GET {#send-data-via-get}

Notez que la taille maximale autorisée pour `GET` les appels est 8 K.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Envoi de données par le biais de POST {#send-data-via-post}

Notez les conditions requises pour envoyer des données à l'aide de `POST` la méthode :

* La taille maximale autorisée est de 32 K.
* Définissez le type de contenu sur `application/x-www-form-urlencoded`.

### Exemple d'appel

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
