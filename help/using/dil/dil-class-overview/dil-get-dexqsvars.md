---
description: Récupère une valeur spécifique à partir d'un serveur d'annonces.
seo-description: Récupère une valeur spécifique à partir d'un serveur d'annonces.
seo-title: Dexgetqsvars
solution: Audience Manager
title: Dexgetqsvars
uuid: 6 d 21 c 7 a 4-43 f 8-456 b -8831-47343 dbb 047 e
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# dexGetQSVars{#dexgetqsvars}

Récupère une valeur spécifique à partir d&#39;un serveur d&#39;annonces.

**Signature de fonction :**`dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Paramètres**

| Nom | Type | Description |
|---|---|---|
| `variableName` | Chaîne | Nom de la variable pour laquelle vous souhaitez obtenir une valeur. |
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | The [!DNL NSID] of the container you&#39;re searching for. Defaults is `0`. |

**Réponse**

Returns the variable value for a [!UICONTROL DIL] instance.

**Exemple de code**

<pre class="java"><code>var value = DIL. dexgetqsvars ('<i>variablename</i>','<i>partnername</i>',<i>containernsid</i>) ;</code>
</pre>
