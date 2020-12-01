---
description: Code requis par DART Enterprise (et d’autres types de destination) pour capturer la valeur de l’ID utilisateur unique d’Audience Manager (UUID).
seo-description: Code requis par DART Enterprise (et d’autres types de destination) pour capturer la valeur de l’ID utilisateur unique d’Audience Manager (UUID).
seo-title: Code get_aamCookie
solution: Audience Manager
title: Code get_aamCookie
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 9%

---


# `get_aamCookie` Code {#get-aamcookie-code}

Code requis par [!DNL DART Enterprise] (et d&#39;autres types de destination) pour capturer la valeur de l&#39;ID utilisateur unique de l&#39;Audience Manager ([!DNL UUID]).

Définissez cette fonction en haut de la page, idéalement dans le bloc de codes `<head>`.

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
