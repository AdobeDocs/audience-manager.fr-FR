---
description: Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées à l’appareil dans toutes les propriétés de votre compte d’Audience Manager.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Ciblage des périphériques à l’aide de clés au niveau des plateformes
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 5%

---

# Ciblage des périphériques à l’aide de clés au niveau des plateformes {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google a mis à jour les fonctionnalités de [!DNL Google Chrome] et tout [!DNL Chromium]des navigateurs basés sur afin de minimiser les informations collectées au moyen de la variable `User-Agent` en-tête .
>Depuis mars 2023, Audience Manager prend en charge ces mises à jour en exploitant les [SDK Web Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en). Pour continuer à utiliser les informations de caractéristiques fournies via la variable `User-Agent` en-tête, vous devez utiliser [SDK Web](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) et activez [Conseils client User-Agent à forte entrée](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en).
>Ces mises à jour ne sont pas prises en charge par [DIL](../../../using/dil/dil-overview.md), donc les clients d’Audience Manager qui utilisent [!DNL DIL] ne pourront pas collecter d’informations sur les caractéristiques via le `User-Agent` en-tête .

Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées à l’appareil dans toutes les propriétés de votre compte d’Audience Manager.

## Objectif des variables au niveau de la plateforme {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Les variables au niveau de la plateforme vous permettent de récupérer les données transmises à partir d’un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre [!DNL Audience Manager] compte . Ces variables sont formées par [paires clé-valeur](../../reference/key-value-pairs-explained.md) avec la clé précédée de `d_` comme illustré ci-dessous.

## Clés définies par l’agent utilisateur au niveau de la plateforme {#keys-user-agent}

Le [!UICONTROL Data Collection Servers] extraire les valeurs de ces clés à partir de la fonction [en-tête de l’agent utilisateur](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) in `HTTP` requêtes. Les valeurs représentent des informations au niveau de l’appareil provenant de la variable [!UICONTROL Device Atlas] base de données. Les signaux du tableau ci-dessous sont disponibles, comme extrait de l’exemple de l’agent utilisateur. [Télécharger une liste des clés les plus courantes](assets/device_keys.csv), en fonction de [!UICONTROL Device Atlas] mesures.

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
>Même si un ou plusieurs signaux ne peuvent pas être récupérés à partir de l’en-tête de l’agent utilisateur, les autres signaux seront toujours transmis à la fonction [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

