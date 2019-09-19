---
description: 'Réponses aux questions courantes sur les destinations basées sur les personnes.  '
seo-description: 'Réponses aux questions courantes sur les destinations basées sur les personnes.  '
seo-title: FAQ sur les destinations basées sur les personnes
solution: Audience Manager
title: FAQ sur les destinations basées sur les personnes
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# FAQ sur les destinations basées sur les personnes {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Je ne peux pas voir[!DNL People-Based Destinations]dans mon compte Audience Manager. Que dois-je savoir sur la disponibilité ?**

[!DNL People-Based Destinations] est une fonctionnalité Premium d’Audience Manager disponible à l’achat. Contactez votre représentant commercial Adobe pour plus d’informations sur les tarifs et la disponibilité.

## Intégration des données {#data-onboarding}

**Comment puis-je intégrer les adresses électroniques des clients dans Audience Manager pour pouvoir les utiliser dans[!DNL People-Based Destinations]?**

Vous pouvez apporter vos données hors ligne à Audience Manager de deux manières [!DNL People-Based Destinations].

* **Utilisez la synchronisation** des identifiants basée sur des fichiers. Pour plus d’informations sur l’aspect des fichiers [de synchronisation des identifiants, reportez-vous à la section](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) Nom et configuration requise du contenu. Lorsque vous utilisez cette méthode, vous pouvez cibler toutes les adresses électroniques hachées de votre [!DNL CRM] base de données.
* **Utilisez les ID** déclarés pour déclarer les adresses électroniques hachées lors de la transmission des ID de client authentifiés. Lors de l’utilisation de cette méthode, Audience Manager active uniquement les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques activées via Facebook ne sont que celles des appels d’événement d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas activées en temps réel.

**Puis-je collecter les adresses électroniques hachées par le biais d’un formulaire Web ou d’une application mobile ou dois-je les transmettre par lots ?**

Vous pouvez collecter des adresses électroniques hachées via l’authentification Web à l’aide [!DNL ECID] d’identifiants [déclarés](../features/declared-ids.md). Le fichier de commandes vous permet également de collecter des adresses électroniques hachées qui ne peuvent pas être envoyées par authentification (par exemple, des utilisateurs inactifs dans votre ([!DNL CRM]) et de les activer dans des destinations basées sur des personnes).

**En quoi l’assimilation d’adresses électroniques hachées via des formulaires Web diffère-t-elle du transfert d’adresses électroniques hachées via des fichiers de commandes ?**

L’assimilation de données hors ligne est conçue pour prendre en charge les cas d’utilisation sans authentification. Une nouvelle règle de fusion de profil ([!UICONTROL All Cross-Device Profiles]) qui s’exécute sur tous les [!DNL CRM] profils hors ligne, quelle que soit l’authentification, est disponible dans le cadre [!DNL People-Based Destinations]. Cette méthode est destinée à compléter l’assimilation d’audiences authentifiées à partir de sources en ligne.

**Quelle est la fréquence maximale à laquelle je peux envoyer/mettre à jour des adresses électroniques hachées ?**

* Lors de l’utilisation d’identifiants déclarés, Audience Manager envoie les adresses électroniques hachées à la destination en temps réel.
* Lors de l’assimilation de données au moyen de fichiers de synchronisation des identifiants, Audience Manager les traite quotidiennement.

**Comment puis-je savoir si le hachage de l’adresse électronique est effectué correctement ?**

Audience Manager n’ingère pas l’adresse électronique brute et nous ne pouvons pas confirmer que le hachage a été effectué correctement. Voir [Conditions préalables et considérations](../features/destinations/people-based-destinations-prerequisites.md) pour en savoir plus sur la manière de hacher les données intégrées.

## Règles de fusion de profils {#profile-merge-rules}

**Existe-t-il une nouvelle règle de fusion de profil que je puisse utiliser[!DNL People-Based Destinations]?**

Oui. Les clients qui achètent [!DNL People-Based Destinations] ont également accès à une nouvelle règle de fusion de profil pour la segmentation hors ligne. La règle est appelée [!DNL All Cross-Device Profiles] et utilisée pour la segmentation hors ligne uniquement. Lorsque vous vous inscrivez [!DNL People-Based Destinations], il s’agit de la quatrième règle de fusion de profil que vous pouvez créer, à l’exception des trois règles existantes basées sur l’authentification.

**Dois-je dupliquer mes segments d’audience existants pour les activer dans[!DNL People-Based Destinations]?**

Ça dépend de votre cas d'utilisation. Si vous prévoyez d’activer des segments propriétaires existants dans des canaux basés sur des personnes, vous n’avez pas besoin de créer de nouveaux segments. Vous pouvez simplement mapper les segments à une destination basée sur les personnes.

Si vous prévoyez d’activer de nouvelles audiences hors ligne dans des canaux basés sur les personnes, vous devez créer de nouveaux segments propriétaires à l’aide de la règle de [!DNL All Cross-Device Profiles] fusion.
>[!NOTE]
>
> Vous pouvez uniquement mapper des segments avec des données propriétaires à [!DNL People-Based Destinations]. Nos plateformes de destination n’acceptent pas les segments avec des données propriétaires et tierces.

## Taux de correspondance {#match-rates}

**Dispose-t-[!DNL People-Based Destinations]il d’une visibilité sur les taux de correspondance ou les audiences adressables ?**

Non. Lors de l’envoi de segments d’audience à [!DNL People-Based Destinations], la correspondance d’audience se produit côté partenaire. Adobe n’a pas accès à ces mesures. Audience Manager vous montre le public partageable maximum pour chaque destination et le nombre en temps réel de personnes appartenant à un segment. Ces informations peuvent vous aider à planifier et à prévoir vos campagnes.

**Comment faire correspondre les taux en[!DNL People-Based Destinations]théorie par rapport à d’autres méthodes d’envoi d’audiences vers des plateformes de destination ?**

Tant que l’adresse électronique est hachée et correctement ingérée, il ne doit pas y avoir de différence dans le taux de correspondance entre [!DNL People-Based Destinations] et les autres méthodes. La seule raison pour laquelle un taux de correspondance serait inférieur à 100 % est que les adresses électroniques introduites dans Audience Manager ne peuvent pas être associées à une adresse électronique dans la base d’utilisateurs de la plateforme de destination.

**Je recueille les adresses électroniques de mes clients, qui sont différentes des adresses électroniques personnelles utilisées dans les réseaux sociaux. Comment faire correspondre les identités entre plusieurs adresses électroniques ?**

Audience Manager peut collecter et envoyer jusqu’à 10 courriers électroniques par utilisateur vers les plateformes de destination, mais les adresses électroniques doivent être capturées au moyen de fichiers de synchronisation. Une fois que Audience Manager envoie les adresses électroniques aux plateformes de destination, il appartient aux plateformes de faire correspondre les adresses électroniques à leur propre base d’utilisateurs. Certaines plateformes peuvent comporter des graphiques d’adresses électroniques supplémentaires pour correspondre aux adresses envoyées d’Audience Manager aux profils utilisateur.

## Contrôles des exportations de données {#data-export-controls}

**Comment[!DNL Data Export Controls]travailler avec[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloque tous les segments contenant des données propriétaires et tiers que les utilisateurs tentent d’envoyer à [!DNL People-Based Destinations]. [!DNL People-Based Destinations] autorise uniquement l’utilisation des données propriétaires pour le ciblage. [!DNL Data Export Controls] bloque également les segments à l’aide [!DNL Profile Merge Rules] de graphiques de périphérique. [!DNL People-Based Destinations] sont créées avec les étiquettes d’exportation de données appropriées cochées et vous ne pouvez pas remplacer les paramètres d’exportation.

## Questions spécifiques aux partenaires {#partner-specific-questions}

### [!DNL Facebook]

**Que dois-je faire avant d’envoyer des segments d’audience à[!DNL Facebook]?**

Avant de pouvoir [!DNL People-Based Destinations] envoyer des segments d’audience à [!DNL Facebook], vous devez exécuter les tâches de configuration suivantes :

1. Ajoutez le compte professionnel Adobe Experience Cloud en tant que partenaire publicitaire dans votre [!DNL Facebook Ad Account]compte. Utilisez `business ID=206617933627973`. Voir Ajout de partenaires à votre gestionnaire d’entreprise pour plus d’informations.

   >[!IMPORTANT]
   >
   > Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l’autorisation Gérer les campagnes. Ceci est nécessaire pour l’ [!DNL People-Based Destinations] intégration.

1. Lisez et signez le [!DNL Facebook Custom Audiences Terms of Service]. Pour ce faire, allez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

**Le ciblage de l’audience est-il pris en charge[!DNL People-Based Destinations]dans d’autres[!DNL Facebook]applications, par exemple[!DNL Instagram]?**

Vous pouvez utiliser [!DNL People-Based Destinations] toute [!DNL Facebook]la famille d’applications prises en charge par [!DNL Custom Audiences], notamment [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] et [!DNL Messenger]. La sélection de l’application sur laquelle vous souhaitez exécuter la campagne est indiquée au niveau de l’emplacement dans [!DNL Facebook Ads Manager].

**Quelle est la différence entre[!DNL People-Based Destinations]et[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] tire parti de l’ [!DNL Custom Audiences (CA)] intégration avec [!DNL Facebook]. La différence entre [!DNL WCA] et [!DNL CA] les intégrations est la clé que les clients utilisent lorsqu’ils envoient des audiences à [!DNL Facebook]. [!DNL WCA] utilise le [!DNL Facebook] pixel (qui serait un ID utilisateur de site Web) alors [!DNL People-Based Destinations] qu’il utilise des adresses électroniques hachées pour s’intégrer à [!DNL CA].

Vous pouvez utiliser l’ [!DNL Facebook] intégration d’Audience Manager [!DNL WCA] via la [!DNL URL Destinations] fonctionnalité sans frais supplémentaires.

Ces deux intégrations sont complémentaires; vous pouvez utiliser les deux pour assurer une meilleure couverture du public. Par exemple, [!DNL WCA] peut être utilisé pour la prospection lorsqu’une entreprise cherche à cibler les visiteurs du site Web qui n’ont pas enregistré de compte, alors [!DNL People-Based Destinations] qu’elle peut vous aider à cibler les clients existants qui ont fourni leur adresse électronique, mais peut-être pas visité le site Web.
