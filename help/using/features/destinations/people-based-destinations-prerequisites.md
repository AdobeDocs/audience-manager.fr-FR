---
description: 'Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire aux Destinations basées sur les personnes.  '
seo-description: 'Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire aux Destinations basées sur les personnes.  '
seo-title: Destinations basées sur les personnes Conditions préalables et considérations
solution: Audience Manager
title: Conditions préalables et considérations
translation-type: tm+mt
source-git-commit: d83f4dae563c9c49ae8d46c28aa41168d746f92c

---


# Conditions préalables et considérations {#prerequisites-considerations}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans ce document n'est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire [!DNL People-Based Destinations].

>[!IMPORTANT]
> Lisez attentivement cet article avant de passer à la phase de mise en oeuvre.

## Inscription pour des destinations basées sur les personnes {#signing-up}

[!DNL People-Based Destinations] est une fonctionnalité haut de gamme qui améliore votre expérience d’Audience Manager en vous permettant d’activer vos segments d’audience propriétaires dans des environnements de personnes, en ciblant votre audience avec des offres personnalisées sur les réseaux sociaux ou par le biais du marketing par courrier électronique.

Contactez votre représentant Adobe pour profiter de cette fonctionnalité de qualité supérieure.

## Conditions préalables spécifiques au partenaire {#partner-prerequisites}

### [!DNL Facebook]

Avant de pouvoir utiliser [!DNL People-Based Destinations] pour envoyer vos segments d’audience propriétaires vers [!DNL Facebook], assurez-vous de respecter les exigences suivantes :

1. L’autorisation [!DNL Facebook] Gérer les campagnes **doit être activée pour votre compte** utilisateur pour le compte publicitaire que vous prévoyez d’utiliser.
1. Ajoutez le compte **Adobe Experience Cloud** en tant que partenaire publicitaire dans votre [!DNL Facebook Ad Account]entreprise. Utilisez `business ID=206617933627973`. Voir [Ajout de partenaires à votre gestionnaire](https://www.facebook.com/business/help/708679622611131) d’entreprise pour en savoir plus.
   >[!IMPORTANT]
   > Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l’autorisation **Gérer les campagnes** . Ceci est nécessaire pour l’ [!DNL People-Based Destinations] intégration.
1. Lisez et signez les [!DNL Facebook Custom Audiences] Conditions d'utilisation. Pour ce faire, allez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

## Intégration des données {#data-onboarding}

L’assimilation de données pour [!DNL People-Based Destinations] l’instant prend en charge jusqu’à 10 adresses électroniques hachées liées à un ID de client ([!DNL CRM ID]), par transfert par lot. Le téléchargement de plus de 10 adresses électroniques hachées liées à un ID de client entraîne l’assimilation de 10 d’entre elles par Audience Manager, sans ordre spécifique.

Le téléchargement de plus de 10 adresses électroniques hachées liées à un ID de client dans plusieurs transferts par lots entraîne la conservation des 10 adresses électroniques ajoutées les plus récentes par Audience Manager.

## Confidentialité des données {#data-privacy}

Bien que vous [!DNL People-Based Destinations] puissiez cibler des audiences en fonction d’adresses électroniques hachées transférées par vous, il vous est toujours interdit de télécharger des informations de visiteur directement identifiables dans Audience Manager. Lors de la phase d’intégration des données, vous devez vous assurer que les adresses électroniques que vous prévoyez d’utiliser sont hachées avec l’ [!DNL SHA256] algorithme. Sinon, vous ne pourrez pas les utiliser dans [!DNL People-Based Destinations].

## Hachage de données contre chiffrement {#data-hashing-encryption}

Le chiffrement est une fonction bidirectionnelle. Toute information chiffrée peut également être déchiffrée à l’aide de la clé de déchiffrement appropriée. Le chiffrement des données dans le contexte d’Audience Manager présente de sérieux risques, car toute forme chiffrée d’informations d’identification personnelle peut également être déchiffrée. Contrairement au chiffrement, [!DNL People-Based Destinations] sont conçus pour fonctionner avec des données hachées.

Le hachage est une fonction à sens unique qui brouille l’entrée pour produire un résultat unique. En utilisant des algorithmes de hachage appropriés, comme [!DNL SHA256], il n'y a aucun moyen d'inverser la fonction de hachage et de révéler les informations non brouillées. Les adresses électroniques à bord d’Audience Manager doivent être hachées avec l’ [!DNL SHA256] algorithme. Ainsi, vous pouvez vous assurer qu’aucune adresse électronique non hachée n’atteint Audience Manager.

## Exigences de hachage {#hashing-requirements}

Lors du hachage des adresses électroniques, veillez à respecter les exigences suivantes :

* Rogner tous les espaces de début et de fin de la chaîne de courrier électronique ; exemple : `johndoe@example.com`, non `<space>johndoe@example.com<space>`;
* Lors du hachage des chaînes de courrier électronique, veillez à hacher la chaîne minuscule ;
   * Exemple : `example@email.com`, non `EXAMPLE@EMAIL.COM`;
* Assurez-vous que la chaîne hachée est en minuscules.
   * Exemple : `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Ne salez pas la chaîne.

Regardez la vidéo ci-dessous pour comprendre les exigences de hachage de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/?captions=fre_fr)

Adobe Experience Cloud vous permet de hacher les ID de client via le service d’ID d’Experience Cloud. Voir Prise en charge du hachage [SHA256 pour setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) pour obtenir des informations détaillées sur la manière d’utiliser ECID pour hacher les ID de client.

## Obtention de l’autorisation utilisateur {#obtaining-user-permission}

Puisque [!DNL People-Based Destinations] vous pouvez activer des données d’audience propriétaires dans des canaux basés sur des personnes, il vous incombe d’informer vos clients et d’obtenir leur consentement sur la manière dont vous utiliserez leurs données à des fins publicitaires ou autres.

Avant de vous inscrire [!DNL People-Based Destinations], assurez-vous d'obtenir le consentement de vos clients avant d'utiliser leurs informations à des fins publicitaires.

Si vos clients souhaitent s’exclure des campagnes publicitaires, reportez-vous à la section Gestion [des](../../overview/data-security-and-privacy/data-privacy-requests.md) exclusions pour plus d’informations sur la manière d’empêcher Audience Manager de collecter des données.

## Activation des données propriétaires {#enforcing-first-party-activation}

Lors de [!DNL People-Based Destinations]l’utilisation, vous pouvez uniquement utiliser des données propriétaires pour activer les segments d’audience dans les canaux basés sur les personnes. Vous ne pouvez pas utiliser de données propriétaires ou tierces pour l’activation de l’audience dans des canaux basés sur des personnes.

Lors de l’utilisation [!UICONTROL People-Based Destinations], utilisez [les contrôles](../data-export-controls.md) d’exportation de données pour étiqueter vos sources de données et destinations en fonction des directives et des exigences des plateformes de destination et des fournisseurs de données.

## Identifiants hachés authentifiés à bord via le ciblage d’identifiants déclarés {#onboard-authenticated-declared-id}

Vous pouvez apporter vos données hors ligne à Audience Manager de deux manières [!DNL People-Based Destinations].

* [Envoyez des données](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) par lot à Audience Manager pour assimiler des adresses électroniques hachées. Cette méthode vous permet d’utiliser les adresses électroniques hachées de votre [!DNL CRM] base de données dans [!DNL People-Based Destinations]. De plus, lorsque vous utilisez cette méthode, vous pouvez également définir les adresses électroniques hachées pour les caractéristiques [](../traits/trait-qualification-reference.md)intégrées.
* Utilisez des ID [déclarés](../declared-ids.md) pour déclarer des adresses électroniques hachées lors de la transmission d’ID de client authentifiés. Lors de l’utilisation de cette méthode, Audience Manager, en votre nom, envoie uniquement aux adresses électroniques hachées [!DNL People-Based Destinations] des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques activées par le biais de canaux basés sur des personnes sont uniquement celles qui figurent dans les appels d’événement d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas envoyées en temps réel.
