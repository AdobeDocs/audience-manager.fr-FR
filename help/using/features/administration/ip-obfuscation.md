---
description: Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.
seo-description: Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.
solution: Audience Manager
title: Obscurcissement d’adresses IP
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# Obscurcissement d’adresses IP {#ip-obfuscation}

Utilisez cette fonctionnalité pour obscurcir les adresses IP collectées dans Audience Manager.

## Overview and Methodology {#overview-and-methodology}

Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.

### Méthodologie d&#39;obscurcissement d&#39;IP

Conformément aux principes de « Respect de la vie privée par conception », Adobe Audience Manager permet aux clients d&#39;activer l&#39;obscurcissement des adresses IP depuis l&#39;interface utilisateur, soit globalement dans toutes les régions géographiques, soit pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (la dernière partie) de l&#39;adresse IP est immédiatement ignoré lorsque l&#39;adresse IP est assimilée dans Audience Manager. Audience Manager ignore cette partie de l&#39;adresse IP avant le traitement (y compris avant toute recherche ou journalisation géographique facultative de l&#39;adresse IP). Par exemple :

* Before obfuscation: `255.255.255.255`
* After obfuscation: `255.255.255.0`

See also, Collecting IP addresses and IP Address Obfuscation in our [Data Privacy section](/help/using/overview/data-security-and-privacy/data-privacy.md).

## IP Address Obfuscation Requirements {#ip-obfuscation-requirements}

L&#39;obscurcissement d&#39;adresses IP est disponible uniquement pour les comptes administrateur d&#39;Audience Manager. See [Create Users](/help/using/features/administration/administration-overview.md#create-users) to understand how to assign administrator privileges for a user.

>[!NOTE]
>
> En raison du volume élevé de données traitées par Audience Manager, les changements d&#39;obscurcissement d&#39;IP peuvent prendre jusqu&#39;à 4 heures, dès lors que vous mettez à jour les paramètres.

## Configure IP Address Obfuscation {#configure-ip-obfuscation}

Suivez les étapes ci-dessous pour configurer l&#39;obscurcissement des adresses IP.

1. Log in to Audience Manager with an administrator account and go to **Administration &gt; Privacy**.
2. Choisissez le type d&#39;obscurcissement d&#39;IP à utiliser.
   1. **Obscurcir toutes les adresses IP :** sélectionnez cette option pour que Audience Manager obscurcit le dernier octet de toutes les adresses IP du visiteur, quelle que soit la région de provenance.
   2. **Obscurcir les adresses IP pour des pays spécifiques :** sélectionnez cette option pour que Audience Manager obscurcit le dernier octet des adresses IP du visiteur pour des pays spécifiques. Use the **List of Countries** or the corresponding **Search** field to find the countries to enable IP obfuscation for, and click the + icon to add them to the **Selected for Obfuscation** list. Once you&#39;ve added all the required countries to the **Selected for Obfuscation** list, click **Save**.

![](assets/ip-obfuscation.png)

## Disable IP Address Obfuscation {#disable-ip-obfuscation}

To disable IP address obfuscation globally, go to **Administration &gt; Privacy**, select **Do not obfuscate IP addresses**, and click **Save**.

To disable IP address obfuscation for specific countries, find the countries in the **Selected for Obfuscation** list, then click their corresponding **X** icon. Click **Save** when you&#39;re done.

## Concepts associés {#related-concepts}

* [Confidentialité des données](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Démonstration vidéo obscurcissement d&#39;adresses IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=fre_fr)

