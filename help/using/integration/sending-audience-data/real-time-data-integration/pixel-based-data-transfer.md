---
description: Les pixels simples (qui peuvent être utilisés pour qualifier les utilisateurs de caractéristiques) effectuent des transferts de données en temps réel. L’interface d’Audience Manager permet aux clients de créer un nombre illimité de pixels en libre-service. Les chaînes en pixels se composent d’identifiants simples ou de paires clé-valeur.
seo-description: Simple pixels (that can be used to qualify users for traits) perform real-time data transfers. The Audience Manager interface lets clients create any number of pixels on a self-service basis. Pixel strings consist of simple IDs or key-value pairs.
seo-title: Pixel-based Data Transfers
solution: Audience Manager
title: Transferts de données basées sur des pixels
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 0%

---

# Transferts de données basées sur des pixels {#pixel-based-data-transfers}

Les pixels simples (qui peuvent être utilisés pour qualifier les utilisateurs de caractéristiques) effectuent des transferts de données en temps réel. L’interface d’Audience Manager permet aux clients de créer un nombre illimité de pixels en libre-service. Les chaînes en pixels se composent d’identifiants simples ou de paires clé-valeur.

<!-- c_rt_inbound_pixel_transfers.xml -->

Pour activer les transferts de données entrants, le fournisseur et le client :

1. Déterminez les caractéristiques que vous souhaitez que le fournisseur ou le partenaire déclenche.
1. Obtenez le pixel de la caractéristique. Dans l’écran de liste des caractéristiques, passez la souris sur la colonne **[!UICONTROL Actions]** et cliquez sur le symbole **[!UICONTROL Get trait URL]** correspondant à la caractéristique souhaitée.
1. Fournissez le [!DNL URL] au fournisseur ou au partenaire.

## Exemples

Cet appel d’événement de base envoie l’ID de caractéristique 1234 à [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Vous pouvez sérialiser les identifiants de caractéristique dans un appel d’événement pour réduire le trafic `HTTP` de la page. Ajoutez des identifiants de caractéristiques supplémentaires à la chaîne d’URL, comme illustré dans l’exemple suivant :

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
