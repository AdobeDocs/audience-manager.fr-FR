---
description: 'Réponses aux questions courantes sur les destinations basées sur les personnes.  '
seo-description: 'Réponses aux questions courantes sur les destinations basées sur les personnes.  '
seo-title: FAQ sur les destinations basées sur les personnes
solution: Audience Manager
title: FAQ sur les destinations basées sur les personnes
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 6e55d8bc5fe2c5cdcdd36107593215288d491331
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 97%

---


# FAQ sur les destinations basées sur les personnes {#people-based-destinations-faq}

Réponses aux questions courantes sur [!DNL People-Based Destinations].

## Disponibilité {#availability}

**Je ne parviens pas à voir [!DNL People-Based Destinations] dans mon compte Audience Manager. Que dois-je savoir sur la disponibilité ?**

[!DNL People-Based Destinations] est une fonctionnalité premium Audience Manager disponible à l’achat. Veuillez contacter votre représentant commercial Adobe pour obtenir des informations sur son prix et sa disponibilité.

## Intégration de données {#data-onboarding}

**Comment puis-je intégrer des adresses électroniques de clients dans Audience Manager afin de pouvoir les utiliser dans [!DNL People-Based Destinations] ?**

Il existe deux manières d’importer vos données hors ligne vers Audience Manager pour [!DNL People-Based Destinations].

* **Utilisez la synchronisation d’identifiants basée sur le fichier**. Consultez [les exigences en matière de contenu pour les fichiers de synchronisation d’identifiants](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) pour obtenir des informations sur ce à quoi les fichiers de synchronisation d’identifiants doivent ressembler. Lorsque vous utilisez cette méthode, vous pouvez cibler toutes les adresses électroniques hachées de votre base de données [!DNL CRM].
* **Utilisez des identifiants déclarés** pour déclarer les adresses électroniques hachées lorsque vous transmettez des identifiants client authentifiés. Lorsque vous utilisez cette méthode, Audience Manager n’active que les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques activées dans Facebook sont seulement celles des appels d’événement d’identifiants déclarés. Les autres adresses électroniques associées à l’identifiant du client ne sont pas activées en temps réel.

**Puis-je collecter des adresses électroniques hachées depuis un formulaire web ou une application mobile ou doivent-elles être regroupées sur un fichier de lot ?**

Vous pouvez collecter des adresses électroniques hachées grâce à l’authentification web à l’aide de [!DNL ECID] avec les [identifiants déclarés](../features/declared-ids.md). Le fichier de lot vous permet également de collecter des adresses électroniques hachées qui ne peuvent pas être envoyées par authentification (par exemple, des utilisateurs inactifs dans votre ([!DNL CRM]) et de les activer dans des destinations basées sur des personnes).

**En quoi l’ingestion des adresses électroniques hachées par des formulaires web est-elle différente du chargement d’adresses électroniques hachées par des fichiers de lot ?**

L’ingestion de données hors ligne est conçue pour prendre en charge des cas d’utilisation sans authentification et une nouvelle stratégie de fusion de profils ([!UICONTROL All Cross-Device Profiles]) qui s’exécute sur tous les profils [!DNL CRM] hors ligne, que l’authentification fasse partie de [!DNL People-Based Destinations] ou non. Cette méthode vise à compléter l’ingestion d’audiences authentifiées de sources en ligne.

**Quelle est la fréquence maximale à laquelle je peux envoyer/mettre à jour des adresses électroniques hachées ?**

* Lorsque vous utilisez des identifiants déclarés, Audience Manager envoie les adresses électroniques hachées à la destination en temps réel.
* Lorsque vous ingérez des données via des fichiers de synchronisation d’identifiants, Audience Manager les traite chaque jour.

**Comment puis-je savoir si le hachage d’adresses électroniques s’effectue correctement ?**

Audience Manager n’ingère pas les adresses électroniques brutes et nous ne pouvons pas valider que le hachage a été effectué correctement. Consultez les [conditions préalables et les considérations](../features/destinations/people-based-destinations-prerequisites.md) pour en savoir plus sur la manière de hacher les données intégrées.

## Stratégies de fusion de profils {#profile-merge-rules}

**Existe-t-il une nouvelle stratégie de fusion de profils que je puisse utiliser avec [!DNL People-Based Destinations] ?**

Oui. Les clients qui achètent [!DNL People-Based Destinations] se voient également accorder l’accès à une nouvelle stratégie de fusion de profils pour la segmentation hors ligne. La règle s’intitule [!DNL All Cross-Device Profiles] et est utilisée pour la segmentation hors ligne uniquement. Lorsque vous vous inscrivez à [!DNL People-Based Destinations], il s’agit de la quatrième stratégie de fusion de profils que vous pouvez créer, en dehors des trois stratégies existantes basées sur l’authentification.

**Dois-je dupliquer mes segments d’audience existants pour les activer dans [!DNL People-Based Destinations] ?**

Cela dépend de votre cas d’utilisation. Si vous prévoyez d’activer des segments de premier niveau existants dans des canaux basés sur les personnes, vous n’avez pas à créer de nouveaux segments. Vous pouvez simplement faire correspondre les segments à une destination basée sur les personnes.

Si vous prévoyez d’activer de nouvelles audiences hors ligne sur des canaux basés sur des personnes, vous avez besoin de créer de nouveaux segments de premier niveau à l’aide de la stratégie de fusion [!DNL All Cross-Device Profiles].
>[!NOTE]
>
> Vous pouvez uniquement faire correspondre des segments avec des données de premier niveau vers [!DNL People-Based Destinations]. Nos plateformes de destination n’acceptent pas les segments possédant des données de deuxième et de troisième niveau.

## Taux de correspondance {#match-rates}

**[!DNL People-Based Destinations] dispose-t-il d’une visibilité sur les taux de correspondance ou les audiences adressables ?**

Non. Lorsque vous envoyez des segments d’audience vers [!DNL People-Based Destinations], la mise en correspondance de l’audience se fait du côté du partenaire. Adobe n’a pas accès à ces mesures. Audience Manager vous montre l’audience maximum pouvant être partagée pour chaque destination et le nombre de personnes en temps réel appartenant à un segment. Ces informations peuvent vous aider à planifier et à prévoir des campagnes.

**Comment les taux de correspondance utilisant [!DNL People-Based Destinations] de manière théorique se compareraient-ils à d’autres méthodes d’envoi d’audiences vers les plateformes de destination ?**

Tant que l’adresse électronique est hachée et ingérée correctement, il ne devrait pas y avoir de différence de taux de correspondance entre [!DNL People-Based Destinations] et les autres méthodes. La seule raison pour laquelle un taux de correspondance pourrait être inférieur à 100 % serait dans le cas où il serait impossible de faire correspondre les adresses électroniques importées dans Audience Manager avec une adresse électronique dans la base d’utilisateurs de la plateforme de destination.

**Je recueille les adresses électroniques professionnelles de mes clients qui sont différentes des adresses électroniques personnelles utilisées sur les réseaux sociaux. Comment faire correspondre les identités avec plusieurs adresses électroniques ?**

Audience Manager peut collecter et envoyer jusqu’à 10 e-mails par utilisateur vers les plateformes de destination, mais les adresses électroniques doivent être capturées dans des fichiers de synchronisation. Lorsqu’Audience Manager envoie les adresses électroniques vers les plateformes de destination, c’est aux plateformes de faire correspondre les adresses électroniques avec leur propre base d’utilisateurs. Certaines plateformes peuvent avoir des graphiques d’adresses électroniques supplémentaires pour faire correspondre les adresses envoyées depuis Audience Manager vers les profils utilisateur.

## Contrôles des exportations de données {#data-export-controls}

**Comment [!DNL Data Export Controls] fonctionne-t-il avec [!DNL People-Based Destinations] ?**

[!DNL Data Export Controls] bloquera tout segment contenant des données de deuxième et de troisième niveau que les utilisateurs tentent d’envoyer vers [!DNL People-Based Destinations]. [!DNL People-Based Destinations] autorise uniquement l’utilisation des données de premier niveau à des fins de ciblage. [!DNL Data Export Controls] bloque également les segments utilisant [!DNL Profile Merge Rules] avec des représentations graphiques des appareils. [!DNL People-Based Destinations] sont créées avec les étiquettes d’exportation des données appropriées vérifiées et vous ne pouvez pas remplacer les paramètres d’exportation.

## Questions spécifiques au partenaire {#partner-specific-questions}

### [!DNL Facebook]

**Que dois-je faire avant de pouvoir envoyer des segments d’audience vers [!DNL Facebook] ?**

Avant de pouvoir utiliser [!DNL People-Based Destinations] pour envoyer des segments d’audience vers [!DNL Facebook], vous devez réaliser les tâches de configuration suivantes :

1. Ajoutez le compte commercial Adobe Experience Cloud comme partenaire publicitaire dans votre [!DNL Facebook Ad Account]. Utilisez `business ID=206617933627973`. Pour plus d’informations, voir Ajouter des partenaires à votre compte Business Manager.

   >[!IMPORTANT]
   >
   > Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l’autorisation Gérer des campagnes. Ceci est obligatoire pour l’intégration de [!DNL People-Based Destinations].

1. Lisez et signez le [!DNL Facebook Custom Audiences Terms of Service]. Pour ce faire, accédez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

**[!DNL People-Based Destinations] prend-il en charge le ciblage des audiences dans d’autres applications [!DNL Facebook], telles que [!DNL Instagram] ?**

Vous pouvez utiliser [!DNL People-Based Destinations] sur la famille d’applications [!DNL Facebook] prises en charge par [!DNL Custom Audiences], notamment [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] et [!DNL Messenger]. La sélection de l’application sur laquelle vous souhaitez exécuter la campagne est indiquée au niveau de l’emplacement dans [!DNL Facebook Ads Manager].

**Quelle est la différence entre [!DNL People-Based Destinations] et [!DNL Website Custom Audiences] ?**

[!DNL People-Based Destinations] tire profit de l’intégration de [!DNL Custom Audiences (CA)] à [!DNL Facebook]. La différence entre les intégrations [!DNL WCA] et [!DNL CA] est la clé que les clients utilisent lorsqu’ils envoient des audiences vers [!DNL Facebook]. [!DNL WCA] utilise le pixel [!DNL Facebook] (qui serait un identifiant d’utilisateur de site web), tandis que [!DNL People-Based Destinations] utilise des adresses électroniques hachées pour s’intégrer à [!DNL CA].

Vous pouvez utiliser l’intégration [!DNL Facebook] [!DNL WCA] d’Audience Manager via la fonctionnalité [!DNL URL Destinations] sans frais supplémentaires.

Ces deux intégrations sont complémentaires ; vous pouvez utiliser les deux pour assurer une meilleure couverture d’audience. À titre d’exemple, vous pouvez utiliser [!DNL WCA] à des fins de prospection lorsqu’une société cherche à cibler les visiteurs d’un site web qui ne possèdent pas encore de compte enregistré, tandis que [!DNL People-Based Destinations] peut vous aider à cibler les clients existants qui ont renseigné leur adresse électronique, mais ne se sont peut-être pas encore rendus sur le site web.

**L&#39;[!DNL People-Based Destinations]intégration avec[!DNL Facebook]prise en charge exclut-elle un utilisateur d&#39;une audience alors qu&#39;il n&#39;y a plus de qualification ?**

Oui, l’intégration prend en charge la suppression des utilisateurs des [!DNL Facebook] audiences lorsqu’ils ne remplissent plus les conditions requises.