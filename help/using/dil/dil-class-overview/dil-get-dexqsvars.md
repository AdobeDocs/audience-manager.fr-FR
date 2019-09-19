---
description: Récupère une valeur spécifique d’un serveur d’annonces.
seo-description: Récupère une valeur spécifique d’un serveur d’annonces.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# dexGetQSVars{#dexgetqsvars}

Récupère une valeur spécifique d’un serveur d’annonces.

**** Signature de fonction : `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `variableName` | Chaîne | Nom de la variable pour laquelle vous souhaitez obtenir une valeur. |
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | Le conteneur [!DNL NSID] que vous recherchez. Les valeurs par défaut sont `0`. |

**Réponse**

Renvoie la valeur de la variable pour une [!UICONTROL DIL] instance.

**Exemple de code**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
