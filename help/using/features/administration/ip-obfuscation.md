---
description: Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.
seo-description: Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.
solution: Audience Manager
title: Obscurcissement d’adresses IP
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 22%

---


# Obscurcissement d’adresses IP {#ip-obfuscation}

Utilisez cette fonction pour obscurcir les adresses IP collectées dans l’Audience Manager.

## Présentation et méthodologie {#overview-and-methodology}

Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.

### Méthodologie d’obscurcissement d’IP

Suivant les principes de &quot;Confidentialité par conception&quot;, l&#39;Adobe Audience Manager permet aux clients d&#39;activer l&#39;obscurcissement d&#39;IP à partir de l&#39;interface utilisateur, que ce soit globalement dans toutes les régions géographiques ou pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (dernière partie) de l’adresse IP est immédiatement ignoré lorsque l’adresse IP est assimilée à une Audience Manager. L’Audience Manager ignore cette partie de l’adresse IP avant le traitement (y compris avant toute recherche géographique ou consignation facultative de l’adresse IP). Par exemple :

* Avant l&#39;obscurcissement : `255.255.255.255`
* Après obscurcissement : `255.255.255.0`

Voir aussi Collecte d’adresses IP et Obscurcissement d’adresse IP dans la section [Confidentialité des](/help/using/overview/data-security-and-privacy/data-privacy.md)données.

## Exigences d&#39;obscurcissement d&#39;adresse IP {#ip-obfuscation-requirements}

L’obscurcissement d’adresse IP n’est disponible que pour les comptes d’administrateur d’Audience Manager. Voir [Création d’utilisateurs](/help/using/features/administration/administration-overview.md#create-users) pour savoir comment attribuer des privilèges d’administrateur à un utilisateur.

>[!NOTE]
>
> En raison du volume important de données traitées par l’Audience Manager, les modifications d’obscurcissement d’IP peuvent prendre jusqu’à 4 heures pour entrer en vigueur, à partir du moment où vous mettez à jour les paramètres.

## Configuration de l’obscurcissement d’adresse IP {#configure-ip-obfuscation}

Suivez les étapes ci-dessous pour configurer l’obscurcissement d’adresse IP.

1. Connectez-vous à l’Audience Manager avec un compte administrateur et accédez à **Administration > Confidentialité**.
2. Sélectionnez le type d’obscurcissement d’IP à utiliser.
   1. **Obscurcir toutes les adresses IP :** sélectionnez cette option pour que l’Audience Manager obscurcit le dernier octet de toutes les adresses IP du visiteur, quelle que soit la région d’où elles proviennent.
   2. **Obscurcir les adresses IP pour certains pays :** sélectionnez cette option pour que l’Audience Manager obscurcit le dernier octet d’adresses IP du visiteur pour des pays spécifiques. Utilisez la **Liste des pays** ou le champ de **recherche** correspondant pour rechercher les pays pour lesquels l’obscurcissement d’IP est activé, puis cliquez sur l’icône + pour les ajouter à la liste **Sélectionné pour l’obscurcissement** . Une fois que vous avez ajouté tous les pays requis à la liste **Sélectionné pour obscurcissement** , cliquez sur **Enregistrer**.

![](assets/ip-obfuscation.png)

## Désactiver l&#39;obscurcissement d&#39;adresse IP {#disable-ip-obfuscation}

Pour désactiver globalement l’obscurcissement d’adresse IP, sélectionnez **Administration > Confidentialité**, **Ne pas obscurcir les adresses** IP, puis cliquez sur **Enregistrer**.

Pour désactiver l’obscurcissement d’adresse IP pour certains pays, recherchez les pays dans la liste **Sélectionné pour l’obscurcissement** , puis cliquez sur l’icône **X** correspondante. Click **Save** when you&#39;re done.

## Concepts associés {#related-concepts}

* [Confidentialité des données](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Vidéo sur l&#39;obscurcissement d&#39;adresse IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

