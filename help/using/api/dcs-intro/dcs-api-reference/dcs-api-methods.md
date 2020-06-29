---
description: Envoyez des données à l’API DCS à l’aide des méthodes GET ou POST.
seo-description: Envoyez des données à l’API DCS à l’aide des méthodes GET ou POST.
seo-title: Méthodes de l’API DCS
solution: Audience Manager
title: Méthodes de l’API DCS
uuid: 6e407458-11d4-4342-a84a-512afa5fc183
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 0%

---


# [!DNL DCS] [!DNL API] Méthodes {#dcs-api-methods}

Envoyez des données à l’ [!DNL DCS] utilisateur à l’ [!DNL API] aide `GET` ou `POST` de méthodes.

Vous pouvez envoyer des données à l’ [!DNL DCS] utilisateur à l’aide de l’une des méthodes `GET` ou `POST` . Consultez les exemples d’appels ci-dessous, en utilisant [curl](https://curl.haxx.se/). Dans les trois exemples d&#39;appels, nous ajoutons les signaux `c_likes = famous popstar` et `c_loves = famous actress` au profil de l&#39;appareil `12345678901234567890123456789012345678`.

## Envoyer des données via [!DNL GET] {#send-data-via-get}

Notez que la taille maximale autorisée pour les `GET` appels est de 8 Ko.

```
curl -i "yourcompany.demdex.net/event?d_uuid=12345678901234567890123456789012345678&d_rtbd=json&c_likes=famous%20popstar&c_loves=famous%20actress"
```

## Envoyer des données via [!DNL POST] {#send-data-via-post}

Notez les conditions requises pour l’envoi de données à l’aide de la `POST` méthode :

* La taille maximale autorisée est de 32 Ko.
* Définissez le type de contenu sur `application/x-www-form-urlencoded`.

### Exemple d’appel

```js
curl -X POST \
  https://yourcompany.demdex.net/event \
  -H 'content-type: application/x-www-form-urlencoded' \
  -d 'c_likes=famous%20popstar&c_loves=famous%20actress&d_uuid=12345678901234567890123456789012345678'
```
