---
description: Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Obscurcissement des adresses IP
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 14%

---

# Obscurcissement des adresses IP {#ip-obfuscation}

Utilisez cette fonction pour obscurcir les adresses IP collectées dans Audience Manager.

## Présentation et méthodologie {#overview-and-methodology}

Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.

### Méthodologie d’obscurcissement des adresses IP

Conformément aux principes de &quot;Confidentialité dès la conception&quot;, Adobe Audience Manager permet aux clients d’activer l’obscurcissement des adresses IP à partir de l’interface utilisateur, dans l’ensemble des régions géographiques ou pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (la dernière partie) de l’adresse IP est immédiatement ignoré lorsque l’adresse IP est ingérée dans Audience Manager. L’Audience Manager ignore cette partie de l’adresse IP avant le traitement (y compris avant toute recherche géographique ou journalisation facultative de l’adresse IP). Par exemple :

* Avant obscurcissement : `255.255.255.255`
* Après obscurcissement : `255.255.255.0`

Voir aussi Collecte d’adresses IP et Obscurcissement des adresses IP dans notre [Section Confidentialité des données](/help/using/overview/data-security-and-privacy/data-privacy.md).

### Précédence d’obscurcissement d’IP {#precedence}

[Obscurcissement de l’adresse IP au niveau du flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#create) a la priorité sur toute option d’obscurcissement d’IP définie dans Audience Manager et elle est appliquée à toutes les adresses IP. Toute recherche de géolocalisation effectuée par l’Audience Manager est impactée par le niveau du flux de données. [!UICONTROL IP obfuscation] . Une recherche de géolocalisation dans l’Audience Manager, basée sur une adresse IP complètement obscurcie, entraînera une région inconnue et aucun segment basé sur les données de géolocalisation résultantes ne sera réalisé.

## Exigences d’obscurcissement des adresses IP {#ip-obfuscation-requirements}

L’obscurcissement des adresses IP n’est disponible que pour les comptes d’administrateur d’Audience Manager. Voir [Création d’utilisateurs](/help/using/features/administration/administration-overview.md#create-users) pour comprendre comment attribuer des privilèges d’administrateur à un utilisateur.

>[!NOTE]
>
> En raison du volume important de données traitées par l’Audience Manager, les modifications d’obscurcissement d’IP peuvent prendre jusqu’à 4 heures pour entrer en vigueur, à partir du moment où vous mettez à jour les paramètres.

## Configuration de l’obscurcissement des adresses IP {#configure-ip-obfuscation}

Suivez les étapes ci-dessous pour configurer l’obscurcissement des adresses IP.

1. Connectez-vous à une Audience Manager avec un compte administrateur et accédez à **Administration > Confidentialité**.
2. Sélectionnez le type d’obscurcissement d’IP à utiliser.
   1. **Obscurcir toutes les adresses IP :** sélectionnez cette option pour que l’Audience Manager obscurcisse le dernier octet de toutes les adresses IP du visiteur, quelle que soit la région d’où il provient.
   2. **Obscurcir les adresses IP pour des pays spécifiques :** sélectionnez cette option pour masquer le dernier octet d’adresses IP du visiteur pour des pays spécifiques. Utilisez la variable **Liste des pays** ou le **Rechercher** pour rechercher les pays pour lesquels activer l’obscurcissement des adresses IP, puis cliquez sur l’icône + pour les ajouter au **Sélectionné pour l’obscurcissement** liste. Une fois que vous avez ajouté tous les pays requis au **Sélectionné pour l’obscurcissement** liste, cliquez sur **Enregistrer**.

![](assets/ip-obfuscation.png)

## Désactiver l’obscurcissement des adresses IP {#disable-ip-obfuscation}

Pour désactiver globalement l’obscurcissement des adresses IP, accédez à **Administration > Confidentialité**, sélectionnez **Ne pas obscurcir les adresses IP**, puis cliquez sur **Enregistrer**.

Pour désactiver l’obscurcissement des adresses IP pour des pays spécifiques, recherchez les pays dans la variable **Sélectionné pour l’obscurcissement** liste, puis cliquez sur la **X** Icône Cliquez sur **Enregistrer** lorsque vous avez fini.

## Concepts associés {#related-concepts}

* [Confidentialité des données](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Vidéo de démonstration d’obscurcissement d’adresse IP
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
