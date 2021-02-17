---
description: Récupère une instance de DIL spécifique au partenaire.
keywords: api du gestionnaire d’audiences ; api aam ; apis du gestionnaire d’audiences ; apis aam
seo-description: Récupère une instance de DIL spécifique au partenaire.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '83'
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

Une correspondance NSID de partenaire et de conteneur réussie renvoie une instance [!UICONTROL DIL] spécifique au partenaire. S&#39;il n&#39;y a aucune correspondance, l&#39;API renvoie (ne renvoie pas) une erreur avec le message &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;.

## Exemple de code

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
