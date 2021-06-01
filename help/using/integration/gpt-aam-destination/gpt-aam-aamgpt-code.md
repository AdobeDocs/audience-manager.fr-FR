---
description: AamGpt est une fonction JavaScript qui lit les données de cookie d’Audience Manager et envoie ces informations à Google Publisher Tags.
seo-description: AamGpt est une fonction JavaScript qui lit les données de cookie d’Audience Manager et envoie ces informations à Google Publisher Tags.
seo-title: Code Audience Manager pour les Google Publisher Tags
solution: Audience Manager
title: Code Audience Manager pour les Google Publisher Tags
uuid: 24ff5d16-b360-46cc-a4c6-6db34d7fda75
feature: Intégration tierce
exl-id: 04e74399-7b6a-400e-a1e6-94fe296e7209
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 19%

---

# Code Audience Manager pour les Google Publisher Tags {#audience-manager-code-for-google-publisher-tags}

`AamGpt` est une  [!DNL JavaScript] fonction qui lit les données de cookie d’Audience Manager et envoie ces informations à  [!DNL Google Publisher Tags].

>[!NOTE]
>
>Cette fonction n’est pas requise si vous disposez de votre propre code pour lire les données de cookies d’Audience Manager provenant des cookies [!UICONTROL UUID] et de destination.

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
