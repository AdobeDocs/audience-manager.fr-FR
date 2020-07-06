---
description: Questions et problématiques courantes liées à la collecte et à l’intégration des données.
seo-description: Questions et problématiques courantes liées à la collecte et à l’intégration des données.
seo-title: FAQ sur la collecte de données et l’intégration de produit
solution: Audience Manager
title: FAQ sur la collecte de données et l’intégration de produit
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
feature: Administration
translation-type: tm+mt
source-git-commit: 27ce94084e35ffa770858027d12235ca9f1f8430
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 96%

---


# FAQ sur la collecte de données et l’intégration de produit {#data-collection-and-product-integration-faq}

Questions et problématiques courantes liées à la collecte et à l’intégration des données.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Comment différencier le trafic entrant du trafic [!DNL DCS] dans les exportations de fichiers journaux [!DNL DCS] ?**

Les caractéristiques intégrées au moyen d’[!UICONTROL Inbound] sont remplies par [!UICONTROL Inbound] exactement comme le fait [!DNL DCS]. Il existe plusieurs manières de déterminer que le trafic provient d’[!UICONTROL Inbound] :

* L’adresse IP distante sera définie sur 68.67.173.18
* L’identifiant de domaine sera défini sur 5325
* La région sera définie sur 0

<br> 

**Pouvez-vous me fournir une liste d’adresses IP que je peux ajouter à une liste autorisée pour dpm.demdex.net ?**

Cela est malheureusement impossible. Ces adresses IP sont attribuées dynamiquement par [!DNL Amazon Web Services] selon leur zone géographique. Par conséquent, [!DNL Audience Manager] n’a aucun contrôle sur la plage d’adresses IP pouvant être attribuées à cette adresse.

<br> 

**Pouvez-vous me fournir une adresse IP que je peux ajouter à une liste autorisée pour votre serveur sFTP entrant et sortant ?**

Oui : voir ci-dessous.

| Élément | Adresse |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quelles sont les exigences en matière de placement de code et de chargement de page pour une intégration de données [!UICONTROL DIL]/[!DNL Analytics] ?**

Pour importer des données [!DNL Analytics] dans [!DNL Audience Manager], chargez [!UICONTROL DIL] après le module `s_code` et *avant* la fonction `s.t()`. Par exemple, renseignez votre code, ou assurez-vous qu’il se charge, dans l’ordre suivant :

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] module

3. [!DNL Analytics] `s.t()` fonction

Il est recommandé de configurer votre intégration [!DNL Audience Manager]— [!DNL Analytics] en suivant l’une de ces deux méthodes :

* Insérez [!UICONTROL DIL] directement dans le `s_code`.

* Renseignez [!UICONTROL DIL] et le `s_code` dans [!DNL Adobe Experience Platform Launch] ou [!DNL Adobe DTM].

Voir [API Data Integration Library (DIL)](../dil/dil-overview.md).

<br> 

**Pourquoi mes variables [!DNL Analytics] sont-elles absentes d’un appel d’événement [!DNL Audience Manager] ?**

Cela se produit généralement lorsque :

* vous renseignez la [!UICONTROL DIL] dans un système de gestion des balises qui la charge de manière asynchrone avec d’autres éléments de code sur la page ;
* la fonction `s.t()` se charge avant [!UICONTROL DIL].

<br> 

**Quelles versions de [!DNL Analytics] fonctionnent avec [!UICONTROL DIL] ?**

Vous devez utiliser la version 20.2 (ou ultérieure) de [!DNL Analytics] et la version 3.5.2 (ou ultérieure) de la bibliothèque [!DNL Adobe AppMeasurement AS] pour travailler avec [!UICONTROL DIL]. Si vous ne connaissez pas votre version [!DNL Analytics] ou [!DNL AppMeasurement], vérifiez l’appel [!DNL Analytics] généré à partir de la page. Les informations de version sont affichées ci-dessous :

Ce client utilise la version 24.4 de [!DNL Analytics] :

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Ce client utilise la version 3.5.2 de [!DNL AppMeasurement] :

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Puis-je collecter des données de page si je ne suis pas un client [!DNL Analytics] ?**

Oui. Le module [!UICONTROL DIL] vous aide à collecter des données de page même si vous n’utilisez pas [!DNL Analytics]. Lorsqu’il est correctement configuré, [!UICONTROL DIL] peut capturer des données à partir et à propos des éléments suivants :

* Balises META
* URL et en-têtes d’URL
* Types de moteur de recherche
* Mots-clés

Les clients peuvent également déployer un objet simple sur site et le remplir avec des paires clé-valeur à propos desquelles vous souhaitez que [!UICONTROL DIL] collecte des données. Cela vous permet d’ajouter et de supprimer des points de données d’audience spécifiques sur votre site sans aucune mise à jour d’[!DNL Audience Management]. Rapprochez-vous de votre représentant Partenaires en solutions pour réaliser correctement cette configuration et vous assurer que le module [!DNL DIL] référence correctement l’objet de page.

<br> 

**[!UICONTROL DIL] peut-il collecter des données à partir de [!DNL Google Analytics] ?**

Oui. [!UICONTROL DIL] peut collecter certains éléments [!DNL Google Analytics] (GA) et transmettre ces données à [!DNL Audience Manager]. Voir :

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Puis-je obtenir des données brutes d’[!DNL Audience Manager] ? Quel est le degré de granularité ?**

Oui, [!DNL Audience Manager] peut vous fournir les données collectées pour les utilisateurs détectés dans votre inventaire. Cela inclut :

* L’identifiant utilisateur unique (UUID) attribué par [!DNL Audience Manager]
* Les identifiants de caractéristique et de segment
* Les signaux inutilisés
* Les horodatages
* Les URL de page

<br> 

**Je souhaite collecter des données sur un site et cibler les utilisateurs au moyen de DFP sur un autre site. Dois-je déployer du code sur l’autre propriété si je ne souhaite pas collecter de données à partir de cet emplacement ?**

Non. Si la collecte de données sur le deuxième site n’est pas nécessaire, vous n’avez pas besoin d’y déployer DIL. Tant que vous avez accès à l’inventaire sur le deuxième site par le biais de DFP, vous pouvez utiliser la collecte de données depuis le premier site et cibler les utilisateurs au moyen de DFP.

<br> 

**Quel est le meilleur fournisseur de données tiers ?**

Chaque fournisseur possède sa propre particularité ; la réponse à cette question dépend donc de ce que vous cherchez. Nous pouvons activer les rapports de chevauchement (sans frais) pour vous aider à voir quel fournisseur vous conviendrait le mieux.

<br> 

**Comment [!DNL Audience Manager] définit-il des cookies et transmet-il des variables à DFP ?**

[!DNL Audience Manager] définit 2 cookies : l’un envoie les variables de segment à la balise publicitaire DFP et l’autre définit notre identifiant utilisateur unique (UUID), également lu par DFP. L’ajout de l’UUID à la balise publicitaire permet de créer des rapports et de découvrir des audiences au niveau de l’utilisateur.

<br> 

**Est-il possible d’envoyer des informations au fournisseur de services de données à propos des points dans l’entonnoir de conversion atteints par un utilisateur ?**

Oui. Nous pouvons envoyer des données concernant l’entonnoir, mais le fournisseur de services de données doit disposer des capacités techniques pour les utiliser. Un fournisseur de services de données doit confirmer qu’il peut gérer plusieurs segments. S’il ne le peut pas, il est possible que nous devions créer des segments spécifiques afin d’extraire un utilisateur d’autres segments en fonction de la progression de sa conversion (par exemple, s’il a terminé les étapes 1 et 2, mais pas l’étape 3). Vous pouvez envoyer ces informations à un fournisseur de services de données afin qu’il puisse recibler les utilisateurs, les diriger vers une page d’entrée spécifique ou afficher un contenu créatif en particulier.

<br> 

**Comment puis-je confirmer que les données envoyées par FTP ont bien été récupérées par [!DNL Audience Manager] ?**

Un fichier a bien été récupéré lorsque son extension passe de `.sync` à `.processed`. Lorsque ce changement se produit, le fichier se trouve dans la file d’attente d’ingestion. Votre gestionnaire de compte peut également confirmer le chargement d’un fichier.

<br> 

**Je veux tester les fonctionnalités de l’[API DCS](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). J’envoie des appels d’événement semblables à celui illustré ci-dessous. Les appels contiennent des [identifiants déclarés](../features/declared-ids.md) ainsi que des signaux, ce qui devrait créer certains des segments et des caractéristiques que j’ai déjà configurés. Puis-je utiliser les [!UICONTROL General Reports] et les [!UICONTROL Trend Reports] pour vérifier si les populations de caractéristiques et de segments augmentent ?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Non, vous ne pouvez pas vous en remettre aux [!UICONTROL General Reports] et aux [!UICONTROL Trend Reports] dans ce cas.

Les rapports calculent les populations en fonction des enregistrements de profil non authentifiés (UUID) détectés dans le serveur principal au moment de la génération des rapports.

Lors d’un premier appel à [!DNL DCS], les identifiants déclarés ne sont liés à *aucun* UUID (c.-à-d. qu’aucun [cookie demdex](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) n’est présent côté client). Le [!DNL DCS] génère de manière aléatoire un UUID, définit un cookie [!DNL demdex] et le transmet dans l’appel de réponse, mais il ne transmet pas l’UUID au serveur principal.

>[!NOTE]
>
>L’UUID généré n’est matérialisé dans notre serveur principal de stockage des données qu’une fois que l’appareil sur lequel le cookie est défini déclenche une activité supplémentaire.

C’est pourquoi les rapports ne refléteront pas les événements déclenchés par les identifiants déclarés dans votre appel. Nous vous recommandons d’utiliser l’UUID, l’ECID (anciennement MID) ou les identifiants d’appareils mobiles dans les appels de test d’événement à [!DNL DCS]. Vous pouvez ensuite vérifier les réalisations des caractéristiques et des segments dans les [!UICONTROL General Reports] et les [!UICONTROL Trend Reports].

Voir également l’[Index des identifiants d’Audience Manager](../reference/ids-in-aam.md).

<br> 

**Combien de temps faut-il aux profils utilisateur pour se synchroniser dans les [régions](../api/dcs-intro/dcs-api-reference/dcs-regions.md) ?**

La synchronisation d’un profil utilisateur dans les régions prend en général jusqu’à 24 heures. Dans de rares cas, le processus peut cependant prendre jusqu’à 48 heures.
