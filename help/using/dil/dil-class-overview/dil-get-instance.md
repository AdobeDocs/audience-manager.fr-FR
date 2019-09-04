---
description: Récupère une instance DIL spécifique au partenaire.
keywords: audience manager api ; aam api ; audience manager apis ; aam apis
seo-description: Récupère une instance DIL spécifique au partenaire.
seo-title: Getdil
solution: Audience Manager
title: Getdil
uuid: 7 b 95 f 9 bf -14 c 0-4 c 74-b 6 b 9-d 6 b 38513 d 487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Getdil{#getdil}

Récupère une instance DIL spécifique au partenaire.

**Signature de fonction :**`getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Paramètres

| Nom | Type | Description |
|---|---|---|
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | Valeurs par défaut `0`: NSID du conteneur que vous recherchez. Facultatif. |

## Réponse

Une correspondance NSID de partenaire et de conteneur réussie renvoie une [!UICONTROL DIL] instance spécifique au partenaire. S'il n'y a aucune correspondance, l'API renvoie (ne renvoie pas) une erreur avec le message, «  `The DIL instance with partner <name> and containerNSID <ID> was not found.` »

## Exemple de code

<pre class="java"><code>DIL. getdil ('<i>partner</i>', <i>containernsid</i>) ; 
DIL. getdil ('<i>partner</i>') ;</code></pre>
