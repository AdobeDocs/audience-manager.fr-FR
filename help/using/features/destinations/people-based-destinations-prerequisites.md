---
description: 'Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire à des destinations basées sur les personnes.  '
seo-description: 'Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire à des destinations basées sur les personnes.  '
seo-title: Destinations basées sur les personnes Conditions préalables et considérations
solution: Audience Manager
title: Conditions préalables et considérations
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 4%

---


# Conditions préalables et considérations {#prerequisites-considerations}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lisez attentivement cet article avant de passer à la phase de mise en oeuvre.

## Inscription pour [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] est une fonctionnalité haut de gamme qui améliore votre expérience d’Audience Manager en vous permettant d’activer vos segments d’audience propriétaires dans des environnements basés sur des personnes, en ciblant votre audience avec des offres personnalisées sur les réseaux sociaux ou par le biais du marketing par courriel.

Veuillez contacter votre représentant Adobe pour profiter de cette fonctionnalité haut de gamme.

## Conditions préalables spécifiques au partenaire {#partner-prerequisites}

### [!DNL Facebook]

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer votre audience propriétaire [!UICONTROL segments] à [!DNL Facebook], assurez-vous de respecter les exigences suivantes :

1. L’autorisation [!DNL Facebook] Gérer les campagnes **doit être activée pour votre compte** utilisateur pour le compte publicitaire que vous prévoyez d’utiliser.
2. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. Utilisez `business ID=206617933627973`. See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/1717412048538897) for details.
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the **Manage campaigns** permission. Ceci est obligatoire pour l’intégration de [!UICONTROL People-Based Destinations].
3. Lisez et signez les [!DNL Facebook Custom Audiences] conditions d’utilisation. Pour ce faire, accédez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn]

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d’audience propriétaires à [!DNL LinkedIn], assurez-vous que votre [!DNL LinkedIn Campaign Manager] compte dispose d’un niveau d’autorisation [!DNL Creative Manager] ou supérieur.

Pour savoir comment modifier vos autorisations d’ [!DNL LinkedIn Campaign Manager] utilisateur, voir [Ajouter, modifier et supprimer des autorisations d’utilisateur sur des comptes](https://www.linkedin.com/help/lms/answer/5753) publicitaires dans la documentation LinkedIn.

Voir [Présentation et configuration de la destination](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) basée sur les personnes LinkedIn pour obtenir des instructions vidéo.

## Intégration de données {#data-onboarding}

L&#39;assimilation de données pour [!UICONTROL People-Based Destinations] l&#39;instant prend en charge jusqu&#39;à 10 adresses électroniques hachées liées à un ID de client ([!DNL CRM ID]), par transfert par lot. Le chargement de plus de 10 adresses électroniques hachées liées à un ID de client entraîne l’Audience Manager d’en importer 10, sans ordre spécifique.

Le téléchargement de plus de 10 adresses électroniques hachées liées à un ID de client dans plusieurs transferts par lots entraîne la conservation des 10 adresses électroniques ajoutées les plus récentes.

## Confidentialité des données {#data-privacy}

Bien que [!UICONTROL People-Based Destinations] vous puissiez cible des audiences en fonction d’adresses électroniques hachées que vous avez téléchargées, vous n’avez pas le droit de transférer des informations directement identifiables sur le visiteur dans l’Audience Manager. Lors de la phase d’intégration des données, vous devez vous assurer que les adresses électroniques que vous prévoyez d’utiliser sont hachées avec l’ [!DNL SHA256] algorithme. Sinon, vous ne pourrez pas les utiliser dans [!UICONTROL People-Based Destinations].

## Hachage de données contre chiffrement {#data-hashing-encryption}

Le chiffrement est une fonction bidirectionnelle. Toutes les informations chiffrées peuvent également être déchiffrées à l’aide de la clé de déchiffrement appropriée. Le cryptage des données dans le contexte de l&#39;Audience Manager présente de sérieux risques, car toute forme cryptée d&#39;informations personnelles identifiables peut également être déchiffrée. Contrairement au chiffrement, [!UICONTROL People-Based Destinations] ils sont conçus pour fonctionner avec des données hachées.

Le hachage est une fonction à sens unique qui brouille l’entrée pour produire un résultat unique. En utilisant des algorithmes de hachage appropriés, comme [!DNL SHA256], il n&#39;y a aucun moyen d&#39;inverser la fonction de hachage et de révéler les informations non brouillées. Les adresses électroniques que vous allez prendre en compte pour l’Audience Manager doivent être hachées avec l’ [!DNL SHA256] algorithme. Ainsi, vous pouvez vous assurer qu’aucune adresse électronique non hachée n’atteint l’Audience Manager.

## Exigences de hachage {#hashing-requirements}

Lorsque vous hachez les adresses électroniques, veillez à respecter les exigences suivantes :

* Rogner tous les espaces de début et de fin de la chaîne de courriel ; exemple : `johndoe@example.com`, non `<space>johndoe@example.com<space>`;
* Lors du hachage des chaînes de courrier électronique, veillez à mettre la chaîne en minuscules en hachage ;
   * Exemple : `example@email.com`, non `EXAMPLE@EMAIL.COM`;
* Assurez-vous que la chaîne hachée est en minuscules.
   * Exemple : `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Ne salez pas la chaîne.

Regardez la vidéo ci-dessous pour comprendre les exigences de hachage de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud vous offre la possibilité de hacher les ID de client par le biais du [!DNL Adobe Experience Platform Identity Service (ECID)]. Voir Prise en charge du hachage [SHA256 pour setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) pour obtenir des informations détaillées sur l’utilisation de l’ECID pour hacher les ID de client.

## Obtention de l’autorisation d’utilisateur {#obtaining-user-permission}

Puisque [!UICONTROL People-Based Destinations] vous aidez à activer les données d’audience propriétaires dans des canaux basés sur des personnes, il vous incombe d’informer vos clients et d’obtenir leur consentement nécessaire sur la manière dont vous utiliserez leurs données à des fins publicitaires ou autres.

Avant de vous inscrire [!UICONTROL People-Based Destinations], assurez-vous d&#39;obtenir le consentement de vos clients avant d&#39;utiliser leurs informations à des fins publicitaires.

Si vos clients souhaitent se désabonner des campagnes publicitaires, consultez la section Gestion [des](../../overview/data-security-and-privacy/data-privacy-requests.md) exclusions pour plus d’informations sur la manière d’empêcher l’Audience Manager de collecter des données.

## Application de l’Activation des données propriétaires {#enforcing-first-party-activation}

Lors de l’utilisation [!UICONTROL People-Based Destinations], vous pouvez uniquement utiliser des données propriétaires pour activer des segments d’audience dans des canaux basés sur des personnes. Vous ne pouvez pas utiliser de données tierces ou de seconde partie pour l’activation des audiences dans les canaux basés sur les personnes.

Lors de l’utilisation de [!UICONTROL People-Based Destinations]Data Export Controls [, utilisez](../data-export-controls.md) Data Export Controls pour étiqueter vos données [!UICONTROL data sources] et [!UICONTROL destinations] conformément aux directives et aux exigences des plateformes de destination et des fournisseurs de données.

## Identifiants hachés authentifiés à bord via le ciblage d’identifiants déclarés {#onboard-authenticated-declared-id}

Il existe deux manières d’importer vos données hors ligne vers Audience Manager pour [!UICONTROL People-Based Destinations].

* [Envoyez des données](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) par lot à l’Audience Manager pour importer des adresses électroniques hachées. Cette méthode vous permet d’utiliser les adresses électroniques hachées de votre [!DNL CRM] base de données dans [!UICONTROL People-Based Destinations]. De plus, lorsque vous utilisez cette méthode, vous pouvez également définir les adresses électroniques hachées pour les caractéristiques [](../traits/trait-and-segment-qualification-reference.md)intégrées.
* Use [Declared IDs](../declared-ids.md) to declare hashed email addresses when passing in authenticated customer IDs. When using this method, Audience Manager, on your behalf, only sends to [!UICONTROL People-Based Destinations] the hashed email addresses from users who have authenticated online. Les adresses électroniques activées par le biais de canaux basés sur des personnes ne sont que celles des appels de événement d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas envoyées en temps réel.
