---
description: Récupère une valeur spécifique d’un serveur de publicités.
seo-description: Récupère une valeur spécifique d’un serveur de publicités.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: Mise en oeuvre du DIL
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 17%

---

# dexGetQSVars{#dexgetqsvars}

Récupère une valeur spécifique d’un serveur de publicités.

**Signature de fonction :** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `variableName` | Chaîne | Nom de la variable pour laquelle vous souhaitez obtenir une valeur. |
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | [!DNL NSID] du conteneur que vous recherchez. La valeur par défaut est `0`. |

**Réponse**

Renvoie la valeur de la variable pour une instance [!UICONTROL DIL].

**Exemple de code**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
