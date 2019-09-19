---
description: Définitions et liens vers d’autres lectures.
seo-description: Définitions et liens vers d’autres lectures.
seo-title: Glossaire
solution: Audience Manager
title: Glossaire
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
translation-type: tm+mt
source-git-commit: d5a8b763d2d0d1ceebe2252ebd283943dcbc1754

---


# Glossaire{#glossary}

Définitions et liens vers d’autres lectures.

## A-B {#a-b}

**Modélisation algorithmique**

Utilisez [!UICONTROL Algorithmic Modeling] comme un moyen d'étendre la portée au-delà du noyau des utilisateurs que vous avez identifiés. Cette fonctionnalité vous permet de découvrir de nouvelles audiences uniques grâce à l’analyse automatisée des données. Gérez votre [!UICONTROL Algorithmic Models] dans **[!UICONTROL Audience Data > Models]**.

Voir [Présentation des modèles](../features/algorithmic-models/understanding-models.md#understanding-models)algorithmiques.

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]. Les [!UICONTROL Bulk Management Tools] dans [!DNL Audience Manager] sont un ensemble d'outils Microsoft Excel qui vous permet de créer, modifier ou supprimer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser des sources de données, des signaux dérivés, des destinations, des dossiers, des segments et des caractéristiques. Cette fonctionnalité utilise une feuille de calcul Microsoft Excel avec des macros qui effectuent des appels sécurisés et authentifiés aux [!DNL Audience Manager] API.

Voir Outils [de gestion](../reference/bulk-management-tools/bulk-management-intro.md)en masse.

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Un [!UICONTROL CDF] fichier représente un téléchargement en masse de données collectées par [!DNL Audience Manager] [!DNL Audience Manager] et vous permet de travailler avec des données en dehors des limites imposées par notre interface utilisateur. Un [!UICONTROL CDF] fichier contient les mêmes données qu’un appel [!DNL Audience Manager] d’événement ( `/event`) envoie à nos serveurs. Cela inclut des données telles que les ID utilisateur, les ID de caractéristiques, les ID de segment et tous les autres paramètres capturés par un appel d’événement.

See [Customer Data Feeds](../features/cdf-files.md).

<br> 

**ID CRM**

L’ID CRM est l’identifiant par lequel les clients identifient les utilisateurs dans leur propre système de gestion de la relation client. Au lieu de l’identifiant CRM, nous utilisons le terme DPUUID dans Audience Manager.

Voir DPUUID dans l’ [index des identifiants d’Audience Manager](../reference/ids-in-aam.md).

<br> 

**Audience adressable au client**

Dans l’audience [](/help/using/features/addressable-audiences.md)adressable, cette mesure représente les périphériques qui :
* Ont réalisé une caractéristique basée sur des règles ou une caractéristique intégrée pendant la fenêtre de retour
   **ET**
* Synchronisez l’ID avec la destination choisie, quelle que soit l’heure de la synchronisation.

<br> 

**Attributs du client**

See [Customer Attributes](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.

<br> 

**Taux de correspondance client**

Audience adressable au client : audience totale du client exprimée en %. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Public total du client**

Dans l’audience [](/help/using/features/addressable-audiences.md)adressable, cette mesure représente le nombre de périphériques qui ont réalisé une caractéristique basée sur des règles sur vos propriétés ou une caractéristique intégrée de vos fichiers hors ligne pendant la fenêtre de retour.

<br> 

**demdex.net**

Demdex.net est un domaine hérité contrôlé par [!DNL Adobe]. Il reflète [!DNL Audience Manager]le nom d’origine de la préacquisition ( [!DNL Demdex]). [!DNL Adobe] acquis [!DNL Demdex] en 2011 et renommé l'entreprise [!DNL Audience Manager]. Tous les appels HTTP vers `demdex.net` les domaines sont des appels envoyés vers [!DNL Adobe].

Voir [Signification des appels vers le domaine Demdex](../reference/demdex-calls.md) (Understanding Calls to the Demdex Domain).

<br> 

**DAID**

[!UICONTROL Device Advertising IDs] sont des identifiants de périphérique uniques, utilisés pour identifier un périphérique mobile. Ces identifiants sont attribués par le fabricant du périphérique et non par Adobe. Nous prenons en charge les ID de périphérique iOS et Android dans [!DNL Audience Manager].

See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Destination**

Dans [!DNL Audience Manager], une destination correspond à tout autre système (serveur d’annonces, fournisseur de services de distribution de données, réseau publicitaire, etc.) que vous souhaitez partager avec. Dans [!UICONTROL Destination Builder] notre interface utilisateur, vous disposez des outils qui vous permettent de créer et de gérer ces processus de diffusion de données. [!DNL Audience Manager] les fonctions de destination se trouvent dans **[!UICONTROL Audience Data > Destinations]**.

<br> 

**DIL**

Il [!UICONTROL Data Integration Library] s’agit d’une bibliothèque API utilisée par [!DNL Audience Manager] pour collecter les données d’interaction utilisateur. See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]. Il indique aux [!DNL Adobe] systèmes internes qu’un appel du service [!DNL Audience Manager] d’ID ou du service d’ID transmet les données client pour synchronisation ou demande un ID. Voir [Signification des appels vers le domaine Demdex](../reference/demdex-calls.md) (Understanding Calls to the Demdex Domain).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Précédemment nommé [!DNL Marketing Cloud] ID (MID ou MCID). L’ [!DNL Experience Cloud] ID est au coeur du service d’ID. Il s’agit d’un identifiant unique et persistant pour les visiteurs de votre site. See Cookies and the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html).

<br> 

**Caractéristique du dossier**

Regroupement automatique des caractéristiques dans votre taxonomie de dossier. Chaque dossier de votre hiérarchie crée automatiquement une caractéristique qui peut être utilisée pour définir des segments.

Voir Caractéristiques [des dossiers : À propos](../features/traits/about-folder-traits.md).

<br> 

**plafonnement des fréquences**

Nombre maximal de fois qu’un annonceur souhaite afficher un élément créatif donné à un utilisateur final. Vous pouvez configurer différentes expressions de plafonnement des fréquences dans [!UICONTROL Segment Builder].

Voir [Récence et fréquence](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

Identifiant Google Advertising, identifiant de périphérique unique attribué par Google aux périphériques matériels exécutant le système d’exploitation Android. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

Acronyme de Globally Unique Identifier. Nous n'utilisons pas le terme GUID dans [!DNL Audience Manager]. Dans notre cas, le GUID est l' [!DNL Audience Manager] UUID.
See [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identifiant pour les annonceurs, l’ID de périphérique unique qu’Apple attribue à ses produits. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Entrant**

Processus par lequel vous pouvez envoyer des données d’audience à partir d’autres sources [!DNL Audience Manager]. Voir [Envoi de données](/help/using/integration/sending-audience-data/send-audience-data.md)d’audience.

<br> 

**Code d’intégration**

Lorsque vous travaillez avec l’ [!DNL Audience Manager] interface utilisateur ou l’API, vous avez la possibilité d’ajouter un code d’intégration lors de la création de caractéristiques, de segments ou de sources de données. Les codes d’intégration ont des objectifs différents dans ces cas :

* [!UICONTROL Traits]: un code d’intégration est un champ pour un ID, un SKU ou toute autre valeur utilisée par vos processus internes. Facultatif.
* [!UICONTROL Segments]: un code d’intégration est un champ pour un ID défini par l’utilisateur ou d’autres informations propres à l’entreprise. Facultatif.
* [!UICONTROL Data Sources]: les codes d’intégration sont requis lorsque vous souhaitez créer des sources de données inter-périphériques, utiliser le service d’ID Experience Cloud ou travailler avec [!UICONTROL Profile Merge Rules]. Voir [Création d’une source](../features/manage-datasources.md#create-data-source) de données pour plus d’informations.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Voir Modélisation [algorithmique](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Voir le [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. La [!UICONTROL PCS] base de données est volumineuse, et s'exécute sur Apache Cassandra. Il stocke les données reçues pour les utilisateurs actifs à partir des transferts serveur à serveur et du [!UICONTROL DCS]. [!UICONTROL PCS] les données sont constituées d’ID de périphérique, d’ID de profil authentifiés et des caractéristiques associées.

Voir Composants [de collecte de](../reference/system-components/components-data-collection.md)données.

<br> 

**Profile Link**

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**Règles de fusion de profils**

[!UICONTROL Profile Merge Rules] vous permet de contrôler le type d’ [!DNL Audience Manager] utilisation des données pour la segmentation.

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Réalisation**

Action par laquelle un visiteur de votre site est admissible pour une caractéristique. Vous pouvez utiliser l’outil Visionneuse [de profil du](../features/visitor-profile-viewer.md) visiteur pour obtenir des informations sur la création de caractéristiques par un utilisateur spécifique.

## S-T {#s-t}

**Segment**

Un segment (ou une audience) est un ensemble d’utilisateurs qui partagent des attributs communs.

Voir [Segments : But, composition et règles](../features/segments/segments-purpose.md).

<br> 

**Public adressable aux segments**

Dans l’audience [](/help/using/features/addressable-audiences.md)adressable, cette mesure représente le nombre d’utilisateurs qui ont appartenu au segment pendant la période de recherche en arrière-plan du rapport et qui ont une synchronisation active des identifiants sur votre site. Les segments peuvent inclure vos propres données propriétaires, ainsi que les données propriétaires et tierces, au moyen de caractéristiques acquises dans [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**Population totale du segment**

Dans l’audience [](/help/using/features/addressable-audiences.md)adressable, cette mesure représente le nombre de tous les périphériques qui étaient membres de votre segment pendant la période de consultation du rapport.

<br> 

**Taux de correspondance des segments**

Public adressable aux segments : Total des segments Population exprimée en %. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Signal**

Les signaux sont les unités de données les plus petites de [!DNL Audience Manager] la zone et sont exprimés en paires clé-valeur.

Voir [Signaux, Caractéristiques et Segments](../reference/signal-trait-segment.md).

<br> 

**Caractéristique**

Une caractéristique est une combinaison d’un ou de plusieurs signaux. Voir [Signaux, Caractéristiques et Segments](../reference/signal-trait-segment.md).

<br> 

**Population de caractéristiques**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Durée de vie)**

TTL définit le nombre de jours qu’un visiteur qualifié reste dans une caractéristique. TTL est défini sur les caractéristiques et non sur les segments. Les visiteurs sortent d’un segment s’ils ne voient pas une caractéristique admissible avant la fin de l’intervalle TTL. Pour en savoir plus, reportez-vous aux sections [Segment et Durée de vie des caractéristiques](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] ID utilisateur unique. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Visitor ID**

The [!DNL Experience Cloud] ID Service (formerly visitor ID) provides a universal, persistent ID that identifies your visitors across all the solutions in the [!DNL Experience Cloud].

See the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/reference/marketing-cloud-id-service.html) documentation.

## W-X-Y-Z {#w-z}

