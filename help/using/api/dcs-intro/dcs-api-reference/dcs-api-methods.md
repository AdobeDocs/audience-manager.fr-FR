---
description: Envoyez des données à l’API DCS à l’aide de méthodes de GET ou de POST.
seo-description: Envoyez des données à l’API DCS à l’aide de méthodes de GET ou de POST.
seo-title: Méthodes d’API DCS
solution: Audience Manager
title: Méthodes d’API DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 6%

---


# [!DNL DCS] [!DNL API] Méthodes {#dcs-api-methods}

Envoyez les données à [!DNL DCS] [!DNL API] en utilisant les méthodes `GET` ou `POST`.

Vous pouvez envoyer des données à [!DNL DCS] à l&#39;aide de l&#39;une des méthodes `GET` ou `POST`. Consultez les exemples d’appels ci-dessous, en utilisant [curl](https://curl.haxx.se/). Dans les trois exemples d&#39;appels, nous ajoutons les signaux `c_likes = famous popstar` et `c_loves = famous actress` au profil de l&#39;appareil `12345678901234567890123456789012345678`.

## Envoyer des données par [!DNL GET] {#send-data-via-get}

Notez que la taille maximale autorisée pour les appels `GET` est de 8 Ko.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Envoyer des données par [!DNL POST] {#send-data-via-post}

Notez les conditions requises pour envoyer des données à l&#39;aide de la méthode `POST` :

* La taille maximale autorisée est de 32 Ko.
* Définissez le type de contenu sur `application/x-www-form-urlencoded`.

### Exemple d’appel

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
