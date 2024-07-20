---
description: Envoyez des données à l’API DCS à l’aide de méthodes de GET ou de POST.
seo-description: Send data to the DCS API using GET or POST methods.
seo-title: DCS API Methods
solution: Audience Manager
title: Méthodes d’API DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
exl-id: 258994e1-6b15-4ae1-9e1f-c6e0685350c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '99'
ht-degree: 0%

---

# [!DNL DCS] [!DNL API] Méthodes {#dcs-api-methods}

Envoyez des données à [!DNL DCS] [!DNL API] à l’aide des méthodes `GET` ou `POST`.

Vous pouvez envoyer des données à [!DNL DCS] à l’aide de l’une des méthodes `GET` ou `POST`. Consultez les exemples d’appels ci-dessous à l’aide de [curl](https://curl.haxx.se/). Dans les trois exemples d’appels, nous ajoutons les signaux `c_likes = famous popstar` et `c_loves = famous actress` au profil de l’appareil `12345678901234567890123456789012345678`.

## Envoi de données via [!DNL GET] {#send-data-via-get}

Notez que la taille maximale autorisée pour les appels `GET` est de 8 Ko.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Envoi de données via [!DNL POST] {#send-data-via-post}

Notez les conditions requises pour envoyer des données à l’aide de la méthode `POST` :

* La taille maximale autorisée est de 32 Ko.
* Définissez le type de contenu sur `application/x-www-form-urlencoded`.

### Exemple d’appel

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
