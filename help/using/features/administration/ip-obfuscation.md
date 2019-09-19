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

## Aperçu et méthodologie {#overview-and-methodology}

Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.

### Méthodologie d’obscurcissement d’IP

Conformément aux principes de "Confidentialité par conception", Adobe Audience Manager permet aux clients d’activer l’obscurcissement d’IP à partir de l’interface utilisateur, que ce soit globalement dans toutes les régions géographiques ou pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (dernière partie) de l’adresse IP est immédiatement ignoré lorsque l’adresse IP est assimilée à Audience Manager. Audience Manager ignore cette partie de l’adresse IP avant le traitement (y compris avant toute recherche géographique ou journalisation facultative de l’adresse IP). Par exemple :

* Avant l'obscurcissement : `255.255.255.255`
* Après obscurcissement : `255.255.255.0`

Voir aussi Collecte des adresses IP et Obscurcissement des adresses IP dans notre section [Confidentialité des](/help/using/overview/data-security-and-privacy/data-privacy.md)données.

## Conditions requises pour l'obscurcissement des adresses IP {#ip-obfuscation-requirements}

L’obscurcissement d’adresse IP n’est disponible que pour les comptes d’administrateur Audience Manager. Voir [Création d’utilisateurs](/help/using/features/administration/administration-overview.md#create-users) pour savoir comment attribuer des privilèges d’administrateur à un utilisateur.

>[!NOTE]
>
> En raison du volume important de données traitées par Audience Manager, les modifications d’obscurcissement d’IP peuvent prendre jusqu’à 4 heures pour entrer en vigueur, à partir du moment où vous mettez à jour les paramètres.

## Configuration de l’obscurcissement d’adresse IP {#configure-ip-obfuscation}

Suivez les étapes ci-dessous pour configurer l’obscurcissement des adresses IP.

1. Connectez-vous à Audience Manager avec un compte administrateur et accédez à **Administration &gt; Confidentialité**.
2. Sélectionnez le type d’obscurcissement d’IP à utiliser.
   1. **** Obscurcir toutes les adresses IP : sélectionnez cette option pour qu’Audience Manager brouille le dernier octet de toutes les adresses IP des visiteurs, quelle que soit la région d’origine.
   2. **** Obscurcir les adresses IP de pays spécifiques : sélectionnez cette option pour qu’Audience Manager brouille le dernier octet d’adresses IP des visiteurs pour des pays spécifiques. Utilisez la **liste des pays** ou le champ de **recherche** correspondant pour rechercher les pays pour lesquels l’obscurcissement d’IP doit être activé, puis cliquez sur l’icône + pour les ajouter à la liste **Sélectionné pour l’obscurcissement** . Une fois que vous avez ajouté tous les pays requis à la liste **Sélectionnés pour l’obscurcissement** , cliquez sur **Enregistrer**.

![](assets/ip-obfuscation.png)

## Désactiver l'obscurcissement d'adresse IP {#disable-ip-obfuscation}

Pour désactiver globalement l’obscurcissement des adresses IP, accédez à **Administration &gt; Confidentialité**, sélectionnez **Ne pas obscurcir les adresses** IP, puis cliquez sur **Enregistrer**.

Pour désactiver l’obscurcissement d’adresse IP pour des pays spécifiques, recherchez les pays dans la liste **Sélectionné pour l’obscurcissement** , puis cliquez sur l’icône **X** correspondante. Click **Save** when you're done.

## Concepts associés {#related-concepts}

* [Confidentialité des données](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Vidéo sur l'obscurcissement d'adresse IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=fre_fr)

