---
description: Définitions et liens pour une lecture plus poussée.
seo-description: Définitions et liens pour une lecture plus poussée.
seo-title: Glossaire
solution: Audience Manager
title: Glossaire
uuid: 01 fc 26 f 5-db 9 d -4 e 90-b 4 c 1-27 c 6 a 510 accc
translation-type: tm+mt
source-git-commit: d5a8b763d2d0d1ceebe2252ebd283943dcbc1754

---


# Glossaire{#glossary}

Définitions et liens pour une lecture plus poussée.

## A-B {#a-b}

**Modélisation algorithmique**

Use [!UICONTROL Algorithmic Modeling] as a means of extending reach beyond the core of users you&#39;ve identified. Cette fonctionnalité vous permet de découvrir de nouvelles audiences uniques grâce à l&#39;analyse automatisée des données. Manage your [!UICONTROL Algorithmic Models] in **[!UICONTROL Audience Data > Models]**.

See [Understanding Algorithmic Models](../features/algorithmic-models/understanding-models.md#understanding-models).

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]. [!UICONTROL Bulk Management Tools] Dans un [!DNL Audience Manager] ensemble d&#39;outils Microsoft Excel, vous pouvez créer, modifier ou supprimer simultanément plusieurs objets en une seule opération. Vous pouvez utiliser des sources de données, des signaux dérivés, des destinations, des dossiers, des segments et des caractéristiques. The feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs.

See [Bulk Management Tools](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. A [!UICONTROL CDF] file represents a bulk download of data collected by [!DNL Audience Manager] and enables you to work with [!DNL Audience Manager] data outside of the limits imposed by our user interface. A [!UICONTROL CDF] file contains the same data that an [!DNL Audience Manager] event call ( `/event`) sends to our servers. Cela inclut les données telles que l&#39;utilisateur - id, ID de caractéristique, ID de segment et tous les autres paramètres capturés par un appel d&#39;événement.

See [Customer Data Feeds](../features/cdf-files.md).

<br> 

**Identifiant de la gestion de la relation client**

L&#39;identifiant CRM est l&#39;identifiant par lequel les clients identifient les utilisateurs dans leur propre système de gestion de la relation client. Au lieu de l&#39;identifiant CRM, nous utilisons le terme DPUUID dans Audience Manager.

See DPUUID in the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Audience adressable par le client**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents devices that:
* A réalisé soit une caractéristique basée sur des règles, soit une caractéristique intégrée au cours de la fenêtre de recherche
   **AND**
* Avoir une synchronisation des identifiants avec la destination choisie, quelle que soit la durée de synchronisation.

<br> 

**Attributs du client**

See [Customer Attributes](https://marketing.adobe.com/resources/help/en_US/mcloud/attributes.html) in the [!DNL Experience Cloud Core Services] product documentation.

<br> 

**Taux de correspondance client**

Audience adressable client ÷ Audience totale du client exprimée en %. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Audience totale du client**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents a count of devices that have realized either a rule-based trait on your properties or an onboarded trait from your offline files during the look-back window.

<br> 

**demdex.net**

Demdex.net is a legacy domain controlled by [!DNL Adobe]. It reflects [!DNL Audience Manager]&#39;s original, pre-acquisition name ( [!DNL Demdex]). [!DNL Adobe] acquise [!DNL Demdex] en 2011 et renommé la société sous [!DNL Audience Manager]la forme de. All HTTP calls to `demdex.net` domains are calls sent in to [!DNL Adobe].

Voir [Signification des appels vers le domaine Demdex](../reference/demdex-calls.md) (Understanding Calls to the Demdex Domain).

<br> 

**DAID**

[!UICONTROL Device Advertising IDs] sont des identifiants de périphérique uniques, utilisés pour identifier un périphérique mobile. Ces ID sont attribués par le fabricant du périphérique et non par Adobe. We support iOS and Android device IDs in [!DNL Audience Manager].

See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Destination**

In [!DNL Audience Manager], a destination is any other system (ad server, DSP, ad network, etc.) dont vous souhaitez partager les données. [!UICONTROL Destination Builder] Dans notre interface utilisateur, vous pouvez créer et gérer ces processus de livraison de données. [!DNL Audience Manager] Les fonctions de destination se trouvent **[!UICONTROL Audience Data > Destinations]** dans.

<br> 

**DIL**

The [!UICONTROL Data Integration Library] is an API library used by [!DNL Audience Manager] to collect user interaction data. See [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]. It tells internal [!DNL Adobe] systems that a call from [!DNL Audience Manager] or the ID service is passing in customer data for synchronization or requesting an ID. Voir [Signification des appels vers le domaine Demdex](../reference/demdex-calls.md) (Understanding Calls to the Demdex Domain).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Previously named the [!DNL Marketing Cloud] ID (MID or MCID). [!DNL Experience Cloud] L&#39;ID est un point central du service d&#39;ID. Il s&#39;agit d&#39;un identifiant unique et persistant pour les visiteurs de votre site. See Cookies and the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html).

<br> 

**Caractéristique du dossier**

Regroupement automatique des caractéristiques dans la taxonomie de dossiers. Chaque dossier de la hiérarchie crée automatiquement une caractéristique qui peut être utilisée pour définir des segments.

See [Folder Traits: About](../features/traits/about-folder-traits.md).

<br> 

**Plafonnement de fréquence**

Nombre de fois qu&#39;un annonceur souhaite afficher un créatif donné à une fin - utilisateur. You can configure various frequency capping expressions in [!UICONTROL Segment Builder].

See [Recency and Frequency](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

ID de publication Google, ID de périphérique unique attribué par Google aux périphériques matériels exécutant le système d&#39;exploitation Android. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

Acronyme de Global - Identifiant unique. We don&#39;t use the term GUID in [!DNL Audience Manager]. In our case, the GUID is the [!DNL Audience Manager] UUID.
See [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Identifiant for Advertisers, l&#39;ID unique d&#39;appareil Apple attribue à ses produits. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Entrant**

The process by which you can send audience data from other sources to [!DNL Audience Manager]. See [Sending Audience Data](/help/using/integration/sending-audience-data/send-audience-data.md).

<br> 

**Code d’intégration**

When working with the [!DNL Audience Manager] UI or API, you have the option of adding an integration code when creating traits, segments, or data sources. Dans ces cas, les codes d&#39;intégration sont différents :

* [!UICONTROL Traits]: un code d&#39;intégration est un champ pour un identifiant, un SKU ou une autre valeur utilisée par vos processus métier internes. Facultatif.
* [!UICONTROL Segments]: un code d&#39;intégration est un champ pour un identifiant défini par l&#39;utilisateur ou d&#39;autres informations spécifiques à l&#39;entreprise. Facultatif.
* [!UICONTROL Data Sources]: les codes d&#39;intégration sont nécessaires lorsque vous souhaitez créer des sources de données inter-périphériques, utiliser le service Experience Cloud ID ou travailler [!UICONTROL Profile Merge Rules]avec. See [Create a Data Source](../features/manage-datasources.md#create-data-source) for more information.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

See [Algorithmic Modeling](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

See the [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. The [!UICONTROL PCS] is a large database, running on Apache Cassandra. It stores data received for active users from server-to-server transfers and the [!UICONTROL DCS]. [!UICONTROL PCS] Les données sont constituées d&#39;ID de périphérique, d&#39;ID de profil authentifiés et de caractéristiques associées.

See [Data Collection Components](../reference/system-components/components-data-collection.md).

<br> 

**Profile Link**

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**Règles de fusion de profils**

[!UICONTROL Profile Merge Rules] vous permet de contrôler le type d&#39;utilisation des données [!DNL Audience Manager] pour la segmentation.

See [Profile Merge Rule Options Defined](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Réalisation**

Action par laquelle un visiteur de votre site se qualifie pour une caractéristique. You can use the [Visitor Profile Viewer](../features/visitor-profile-viewer.md) tool to obtain information on trait realization by a specific user.

## S-T {#s-t}

**Segment**

Un segment (ou une audience) est un ensemble d&#39;utilisateurs qui partagent des attributs communs.

See [Segments: Purpose, Composition, and Rules](../features/segments/segments-purpose.md).

<br> 

**Public adressable de segment**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents the number of users who have belonged to the segment during the report look-back period and have an active ID sync on your site. Segments can include your own first-party data and second party and third party data, via traits acquired in the [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**Population totale de segments**

In [Addressable Audience](/help/using/features/addressable-audiences.md), this metric represents a count of all the devices that were a member of your segment during the report look-back period.

<br> 

**Taux de correspondance des segments**

Audience adressable de segment ÷ Population totale de segments exprimée en %. See [Addressable Audience](/help/using/features/addressable-audiences.md).

<br> 

**Signal**

Signals are the smallest data units in [!DNL Audience Manager] and are expressed as key-value pairs.

See [Signals, Traits, and Segments](../reference/signal-trait-segment.md).

<br> 

**Caractéristique**

Une caractéristique est une combinaison d&#39;un ou de plusieurs signaux. See [Signals, Traits, and Segments](../reference/signal-trait-segment.md).

<br> 

**Population de caractéristiques**

See [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Durée de vie)**

TTL définit le nombre de jours pendant lesquels un visiteur qualifié reste dans une caractéristique. TTL est défini sur des caractéristiques et non sur des segments. Les visiteurs abandonnent un segment s&#39;ils ne voient pas de caractéristique qualifiant avant la fin de l&#39;intervalle TTL. Read more in [Segment and Trait Time-to-Live Explained](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

[!DNL Audience Manager] Utilisateur unique - id. See the [Index of IDs in Audience Manager](../reference/ids-in-aam.md).

<br> 

**Visitor ID**

The [!DNL Experience Cloud] ID Service (formerly visitor ID) provides a universal, persistent ID that identifies your visitors across all the solutions in the [!DNL Experience Cloud].

See the [Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/reference/marketing-cloud-id-service.html) documentation.

## W-X-Y-Z {#w-z}

