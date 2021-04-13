---
description: 'Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire à des destinations basées sur les personnes.  '
seo-description: 'Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire à des destinations basées sur les personnes.  '
seo-title: Destinations basées sur les personnes Conditions préalables et considérations
solution: Audience Manager
title: Conditions préalables et considérations
feature: Destinations basées sur des personnes
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 3%

---

# Conditions préalables et considérations {#prerequisites-considerations}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Vous trouverez ci-dessous un aperçu des besoins des clients que vous devez satisfaire avant de vous inscrire à [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lisez attentivement cet article avant de passer à la phase de mise en oeuvre.

## Inscription pour [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] est une fonctionnalité haut de gamme qui améliore votre expérience d’Audience Manager en vous permettant d’activer vos segments d’audience propriétaires dans des environnements basés sur des personnes, en ciblant votre audience avec des offres personnalisées sur les réseaux sociaux ou par le biais du marketing par courriel.

Veuillez contacter votre représentant d&#39;Adobe pour profiter de cette fonctionnalité haut de gamme.

## Conditions préalables spécifiques au partenaire {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer votre audience propriétaire [!UICONTROL segments] à [!DNL Facebook], assurez-vous de respecter les exigences suivantes :

1. L&#39;autorisation [!DNL Facebook] Gérer les campagnes **doit être activée pour votre compte d&#39;utilisateur** que vous prévoyez d&#39;utiliser.
2. Ajoutez le compte commercial **Adobe Experience Cloud** en tant que partenaire publicitaire dans votre [!DNL Facebook Ad Account]. Utilisez `business ID=206617933627973`. Voir [Ajouter les partenaires à votre gestionnaire d&#39;entreprise](https://www.facebook.com/business/help/1717412048538897) pour plus d&#39;informations.
   >[!IMPORTANT]
   > Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l&#39;autorisation **Gérer les campagnes**. Ceci est obligatoire pour l’intégration de [!UICONTROL People-Based Destinations].
3. Lisez et signez les [!DNL Facebook Custom Audiences] conditions d&#39;utilisation. Pour ce faire, accédez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d&#39;audience propriétaire à [!DNL LinkedIn], assurez-vous que votre compte [!DNL LinkedIn Campaign Manager] a le niveau d&#39;autorisation [!DNL Creative Manager] ou supérieur.

Pour savoir comment modifier vos [!DNL LinkedIn Campaign Manager] autorisations d’utilisateur, voir [Ajouter, modifier et supprimer des autorisations d’utilisateur sur des comptes de publicité](https://www.linkedin.com/help/lms/answer/5753) dans la documentation LinkedIn.

Voir [Présentation et configuration de la destination basée sur les personnes LinkedIn](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) pour obtenir des instructions sur la vidéo.

### [!DNL Google Customer Match] {#gcm}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d&#39;audience propriétaire vers une destination [!DNL Google Customer Match], il est obligatoire que [!DNL Google] vous ajoute à leur liste autorisée.

Contactez votre représentant [!DNL Google] et suivez les instructions de liste autorisée décrites dans la documentation [Utilisation des partenaires de correspondance client pour télécharger vos données](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google].

Une fois ce processus terminé, vous pouvez créer votre [!UICONTROL People-Based Destination].

## Intégration de données {#data-onboarding}

L&#39;assimilation de données pour [!UICONTROL People-Based Destinations] prend actuellement en charge jusqu&#39;à 10 adresses électroniques hachées liées à un ID de client ([!DNL CRM ID]), par transfert par lot. Le chargement de plus de 10 adresses électroniques hachées liées à un ID de client entraîne l’Audience Manager d’en importer 10, sans ordre spécifique.

Le téléchargement de plus de 10 adresses électroniques hachées liées à un ID de client dans plusieurs transferts par lots entraîne la conservation des 10 adresses électroniques ajoutées les plus récentes.

## Confidentialité des données {#data-privacy}

Bien que [!UICONTROL People-Based Destinations] vous permette d&#39;cible des audiences en fonction des adresses électroniques hachées que vous avez téléchargées, vous n&#39;avez pas le droit de transférer des informations directement identifiables sur les visiteurs dans l&#39;Audience Manager. Lors de la phase d’intégration des données, vous devez vous assurer que les adresses électroniques que vous prévoyez d’utiliser sont hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas les utiliser dans [!UICONTROL People-Based Destinations].

## Hachage de données contre chiffrement {#data-hashing-encryption}

Le chiffrement est une fonction bidirectionnelle. Toutes les informations chiffrées peuvent également être déchiffrées à l’aide de la clé de déchiffrement appropriée. Le cryptage des données dans le contexte de l&#39;Audience Manager présente de sérieux risques, car toute forme cryptée d&#39;informations personnelles identifiables peut également être déchiffrée. Contrairement au chiffrement, [!UICONTROL People-Based Destinations] sont conçus pour fonctionner avec des données hachées.

Le hachage est une fonction à sens unique qui brouille l’entrée pour produire un résultat unique. En utilisant des algorithmes de hachage appropriés, tels que [!DNL SHA256], il n&#39;existe aucun moyen d&#39;inverser la fonction de hachage et de révéler les informations non brouillées. Les adresses électroniques que vous allez utiliser pour l&#39;Audience Manager doivent être hachées avec l&#39;algorithme [!DNL SHA256]. Ainsi, vous pouvez vous assurer qu’aucune adresse électronique non hachée n’atteint l’Audience Manager.

## Exigences de hachage {#hashing-requirements}

Lorsque vous hachez les adresses électroniques, veillez à respecter les exigences suivantes :

* Rogner tous les espaces de début et de fin de la chaîne de courriel ; exemple : `johndoe@example.com`, et non `<space>johndoe@example.com<space>`;
* Lors du hachage des chaînes de courrier électronique, veillez à mettre la chaîne en minuscules en hachage ;
   * Exemple : `example@email.com`, et non `EXAMPLE@EMAIL.COM`;
* Assurez-vous que la chaîne hachée est en minuscules.
   * Exemple : `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, et non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Ne salez pas la chaîne.

Regardez la vidéo ci-dessous pour comprendre les exigences de hachage de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud vous permet de hacher les ID de client par le biais de [!DNL Adobe Experience Platform Identity Service (ECID)]. Voir [Prise en charge du hachage SHA256 pour setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) pour obtenir des informations détaillées sur la manière d&#39;utiliser ECID pour hacher les ID de client.

## Obtention de l&#39;autorisation d&#39;utilisateur {#obtaining-user-permission}

Comme [!UICONTROL People-Based Destinations] vous aide à activer les données d&#39;audience propriétaires dans des canaux basés sur des personnes, il vous incombe d&#39;informer vos clients et d&#39;obtenir leur consentement sur la façon dont vous utiliserez leurs données à des fins publicitaires ou autres.

Avant de vous inscrire à [!UICONTROL People-Based Destinations], assurez-vous d&#39;obtenir le consentement de vos clients avant d&#39;utiliser leurs informations à des fins publicitaires.

Si vos clients souhaitent s’exclure des campagnes publicitaires, voir [Gestion des exclusions](../../overview/data-security-and-privacy/data-privacy-requests.md) pour plus d’informations sur la manière d’empêcher l’Audience Manager de collecter des données.

## Application de l’Activation des données propriétaires {#enforcing-first-party-activation}

Lorsque vous utilisez [!UICONTROL People-Based Destinations], vous pouvez uniquement utiliser des données propriétaires pour activer des segments d’audience dans des canaux basés sur des personnes. Vous ne pouvez pas utiliser de données tierces ou de seconde partie pour l’activation des audiences dans les canaux basés sur les personnes.

Lors de l&#39;utilisation de [!UICONTROL People-Based Destinations], utilisez [Data Export Controls](../data-export-controls.md) pour étiqueter [!UICONTROL data sources] et [!UICONTROL destinations] conformément aux directives et aux exigences des plateformes de destination et des fournisseurs de données.

## Identifiants hachés authentifiés à bord via le ciblage d’identifiants déclarés {#onboard-authenticated-declared-id}

Il existe deux manières d’importer vos données hors ligne vers Audience Manager pour [!UICONTROL People-Based Destinations].

* [Envoyez l’Audience Manager ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) des données par lot à assimiler les adresses électroniques hachées. Avec cette méthode, vous pouvez choisir d&#39;utiliser les adresses électroniques hachées de votre base de données [!DNL CRM] dans [!UICONTROL People-Based Destinations]. De plus, lorsque vous utilisez cette méthode, vous pouvez également qualifier les adresses électroniques hachées pour [caractéristiques intégrées](../traits/trait-and-segment-qualification-reference.md).
* Utilisez [Identifiants déclarés](../declared-ids.md) pour déclarer les adresses électroniques hachées lors de la transmission des identifiants de client authentifiés. Lors de l’utilisation de cette méthode, l’Audience Manager, en votre nom, envoie uniquement à [!UICONTROL People-Based Destinations] les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques activées par le biais de canaux basés sur des personnes ne sont que celles des appels de événement d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas envoyées en temps réel.
