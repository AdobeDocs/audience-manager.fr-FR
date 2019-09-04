---
description: Récupère une valeur spécifique à partir d'un serveur d'annonces.
seo-description: Récupère une valeur spécifique à partir d'un serveur d'annonces.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Dexgetqsvars{#dexgetqsvars}

Récupère une valeur spécifique à partir d'un serveur d'annonces.

**Signature de fonction :**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `variableName` | Chaîne | Nom de la variable pour laquelle vous souhaitez obtenir une valeur. |
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | Le [!DNL NSID] conteneur que vous recherchez. Valeurs par défaut `0`: |

**Réponse**

Renvoie la valeur de variable d' [!UICONTROL DIL] une instance.

**Exemple de code**

<pre class="java"><code>var value = DIL. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>) ;</code></pre>
