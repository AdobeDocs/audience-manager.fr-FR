---
description: Décrit les paires clé-valeur de niveau plate-forme courantes que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte Audience Manager.
seo-description: Décrit les paires clé-valeur de niveau plate-forme courantes que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte Audience Manager.
seo-title: Ciblage des périphériques avec clés au niveau de la plateforme
solution: Audience Manager
title: Ciblage des périphériques avec clés au niveau de la plateforme
uuid: bc 048 cc 5-3 df 1-49 bc-ac 78-0 ea 5 d 7 edd 9 cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

Décrit les paires clé-valeur de niveau plate-forme courantes que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte Audience Manager.

## Purpose of Platform-level Variables {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Platform-level variables let you take data passed in from a particular site and make it available for targeting across all the properties in your [!DNL Audience Manager] account. These variables are formed by [key-value pairs](../../reference/key-value-pairs-explained.md) with the key prefixed by `d_` as shown below.

## Platform-level Keys Defined by User Agent {#keys-user-agent}

The [!UICONTROL Data Collection Servers] extract the values for these keys from the [user agent header](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` requests. The values represent device-level information from the [!UICONTROL Device Atlas] database. Les signaux du tableau ci-dessous sont disponibles, comme extrait depuis l&#39;exemple de l&#39;agent utilisateur. [Téléchargez une liste des clés](assets/device_keys.csv)les plus courantes, selon [!UICONTROL Device Atlas] les mesures.

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
>Even if one or more signals cannot be retrieved from the user agent header, the other signals will still be passed to the [!UICONTROL Data Collection Servers].

>[!MORE_ LIKE_ THIS]
>
>* [Exigences en matière de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

