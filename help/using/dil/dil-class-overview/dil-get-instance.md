---
description: Récupère une instance de DIL spécifique au partenaire.
keywords: api d’audience manager;api aam;api d’audience manager;api aam
seo-description: Récupère une instance de DIL spécifique au partenaire.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: Mise en oeuvre du DIL
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 15%

---

# getDil{#getdil}

Récupère une instance de DIL spécifique au partenaire.

**Signature de fonction :** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Paramètres

| Nom | Type | Description |
|---|---|---|
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | La valeur par défaut est `0`. Le NSID du conteneur que vous recherchez. Facultatif. |

## Réponse

Une correspondance NSID de conteneur et de partenaire réussie renvoie une instance [!UICONTROL DIL] spécifique au partenaire. S’il n’y a aucune correspondance, l’API renvoie (ne renvoie pas) une erreur avec le message &quot;`The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;.

## Exemple de code

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
