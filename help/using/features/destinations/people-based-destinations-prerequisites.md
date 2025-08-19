---
description: Lisez ci-dessous pour avoir un aperçu des exigences des clients que vous devez satisfaire avant de vous inscrire aux destinations basées sur les personnes.
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Conditions préalables et considérations
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: 2b823855994f394261a66e896ef7de7bb7a5450f
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 2%

---


# Conditions préalables et considérations {#prerequisites-considerations}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Lisez ci-dessous pour avoir un aperçu des exigences des clients que vous devez satisfaire avant de vous inscrire à [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lisez attentivement cet article avant de passer à la phase de mise en œuvre.

## S’inscrire à [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] est une fonctionnalité premium qui améliore votre expérience Audience Manager en vous permettant d’activer vos segments d’audience propriétaires dans des environnements basés sur des personnes, en ciblant votre audience avec des offres personnalisées sur les réseaux sociaux ou par le biais du marketing par e-mail.

Contactez votre représentant ou représentante Adobe pour tirer parti de cette fonctionnalité premium.

## Conditions préalables spécifiques aux partenaires {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer vos [!UICONTROL segments] d’audience propriétaires à [!DNL Facebook], assurez-vous de respecter les exigences suivantes :

1. Votre compte utilisateur [!DNL Facebook] doit disposer de l’autorisation **Gérer les campagnes** activée pour le compte publicitaire que vous prévoyez d’utiliser.
2. Ajoutez le compte professionnel **Adobe Experience Cloud** en tant que partenaire publicitaire dans votre [!DNL Facebook Ad Account]. Utilisez `business ID=206617933627973`. Voir [Ajouter des partenaires à votre Business Manager](https://www.facebook.com/business/help/1717412048538897) pour plus d’informations.

   >[!IMPORTANT]
   >Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l’autorisation **Gérer les campagnes**. Ceci est obligatoire pour l’intégration de [!UICONTROL People-Based Destinations].

3. Lisez et signez les Conditions d&#39;utilisation de [!DNL Facebook Custom Audiences]. Pour ce faire, accédez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn] {#linkedin}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d’audience propriétaires à [!DNL LinkedIn], assurez-vous que votre compte [!DNL LinkedIn Campaign Manager] dispose du niveau d’autorisation [!DNL Creative Manager] ou supérieur.

Pour savoir comment modifier vos autorisations d’utilisateur [!DNL LinkedIn Campaign Manager], voir [Ajouter, modifier et supprimer des autorisations d’utilisateur sur les comptes Advertising](https://www.linkedin.com/help/lms/answer/5753) dans la documentation LinkedIn.

Consultez [Présentation et configuration de la destination LinkedIn basée sur les personnes](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html?lang=fr) pour obtenir des instructions vidéo.

### [!DNL Google Customer Match] {#gcm}

Avant de pouvoir utiliser [!UICONTROL People-Based Destinations] pour envoyer vos segments d’audience propriétaires vers une destination [!DNL Google Customer Match], veillez à lire et à respecter la politique de Google relative à l’utilisation de [!DNL Customer Match], décrite dans la [documentation de prise en charge de Google](https://support.google.com/google-ads/answer/6299717).

Ensuite, assurez-vous que votre compte [!DNL Google] est configuré pour un niveau d’autorisation [!DNL Standard] ou supérieur. Pour plus d’informations[ consultez la documentation sur les Google Ads ](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&rd=1).

Les clients disposant de comptes conformes sont automatiquement placés sur la liste autorisée par Google.

## Intégration des données {#data-onboarding}

>[!IMPORTANT]
>
>Tous les clients Audience Manager peuvent ingérer des e-mails hachés sans s’inscrire à [!UICONTROL People-Based Destinations].

L’ingestion de données pour [!UICONTROL People-Based Destinations] prend actuellement en charge jusqu’à 10 adresses e-mail hachées liées à un ID client ([!DNL CRM ID]) par transfert par lots.

Le chargement de plus de 10 adresses e-mail hachées liées à un ID de client dans plusieurs transferts par lots entraîne la conservation par Audience Manager des 10 adresses e-mail ajoutées le plus récemment.

Pour ingérer des identifiants hachés, [créez une source de données entre appareils pour les identifiants hachés](../create-data-source-hashed-emails.md) et activez l’option **[!UICONTROL Share associated cross-device IDs in people-based destinations and/or hashed email workflows]** .

![Image de l’interface utilisateur d’Audience Manager montrant l’option de partage des identifiants inter-appareils associés dans les destinations basées sur les personnes et/ou les workflows d’e-mail hachés](assets/data-source-share-ids.png)

## Confidentialité Des Données {#data-privacy}

Bien que les [!UICONTROL People-Based Destinations] vous permettent de cibler des audiences en fonction d’adresses e-mail hachées que vous avez chargées, il vous est toujours interdit de charger des informations de visiteur directement identifiables dans Audience Manager. Lors de la phase d’intégration des données, vous devez vous assurer que les adresses e-mail que vous prévoyez d’utiliser sont hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas les utiliser dans [!UICONTROL People-Based Destinations].

## Hachage De Données Et Chiffrement {#data-hashing-encryption}

Le chiffrement est une fonction bidirectionnelle. Toutes les informations chiffrées peuvent également être déchiffrées à l’aide de la clé de déchiffrement appropriée. Le chiffrement des données dans le cadre d’Audience Manager présente de sérieux risques, car toute forme chiffrée d’informations d’identification personnelle peut également être déchiffrée. Contrairement au chiffrement, les [!UICONTROL People-Based Destinations] sont conçus pour fonctionner avec des données hachées.

Le hachage est une fonction à sens unique qui brouille l’entrée pour produire un résultat unique. En utilisant des algorithmes de hachage appropriés, tels que [!DNL SHA256], il n’existe aucun moyen d’inverser la fonction de hachage et de révéler les informations non brouillées. Les adresses e-mail que vous intégrerez à Audience Manager doivent être hachées avec l’algorithme [!DNL SHA256]. Vous pouvez ainsi vous assurer qu’aucune adresse e-mail non hachée n’atteint Audience Manager.

## Exigences de hachage {#hashing-requirements}

Lors du hachage des adresses e-mail, veillez à respecter les exigences suivantes :

* Supprimez tous les espaces de début et de fin de la chaîne d’e-mail ; par exemple : `johndoe@example.com`, pas `<space>johndoe@example.com<space>` ;
* Lors du hachage des chaînes de l’e-mail, veillez à hacher la chaîne en minuscules ;
   * Exemple : `example@email.com`, pas `EXAMPLE@EMAIL.COM` ;
* Vérifiez que la chaîne hachée est en minuscules
   * Exemple : `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, pas `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149` ;
* Ne salez pas la chaîne.

Regardez la vidéo ci-dessous pour comprendre les exigences de hachage de [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud vous offre la possibilité de hacher les ID de client par le biais du [!DNL Adobe Experience Platform Identity Service (ECID)]. Consultez [SHA256 Prise en charge du hachage pour setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html?lang=fr) pour plus d’informations sur l’utilisation d’ECID pour hacher les ID client.

## Obtention des autorisations utilisateur {#obtaining-user-permission}

Puisque [!UICONTROL People-Based Destinations] vous aide à activer les données d’audience propriétaires dans les canaux basés sur les personnes, il est de votre responsabilité d’informer vos clients et d’obtenir tous les consentements nécessaires sur la manière dont vous utiliserez leurs données à des fins publicitaires ou autres.

Avant de vous inscrire à [!UICONTROL People-Based Destinations], assurez-vous d&#39;obtenir le consentement de vos clients avant d&#39;utiliser leurs renseignements à des fins publicitaires.

Si vos clients souhaitent se désabonner des campagnes publicitaires, consultez [Gestion des désabonnements](../../overview/data-security-and-privacy/data-privacy-requests.md) pour plus d’informations sur la manière d’empêcher Audience Manager de collecter des données.

## Application de l’activation des données propriétaires {#enforcing-first-party-activation}

Lors de l’utilisation de [!UICONTROL People-Based Destinations], vous pouvez uniquement utiliser des données propriétaires pour activer des segments d’audience dans des canaux basés sur des personnes. Vous ne pouvez pas utiliser de données tierces ou secondaires pour l’activation de l’audience dans les canaux basés sur les personnes.

Lors de l’utilisation de [!UICONTROL People-Based Destinations], utilisez [Contrôles d’exportation de données](../data-export-controls.md) pour étiqueter vos [!UICONTROL data sources] et [!UICONTROL destinations] en fonction des directives et des exigences des plateformes de destination et des fournisseurs de données.

## Intégration d’ID hachés authentifiés via le ciblage des ID déclarés {#onboard-authenticated-declared-id}

Il existe deux manières d’importer vos données hors ligne vers Audience Manager pour [!UICONTROL People-Based Destinations].

* [Envoyez des données par lot](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) à Audience Manager pour ingérer des adresses e-mail hachées. Avec cette méthode, vous pouvez choisir d’utiliser les adresses e-mail hachées de votre base de données [!DNL CRM] dans [!UICONTROL People-Based Destinations]. En outre, lorsque vous utilisez cette méthode, vous pouvez également qualifier les adresses e-mail hachées pour les [caractéristiques intégrées](../traits/trait-and-segment-qualification-reference.md).
* Utilisez des [identifiants déclarés](../declared-ids.md) pour déclarer des adresses e-mail hachées lors de la transmission d’identifiants de client authentifiés. Lorsque vous utilisez cette méthode, Audience Manager, pour votre compte, envoie uniquement à [!UICONTROL People-Based Destinations] les adresses e-mail hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses e-mail activées par le biais des canaux basés sur les personnes sont uniquement celles qui figurent dans les appels d’événement d’ID déclarés. Les autres adresses e-mail associées à l’ID de client ne sont pas envoyées en temps réel.
