---
description: Définitions et liens vers d’autres documentations.
seo-description: Définitions et liens vers d’autres documentations.
seo-title: Glossaire
solution: Audience Manager
title: Glossaire
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Glossaire {#glossary}

Définitions et liens vers d’autres documentations.

## A-B {#a-b}

**Modélisation algorithmique**

Utilisez [!UICONTROL Algorithmic Modeling] comme un moyen d’étendre la portée au-delà des principaux utilisateurs que vous avez identifiés. Cette fonctionnalité vous permet de découvrir de nouvelles audiences uniques grâce à l’analyse automatisée des données. Gérez vos [!UICONTROL Algorithmic Models] dans **[!UICONTROL Audience Data > Models]**.

Voir [Signification des modèles algorithmiques](../features/algorithmic-models/algo-models-overview.md).

<br> 

**BAAAM**

[!UICONTROL Bulk Management Tools]. Les [!UICONTROL Bulk Management Tools] d’[!DNL Audience Manager] constituent un ensemble d’outils Microsoft Excel qui vous permettent de créer, de modifier ou de supprimer plusieurs objets à la fois au cours d’une seule opération. Vous pouvez utiliser des sources de données, des signaux dérivés, des destinations, des dossiers, des segments et des caractéristiques. Cette fonctionnalité utilise une feuille de calcul Microsoft Excel avec des macros qui effectuent des appels sécurisés et authentifiés aux API [!DNL Audience Manager].

Voir [Outils de gestion en bloc](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Un fichier [!UICONTROL CDF] représente un téléchargement en bloc de données collectées par [!DNL Audience Manager] et vous permet de travailler avec les données d’[!DNL Audience Manager] sans être contraint par les limites qu’impose notre interface utilisateur. Un fichier [!UICONTROL CDF] contient les mêmes données que celles envoyées à nos serveurs par un appel d’événement [!DNL Audience Manager] (`/event`). Cela inclut des données telles que les identifiants d’utilisateur, de caractéristiques et de segment, ainsi que tous les autres paramètres capturés par un appel d’événement.

Voir [Flux de données client](../features/cdf-files.md).

<br> 

**Identifiant CRM**

L’identifiant CRM est l’identifiant par lequel les clients identifient les utilisateurs dans leur propre système CRM. Dans Audience Manager, nous remplaçons la notion d’identifiant CRM par le terme DPUUID.

Voir DPUUID dans l’[Index des identifiants dans Audience Manager](../reference/ids-in-aam.md).

<br> 

**Audiences adressables au client**

Dans [Audiences adressables](/help/using/features/addressable-audiences.md), cette mesure représente les appareils :
* qui ont créé soit une caractéristique basée sur des règles soit une caractéristique intégrée pendant la période d’analyse
   **ET**
* dont l’identifiant est synchronisé avec la destination sélectionnée, et ce quelle que soit l’heure de la synchronisation.

<br> 

**Attributs du client**

Voir [Attributs du client](https://docs.adobe.com/content/help/fr-FR/core-services/interface/customer-attributes/attributes.html) dans la documentation du produit [!DNL Experience Cloud Core Services].

<br> 

**Taux de correspondance du client**

Audiences adressables du client / audience totale du client, exprimé en %. Voir [Audiences adressables](/help/using/features/addressable-audiences.md).

<br> 

**Audience totale du client**

Dans [Audiences adressables](/help/using/features/addressable-audiences.md), cette mesure représente le nombre d’appareils qui ont créé soit une caractéristique basée sur des règles sur vos propriétés, soit une caractéristique intégrée à partir de vos fichiers hors ligne pendant la période d’analyse.

<br> 

**demdex.net**

Demdex.net est un domaine hérité contrôlé par [!DNL Adobe]. Il reflète le nom original d’[!DNL Audience Manager] avant son acquisition ([!DNL Demdex]). [!DNL Adobe] a fait l’acquisition de [!DNL Demdex] en 2011 et a rebaptisé la société [!DNL Audience Manager]. Tous les appels HTTP vers les domaines `demdex.net` sont des appels envoyés vers [!DNL Adobe].

Voir [Signification des appels vers le domaine Demdex](../reference/demdex-calls.md).

<br> 

**DAID**

Les [!UICONTROL Device Advertising IDs] sont des identifiants d’appareil uniques, utilisés pour identifier un appareil mobile. Ces identifiants sont attribués par le fabricant de l’appareil et non pas par Adobe. Les identifiants des appareils iOS et Android sont pris en charge dans [!DNL Audience Manager].

Voir [Index des identifiants dans Audience Manager](../reference/ids-in-aam.md).

<br> 

**Destination**

Dans [!DNL Audience Manager], une destination correspond à tout autre système (serveur de publicités, plateforme DSP, réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. Le [!UICONTROL Destination Builder] de notre interface utilisateur vous fournit les outils qui vous permettent de créer et de gérer ces processus de diffusion des données. Les fonctionnalités de destination d’[!DNL Audience Manager] se trouvent dans **[!UICONTROL Audience Data > Destinations]**.

<br> 

**DIL**

La [!UICONTROL Data Integration Library] constitue une bibliothèque d’API utilisée par [!DNL Audience Manager] pour collecter des données concernant l’interaction de l’utilisateur. Voir [API Data Integration Library (DIL)](../dil/dil-overview.md).

<br> 

**dpm**

[!UICONTROL Data Provider Match]. Il indique aux systèmes internes d’[!DNL Adobe] qu’un appel d’[!DNL Audience Manager] ou du service d’identification transmet des données client pour synchronisation ou demande un identifiant. Voir [Signification des appels vers le domaine Demdex](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Anciennement nommé identifiant [!DNL Marketing Cloud] (MID ou MCID), l’identifiant [!DNL Experience Cloud] est au cœur du service d’identification. Il s’agit d’un identifiant unique et persistant pour les visiteurs de votre site. Voir les cookies et l’[Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/intro/cookies.html).

<br> 

**Caractéristique de dossier**

Regroupement automatique des caractéristiques au sein de la taxonomie de votre dossier. Chaque dossier de votre hiérarchie crée automatiquement une caractéristique qui peut être utilisée pour définir des segments.

Voir [À propos des caractéristiques de dossier](../features/traits/about-folder-traits.md).

<br> 

**Limitation de la fréquence**

Nombre maximal de fois qu’un annonceur souhaite présenter un contenu créatif en particulier à un utilisateur final. Vous pouvez configurer différentes expressions de la limitation de la fréquence dans [!UICONTROL Segment Builder].

Voir [Récence et fréquence](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

L’identifiant Google Advertising constitue l’identifiant d’appareil unique attribué par Google aux périphériques matériels exécutant le système d’exploitation Android. Voir [Index des identifiants dans Audience Manager](../reference/ids-in-aam.md).

<br> 

**GUID**

Acronyme de Globally Unique Identifier. Le terme GUID n’est pas employé dans [!DNL Audience Manager]. Ici, le GUID correspond à l’UUID [!DNL Audience Manager].
Voir [Index des identifiants dans Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Il s’agit de l’identifiant des annonceurs, l’identifiant d’appareil unique attribué par Apple à ses produits. Voir [Index des identifiants dans Audience Manager](../reference/ids-in-aam.md).

<br> 

**Entrant**

Le processus par lequel vous pouvez envoyer des données d’audience provenant d’autres sources à [!DNL Audience Manager]. Voir [Envoi de données d’audience](/help/using/integration/sending-audience-data/send-audience-data.md).

<br> 

**Code d’intégration**

Lorsque vous utilisez l’interface utilisateur ou l’API [!DNL Audience Manager], il vous est possible d’ajouter un code d’intégration lors de la création de caractéristiques, de segments ou de sources de données. Les codes d’intégration ont des objectifs différents selon les cas :

* [!UICONTROL Traits] : un code d’intégration est un champ destiné à accueillir un identifiant, un SKU ou toute autre valeur utilisée par vos processus d’entreprise internes. Facultatif.
* [!UICONTROL Segments] : un code d’intégration est un champ destiné à accueillir un identifiant défini par l’utilisateur ou d’autres informations spécifiques à la société. Facultatif.
* [!UICONTROL Data Sources] : les codes d’intégration sont requis lorsque vous souhaitez créer des sources de données multi-appareils, utiliser Adobe Experience Platform Identity Service ou travailler avec [!UICONTROL Profile Merge Rules]. Pour plus d’informations, voir la [Création d’une source de données](../features/manage-datasources.md#create-data-source).

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Voir [Modélisation algorithmique](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Voir [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. Le [!UICONTROL PCS] constitue une base de données volumineuse qui s’exécute sous Apache Cassandra. Il stocke les données reçues pour les utilisateurs actifs provenant des transferts serveur à serveur et du [!DNL DCS]. Les données [!UICONTROL PCS] se composent d’identifiants d’appareil, d’identifiants de profil authentifiés et de leurs caractéristiques associées.

Voir [Composants de la collecte de données](../reference/system-components/components-data-collection.md).

<br> 

**Profile Link**

Voir [Définition des options des stratégies de fusion de profils](../features/profile-merge-rules/merge-rule-definitions.md).

<br> 

**Stratégies de fusion de profils**

Les [!UICONTROL Profile Merge Rules] vous permettent de contrôler le type de données utilisé par [!DNL Audience Manager] pour la segmentation.

Voir [Définition des options des stratégies de fusion de profils](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Réalisation**

L’action qui qualifie un visiteur de votre site pour une caractéristique. Vous pouvez utiliser l’outil [Visionneuse de profil du visiteur](../features/visitor-profile-viewer.md) pour obtenir des informations sur la réalisation de caractéristiques par un utilisateur spécifique.

## S-T {#s-t}

**Segment**

Un segment (ou une audience) constitue un groupe d’utilisateurs qui partagent des attributs communs.

Voir [Segments : objectif, composition et règles](../features/segments/segments-purpose.md).

<br> 

**Audience adressable du segment**

Dans [Audiences adressables](/help/using/features/addressable-audiences.md), cette mesure représente le nombre d’utilisateurs qui ont fait partie du segment au cours de la période d’analyse du rapport et qui disposent d’une synchronisation d’identifiant active sur votre site. Les segments peuvent inclure vos propres données propriétaires ainsi que des données de partenariat et des données tierces, au moyen de caractéristiques acquises dans [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md).

<br> 

**Population totale de segments**

Dans [Audiences adressables](/help/using/features/addressable-audiences.md), cette mesure représente le nombre de tous les appareils qui ont fait partie de votre segment pendant la période d’analyse du rapport.

<br> 

**Taux de correspondance du segment**

Audiences adressables du segment / population totale du segment, exprimé en %. Voir [Audiences adressables](/help/using/features/addressable-audiences.md).

<br> 

**Signal**

Les signaux constituent les plus petites unités de données d’[!DNL Audience Manager] et sont exprimés en paires clé-valeur.

Voir [Signaux, caractéristiques et segments](../reference/signal-trait-segment.md).

<br> 

**Caractéristique**

Une caractéristique constitue une combinaison d’un ou de plusieurs signaux. Voir [Signaux, caractéristiques et segments](../reference/signal-trait-segment.md).

<br> 

**Population de caractéristiques**

Voir [Données sur la population de segments et de caractéristiques dans le créateur de segments](../features/segments/segment-builder-data.md).

**Durée de vie**

La durée de vie définit le nombre de jours pendant lesquels un visiteur qualifié fait partie d’une caractéristique. Elle est définie sur les caractéristiques et non sur les segments. Les visiteurs ne font plus partie du segment s’ils ne sont plus qualifiés pour aucune caractéristique avant la fin de la durée de vie. Pour en savoir plus, consultez l’[Explication portant sur la durée de vie des segments et des caractéristiques](/help/using/features/traits/segment-ttl-explained.md).

<br> 

## U-V {#u-v}

**UUID**

Identifiant utilisateur unique d’[!DNL Audience Manager]. Voir [Index des identifiants dans Audience Manager](../reference/ids-in-aam.md).

<br> 

**Identifiant visiteur**

Le service d’identification d’[!DNL Experience Cloud] (anciennement identifiant visiteur) fournit un identifiant persistant et universel qui identifie vos visiteurs dans toutes les solutions [!DNL Experience Cloud].

Voir la [documentation d’Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html).

## W-X-Y-Z {#w-z}

