---
description: Récupère une instance DIL spécifique au partenaire.
keywords: audience manager api ; aam api ; audience manager apis ; aam apis
seo-description: Récupère une instance DIL spécifique au partenaire.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: 128368669163097e604f6b23ab538341adcf8d7a

---


# getDil{#getdil}

Récupère une instance DIL spécifique au partenaire.

**Signature de fonction :**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Paramètres

| Nom | Type | Description |
|---|---|---|
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | Defaults is `0`. NSID du conteneur que vous recherchez. Facultatif. |

## Réponse

A successful partner and container NSID match returns a partner-specific [!UICONTROL DIL] instance. If there is no match, the API returns (does not throw) an error with the message, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Exemple de code

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>) ; 
DIL. getdil ('<i>partner</i>') ;</code>
</pre>
