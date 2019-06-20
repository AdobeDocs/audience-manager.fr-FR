---
description: Les pixels simples (qui peuvent être utilisés pour qualifier les utilisateurs pour les caractéristiques) effectuent des transferts de données en temps réel. L'interface Audience Manager permet aux clients de créer n'importe quel nombre de pixels en libre-service. Les chaînes pixel sont constituées d'identifiants simples ou de paires clé-valeur.
seo-description: Les pixels simples (qui peuvent être utilisés pour qualifier les utilisateurs pour les caractéristiques) effectuent des transferts de données en temps réel. L'interface Audience Manager permet aux clients de créer n'importe quel nombre de pixels en libre-service. Les chaînes pixel sont constituées d'identifiants simples ou de paires clé-valeur.
seo-title: Transferts de données basés sur un pixel
solution: Audience Manager
title: Transferts de données basés sur un pixel
uuid: 8773 bfc 0-6 b 8 d -4 a 6 a-a 8 b 7-e 043744486 ab
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Pixel-based Data Transfers {#pixel-based-data-transfers}

Les pixels simples (qui peuvent être utilisés pour qualifier les utilisateurs pour les caractéristiques) effectuent des transferts de données en temps réel. L&#39;interface Audience Manager permet aux clients de créer n&#39;importe quel nombre de pixels en libre-service. Les chaînes pixel sont constituées d&#39;identifiants simples ou de paires clé-valeur.

<!-- c_rt_inbound_pixel_transfers.xml -->

Pour activer les transferts de données entrants, le fournisseur et le client procéderont comme suit :

1. Déterminez les caractéristiques que vous souhaitez que le fournisseur ou le partenaire se déclenche.
1. Obtenez le pixel correspondant à la caractéristique. In the traits list screen, hover over the **[!UICONTROL Actions]** column and click the **[!UICONTROL Get trait URL]** symbol for the desired trait.
1. Provide the [!DNL URL] to the vendor or partner.

## Exemples

This basic event call sends trait ID 1234 to [!DNL Audience Manager].

```
https://something.demdex.net/event?d_sid=1234
```

You can serialize trait IDs in an event call to help reduce `HTTP` traffic from the page. Ajoutez d&#39;autres ID de caractéristique à la chaîne URL comme indiqué dans l&#39;exemple suivant :

```
https://something.demdex.net/event?d_sid=1234,5678,9876,5432
```
