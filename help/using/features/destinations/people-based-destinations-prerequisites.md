---
description: 'Lisez ci-dessous pour obtenir une présentation des besoins des clients que vous devez respecter avant de vous inscrire pour les destinations basées sur People.  '
seo-description: 'Lisez ci-dessous pour obtenir une présentation des besoins des clients que vous devez respecter avant de vous inscrire pour les destinations basées sur People.  '
seo-title: Conditions préalables aux destinations basées sur les personnes et points à prendre en compte
solution: Audience Manager
title: Conditions préalables et points à prendre en compte
translation-type: tm+mt
source-git-commit: a3380b9019cfc22b020aacc313eafc409486b0c5

---


# Conditions préalables et points à prendre en compte {#prerequisites-considerations}

Lisez ci-dessous une présentation des besoins des clients que vous devez respecter avant [!DNL People-Based Destinations]de vous inscrire.

>[!IMPORTANT]
> Lisez attentivement cet article avant de passer à la phase de mise en œuvre.

## Inscription pour les destinations basées sur People {#signing-up}

[!DNL People-Based Destinations] est une fonctionnalité supérieure qui améliore votre expérience Audience Manager en vous permettant d'activer des segments d'audience propriétaires dans des environnements administrés par des personnes, en ciblant votre public avec des offres personnalisées sur les réseaux sociaux ou par le biais du marketing par courriel.

Pour plus d'informations sur la manière dont vous pouvez vous inscrire, contactez votre représentant commercial Adobe [!DNL People-Based Destinations].

## Conditions préalables spécifiques au partenaire {#partner-prerequisites}

### [!DNL Facebook]

Avant de [!DNL People-Based Destinations] pouvoir envoyer des segments d'audience, [!DNL Facebook]assurez-vous de respecter les exigences suivantes :

1. Votre [!DNL Facebook] compte utilisateur doit avoir l'autorisation **Gérer les campagnes** activée pour le compte publicitaire que vous prévoyez d'utiliser.
1. Ajoutez le compte professionnel **Adobe Experience Cloud** en tant que partenaire de publicité dans [!DNL Facebook Ad Account]votre. Utilisez `business ID=206617933627973`. Pour plus d'informations, consultez [Ajout de partenaires à votre gestionnaire](https://www.facebook.com/business/help/708679622611131) d'activités.
   >[!IMPORTANT]
   > Lors de la configuration des autorisations d'Adobe Experience Cloud, vous devez activer l'autorisation **Gérer les campagnes** . Ceci est requis pour l' [!DNL People-Based Destinations] intégration.
1. Lisez et signez les [!DNL Facebook Custom Audiences] Conditions de service. Pour ce faire, accédez à, où `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]``accountID` est votre [!DNL Facebook Ad Account ID].

## Data Onboarding {#data-onboarding}

L'ingestion des données prend [!DNL People-Based Destinations] en charge actuellement 10 adresses électroniques hachées liées à un ID de client ([!DNL CRM ID]) par transfert par lot. Le chargement de plus de 10 adresses électroniques hachées liées à un ID de client entraîne l'assimilation de 10 d'entre eux, sans ordre spécifique.

Le chargement de plus de 10 adresses électroniques hachées liées à un ID de client dans plusieurs transferts par lot entraîne l'ajout par Audience Manager des 10 adresses électroniques les plus récentes ajoutées.

## Confidentialité des données {#data-privacy}

Bien que [!DNL People-Based Destinations] vous puissiez cibler des audiences basées sur des adresses électroniques, aucune information directement identifiable sur les visiteurs n'atteint Audience Manager. Dans la phase d'intégration des données, vous devez vous assurer que les adresses électroniques que vous prévoyez d'utiliser sont hachées avec l' [!DNL SHA256] algorithme. Dans le cas contraire, vous ne pourrez pas les utiliser [!DNL People-Based Destinations]dans.

## Hachage des données par rapport au chiffrement {#data-hashing-encryption}

Le chiffrement est une fonction bidirectionnelle. Vous pouvez également déchiffrer toutes les informations chiffrées à l'aide de la clé de déchiffrement correcte. Le chiffrement des données dans le contexte d'Audience Manager entraîne un risque de confidentialité important, car toute forme chiffrée d'informations personnelles identifiables peut également être déchiffrée, révélant des données client sensibles. Contrairement au chiffrement, [!DNL People-Based Destinations] sont conçues pour fonctionner avec des données hachées, en protégeant les données client que vous utilisez pour le ciblage.

Le hachage est une fonction unidirectionnelle qui fait défiler l'entrée pour produire un résultat unique. En utilisant des algorithmes de hachage corrects, comme [!DNL SHA256], il n'est pas possible d'inverser la fonction de hachage et de révéler les informations sans défilement. Les adresses électroniques auxquelles vous accédez à Audience Manager doivent être hachées avec l' [!DNL SHA256] algorithme. Ainsi, aucune information personnelle identifiable n'atteint Audience Manager, ce qui permet de protéger vos données client.

## Exigences de hachage {#hashing-requirements}

Lorsque vous hachez les adresses électroniques, veillez à respecter les exigences suivantes :

* Rogner tous les espaces de début et de fin à partir de la chaîne de courriel ; exemple : `johndoe@example.com`, pas `<space>johndoe@example.com<space>`;
* Assurez-vous que la chaîne hachée est tout en minuscules ; exemple : `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, pas `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Ne déclenchez pas la chaîne.

Adobe Experience Cloud vous offre la possibilité de hacher les identifiants des clients via le service Experience Cloud ID. Pour obtenir des informations détaillées sur l'utilisation d'ECID pour hacher les identifiants client, reportez-vous à [la section Prise en charge de hachage SHA 256 pour setcustomerids](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) .

## Obtention des autorisations utilisateur {#obtaining-user-permission}

Dans [!DNL People-Based Destinations] la mesure où vous pouvez activer les données d'audience propriétaires dans les canaux basés sur les personnes, il vous incombe d'informer vos clients de la manière dont vous utiliserez leurs données à des fins de publicité.

Avant de vous inscrire [!DNL People-Based Destinations], veillez à obtenir le consentement de vos clients avant d'utiliser leurs informations à des fins de publicité.

Au cas où vos clients souhaiteraient exclure des campagnes de publication, consultez [la section Gestion d'exclusion](../../overview/data-security-and-privacy/opt-out-management.md) pour plus d'informations sur la façon d'arrêter Audience Manager de collecter les données plus loin.

## Activation de l'activation des données propriétaires {#enforcing-first-party-activation}

Lors de l'utilisation [!DNL People-Based Destinations], vous pouvez uniquement utiliser des données propriétaires pour activer les segments d'audience dans les canaux basés sur les personnes. Vous ne pouvez pas utiliser de données deuxième partie ou tierces pour l'activation de l'audience dans des canaux basés sur des personnes.

## Identifiants hachés authentifiés par le biais du ciblage d'ID déclaré {#onboard-authenticated-declared-id}

Vous pouvez importer vos données hors ligne de deux manières sur Audience [!DNL People-Based Destinations]Manager.

* [Envoyez des données](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) par lots à Audience Manager pour assimiler des adresses électroniques hachées. Avec cette méthode, vous pouvez utiliser toutes les adresses électroniques hachées de votre [!DNL CRM] base de données. [!DNL People-Based Destinations] De plus, lorsque vous utilisez cette méthode, vous pouvez également qualifier les adresses électroniques hachées des [caractéristiques intégrées](../traits/trait-qualification-reference.md).
* Utilisez [les ID déclarés](../declared-ids.md) pour déclarer des adresses électroniques hachées lors de la transmission d'identifiants de client authentifiés. Lors de l'utilisation de cette méthode, Audience Manager envoie uniquement aux [!DNL People-Based Destinations] adresses électroniques hachées des utilisateurs qui sont authentifiés en ligne. Les adresses électroniques activées via Facebook ne sont que celles qui figurent dans les appels d'événement d'ID déclarés. Les autres adresses électroniques associées à l'ID de client ne sont pas envoyées en temps réel.
