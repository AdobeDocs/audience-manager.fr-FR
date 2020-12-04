---
description: AamGpt est une fonction JavaScript qui lit les données des cookies d’Audience Manager et envoie ces informations à Google Publisher Tags.
seo-description: AamGpt est une fonction JavaScript qui lit les données des cookies d’Audience Manager et envoie ces informations à Google Publisher Tags.
seo-title: Code Audience Manager pour les Google Publisher Tags
solution: Audience Manager
title: Code Audience Manager pour les Google Publisher Tags
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: c63467dec62ff08c3cd32f19ac2e4675c9ce18e3
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 19%

---


# Code Audience Manager pour les Google Publisher Tags {#audience-manager-code-for-google-publisher-tags}

`AamGpt` est une  [!DNL JavaScript] fonction qui lit les données des cookies d&#39;Audience Manager et envoie ces informations à  [!DNL Google Publisher Tags].

>[!NOTE]
>
>Cette fonction n&#39;est pas requise si vous disposez de votre propre code pour lire les données des cookies d&#39;Audience Manager provenant des cookies [!UICONTROL UUID] et de destination.

## Exemple de code

Placez le code `AamGpt` en haut de la page, idéalement dans le bloc de code `<head>`. Le code `AamGpt` est disponible ci-dessous :

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```
