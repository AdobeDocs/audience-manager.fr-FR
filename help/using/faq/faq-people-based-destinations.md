---
description: 'Réponses aux questions courantes sur les destinations basées sur les personnes.  '
seo-description: 'Réponses aux questions courantes sur les destinations basées sur les personnes.  '
seo-title: FAQ sur les destinations basées sur les personnes
solution: Audience Manager
title: FAQ sur les destinations basées sur les personnes
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 0%

---


# FAQ sur les destinations basées sur les personnes {#people-based-destinations-faq}

Answers to common questions about [!DNL People-Based Destinations].

## Availability {#availability}

**Je ne peux pas voir[!DNL People-Based Destinations]dans mon compte d&#39;Audience Manager. Que dois-je savoir sur la disponibilité ?**

[!DNL People-Based Destinations] est une fonction d’Audience Manager haut de gamme disponible à l’achat. Veuillez contacter votre représentant commercial Adobe pour plus de détails sur les tarifs et la disponibilité.

## Intégration des données {#data-onboarding}

**Comment puis-je embarquer les adresses électroniques des clients dans l’Audience Manager pour pouvoir les utiliser dans[!DNL People-Based Destinations]?**

Il existe deux façons d’apporter vos données hors ligne à l’Audience Manager [!DNL People-Based Destinations].

* **Utilisez la synchronisation** des identifiants basée sur des fichiers. Voir Exigences en matière de [nom et de contenu pour les fichiers](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) de synchronisation des identifiants pour en savoir plus sur les fichiers de synchronisation des identifiants. Lorsque vous utilisez cette méthode, vous pouvez cible toutes les adresses électroniques hachées de votre [!DNL CRM] base de données.
* **Utilisez des identifiants** déclarés pour déclarer les adresses électroniques hachées lors de la transmission d’identifiants de client authentifiés. Lors de l’utilisation de cette méthode, l’Audience Manager active uniquement les adresses électroniques hachées des utilisateurs qui se sont authentifiés en ligne. Les adresses électroniques activées via Facebook ne sont que celles qui figurent dans les appels d’événement d’ID déclarés. Les autres adresses électroniques associées à l’ID de client ne sont pas activées en temps réel.

**Puis-je collecter les adresses électroniques hachées par le biais d’un formulaire Web ou d’une application mobile ou dois-je les transmettre par lots ?**

Vous pouvez collecter des adresses électroniques hachées via l’authentification Web à l’aide [!DNL ECID] d’identifiants [](../features/declared-ids.md)déclarés. Le fichier de commandes vous permet également de collecter des adresses électroniques hachées qui ne peuvent pas être envoyées par authentification (par exemple, des utilisateurs inactifs dans votre ([!DNL CRM]) et de les activer dans des destinations basées sur des personnes).

**En quoi l’assimilation d’adresses électroniques hachées via des formulaires Web diffère-t-elle du transfert d’adresses électroniques hachées via des fichiers de commandes ?**

L&#39;assimilation des données hors ligne est conçue pour prendre en charge les cas d&#39;utilisation sans authentification, et une nouvelle règle de fusion de profil ([!UICONTROL All Cross-Device Profiles]) qui s&#39;exécute sur tous les [!DNL CRM] profils hors ligne, indépendamment de l&#39;authentification, est disponible dans le cadre [!DNL People-Based Destinations]. Cette méthode est destinée à compléter l’assimilation d’audiences authentifiées à partir de sources en ligne.

**Quelle est la fréquence maximale à laquelle je peux envoyer/mettre à jour des adresses électroniques hachées ?**

* Lors de l’utilisation d’identifiants déclarés, l’Audience Manager envoie les adresses électroniques hachées à la destination en temps réel.
* Lors de l’assimilation de données au moyen de fichiers de synchronisation des identifiants, l’Audience Manager les traite quotidiennement.

**Comment puis-je savoir si le hachage de l’adresse électronique est effectué correctement ?**

L&#39;Audience Manager n&#39;ingère pas l&#39;adresse de courriel brute et nous ne pouvons pas valider que le hachage a été effectué correctement. Voir [Conditions préalables et considérations](../features/destinations/people-based-destinations-prerequisites.md) pour en savoir plus sur la manière de hacher les données intégrées.

## Règles de fusion des Profils {#profile-merge-rules}

**Existe-t-il une nouvelle règle de fusion de profil que je puisse utiliser[!DNL People-Based Destinations]?**

Oui. Les clients qui achètent [!DNL People-Based Destinations] ont également accès à une nouvelle règle de fusion de profils pour la segmentation hors ligne. La règle est appelée [!DNL All Cross-Device Profiles] et elle est utilisée pour la segmentation hors ligne uniquement. Lorsque vous vous inscrivez pour [!DNL People-Based Destinations], il s’agit de la quatrième règle de fusion de profil que vous pouvez créer, en dehors des trois règles existantes basées sur l’authentification.

**Dois-je duplicata mes segments d’audience existants pour les activer dans[!DNL People-Based Destinations]?**

Cela dépend de votre cas d&#39;utilisation. Si vous prévoyez d’activer des segments propriétaires existants dans des canaux basés sur des personnes, il n’est pas nécessaire de créer de nouveaux segments. Vous pouvez simplement mapper les segments à une destination basée sur les personnes.

Si vous prévoyez d’activer de nouvelles audiences hors ligne dans des canaux basés sur des personnes, vous devez créer de nouveaux segments propriétaires à l’aide de la règle de [!DNL All Cross-Device Profiles] fusion.
>[!NOTE]
>
> Vous pouvez uniquement mapper des segments avec des données propriétaires à [!DNL People-Based Destinations]. Nos plateformes de destination n’acceptent pas les segments contenant des données propriétaires et tiers.

## Taux de correspondance {#match-rates}

**Dispose-t-[!DNL People-Based Destinations]d&#39;une visibilité sur les taux de correspondance ou les audiences adressables ?**

Non. Lors de l’envoi de segments d’audience à [!DNL People-Based Destinations], la mise en correspondance des audiences se produit du côté partenaire. Adobe n’a pas accès à ces mesures. L’Audience Manager vous montre l’audience maximale partageable pour chaque destination et le nombre en temps réel de personnes appartenant à un segment. Ces informations peuvent vous aider à planifier et à prévoir des campagnes.

**Comment faire correspondre les taux en utilisant[!DNL People-Based Destinations]théoriquement une comparaison avec d&#39;autres méthodes d&#39;envoi d&#39;audiences vers les plateformes de destination ?**

Tant que l’adresse électronique est hachée et correctement ingérée, il ne doit pas y avoir de différence dans le taux de correspondance entre les [!DNL People-Based Destinations] méthodes et les autres. La seule raison pour laquelle un taux de correspondance serait inférieur à 100 % est que les adresses électroniques introduites en Audience Manager ne peuvent pas être associées à une adresse électronique dans la base d’utilisateurs de la plateforme de destination.

**Je recueille les adresses électroniques de mes clients, qui sont différentes des adresses électroniques personnelles utilisées dans les réseaux sociaux. Comment faire correspondre les identités entre plusieurs adresses électroniques ?**

L’Audience Manager peut collecter et envoyer jusqu’à 10 courriers électroniques par utilisateur vers les plateformes de destination, mais les adresses électroniques doivent être capturées au moyen de fichiers de synchronisation. Une fois que l’Audience Manager envoie les adresses électroniques aux plateformes de destination, il appartient aux plateformes de faire correspondre les adresses électroniques à leur propre base d’utilisateurs. Certaines plateformes peuvent comporter des graphiques d’adresses électroniques supplémentaires pour correspondre aux adresses envoyées d’Audience Manager aux profils utilisateur.

## Contrôles des exportations de données {#data-export-controls}

**Comment fonctionne-t-[!DNL Data Export Controls]-on[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] bloquera tous les segments contenant des données tierces et secondaires que les utilisateurs tentent d&#39;envoyer à [!DNL People-Based Destinations]. [!DNL People-Based Destinations] autorise uniquement l’utilisation de données propriétaires pour le ciblage. [!DNL Data Export Controls] bloque également les segments à l’aide [!DNL Profile Merge Rules] de graphiques de périphérique. [!DNL People-Based Destinations] sont créées avec les étiquettes d’exportation de données appropriées cochées et vous ne pouvez pas remplacer les paramètres d’exportation.

## Questions spécifiques au partenaire {#partner-specific-questions}

### [!DNL Facebook]

**Que dois-je faire avant de pouvoir envoyer des segments d’audience à[!DNL Facebook]?**

Avant de pouvoir utiliser [!DNL People-Based Destinations] pour envoyer des segments d’audience à [!DNL Facebook], vous devez effectuer les tâches de configuration suivantes :

1. Ajoutez le compte professionnel Adobe Experience Cloud en tant que partenaire publicitaire dans votre [!DNL Facebook Ad Account]compte. Utilisez `business ID=206617933627973`. Pour plus d&#39;informations, consultez Ajouter des partenaires à votre gestionnaire d&#39;entreprise.

   >[!IMPORTANT]
   >
   > Lors de la configuration des autorisations pour Adobe Experience Cloud, vous devez activer l’autorisation Gérer les campagnes. Cela est nécessaire pour l&#39; [!DNL People-Based Destinations] intégration.

1. Lisez et signez le [!DNL Facebook Custom Audiences Terms of Service]. Pour ce faire, allez à `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, où `accountID` est votre [!DNL Facebook Ad Account ID].

**Le ciblage des audiences est-il[!DNL People-Based Destinations]pris en charge dans d’autres[!DNL Facebook]applications, telles que[!DNL Instagram]?**

Vous pouvez utiliser [!DNL People-Based Destinations] les différentes applications [!DNL Facebook]de la famille qui sont prises en charge par [!DNL Custom Audiences], notamment [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] et [!DNL Messenger]. La sélection de l&#39;application sur laquelle vous souhaitez exécuter la campagne est indiquée au niveau de l&#39;emplacement dans [!DNL Facebook Ads Manager].

**Quelle est la différence entre[!DNL People-Based Destinations]et[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] tire parti de l&#39; [!DNL Custom Audiences (CA)] intégration avec [!DNL Facebook]. La différence entre [!DNL WCA] et [!DNL CA] les intégrations est la clé que les clients utilisent lorsqu’ils envoient des audiences à [!DNL Facebook]. [!DNL WCA] utilise le [!DNL Facebook] pixel (qui serait un ID utilisateur de site Web) tandis [!DNL People-Based Destinations] qu’il utilise des adresses électroniques hachées pour s’intégrer à [!DNL CA].

Vous pouvez utiliser l’ [!DNL Facebook][!DNL WCA] intégration de l’Audience Manager via la [!DNL URL Destinations] fonction sans frais supplémentaires.

Ces deux intégrations sont complémentaires ; vous pouvez utiliser les deux pour assurer une meilleure couverture des audiences. À titre d’exemple, [!DNL WCA] peut être utilisé pour la prospection lorsqu’une société se tourne vers des visiteurs de site Web de cible qui n’ont pas enregistré de compte, alors qu’ [!DNL People-Based Destinations] il peut vous aider à cible les clients existants qui ont fourni leur adresse électronique, mais qui n’ont peut-être pas visité le site Web.
