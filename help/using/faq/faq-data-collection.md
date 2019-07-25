---
description: Questions et problèmes courants sur la collecte et l'intégration de données.
seo-description: Questions et problèmes courants sur la collecte et l'intégration de données.
seo-title: FAQ sur la collecte de données et l'intégration des produits
solution: Audience Manager
title: FAQ sur la collecte de données et l'intégration des produits
uuid: fa 8 e 79 f 4-99 cb -41 fd -8 a 85-d 4 f 92 d 03 c 7 a 5
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Data Collection and Product Integration FAQ{#data-collection-and-product-integration-faq}

Questions et problèmes courants sur la collecte et l'intégration de données.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Comment différencier le trafic entrant du[!UICONTROL DCS]trafic dans les exportations[!UICONTROL DCS]de fichiers journaux ?**

Traits onboarded via [!UICONTROL Inbound] are populated by [!UICONTROL Inbound] the same way they get populated by [!UICONTROL DCS]. There are a few different ways to tell that traffic came from [!UICONTROL Inbound]:

* L'adresse IP distante est définie sur 68.67.173.18
* Domainid est défini sur 5325
* La région sera définie sur 0

<br> 

**Pouvez-vous me fournir la liste des adresses IP que je peux liste blanche pour dpm. demdex. net ?**

Malheureusement, nous ne le pouvons pas. These IPs are assigned dynamically, by geographic region, through [!DNL Amazon Web Services]. As a result, [!DNL Audience Manager] does not control the range of IPs that can be assigned to this address.

<br> 

**Puis-je me fournir une adresse IP que je peux liste blanche pour votre serveur FTP entrant et sortant ?**

Oui, voir ci-dessous.

| Élément | Adresse |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quelles sont les exigences de placement de code et de chargement de page pour une[!UICONTROL DIL]intégration de[!DNL Analytics]données ?**

To bring [!DNL Analytics] data into [!DNL Audience Manager], load [!UICONTROL DIL] after the `s_code` module but *before* the `s.t()` function. Par exemple, placez votre code ou assurez-vous qu'il se charge dans cet ordre :

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager][!UICONTROL DIL] module

3. [!DNL Analytics]`s.t()`n’est pas déclarée 

As a best practice, set up your [!DNL Audience Manager]- [!DNL Analytics] integration with either of these 2 methods:

* Put [!UICONTROL DIL] directly in the `s_code`.

* Serve [!UICONTROL DIL] and the `s_code` through [!DNL Adobe Launch] or [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Pourquoi mes[!DNL Analytics]variables ne sont-elles pas manquantes dans un appel[!DNL Audience Manager]d'événement ?**

Cela se produit généralement lorsque :

* You serve [!UICONTROL DIL] through a tag management system that loads it asynchronously with other code elements on the page.
* `s.t()` La fonction se charge auparavant [!UICONTROL DIL].

<br> 

**Quelles versions[!DNL Analytics]de travail[!UICONTROL DIL]?**

You must use [!DNL Analytics] version 20.2 (or higher) and the [!DNL Adobe AppMeasurement AS] library version 3.5.2 (or higher) to work with [!UICONTROL DIL]. If you don't know your [!DNL Analytics] or [!DNL AppMeasurement] version, check the [!DNL Analytics] call that gets made from the page. Informations sur la version illustrées ci-dessous :

This customer uses [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

This customer uses [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Puis-je collecter des données de page si je ne suis pas[!DNL Analytics]client ?**

Oui. The [!UICONTROL DIL] module helps you collect page data even if you're not using [!DNL Analytics]. When set up properly, [!UICONTROL DIL] can capture data from and about:

* Métabalises
* URL et en-têtes d'URL
* Types de moteur de recherche
* Mots-clés

Additionally, clients can deploy a simple onsite object and populate it with key-value pairs that you want [!UICONTROL DIL] to collect data on. This lets you add and remove specific audience data points on your site without any [!DNL Audience Management] updates. Work with your Partner Solutions representative to properly set this up and ensure the [!DNL DIL] module references the page object correctly.

<br> 

**[!UICONTROL DIL]Peut-on collecter des données[!DNL Google Analytics]?**

Oui. [!UICONTROL DIL] peut collecter certains [!DNL Google Analytics] éléments (GA) et transmettre ces données [!DNL Audience Manager]. Voir :

* [GA. submituniversalanalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA. init](../dil/dil-modules.md#ga-init)

<br> 

**Puis-je obtenir des données brutes et[!DNL Audience Manager]à quel niveau ?**

Yes, [!DNL Audience Manager] can provide you with data collected for users we've seen on your inventory. Cela inclut :

* The unique user ID (UUID) assigned by [!DNL Audience Manager]
* ID de caractéristique et de segment
* Signaux inutilisés
* Horodatages
* URL de page

<br> 

**Je souhaite collecter des données sur un site et cibler les utilisateurs via DFP sur un autre site. Do I need to deploy code on the other property if I don't want to collect data from that location?**

Non. Si la collecte de données sur le deuxième site n'est pas une exigence, vous n'avez pas besoin de déployer le code DIL ici. Tant que vous avez accès à l'inventaire du second site via DFP, vous pouvez utiliser la collecte de données depuis le site initial et la cible via DFP.

<br> 

**Quel est le meilleur fournisseur de données tiers ?**

Chaque fournisseur apporte un élément unique au tableau. La réponse dépend de ce que vous recherchez. Nous pouvons activer la création de rapports de chevauchement (sans frais) pour vous aider à déterminer quel fournisseur vous convient le mieux.

<br> 

**Comment[!DNL Audience Manager]définir les cookies et transmettre les variables au DFP ?**

[!DNL Audience Manager] définit 2 cookies : L'un envoie des variables de segment à la balise publicitaire DFP et l'autre définit notre utilisateur unique - id (UUID), également lu par DFP. L'ajout de l'UUID à la balise d'annonce signifie que nous pouvons créer des rapports de niveau utilisateur et une découverte d'audience.

<br> 

**Pouvons-nous envoyer des informations DSP sur les points de l'entonnoir de conversion atteints par un utilisateur ?**

Oui. Nous pouvons envoyer des données entonnoir, mais le DSP doit posséder la fonctionnalité technique pour l'utiliser. Un DSP doit confirmer qu'il peut gérer plusieurs segments. S'ils ne le peuvent pas, nous devons créer des segments spécifiques pour extraire un utilisateur d'autres segments en fonction de leur progression de conversion (par ex., les étapes 1 et 2 complétées mais pas l'étape 3). Vous pouvez envoyer ces informations à un DSP afin qu'elles puissent recibler les utilisateurs, les diriger vers une page d'entrée spécifique ou afficher des créations spécifiques.

<br> 

**Comment puis-je confirmer que les données envoyées par FTP ont été récupérées[!DNL Audience Manager]?**

A file has been picked up when the extension changes from `.sync` to `.processed`. Dans ce cas, le fichier se trouve dans la file d'attente d'assimilation. En outre, votre gestionnaire de compte peut confirmer qu'un fichier a été téléchargé.

<br> 

**Je souhaite tester les fonctionnalités de l'API[DCS](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). J'envoie des appels d'événement comme celui illustré ci-dessous. The calls contain[Declared IDs](../features/declared-ids.md)and signals, which should realize some traits and segments I have already set up. Can I use the[!UICONTROL General Reports]and[!UICONTROL Trend Reports]to verify if the trait and segment populations are increasing?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

No, do not rely on the [!UICONTROL General Reports] and [!UICONTROL Trend Reports] in this case.

Les rapports calculent les populations en fonction des enregistrements de profil non authentifiés (UUID) que nous voyons dans le serveur principal au moment de la génération des rapports.

On a first call to the [!UICONTROL DCS], the declared IDs are *not* linked to any UUID (i.e. no [demdex cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) is present on the client side). The [!UICONTROL DCS] will randomly generate a UUID and set a [!DNL demdex] cookie and pass it on in the response call, but it will not transmit the UUID to the backend.

>[!NOTE]
>
>L'UUID généré ne sera matérialisé que dans le stockage de données principal une fois le périphérique sur lequel le cookie est défini déclenche une activité supplémentaire.

C'est pourquoi les rapports ne refléteront pas les événements déclenchés par les ID déclarés dans votre appel. We recommend you use UUID, ECID (formerly MID) or mobile device IDs in event test calls to the [!UICONTROL DCS]. Then, you can verify the trait and segment realizations in the [!UICONTROL General Reports] and in the [!UICONTROL Trend Reports].

See also, the [Index of Audience Manager IDs](../reference/ids-in-aam.md).

<br> 

**Combien de temps faut-il pour la synchronisation des profils d'utilisateurs entre[les différentes régions](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Il faut généralement 24 heures pour la synchronisation d'un profil utilisateur entre différentes régions. Cependant, dans de rares cas, le processus peut prendre jusqu'à 48 heures.
