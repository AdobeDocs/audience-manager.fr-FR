---
description: Décrit les paires clé-valeur communes au niveau de la plate-forme que vous pouvez utiliser pour cible les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte d’Audience Manager.
seo-description: Décrit les paires clé-valeur communes au niveau de la plate-forme que vous pouvez utiliser pour cible les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte d’Audience Manager.
seo-title: Ciblage des périphériques à l’aide de clés au niveau des plateformes
solution: Audience Manager
title: Ciblage des périphériques à l’aide de clés au niveau des plateformes
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 9%

---


# Ciblage des périphériques à l’aide de clés au niveau des plateformes {#device-targeting-with-platform-level-keys}

Décrit les paires clé-valeur communes au niveau de la plate-forme que vous pouvez utiliser pour cible les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte d’Audience Manager.

## Objet des variables au niveau de la plate-forme {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Les variables au niveau de la plate-forme vous permettent de prendre les données transmises à partir d&#39;un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre compte [!DNL Audience Manager]. Ces variables sont formées par des paires [clé-valeur](../../reference/key-value-pairs-explained.md) avec la clé précédée de `d_` comme indiqué ci-dessous.

## Clés de niveau plate-forme définies par l&#39;agent utilisateur {#keys-user-agent}

[!UICONTROL Data Collection Servers] extrait les valeurs de ces clés de l&#39;en-tête de l&#39;agent utilisateur [](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) dans les requêtes `HTTP`. Les valeurs représentent des informations au niveau du périphérique provenant de la base de données [!UICONTROL Device Atlas]. Les signaux du tableau ci-dessous sont disponibles, comme extrait de l&#39;exemple de l&#39;agent utilisateur. [Téléchargez une liste des clés](assets/device_keys.csv) les plus courantes, selon  [!UICONTROL Device Atlas] les mesures.

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>Même si un ou plusieurs signaux ne peuvent pas être extraits de l&#39;en-tête de l&#39;agent utilisateur, les autres signaux seront toujours transmis à [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

