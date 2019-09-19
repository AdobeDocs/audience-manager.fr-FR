---
description: Récupère une instance DIL spécifique au partenaire.
keywords: api du gestionnaire d’audiences;api aam;apis du gestionnaire d’audiences;apis aam
seo-description: Récupère une instance DIL spécifique au partenaire.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# getDil{#getdil}

Récupère une instance DIL spécifique au partenaire.

**** Signature de fonction : `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Paramètres

| Nom | Type | Description |
|---|---|---|
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | Les valeurs par défaut sont `0`. Le NSID du conteneur que vous recherchez. Facultatif. |

## Réponse

Une correspondance NSID de partenaire et de conteneur réussie renvoie une [!UICONTROL DIL] instance spécifique au partenaire. En l’absence de correspondance, l’API renvoie (ne renvoie pas) une erreur avec le message " `The DIL instance with partner <name> and containerNSID <ID> was not found.`".

## Exemple de code

<pre class="java"><code>DIL.getDil('<i>partenaire</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partenaire</i>');</code></pre>
