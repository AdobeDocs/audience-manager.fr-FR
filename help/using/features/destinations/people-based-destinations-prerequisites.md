---
description: 'Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire aux Destinations basées sur les personnes.  '
seo-description: 'Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire aux Destinations basées sur les personnes.  '
seo-title: Destinations basées sur les personnes Conditions préalables et considérations
solution: Audience Manager
title: Conditions préalables et considérations
translation-type: tm+mt
source-git-commit: f3fe6abe913d98549ae6c090a2d5f721485308c2

---


# Conditions préalables et considérations {#prerequisites-considerations}

Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire [!DNL People-Based Destinations].

>[!IMPORTANT]
> Lisez attentivement cet article avant de passer à la phase de mise en oeuvre.

## Inscription pour des destinations basées sur les personnes {#signing-up}

[!DNL People-Based Destinations] est une fonctionnalité haut de gamme qui améliore votre expérience d’Audience Manager en vous permettant d’activer des segments d’audience propriétaires dans des environnements de personnes, en ciblant votre audience avec des offres personnalisées sur les réseaux sociaux ou par le biais du marketing par courrier électronique.

Contactez votre représentant Adobe pour profiter de cette fonctionnalité de qualité supérieure.

## Conditions préalables spécifiques au partenaire {#partner-prerequisites}

### [!DNL Facebook]

Avant de pouvoir utiliser [!DNL People-Based Destinations] pour envoyer des segments d’audience à [!DNL Facebook], assurez-vous de respecter les exigences suivantes :

1. L’autorisation [!DNL Facebook] Gérer les campagnes **doit être activée pour votre compte** utilisateur pour le compte publicitaire que vous prévoyez d’utiliser.
1. Ajoutez le compte **Adobe Experience Cloud** en tant que partenaire publicitaire dans votre [!DNL Facebook Ad Account]entreprise. Utilisez `business ID=206617933627973`. Voir [Ajout de partenaires à votre gestionnaire](https://www.facebook.com/business/help/708679622611131) d’entreprise pour en savoir plus.
   >[!IMPORTANT]
   > Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l’autorisation **Gérer les campagnes** . Ceci est nécessaire pour l’ [!DNL People-Based Destinations] intégration.
1. Lisez et signez les [!DNL Facebook Custom Audiences] Conditions d'utilisation. Pour ce faire, allez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

## Intégration des données {#data-onboarding}

L’assimilation de données pour [!DNL People-Based Destinations] l’instant prend en charge jusqu’à 10 adresses électroniques hachées liées à un ID de client ([!DNL CRM ID]), par transfert par lot. Le téléchargement de plus de 10 adresses électroniques hachées liées à un ID de client entraîne l’assimilation de 10 d’entre elles par Audience Manager, sans ordre spécifique.

Le téléchargement de plus de 10 adresses électroniques hachées liées à un ID de client dans plusieurs transferts par lots entraîne la conservation des 10 adresses électroniques ajoutées les plus récentes par Audience Manager.

## Confidentialité des données {#data-privacy}

Bien que [!DNL People-Based Destinations] vous puissiez cibler des audiences en fonction d’adresses électroniques, aucune information de visiteur directement identifiable n’atteint jamais Audience Manager. Lors de la phase d’intégration des données, vous devez vous assurer que les adresses électroniques que vous prévoyez d’utiliser sont hachées avec l’ [!DNL SHA256] algorithme. Sinon, vous ne pourrez pas les utiliser dans [!DNL People-Based Destinations].

## Hachage de données contre chiffrement {#data-hashing-encryption}

Le chiffrement est une fonction bidirectionnelle. Toute information chiffrée peut également être déchiffrée à l’aide de la clé de déchiffrement appropriée. Le chiffrement des données dans le contexte d’Audience Manager présente un risque sérieux pour la confidentialité, car toute forme chiffrée d’informations d’identification personnelle peut également être déchiffrée, révélant des données sensibles sur les clients. Contrairement au chiffrement, [!DNL People-Based Destinations] sont conçus pour fonctionner avec les données hachées, ce qui protège les données client que vous utilisez pour le ciblage.

Le hachage est une fonction à sens unique qui brouille l’entrée pour produire un résultat unique. En utilisant des algorithmes de hachage appropriés, comme [!DNL SHA256], il n'y a aucun moyen d'inverser la fonction de hachage et de révéler les informations non brouillées. Les adresses électroniques à bord d’Audience Manager doivent être hachées avec l’ [!DNL SHA256] algorithme. Ainsi, aucune information d’identification personnelle n’atteint jamais Audience Manager, ce qui permet de protéger vos données client.

## Exigences de hachage {#hashing-requirements}

Lors du hachage des adresses électroniques, veillez à respecter les exigences suivantes :

* Rogner tous les espaces de début et de fin de la chaîne de courrier électronique ; exemple : `johndoe@example.com`, non `<space>johndoe@example.com<space>`;
* Assurez-vous que la chaîne hachée est en minuscules ; exemple : `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Ne salez pas la chaîne.

Adobe Experience Cloud vous permet de hacher les ID de client via le service d’ID Experience Cloud. Voir Prise en charge du hachage [SHA256 pour setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) pour obtenir des informations détaillées sur la manière d’utiliser ECID pour hacher les ID de client.

## Obtention de l’autorisation utilisateur {#obtaining-user-permission}

Puisque [!DNL People-Based Destinations] vous pouvez activer des données d’audience propriétaires dans des canaux basés sur des personnes, il vous incombe d’informer vos clients de la manière dont vous utiliserez leurs données à des fins publicitaires.

Avant de vous inscrire [!DNL People-Based Destinations], assurez-vous d'obtenir le consentement de vos clients avant d'utiliser leurs informations à des fins publicitaires.

Si vos clients souhaitent s’exclure des campagnes publicitaires, reportez-vous à la section Gestion [des](../../overview/data-security-and-privacy/opt-out-management.md) exclusions pour plus d’informations sur la manière d’empêcher Audience Manager de collecter des données.

## Activation des données propriétaires {#enforcing-first-party-activation}

Lors de [!DNL People-Based Destinations]l’utilisation, vous pouvez uniquement utiliser des données propriétaires pour activer les segments d’audience dans les canaux basés sur les personnes. Vous ne pouvez pas utiliser de données propriétaires ou tierces pour l’activation de l’audience dans des canaux basés sur des personnes.

## Identifiants hachés authentifiés à bord via le ciblage d’identifiants déclarés {#onboard-authenticated-declared-id}

Vous pouvez apporter vos données hors ligne à Audience Manager de deux manières [!DNL People-Based Destinations].

* [Envoyez des données](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) par lot à Audience Manager pour assimiler des adresses électroniques hachées. Avec cette méthode, vous pouvez utiliser toutes les adresses électroniques hachées de votre [!DNL CRM] base de données dans [!DNL People-Based Destinations]. De plus, lorsque vous utilisez cette méthode, vous pouvez également définir les adresses électroniques hachées pour les caractéristiques [](../traits/trait-qualification-reference.md)intégrées.
* Utilisez des ID [déclarés](../declared-ids.md) pour déclarer des adresses électroniques hachées lors de la transmission d’ID de client authentifiés. Lors de l’utilisation de cette méthode, Audience Manager envoie uniquement aux adresses électroniques hachées [!DNL People-Based Destinations] les adresses des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques activées via Facebook ne sont que celles des appels d’événement d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas envoyées en temps réel.
