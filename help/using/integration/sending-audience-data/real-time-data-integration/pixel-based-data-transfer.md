---
description: Les pixels simples (qui peuvent être utilisés pour définir les caractéristiques des utilisateurs) effectuent des transferts de données en temps réel. L’interface d’Audience Manager permet aux clients de créer n’importe quel nombre de pixels en libre-service. Les chaînes en pixels sont composées d’ID simples ou de paires clé-valeur.
seo-description: Les pixels simples (qui peuvent être utilisés pour définir les caractéristiques des utilisateurs) effectuent des transferts de données en temps réel. L’interface d’Audience Manager permet aux clients de créer n’importe quel nombre de pixels en libre-service. Les chaînes en pixels sont composées d’ID simples ou de paires clé-valeur.
seo-title: Transferts de données basés sur des pixels
solution: Audience Manager
title: Transferts de données basés sur des pixels
uuid: 8773bfc0-6b8d-4a6a-a8b7-e04374486ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Transferts de données basés sur des pixels {#pixel-based-data-transfers}

Les pixels simples (qui peuvent être utilisés pour définir les caractéristiques des utilisateurs) effectuent des transferts de données en temps réel. L’interface d’Audience Manager permet aux clients de créer n’importe quel nombre de pixels en libre-service. Les chaînes en pixels sont composées d’ID simples ou de paires clé-valeur.

<!-- c_rt_inbound_pixel_transfers.xml -->

Pour activer les transferts de données entrants, le fournisseur et le client doivent :

1. Déterminez les caractéristiques que vous souhaitez que le fournisseur ou le partenaire se déclenche.
1. Obtenez le pixel pour le trait. Dans l’écran de liste des caractéristiques, passez la souris sur la **[!UICONTROL Actions]** colonne et cliquez sur le **[!UICONTROL Get trait URL]** symbole correspondant à la caractéristique souhaitée.
1. Fournissez le [!DNL URL] service au fournisseur ou au partenaire.

## Exemples

Cet appel d’événement de base envoie l’ID de caractéristique 1234 à [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Vous pouvez sérialiser les ID de caractéristique dans un appel d’événement afin de réduire `HTTP` le trafic à partir de la page. Ajoutez d’autres ID de caractéristique à la chaîne URL, comme illustré dans l’exemple suivant :

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
