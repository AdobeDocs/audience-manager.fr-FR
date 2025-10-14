---
description: Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Obscurcissement de l’adresse IP
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 12%

---

# Obscurcissement de l’adresse IP {#ip-obfuscation}

Utilisez cette fonctionnalité pour obscurcir les adresses IP collectées dans Audience Manager.

## Présentation et méthodologie {#overview-and-methodology}

Votre entreprise peut souhaiter obscurcir l’adresse IP dans de nombreux pays en raison de la réglementation mondiale en matière de confidentialité. Audience Manager vous permet d’obsurcir les adresses IP des visiteurs de manière globale ou pays par pays.

### Méthodologie d’obscurcissement d’IP

Conformément aux principes de la « confidentialité par conception », Adobe Audience Manager permet aux clients d’activer l’obscurcissement de l’adresse IP à partir de l’interface utilisateur, soit globalement, dans toutes les régions géographiques, soit pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (la dernière partie) de l’adresse IP est immédiatement ignoré lorsque l’adresse IP est ingérée dans Audience Manager. Audience Manager ignore cette partie de l’adresse IP avant le traitement (y compris avant toute recherche géographique ou journalisation facultative de l’adresse IP). Par exemple :

* Avant l’obscurcissement : `255.255.255.255`
* Après l’obscurcissement : `255.255.255.0`

Consultez également la section Collecte d’adresses IP et obscurcissement d’adresses IP dans notre [section Confidentialité des données](/help/using/overview/data-security-and-privacy/data-privacy.md).

### Priorité d’obscurcissement des adresses IP {#precedence}

L’[obscurcissement de l’adresse IP au niveau du flux de données](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=fr#create) est prioritaire par rapport à toute option d’obscurcissement d’adresse IP définie dans Audience Manager et s’applique à toutes les adresses IP. Toute recherche de géolocalisation effectuée par Audience Manager est affectée par l’option de [!UICONTROL IP obfuscation] au niveau du train de données. Une recherche de géolocalisation dans Audience Manager, basée sur une adresse IP entièrement obscurcie, entraîne la création d’une région inconnue et les segments basés sur les données de géolocalisation obtenues ne sont pas réalisés.

## Exigences en matière d’obscurcissement des adresses IP {#ip-obfuscation-requirements}

L’obscurcissement des adresses IP est disponible uniquement pour les comptes d’administration Audience Manager. Voir [Créer des utilisateurs](/help/using/features/administration/administration-overview.md#create-users) pour comprendre comment attribuer des privilèges d’administrateur à un utilisateur.

>[!NOTE]
>
> En raison du volume important de données traitées par Audience Manager, les modifications de l’obscurcissement des adresses IP peuvent prendre jusqu’à 4 heures pour prendre effet au moment de la mise à jour des paramètres.

## Configurer l’obscurcissement des adresses IP {#configure-ip-obfuscation}

Suivez les étapes ci-dessous pour configurer l’obscurcissement des adresses IP.

1. Connectez-vous à Audience Manager avec un compte administrateur et accédez à **Administration > Confidentialité**.
2. Sélectionnez le type d’obscurcissement d’IP que vous souhaitez utiliser.
   1. **Obscurcir toutes les adresses IP :** sélectionnez cette option pour qu’Audience Manager obscurcisse le dernier octet de toutes les adresses IP des visiteurs, quelle que soit la région d’où elles proviennent.
   2. **Obscurcir les adresses IP pour des pays spécifiques :** sélectionnez cette option pour qu’Audience Manager obscurcisse le dernier octet des adresses IP des visiteurs pour des pays spécifiques. Utilisez le champ **Liste de pays** ou le champ **Rechercher** correspondant pour trouver les pays pour lesquels activer l’obscurcissement des adresses IP, puis cliquez sur l’icône + pour les ajouter à la liste **Sélectionné pour l’obscurcissement**. Une fois que vous avez ajouté tous les pays requis à la liste **Sélectionné pour l’obscurcissement**, cliquez sur **Enregistrer**.

![](assets/ip-obfuscation.png)

## Désactiver l’obscurcissement des adresses IP {#disable-ip-obfuscation}

Pour désactiver l’obscurcissement des adresses IP au niveau mondial, accédez à **Administration > Confidentialité**, sélectionnez **Ne pas obscurcir les adresses IP**, puis cliquez sur **Enregistrer**.

Pour désactiver l’obscurcissement des adresses IP pour des pays spécifiques, recherchez les pays dans la liste **Sélectionné pour l’obscurcissement**, puis cliquez sur leur icône **X** correspondante. Cliquez sur **Enregistrer** lorsque vous avez terminé.

## Concepts associés {#related-concepts}

* [&#x200B; Confidentialité des données &#x200B;](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Démonstration vidéo de l’obscurcissement des adresses IP
>[!VIDEO](https://video.tv.adobe.com/v/34978?captions=fre_fr)
