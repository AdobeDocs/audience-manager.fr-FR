---
description: 'Réponses aux questions courantes sur les destinations basées sur People.  '
seo-description: 'Réponses aux questions courantes sur les destinations basées sur People.  '
seo-title: FAQ sur les destinations basées sur People
solution: Audience Manager
title: FAQ sur les destinations basées sur People
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# FAQ sur les destinations basées sur People {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Je ne vois pas[!DNL People-Based Destinations]dans mon compte Audience Manager. Que dois-je savoir sur la disponibilité ?**

[!DNL People-Based Destinations] est une fonctionnalité Premium de Audience Manager disponible lors de l'achat. Pour plus d'informations sur les tarifs et la disponibilité, contactez votre représentant commercial Adobe.

## Data Onboarding {#data-onboarding}

**Comment puis-je utiliser les adresses électroniques des clients dans Audience Manager pour les utiliser[!DNL People-Based Destinations]dans ?**

Vous pouvez importer vos données hors ligne de deux manières sur Audience [!DNL People-Based Destinations]Manager.

* **Utilisez la synchronisation des identifiants basée sur un fichier**. Pour plus d'informations sur les fichiers de synchronisation d'ID, reportez-vous à [la section Nom et exigences de contenu pour les fichiers](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de synchronisation des identifiants. Lorsque vous utilisez cette méthode, vous pouvez cibler toutes les adresses électroniques hachées à partir de votre [!DNL CRM] base de données.
* **Utilisez les ID déclarés** pour déclarer des adresses électroniques hachées lors de la transmission d'identifiants de client authentifiés. Lors de l'utilisation de cette méthode, Audience Manager active uniquement les adresses électroniques hachées des utilisateurs qui sont authentifiés en ligne. Les adresses électroniques activées via Facebook ne sont que celles qui figurent dans les appels d'événement d'ID déclarés. Les autres adresses électroniques associées à l'ID de client ne sont pas activées en temps réel.

**Puis-je collecter des adresses électroniques hachées par l'intermédiaire d'un formulaire Web ou d'une application mobile ou bien les utiliser dans un fichier de commandes ?**

Vous pouvez collecter des adresses électroniques hachées par l'intermédiaire d'une authentification Web avec [!DNL ECID] des ID [déclarés](../features/declared-ids.md). Le fichier de commandes vous permet également de collecter des adresses électroniques hachées qui ne peuvent pas être envoyées via une authentification (utilisateurs inactifs par exemple dans votre ([!DNL CRM]) et les activer dans des destinations basées sur des personnes.

**Comment l'assimilation d'adresses électroniques hachées par des formulaires Web diffère-t-elle du transfert des adresses électroniques hachées par le biais de fichiers par lots ?**

L'ingestion des données hors ligne est conçue pour prendre en charge les cas d'utilisation sans authentification et une nouvelle règle de fusion de profil ([!UICONTROL All Cross-Device Profiles]) qui s'exécute sur tous [!DNL CRM] les profils hors ligne, quelle [!DNL People-Based Destinations]que soit l'authentification disponible. Cette méthode est censée compléter l'assimilation d'audiences authentifiées provenant de sources en ligne.

**Quelle est la fréquence maximale à laquelle je peux envoyer/mettre à jour des adresses électroniques hachées ?**

* Lors de l'utilisation d'ID déclarés, Audience Manager envoie les adresses électroniques hachées à la destination en temps réel.
* Lors de l'assimilation de données via des fichiers de synchronisation d'ID, Audience Manager les traite quotidiennement.

**Comment savoir si le hachage de l'adresse électronique est effectué correctement ?**

Audience Manager n'imbrique pas l'adresse électronique brute et nous ne pouvons pas vérifier que le hachage a été effectué correctement. Pour plus d'informations sur la façon de hacher les données intégrées, reportez-vous à [la section Conditions préalables et points à prendre en compte](../features/destinations/people-based-destinations-prerequisites.md) .

## Règles de fusion de profils {#profile-merge-rules}

**Existe-t-il une nouvelle règle de fusion de profil avec[!DNL People-Based Destinations]laquelle je peux utiliser ?**

Oui. Les clients qui achètent [!DNL People-Based Destinations] sont également autorisés à accéder à une nouvelle règle de fusion de profil pour la segmentation hors ligne. La règle est appelée [!DNL All Cross-Device Profiles] et elle est utilisée pour la segmentation hors ligne uniquement. Lorsque vous vous inscrivez [!DNL People-Based Destinations], il s'agit de la quatrième règle de fusion de profil que vous pouvez créer, en plus des trois règles d'authentification existantes.

**Dois-je dupliquer mes segments d'audience existants pour les activer[!DNL People-Based Destinations]?**

Cela dépend de votre cas d'utilisation. Si vous envisagez d'activer des segments propriétaires existants dans des canaux tiers, vous n'avez pas besoin de créer de segments. Vous pouvez simplement mapper les segments à une destination basée sur des personnes.

Si vous envisagez d'activer de nouvelles audiences hors ligne dans les canaux basés sur les personnes, vous devez créer de nouveaux segments propriétaires à l'aide de [!DNL All Cross-Device Profiles] la règle de fusion.
>[!NOTE]
>
> Vous pouvez uniquement mapper les segments avec des données propriétaires à [!DNL People-Based Destinations]. Nos plateformes de destination n'acceptent pas les segments avec des données tierces et tierces.

## Taux de correspondance {#match-rates}

**Les[!DNL People-Based Destinations]taux de correspondance ou les audiences adressables sont-ils visibles ?**

Non. Lors de l'envoi de segments d'audience, [!DNL People-Based Destinations]la correspondance de l'audience se produit côté partenaire. Adobe n'a pas accès à ces mesures. Audience Manager vous montre l'audience partageable maximale pour chaque destination et le nombre réel de personnes appartenant à un segment. Ces informations peuvent vous aider à planifier la planification et la planification des campagnes.

**Comment les taux de correspondance sont-ils comparés[!DNL People-Based Destinations]théoriquement à d'autres méthodes d'envoi d'audiences aux plateformes de destination ?**

Tant que l'adresse électronique est hachée et assimilée correctement, il ne doit pas y avoir de différence dans le taux de correspondance entre [!DNL People-Based Destinations] et d'autres méthodes. La seule raison pour laquelle un taux de correspondance est inférieur à 100 % est que les adresses électroniques introduites dans Audience Manager ne peuvent pas correspondre à une adresse électronique dans la base d'utilisateurs de la plateforme de destination.

**Je recueille des adresses électroniques de travail de mes clients, qui diffèrent des adresses électroniques personnelles utilisées dans les réseaux sociaux. Comment faire pour associer les identités à plusieurs adresses électroniques ?**

Audience Manager peut collecter et envoyer jusqu'à 10 courriels par utilisateur aux plateformes de destination, mais les adresses de courriel doivent être capturées par des fichiers de synchronisation. Une fois que Audience Manager envoie les adresses électroniques aux plateformes de destination, il appartient aux plateformes de correspondre aux adresses de courriel par rapport à leur base d'utilisateurs. Certaines plateformes peuvent comporter des graphiques d'adresses de courriel supplémentaires pour correspondre aux adresses envoyées par Audience Manager à des profils utilisateur.

## Contrôles des exportations de données {#data-export-controls}

**Comment[!DNL Data Export Controls]fonctionne[!DNL People-Based Destinations]-t-on ?**

[!DNL Data Export Controls] bloque tous les segments contenant des données tierces et tierces que les utilisateurs tentent [!DNL People-Based Destinations]d'envoyer. [!DNL People-Based Destinations] autoriser uniquement les données propriétaires à utiliser pour le ciblage. [!DNL Data Export Controls] bloquer également les segments à l'aide [!DNL Profile Merge Rules] de graphiques de périphérique. [!DNL People-Based Destinations] sont créées avec les étiquettes d'exportation de données appropriées cochées et vous ne pouvez pas remplacer les paramètres d'exportation.

## Questions spécifiques au partenaire {#partner-specific-questions}

### [!DNL Facebook]

**Que dois-je faire avant d'envoyer des segments d'audience[!DNL Facebook]?**

Avant de [!DNL People-Based Destinations] pouvoir envoyer des segments d'audience, [!DNL Facebook]vous devez effectuer les tâches de configuration suivantes :

1. Ajoutez le compte professionnel Adobe Experience Cloud en tant que partenaire de publicité dans [!DNL Facebook Ad Account]votre. Utilisez `business ID=206617933627973`. Pour plus d'informations, consultez Ajout de partenaires à votre gestionnaire d'activités.

   >[!IMPORTANT]
   >
   > Lors de la configuration des autorisations d'Adobe Experience Cloud, vous devez activer l'autorisation Gérer les campagnes. Ceci est requis pour l' [!DNL People-Based Destinations] intégration.

1. Lisez et signez le [!DNL Facebook Custom Audiences Terms of Service]. Pour ce faire, accédez à, où `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]``accountID` est votre [!DNL Facebook Ad Account ID].

**Le ciblage d'audience est-il[!DNL People-Based Destinations]pris en charge dans d'autres[!DNL Facebook]applications,[!DNL Instagram]telles que ?**

Vous pouvez utiliser [!DNL People-Based Destinations] la [!DNL Facebook]famille d'applications prises en charge par [!DNL Custom Audiences], y compris [!DNL Facebook], [!DNL Instagram][!DNL Audience Network] et [!DNL Messenger]. La sélection de l'application sur laquelle vous souhaitez exécuter la campagne est indiquée au niveau de l'emplacement dans [!DNL Facebook Ads Manager].

**Quelle est la différence entre[!DNL People-Based Destinations]et[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] exploite l' [!DNL Custom Audiences (CA)] intégration. [!DNL Facebook] La différence entre [!DNL WCA] et [!DNL CA] les intégrations est la clé utilisée par les clients lors de l'envoi des audiences. [!DNL Facebook] [!DNL WCA] utilise [!DNL Facebook] le pixel (qui serait un utilisateur de site Web - id) tout en [!DNL People-Based Destinations] utilisant des adresses électroniques hachées à intégrer [!DNL CA].

Vous pouvez utiliser [!DNL Facebook][!DNL WCA] l'intégration d'Audience Manager via [!DNL URL Destinations] la fonctionnalité sans frais supplémentaires.

Ces deux intégrations sont complémentaires ; vous pouvez utiliser les deux pour assurer une meilleure couverture d'audience. À titre d'exemple, [!DNL WCA] vous pouvez utiliser la prospection lorsqu'une entreprise cherche à cibler les visiteurs du site Web qui n'ont pas enregistré de compte, alors [!DNL People-Based Destinations] qu'ils peuvent vous aider à cibler les clients qui ont fourni leur adresse électronique mais qui n'ont peut-être pas visité le site Web.
