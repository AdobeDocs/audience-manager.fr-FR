---
description: Code requis par DART Enterprise (et d’autres types de destination) pour capturer la valeur de l’ID utilisateur unique d’Audience Manager (UUID).
seo-description: Code requis par DART Enterprise (et d’autres types de destination) pour capturer la valeur de l’ID utilisateur unique d’Audience Manager (UUID).
seo-title: Code get_aamCookie
solution: Audience Manager
title: Code get_aamCookie
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 7d0735fa9620b7765db7be8d3a7c8731536ffd32
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 11%

---


# Code get_aamCookie {#get-aamcookie-code}

Code requis par [!DNL DART Enterprise] (et d’autres types de destination) pour capturer la valeur de l’ID utilisateur unique ([!DNL UUID]) d’Audience Manager.

Définissez cette fonction en haut de la page, idéalement dans le bloc de `<head>` code.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```
