---
description: Code requis par DART Enterprise (et d’autres types de destination) pour capturer la valeur de l’ID utilisateur unique (UUID) d’Audience Manager.
seo-description: Code requis par DART Enterprise (et d’autres types de destination) pour capturer la valeur de l’ID utilisateur unique (UUID) d’Audience Manager.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie Code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` Code {#get-aamcookie-code}

Code requis par [!DNL DART Enterprise] (et d’autres types de destination) pour capturer la valeur de l’ID utilisateur unique ([!DNL UUID]) Audience Manager.

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
