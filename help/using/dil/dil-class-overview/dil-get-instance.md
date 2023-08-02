---
description: Récupère une instance de DIL spécifique au partenaire.
keywords: api d’audience manager;api aam;api d’audience manager;api aam
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 7%

---

# getDil{#getdil}

>[!WARNING]
>
>Depuis juillet 2023, l’Adobe a cessé de développer la [!DNL Data Integration Library (DIL)] et la variable [!DNL DIL] extension .
>
>Les clients existants peuvent continuer à utiliser leurs [!DNL DIL] implémentation. Cependant, l’Adobe ne se développera pas. [!DNL DIL] au-delà de ce point. Les clients sont encouragés à évaluer [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) pour leur stratégie de collecte de données à long terme.
>
>Les clients qui souhaitent mettre en oeuvre de nouvelles intégrations de collecte de données après juillet 2023 doivent utiliser [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) au lieu de .

Récupère une instance de DIL spécifique au partenaire.

**Signature de fonction :** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Paramètres

| Nom | Type | Description |
|---|---|---|
| `partner` | Chaîne | Nom du partenaire à rechercher. |
| `containerNSID` | Entier | La valeur par défaut est `0`. Le NSID du conteneur que vous recherchez. Facultatif. |

## Réponse

Une correspondance NSID de conteneur et de partenaire réussie renvoie un partenaire spécifique [!UICONTROL DIL] instance. Si aucune correspondance n’est trouvée, l’API renvoie (ne renvoie pas) une erreur avec le message : &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Exemple de code

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
