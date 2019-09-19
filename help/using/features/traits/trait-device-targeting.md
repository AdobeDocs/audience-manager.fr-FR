---
description: Décrit les paires clé-valeur communes au niveau de la plate-forme que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte Audience Manager.
seo-description: Décrit les paires clé-valeur communes au niveau de la plate-forme que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte Audience Manager.
seo-title: Ciblage De Périphériques Avec Clés Au Niveau De La Plateforme
solution: Audience Manager
title: Ciblage De Périphériques Avec Clés Au Niveau De La Plateforme
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Device Targeting With Platform-level Keys {#device-targeting-with-platform-level-keys}

Décrit les paires clé-valeur communes au niveau de la plate-forme que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées au périphérique sur toutes les propriétés de votre compte Audience Manager.

## Objectif des variables au niveau de la plateforme {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Les variables de niveau plate-forme vous permettent de prendre en compte les données transmises à partir d’un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre [!DNL Audience Manager] compte. Ces variables sont formées par des paires [clé-valeur](../../reference/key-value-pairs-explained.md) avec la clé précédée du préfixe `d_` comme illustré ci-dessous.

## Clés de niveau plateforme définies par l’agent utilisateur {#keys-user-agent}

L’ [!UICONTROL Data Collection Servers] utilisateur extrait les valeurs de ces clés de l’en-tête [de l’agent](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) utilisateur dans `HTTP` les requêtes. Les valeurs représentent des informations au niveau du périphérique issues de la [!UICONTROL Device Atlas] base de données. Les signaux du tableau ci-dessous sont disponibles, comme extrait de l’exemple de l’agent utilisateur. [Téléchargez la liste des clés](assets/device_keys.csv)les plus courantes, selon [!UICONTROL Device Atlas] les mesures.

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
>Même si un ou plusieurs signaux ne peuvent pas être extraits de l'en-tête de l'agent utilisateur, les autres signaux seront toujours transmis à l' [!UICONTROL Data Collection Servers]agent utilisateur.

>[!MORE_LIKE_This]
>
>* [Préfixe requis pour les variables clés](../../features/traits/trait-variable-prefixes.md)

