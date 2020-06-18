---
description: Questions et problèmes courants liés à la collecte et à l’intégration des données.
seo-description: Questions et problèmes courants liés à la collecte et à l’intégration des données.
seo-title: FAQ sur la collecte de données et l’intégration de produits
solution: Audience Manager
title: FAQ sur la collecte de données et l’intégration de produits
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---


# FAQ sur la collecte de données et l’intégration de produits{#data-collection-and-product-integration-faq}

Questions et problèmes courants liés à la collecte et à l’intégration des données.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Comment puis-je différencier le trafic entrant du[!DNL DCS]trafic dans les exportations de[!DNL DCS]fichiers journaux ?**

Les caractéristiques embarquées via [!UICONTROL Inbound] sont renseignées de [!UICONTROL Inbound] la même manière que [!DNL DCS]celles qui les occupent. Il existe plusieurs façons de déterminer que le trafic provient [!UICONTROL Inbound]:

* L&#39;adresse IP distante sera définie sur 68.67.173.18
* DomainID sera défini sur 5325
* La région sera définie sur 0

<br> 

**Pouvez-vous me fournir une liste d’adresses IP que je peux ajouter à une liste autorisée pour dpm.demdex.net ?**

Malheureusement, nous ne le pouvons pas. Ces adresses IP sont attribuées dynamiquement, par région géographique, par [!DNL Amazon Web Services]. Par conséquent, [!DNL Audience Manager] ne contrôle pas la plage d’adresses IP pouvant être attribuées à cette adresse.

<br> 

**Pouvez-vous me fournir une adresse IP que je peux ajouter à une liste autorisée pour votre serveur sFTP entrant et sortant ?**

Oui, voir ci-dessous.

| Élément | Adresse |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quelles sont les exigences en matière de placement de code et de chargement de page pour une intégration de données[!UICONTROL DIL]/[!DNL Analytics]?**

Pour importer [!DNL Analytics] des données dans [!DNL Audience Manager], chargez [!UICONTROL DIL] après le `s_code` module mais *avant* la `s.t()` fonction. Par exemple, placez votre code, ou assurez-vous qu’il se charge, dans l’ordre suivant :

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] module

3. [!DNL Analytics]`s.t()`n’est pas déclarée 

Il est recommandé de configurer votre [!DNL Audience Manager]- [!DNL Analytics] intégration avec l’une des deux méthodes suivantes :

* Mets [!UICONTROL DIL] directement dans le `s_code`.

* Servir [!UICONTROL DIL] et le `s_code` jusqu&#39; [!DNL Adobe Experience Platform Launch] au ou [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Pourquoi mes[!DNL Analytics]variables sont-elles absentes d’un appel de[!DNL Audience Manager]événement ?**

Cela se produit généralement lorsque :

* Vous utilisez [!UICONTROL DIL] un système de gestion des balises qui le charge de manière asynchrone avec d’autres éléments de code sur la page.
* La `s.t()` fonction se charge avant [!UICONTROL DIL].

<br> 

**Avec quelles versions de[!DNL Analytics]fonctionne[!UICONTROL DIL]?**

Vous devez utiliser [!DNL Analytics] la version 20.2 (ou ultérieure) et la [!DNL Adobe AppMeasurement AS] version 3.5.2 (ou ultérieure) de la bibliothèque pour travailler avec [!UICONTROL DIL]. Si vous ne connaissez pas votre [!DNL Analytics] ou [!DNL AppMeasurement] version, vérifiez l’ [!DNL Analytics] appel généré à partir de la page. Informations de version affichées ci-dessous :

Ce client utilise [!DNL Analytics] la version 24.4 :

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Ce client utilise [!DNL AppMeasurement] la version 3.5.2 :

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Puis-je collecter des données de page si je ne suis pas un[!DNL Analytics]client ?**

Oui. Le [!UICONTROL DIL] module vous aide à collecter des données de page même si vous n’utilisez pas [!DNL Analytics]. Lorsque la configuration est correcte, [!UICONTROL DIL] vous pouvez capturer des données à partir des éléments suivants :

* Métadonnées
* URL et en-têtes d’URL
* Types de moteurs de recherche
* Mots-clés

En outre, les clients peuvent déployer un objet sur site simple et le renseigner avec des paires clé-valeur sur lesquelles vous souhaitez collecter [!UICONTROL DIL] des données. Cela vous permet d’ajouter et de supprimer des points de données d’audience spécifiques sur votre site sans aucune [!DNL Audience Management] mise à jour. Contactez votre représentant Solutions partenaires pour configurer correctement cette configuration et vous assurer que le [!DNL DIL] module référence correctement l&#39;objet de page.

<br> 

**Est-il[!UICONTROL DIL]possible de collecter des données[!DNL Google Analytics]?**

Oui. [!UICONTROL DIL] peut collecter certains éléments [!DNL Google Analytics] (GA) et transmettre ces données à [!DNL Audience Manager]. Voir :

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Puis-je obtenir des données brutes[!DNL Audience Manager]et à quel point est-ce granulaire ?**

Oui, [!DNL Audience Manager] peut vous fournir les données collectées pour les utilisateurs que nous avons vus sur votre inventaire. Cela inclut :

* ID utilisateur unique (UUID) attribué par [!DNL Audience Manager]
* ID de caractéristiques et de segments
* Signaux inutilisés
* Horodatages
* URL de page

<br> 

**Je souhaite collecter des données sur un site et sur les utilisateurs de cible via DFP sur un autre site. Dois-je déployer du code sur l’autre propriété si je ne souhaite pas collecter de données à partir de cet emplacement ?**

Non. Si la collecte de données sur le deuxième site n’est pas obligatoire, vous n’avez pas besoin de déployer le code DIL à cet endroit. Tant que vous avez accès à l’inventaire sur le deuxième site via DFP, vous pouvez utiliser la collecte de données depuis le site initial et la cible via DFP.

<br> 

**Quel est le meilleur fournisseur de données tiers ?**

Chaque fournisseur apporte quelque chose d&#39;unique à la table, donc la réponse dépend de ce que vous cherchez. Nous pouvons activer le rapports de chevauchement (sans frais) pour vous aider à comprendre quel fournisseur peut fonctionner le mieux pour vous.

<br> 

**Comment définir[!DNL Audience Manager]des cookies et transmettre des variables à DFP ?**

[!DNL Audience Manager] définit 2 cookies : L’un envoie les variables de segment à la balise publicitaire DFP et l’autre définit notre identifiant utilisateur unique (UUID), également lu par la fonction DFP. Ajouter l’identifiant UUID à la balise d’annonce signifie que nous pouvons effectuer la détection des rapports et des audiences au niveau de l’utilisateur.

<br> 

**Pouvons-nous envoyer des informations DSP sur les points de l&#39;entonnoir de conversion atteints par un utilisateur ?**

Oui. Nous pouvons envoyer des données d&#39;entonnoir, mais le DSP doit avoir la capacité technique de les utiliser. Un DSP doit confirmer qu’il peut gérer plusieurs segments. S’ils ne le peuvent pas, il se peut que nous devions créer des segments spécifiques pour extraire un utilisateur d’autres segments en fonction de leur progression de conversion (par exemple, aux étapes 1 et 2, mais pas à l’étape 3). Vous pouvez envoyer ces informations à un fournisseur de services de données afin qu’il puisse recibler les utilisateurs, les diriger vers un landing page spécifique ou afficher des éléments créatifs spécifiques.

<br> 

**Comment puis-je confirmer que les données envoyées par FTP ont été récupérées par[!DNL Audience Manager]?**

Un fichier a été récupéré lorsque l&#39;extension passe de `.sync` à `.processed`. Dans ce cas, le fichier se trouve dans la file d’attente d’assimilation. En outre, votre gestionnaire de compte peut confirmer qu’un fichier a été téléchargé.

<br> 

**Je veux tester les fonctionnalités de l’API[](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)DCS. J&#39;envoie des appels de événement comme celui illustré ci-dessous. Les appels contiennent des identifiants[et des signaux](../features/declared-ids.md)déclarés, ce qui devrait permettre d&#39;identifier certains traits et segments que j&#39;ai déjà configurés. Puis-je utiliser le[!UICONTROL General Reports]et[!UICONTROL Trend Reports]pour vérifier si les populations de caractéristiques et de segments augmentent ?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Non, ne comptez pas sur les [!UICONTROL General Reports] et [!UICONTROL Trend Reports] dans ce cas.

Les rapports calculent les populations en fonction des enregistrements de profil non authentifiés (UUID) que nous voyons dans l’arrière-plan au moment de la génération des rapports.

Lors d’un premier appel au [!DNL DCS]service, les identifiants déclarés *ne sont liés à aucun UUID (c’est-à-dire qu’aucun cookie* [](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) demdex n’est présent côté client). Le [!DNL DCS] système génère de manière aléatoire un UUID et définit un [!DNL demdex] cookie et le transmet dans l’appel de réponse, mais il ne transmet pas l’UUID au serveur principal.

>[!NOTE]
>
>L’identifiant UUID généré ne sera matérialisé dans notre enregistrement de données principal qu’une fois que le périphérique sur lequel le cookie est défini déclenchera une activité supplémentaire.

Pour cette raison, les rapports ne reflètent pas les événements déclenchés par les identifiants déclarés dans votre appel. Nous vous recommandons d’utiliser l’UUID, l’ECID (anciennement MID) ou les ID de périphérique mobile dans les appels de test de événement à la [!DNL DCS]variable. Ensuite, vous pouvez vérifier les réalisations des caractéristiques et des segments dans le [!UICONTROL General Reports] et dans le [!UICONTROL Trend Reports].

Voir aussi [Index des ID](../reference/ids-in-aam.md)d’Audience Manager.

<br> 

**Combien de temps faut-il aux profils utilisateurs pour synchroniser les[régions](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

La synchronisation d’un profil d’utilisateur peut prendre jusqu’à 24 heures. Cependant, dans de rares cas, le processus peut prendre jusqu&#39;à 48 heures.
