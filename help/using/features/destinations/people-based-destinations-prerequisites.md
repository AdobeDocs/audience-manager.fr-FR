---
description: 'Lisez ci-dessous pour une vue d’ensemble des exigences des clients que vous devez satisfaire avant de vous inscrire aux destinations basées sur les personnes.  '
seo-description: 'Lisez ci-dessous pour une vue d’ensemble des exigences des clients que vous devez satisfaire avant de vous inscrire aux destinations basées sur les personnes.  '
seo-title: Conditions préalables et considérations relatives aux destinations basées sur les personnes
solution: Audience Manager
title: Conditions préalables et considérations
feature: Destinations basées sur les personnes
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1017'
ht-degree: 3%

---

# Conditions préalables et considérations {#prerequisites-considerations}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Lisez ci-dessous pour une vue d’ensemble des exigences du client que vous devez satisfaire avant de vous inscrire à [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lisez attentivement cet article avant de passer à la phase de mise en oeuvre.

## Inscrivez-vous à [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] est une fonctionnalité premium qui améliore votre expérience d’Audience Manager en vous permettant d’activer vos segments d’audience propriétaires dans des environnements basés sur les personnes, en ciblant votre audience avec des offres personnalisées sur les réseaux sociaux ou par le biais du marketing par e-mail.

Veuillez contacter votre représentant Adobe pour profiter de cette fonctionnalité premium.

## Conditions préalables spécifiques au partenaire {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer votre audience propriétaire [!UICONTROL segments] à [!DNL Facebook], assurez-vous de respecter les conditions suivantes :

1. L’autorisation [!DNL Facebook] Gérer les campagnes **doit être activée pour votre compte utilisateur pour le compte publicitaire que vous prévoyez d’utiliser.**
2. Ajoutez le compte commercial **Adobe Experience Cloud** en tant que partenaire publicitaire dans votre [!DNL Facebook Ad Account]. Utilisez `business ID=206617933627973`. Voir [Ajout de partenaires à votre compte Business Manager](https://www.facebook.com/business/help/1717412048538897) pour plus d’informations.
   >[!IMPORTANT]
   > Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l’autorisation **Gérer les campagnes** . Ceci est obligatoire pour l’intégration de [!UICONTROL People-Based Destinations].
3. Lisez et signez les [!DNL Facebook Custom Audiences] Conditions d’utilisation. Pour ce faire, accédez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d’audience propriétaires à [!DNL LinkedIn], assurez-vous que votre compte [!DNL LinkedIn Campaign Manager] a le niveau d’autorisation [!DNL Creative Manager] ou supérieur.

Pour savoir comment modifier vos [!DNL LinkedIn Campaign Manager] autorisations d’utilisateur, voir [Ajout, modification et suppression des autorisations d’utilisateur sur les comptes Advertising](https://www.linkedin.com/help/lms/answer/5753) dans la documentation LinkedIn.

Voir [Présentation et configuration de la destination basée sur les personnes de LinkedIn](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) pour obtenir des instructions vidéo.

### [!DNL Google Customer Match] {#gcm}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d’audience propriétaires à une destination [!DNL Google Customer Match], il est obligatoire que [!DNL Google] vous ajoute à leur liste autorisée.

Contactez votre représentant [!DNL Google] et suivez les instructions de liste autorisée décrites dans la documentation [Utilisation des partenaires de correspondance du client pour télécharger vos données](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google] .

Une fois ce processus terminé, vous pouvez créer votre [!UICONTROL People-Based Destination].

## Intégration de données {#data-onboarding}

L’ingestion de données pour [!UICONTROL People-Based Destinations] prend actuellement en charge jusqu’à 10 adresses électroniques hachées liées à un ID de client ([!DNL CRM ID]), par transfert par lots. Le téléchargement de plus de 10 adresses électroniques hachées liées à un ID de client entraîne l’Audience Manager d’en ingérer 10, sans ordre spécifique.

Le chargement de plus de 10 adresses électroniques hachées liées à un ID de client dans plusieurs transferts par lots entraîne l’Audience Manager à conserver les 10 adresses électroniques ajoutées les plus récentes.

## Confidentialité des données {#data-privacy}

Bien que [!UICONTROL People-Based Destinations] vous permette de cibler des audiences en fonction d’adresses électroniques hachées que vous avez téléchargées, vous n’avez pas le droit de transférer des informations de visiteur directement identifiables dans Audience Manager. Lors de la phase d’intégration des données, vous devez vous assurer que les adresses électroniques que vous prévoyez d’utiliser sont hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas les utiliser dans [!UICONTROL People-Based Destinations].

## Hachage de données contre chiffrement {#data-hashing-encryption}

Le chiffrement est une fonction bidirectionnelle. Toutes les informations cryptées peuvent également être décryptées à l’aide de la clé de décryptage correcte. Le cryptage des données dans le contexte de l’Audience Manager présente de sérieux risques, dans la mesure où toute forme cryptée d’informations d’identification personnelle peut également être déchiffrée. Contrairement au chiffrement, [!UICONTROL People-Based Destinations] est conçu pour fonctionner avec des données hachées.

Le hachage est une fonction unidirectionnelle qui fait défiler l’entrée pour produire un résultat unique. En utilisant des algorithmes de hachage appropriés, comme [!DNL SHA256], il n’existe aucun moyen d’inverser la fonction de hachage et de révéler les informations non brouillées. Les adresses électroniques que vous allez intégrer à l’Audience Manager doivent être hachées avec l’algorithme [!DNL SHA256]. Ainsi, vous pouvez vous assurer qu’aucune adresse électronique non hachée n’atteint l’Audience Manager.

## Exigences de hachage {#hashing-requirements}

Lors du hachage des adresses email, veillez à respecter les exigences suivantes :

* Rogner tous les espaces de début et de fin de la chaîne de courrier électronique ; exemple : `johndoe@example.com` et non `<space>johndoe@example.com<space>`;
* Lors du hachage des chaînes d’email, veillez à mettre la chaîne en minuscules par hachage.
   * Exemple : `example@email.com` et non `EXAMPLE@EMAIL.COM`;
* Assurez-vous que la chaîne hachée est entièrement en minuscules.
   * Exemple : `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149` et non `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Ne salez pas la chaîne.

Regardez la vidéo ci-dessous pour comprendre les exigences de hachage de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud vous offre la possibilité de hacher les ID de client par le biais de [!DNL Adobe Experience Platform Identity Service (ECID)]. Voir [Prise en charge du hachage SHA-256 pour setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) pour plus d’informations sur l’utilisation de l’ECID pour hacher les ID de client.

## Obtention de l’autorisation de l’utilisateur {#obtaining-user-permission}

Comme [!UICONTROL People-Based Destinations] vous aide à activer les données d’audience propriétaires dans des canaux basés sur des personnes, il vous incombe d’informer vos clients et d’obtenir tout consentement nécessaire de leur part sur la manière dont vous utiliserez leurs données à des fins publicitaires ou autres.

Avant de vous inscrire à [!UICONTROL People-Based Destinations], veillez à obtenir le consentement de vos clients avant d’utiliser leurs informations à des fins publicitaires.

Si vos clients souhaitent se désabonner des campagnes publicitaires, voir [Gestion des exclusions](../../overview/data-security-and-privacy/data-privacy-requests.md) pour plus d’informations sur la manière d’empêcher l’Audience Manager de collecter des données.

## Application de l’activation des données propriétaires {#enforcing-first-party-activation}

Lorsque vous utilisez [!UICONTROL People-Based Destinations], vous ne pouvez utiliser que des données propriétaires pour activer les segments d’audience dans des canaux basés sur les personnes. Vous ne pouvez pas utiliser de données de deuxième ou de troisième niveau pour l’activation de l’audience dans des canaux basés sur des personnes.

Lors de l’utilisation de [!UICONTROL People-Based Destinations], utilisez [Contrôles des exportations de données](../data-export-controls.md) pour étiqueter vos [!UICONTROL data sources] et [!UICONTROL destinations] selon les directives et les exigences des plateformes de destination et des fournisseurs de données.

## Identifiants hachés authentifiés intégrés par le biais du ciblage des identifiants déclarés {#onboard-authenticated-declared-id}

Il existe deux manières d’importer vos données hors ligne vers Audience Manager pour [!UICONTROL People-Based Destinations].

* [Envoyez des ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) données par lots pour ingérer des adresses électroniques hachées. Avec cette méthode, vous pouvez choisir d’utiliser les adresses électroniques hachées de votre base de données [!DNL CRM] dans [!UICONTROL People-Based Destinations]. En outre, lorsque vous utilisez cette méthode, vous pouvez également qualifier les adresses électroniques hachées pour les [caractéristiques intégrées](../traits/trait-and-segment-qualification-reference.md).
* Utilisez [les identifiants déclarés](../declared-ids.md) pour déclarer les adresses électroniques hachées lors de la transmission des identifiants client authentifiés. Lors de l’utilisation de cette méthode, l’Audience Manager, en votre nom, envoie uniquement à [!UICONTROL People-Based Destinations] les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques activées par le biais de canaux basés sur les personnes ne sont que celles des appels d’événement d’ID déclaré. Les autres adresses électroniques associées à l’ID de client ne sont pas envoyées en temps réel.
