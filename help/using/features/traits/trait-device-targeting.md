---
description: Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées à l’appareil dans toutes les propriétés de votre compte d’Audience Manager.
seo-description: Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées à l’appareil dans toutes les propriétés de votre compte d’Audience Manager.
seo-title: Ciblage des périphériques à l’aide de clés au niveau des plateformes
solution: Audience Manager
title: Ciblage des périphériques à l’aide de clés au niveau des plateformes
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: 'Caractéristiques '
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 9%

---

# Ciblage des périphériques à l’aide de clés au niveau des plateformes {#device-targeting-with-platform-level-keys}

Décrit les paires clé-valeur courantes au niveau de la plateforme que vous pouvez utiliser pour cibler les utilisateurs avec des variables liées à l’appareil dans toutes les propriétés de votre compte d’Audience Manager.

## Objectif des variables au niveau de la plateforme {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Les variables au niveau de la plateforme vous permettent de prendre les données transmises à partir d’un site particulier et de les rendre disponibles pour le ciblage sur toutes les propriétés de votre compte [!DNL Audience Manager]. Ces variables sont formées par des [paires clé-valeur](../../reference/key-value-pairs-explained.md) avec le préfixe clé `d_` comme illustré ci-dessous.

## Clés définies par l’agent utilisateur au niveau de la plateforme {#keys-user-agent}

[!UICONTROL Data Collection Servers] extrait les valeurs de ces clés de l’en-tête [de l’agent utilisateur](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) dans les demandes `HTTP`. Les valeurs représentent des informations au niveau de l’appareil de la base de données [!UICONTROL Device Atlas]. Les signaux du tableau ci-dessous sont disponibles, comme extrait de l’exemple de l’agent utilisateur. [Téléchargez une liste des clés](assets/device_keys.csv) les plus courantes, selon les  [!UICONTROL Device Atlas] mesures.

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
>Même si un ou plusieurs signaux ne peuvent pas être récupérés à partir de l’en-tête de l’agent utilisateur, les autres signaux seront toujours transmis à la balise [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)

