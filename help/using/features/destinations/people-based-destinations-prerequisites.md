---
description: 'Lisez ci-dessous pour une vue d’ensemble des exigences des clients que vous devez satisfaire avant de vous inscrire aux destinations basées sur les personnes.  '
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Conditions préalables et considérations
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# Conditions préalables et considérations {#prerequisites-considerations}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent article n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Lisez ci-dessous pour une vue d’ensemble des exigences du client que vous devez satisfaire avant de vous abonner à [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lisez attentivement cet article avant de passer à la phase de mise en oeuvre.

## Inscrivez-vous à [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] est une fonctionnalité premium qui améliore votre expérience d’Audience Manager en vous permettant d’activer vos segments d’audience propriétaires dans des environnements basés sur les personnes, en ciblant votre audience avec des offres personnalisées sur les réseaux sociaux ou par le biais du marketing par e-mail.

Veuillez contacter votre représentant Adobe pour profiter de cette fonctionnalité premium.

## Conditions préalables spécifiques au partenaire {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Avant d’utiliser [!UICONTROL People-Based Destinations] pour envoyer votre audience propriétaire [!UICONTROL segments] to [!DNL Facebook], assurez-vous de respecter les conditions suivantes :

1. Votre [!DNL Facebook] Le compte utilisateur doit avoir la variable **Gestion des campagnes** autorisation activée pour le compte publicitaire que vous prévoyez d’utiliser.
2. Ajoutez la variable **Adobe Experience Cloud** compte commercial en tant que partenaire publicitaire dans votre [!DNL Facebook Ad Account]. Utilisez `business ID=206617933627973`. Voir [Ajout de partenaires à votre compte Business Manager](https://www.facebook.com/business/help/1717412048538897) pour plus d’informations.
   >[!IMPORTANT]
   > Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l’option **Gestion des campagnes** autorisation. Ceci est obligatoire pour l’intégration de [!UICONTROL People-Based Destinations].
3. Lisez et signez le [!DNL Facebook Custom Audiences] Conditions d’utilisation. Pour ce faire, accédez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Avant d’utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d’audience propriétaires à [!DNL LinkedIn], assurez-vous que [!DNL LinkedIn Campaign Manager] Le compte a la variable [!DNL Creative Manager] ou niveau d’autorisation supérieur.

Pour savoir comment modifier votre [!DNL LinkedIn Campaign Manager] autorisations utilisateur, voir [Ajout, modification et suppression des autorisations d’utilisateur sur les comptes Advertising](https://www.linkedin.com/help/lms/answer/5753) dans la documentation de LinkedIn.

Voir [Présentation et configuration de la destination basée sur les personnes de LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) pour obtenir des instructions vidéo.

### [!DNL Google Customer Match] {#gcm}

Avant d’utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d’audience propriétaires à un [!DNL Google Customer Match] destination, veillez à lire et à respecter la politique de Google pour l’utilisation de [!DNL Customer Match], comme indiqué dans la section [Documentation de prise en charge de Google](https://support.google.com/google-ads/answer/6299717).

Ensuite, assurez-vous que la variable [!DNL Google] compte configuré pour un [!DNL Standard] ou niveau d’autorisation supérieur. Voir [Documentation sur Google Ads](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) pour plus d’informations.

Les clients disposant de comptes conformes sont automatiquement autorisés à être répertoriés par Google.

## Intégration de données {#data-onboarding}

Ingestion de données pour [!UICONTROL People-Based Destinations] prend actuellement en charge jusqu’à 10 adresses électroniques hachées liées à un ID de client ([!DNL CRM ID]), par transfert par lot. Le téléchargement de plus de 10 adresses électroniques hachées liées à un ID de client entraîne l’Audience Manager d’en ingérer 10, sans ordre spécifique.

Le chargement de plus de 10 adresses électroniques hachées liées à un ID de client dans plusieurs transferts par lots entraîne l’Audience Manager à conserver les 10 adresses électroniques ajoutées les plus récentes.

## Confidentialité des données {#data-privacy}

Bien que [!UICONTROL People-Based Destinations] pour vous permettre de cibler des audiences en fonction d’adresses électroniques hachées que vous avez téléchargées, il vous est toujours interdit de charger des informations de visiteur directement identifiables dans Audience Manager. Lors de la phase d’intégration des données, vous devez vous assurer que les adresses électroniques que vous prévoyez d’utiliser sont hachées avec la variable [!DNL SHA256] algorithme. Sinon, vous ne pourrez pas les utiliser dans [!UICONTROL People-Based Destinations].

## Hachage de données contre chiffrement {#data-hashing-encryption}

Le chiffrement est une fonction bidirectionnelle. Toutes les informations cryptées peuvent également être décryptées à l’aide de la clé de décryptage correcte. Le cryptage des données dans le contexte de l’Audience Manager présente de sérieux risques, dans la mesure où toute forme cryptée d’informations d’identification personnelle peut également être déchiffrée. Contrairement au chiffrement, [!UICONTROL People-Based Destinations] sont conçus pour fonctionner avec des données hachées.

Le hachage est une fonction unidirectionnelle qui fait défiler l’entrée pour produire un résultat unique. En utilisant des algorithmes de hachage appropriés, comme [!DNL SHA256], il n’existe aucun moyen d’inverser la fonction de hachage et de révéler les informations non brouillées. Les adresses électroniques que vous allez intégrer à l’Audience Manager doivent être hachées avec la variable [!DNL SHA256] algorithme. Ainsi, vous pouvez vous assurer qu’aucune adresse électronique non hachée n’atteint l’Audience Manager.

## Exigences de hachage {#hashing-requirements}

Lors du hachage des adresses email, veillez à respecter les exigences suivantes :

* Rogner tous les espaces de début et de fin de la chaîne de courrier électronique ; exemple : `johndoe@example.com`, not `<space>johndoe@example.com<space>`;
* Lors du hachage des chaînes d’email, veillez à mettre la chaîne en minuscules par hachage.
   * Exemple : `example@email.com`, not `EXAMPLE@EMAIL.COM`;
* Assurez-vous que la chaîne hachée est entièrement en minuscules.
   * Exemple : `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, not `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Ne salez pas la chaîne.

Regardez la vidéo ci-dessous pour comprendre les exigences de hachage de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud vous offre la possibilité de hacher des ID de client via le [!DNL Adobe Experience Platform Identity Service (ECID)]. Voir [Prise en charge du hachage SHA-256 pour setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) pour obtenir des informations détaillées sur l’utilisation d’ECID pour hacher les ID de client.

## Obtention de l’autorisation d’utilisateur {#obtaining-user-permission}

Depuis [!UICONTROL People-Based Destinations] vous aide à activer les données d’audience propriétaires dans des canaux basés sur des personnes. Il vous incombe d’informer vos clients et d’obtenir tout consentement nécessaire de leur part sur la manière dont vous utiliserez leurs données à des fins publicitaires ou autres.

Avant de vous inscrire [!UICONTROL People-Based Destinations], veillez à obtenir le consentement de vos clients avant d’utiliser leurs informations à des fins publicitaires.

Si vos clients souhaitent se désinscrire des campagnes publicitaires, reportez-vous à la section [Gestion des exclusions](../../overview/data-security-and-privacy/data-privacy-requests.md) pour plus d’informations sur la manière d’empêcher l’Audience Manager de collecter des données.

## Application de l’activation des données propriétaires {#enforcing-first-party-activation}

Lors de l’utilisation de [!UICONTROL People-Based Destinations], vous pouvez uniquement utiliser des données propriétaires pour activer les segments d’audience dans des canaux basés sur les personnes. Vous ne pouvez pas utiliser de données de deuxième ou de troisième niveau pour l’activation de l’audience dans des canaux basés sur des personnes.

Lors de l’utilisation de [!UICONTROL People-Based Destinations], utilisez [Contrôles des exportations de données](../data-export-controls.md) pour étiqueter votre [!UICONTROL data sources] et [!UICONTROL destinations] selon les directives et les exigences des plateformes de destination et des fournisseurs de données.

## Intégrer les identifiants hachés authentifiés par le biais du ciblage des identifiants déclarés {#onboard-authenticated-declared-id}

Il existe deux manières d’importer vos données hors ligne vers Audience Manager pour [!UICONTROL People-Based Destinations].

* [Envoi de données par lot](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) Audience Manager d’ingérer des adresses électroniques hachées. Grâce à cette méthode, vous pouvez choisir d’utiliser les adresses électroniques hachées de votre [!DNL CRM] base de données dans [!UICONTROL People-Based Destinations]. En outre, lorsque vous utilisez cette méthode, vous pouvez également qualifier les adresses électroniques hachées pour [caractéristiques intégrées](../traits/trait-and-segment-qualification-reference.md).
* Utilisation [Identifiants déclarés](../declared-ids.md) pour déclarer des adresses électroniques hachées lors de la transmission d’identifiants client authentifiés. Lors de l’utilisation de cette méthode, l’Audience Manager, en votre nom, envoie uniquement à [!UICONTROL People-Based Destinations] les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques activées par le biais de canaux basés sur les personnes ne sont que celles des appels d’événement d’ID déclaré. Les autres adresses électroniques associées à l’ID de client ne sont pas envoyées en temps réel.
