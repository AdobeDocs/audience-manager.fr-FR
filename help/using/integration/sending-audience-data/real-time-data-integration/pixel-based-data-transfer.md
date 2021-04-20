---
description: Les pixels simples (qui peuvent être utilisés pour définir les caractéristiques des utilisateurs) effectuent des transferts de données en temps réel. L’interface d’Audience Manager permet aux clients de créer n’importe quel nombre de pixels en libre-service. Les chaînes en pixels se composent d’identifiants simples ou de paires clé-valeur.
seo-description: Les pixels simples (qui peuvent être utilisés pour définir les caractéristiques des utilisateurs) effectuent des transferts de données en temps réel. L’interface d’Audience Manager permet aux clients de créer n’importe quel nombre de pixels en libre-service. Les chaînes en pixels se composent d’identifiants simples ou de paires clé-valeur.
seo-title: Transferts de données basées sur des pixels
solution: Audience Manager
title: Transferts de données basées sur des pixels
uuid: 8773bfc0-6b8d-4a6a-a8b7-e043744486ab
feature: Inbound Data Transfers
exl-id: fe9ecb97-4a45-4fbb-855e-01df007144cf
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 5%

---

# Transferts de données basées sur des pixels {#pixel-based-data-transfers}

Les pixels simples (qui peuvent être utilisés pour définir les caractéristiques des utilisateurs) effectuent des transferts de données en temps réel. L’interface d’Audience Manager permet aux clients de créer n’importe quel nombre de pixels en libre-service. Les chaînes en pixels se composent d’identifiants simples ou de paires clé-valeur.

<!-- c_rt_inbound_pixel_transfers.xml -->

Pour activer les transferts de données entrants, le fournisseur et le client doivent :

1. Déterminez quelles caractéristiques vous souhaitez que le fournisseur ou le partenaire se déclenche.
1. Obtenez le pixel pour la caractéristique. Dans l’écran de liste des caractéristiques, passez la souris sur la colonne **[!UICONTROL Actions]** et cliquez sur le symbole **[!UICONTROL Get trait URL]** correspondant à la caractéristique souhaitée.
1. Fournissez le [!DNL URL] au fournisseur ou au partenaire.

## Exemples

Cet appel de événement de base envoie l’ID de caractéristique 1234 à [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

Vous pouvez sérialiser les identifiants de caractéristiques dans un appel de événement afin de réduire le trafic `HTTP` de la page. Ajoutez d’autres ID de caractéristique à la chaîne URL, comme indiqué dans l’exemple suivant :

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
