---
description: Questions et problèmes courants liés à la collecte et à l’intégration des données.
seo-description: Questions et problèmes courants liés à la collecte et à l’intégration des données.
seo-title: FAQ sur la collecte de données et l’intégration de produits
solution: Audience Manager
title: FAQ sur la collecte de données et l’intégration de produits
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# FAQ sur la collecte de données et l’intégration de produits{#data-collection-and-product-integration-faq}

Questions et problèmes courants liés à la collecte et à l’intégration des données.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Comment puis-je différencier le trafic entrant du[!UICONTROL DCS]trafic dans les exportations de fichiers[!UICONTROL DCS]journaux ?**

Les caractéristiques embarquées via [!UICONTROL Inbound] sont renseignées de [!UICONTROL Inbound] la même manière que [!UICONTROL DCS]. Il existe plusieurs manières de dire que le trafic provient [!UICONTROL Inbound]:

* L’adresse IP distante sera définie sur 68.67.173.18
* DomainID sera défini sur 5325
* La région sera définie sur 0

<br> 

**Pouvez-vous me fournir un d’adresses IP que je peux mettre en liste blanche pour dpm.demdex.net ?**

Malheureusement, nous ne le pouvons pas. Ces adresses IP sont attribuées dynamiquement, par région géographique, par [!DNL Amazon Web Services]. Par conséquent, [!DNL Audience Manager] ne contrôle pas la plage des adresses IP pouvant être attribuées à cette adresse.

<br> 

**Pouvez-vous me fournir une adresse IP que je peux mettre en liste blanche pour votre serveur FTP entrant et sortant ?**

Oui, voir ci-dessous.

| Élément | Adresse |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Quelles sont les exigences en matière de placement de code et de chargement de page pour une intégration[!UICONTROL DIL]/[!DNL Analytics]de données ?**

Pour importer [!DNL Analytics] des données [!DNL Audience Manager], chargez [!UICONTROL DIL] après le module mais `s_code` avant *la* `s.t()` fonction. Par exemple, placez votre code, ou assurez-vous qu’il se charge, dans l’ordre suivant :

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] module

3. [!DNL Analytics]`s.t()`n’est pas déclarée 

En règle générale, configurez votre [!DNL Audience Manager]- [!DNL Analytics] intégration avec l’une des deux méthodes suivantes :

* Mets [!UICONTROL DIL] directement dans le `s_code`.

* Servir [!UICONTROL DIL] et le `s_code` par [!DNL Adobe Experience Platform Launch] ou [!DNL Adobe DTM].

See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Pourquoi mes[!DNL Analytics]variables sont-elles absentes d’un appel de[!DNL Audience Manager]?**

Cela se produit généralement lorsque :

* Vous utilisez [!UICONTROL DIL] un système de gestion des balises qui le charge de manière asynchrone avec d’autres éléments de code sur la page.
* La `s.t()` fonction se charge avant [!UICONTROL DIL].

<br> 

**Avec quelles versions de[!DNL Analytics]fonctionne-t-il[!UICONTROL DIL]?**

Vous devez utiliser la [!DNL Analytics] version 20.2 (ou ultérieure) et la [!DNL Adobe AppMeasurement AS] version 3.5.2 (ou ultérieure) de la bibliothèque pour travailler avec [!UICONTROL DIL]. Si vous ne connaissez pas votre [!DNL Analytics] ou [!DNL AppMeasurement] version, vérifiez l’ [!DNL Analytics] appel généré à partir de la page. Informations de version illustrées ci-dessous :

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

Oui. Le [!UICONTROL DIL] module vous aide à collecter des données de page, même si vous n’utilisez pas [!DNL Analytics]. Une fois la configuration correcte effectuée, [!UICONTROL DIL] vous pouvez capturer des données à partir de et autour de :

* Métadonnées
* URL et en-têtes d’URL
* Types de moteurs de recherche
* Mots-clés

De plus, les clients peuvent déployer un objet sur site simple et le renseigner avec des paires clé-valeur sur lesquelles vous souhaitez [!UICONTROL DIL] collecter des données. Cela vous permet d’ajouter et de supprimer des points de données  spécifiques  de votre site sans aucune [!DNL Audience Management] mise à jour. Contactez votre représentant Solutions partenaires pour configurer correctement cette configuration et vous assurer que le [!DNL DIL] module référence correctement l’objet de page.

<br> 

**Peut-[!UICONTROL DIL]il collecter des données à partir de[!DNL Google Analytics]?**

Oui. [!UICONTROL DIL] peut collecter certains éléments [!DNL Google Analytics] (GA) et transmettre ces données à [!DNL Audience Manager]. Voir :

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Puis-je obtenir des données brutes[!DNL Audience Manager]et à quel point est-ce granulaire ?**

Oui, [!DNL Audience Manager] peut vous fournir les données collectées pour les utilisateurs que nous avons vus dans votre inventaire. Cela inclut :

* L’ID utilisateur unique (UUID) attribué par [!DNL Audience Manager]
* ID de caractéristiques et de segments
* Signaux inutilisés
* Horodatages
* URL de page

<br> 

**Je souhaite collecter des données sur un site et des utilisateurs via DFP sur un autre site. Dois-je déployer du code sur l’autre propriété si je ne souhaite pas collecter des données à partir de cet emplacement ?**

Non. Si la collecte de données sur le deuxième site n’est pas obligatoire, vous n’avez pas besoin de déployer le code DIL là-bas. Tant que vous avez accès à l’inventaire sur le deuxième site via DFP, vous pouvez utiliser la collecte de données depuis le site initial et les  via DFP.

<br> 

**Quel est le meilleur fournisseur de données tiers ?**

Chaque fournisseur apporte quelque chose d&#39;unique à la table, donc la réponse dépend de ce que vous recherchez. Nous pouvons activer les  de chevauchement (sans frais) pour vous aider à comprendre quel fournisseur fonctionne le mieux pour vous.

<br> 

**Comment[!DNL Audience Manager]définir des cookies et transmettre des variables à DFP ?**

[!DNL Audience Manager] définit 2 cookies : L’un envoie les variables de segment à la balise publicitaire DFP et l’autre définit notre identifiant utilisateur unique (UUID), également lu par le DFP. L’ajout de l’UUID à la balise publicitaire signifie que nous pouvons effectuer des  de niveau utilisateur et  la découverte de .

<br> 

**Pouvons-nous envoyer des informations DSP sur les points de l’entonnoir de conversion auxquels un utilisateur a accès ?**

Oui. Nous pouvons envoyer des données d&#39;entonnoir, mais le DSP doit avoir la capacité technique de les utiliser. Un DSP doit confirmer qu’il peut gérer plusieurs segments. S’ils ne le peuvent pas, il se peut que nous devions créer des segments spécifiques pour extraire un utilisateur d’autres segments en fonction de la progression de sa conversion (par exemple, les étapes 1 et 2 terminées, mais pas l’étape 3). Vous souhaitez peut-être envoyer ces informations à un fournisseur de services partagés afin qu’il puisse recibler les utilisateurs, les diriger vers un spécifique ou afficher des éléments créatifs spécifiques.

<br> 

**Comment puis-je confirmer que les données envoyées par FTP ont été récupérées par[!DNL Audience Manager]?**

Un fichier a été récupéré lorsque l&#39;extension passe de `.sync` à `.processed`. Dans ce cas, le fichier se trouve dans la file d’attente d’assimilation. En outre, votre gestionnaire de compte peut confirmer le moment où un fichier a été téléchargé.

<br> 

**Je veux tester la fonctionnalité de l’API[](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)DCS. J&#39;envoie  appels comme celui illustré ci-dessous. Les appels contiennent des identifiants et des[signaux](../features/declared-ids.md)déclarés, ce qui devrait permettre de réaliser certaines caractéristiques et certains segments que j’ai déjà configurés. Puis-je utiliser le[!UICONTROL General Reports]et[!UICONTROL Trend Reports]vérifier si les populations de caractéristiques et de segments augmentent?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Non, ne comptez pas sur le [!UICONTROL General Reports] et [!UICONTROL Trend Reports] dans ce cas.

Les rapports calculent les populations en fonction des enregistrements d’ non authentifiés (UUID) que nous voyons dans l’arrière-plan au moment de la génération des rapports.

Lors d’un premier appel à la [!UICONTROL DCS], les identifiants déclarés *ne sont liés à aucun UUID (c’est-à-dire qu’aucun cookie* [](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex n’est présent côté client). Le [!UICONTROL DCS] système génère de manière aléatoire un UUID et définit un [!DNL demdex] cookie et le transmet dans l’appel de réponse, mais il ne transmet pas l’UUID au serveur principal.

>[!NOTE]
>
>L’UUID généré ne sera matérialisé que dans notre de données d’arrière-plan  une fois que l’appareil sur lequel le cookie est défini déclenchera d’autres  de.

Pour cette raison, les rapports ne reflètent pas le  déclenché par les identifiants déclarés dans votre appel. Nous vous recommandons d’utiliser l’UUID, l’ECID (anciennement MID) ou les ID de périphérique mobile dans les appels de  test du [!UICONTROL DCS]. Ensuite, vous pouvez vérifier les réalisations des caractéristiques et des segments dans le [!UICONTROL General Reports] et dans le [!UICONTROL Trend Reports].

Voir aussi l’ [index des ID de   Manager](../reference/ids-in-aam.md).

<br> 

**Combien de temps faut-il aux d’utilisateurs pour synchroniser les  entre[régions](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Il faut généralement jusqu’à 24 heures pour qu’un utilisateur  synchroniser les différentes régions. Cependant, dans de rares cas, le processus peut prendre jusqu&#39;à 48 heures.
