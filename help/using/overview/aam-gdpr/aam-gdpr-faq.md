---
description: Ce document contient quelques-unes des questions les plus courantes posées par nos clients et partenaires en ce qui concerne le GDPR (Europe General Data Protection Regulation) et la manière dont Adobe Audience Manager, en tant qu'application de traitement de données, répond aux différents besoins du GDPR.
seo-description: Ce document contient quelques-unes des questions les plus courantes posées par nos clients et partenaires en ce qui concerne le GDPR (Europe General Data Protection Regulation) et la manière dont Adobe Audience Manager, en tant qu'application de traitement de données, répond aux différents besoins du GDPR.
seo-title: FAQ relative au RGPD
solution: Audience Manager
title: FAQ relative au RGPD
uuid: e 52 cad 27-6 a 44-45 ee -8524-6080 adb 86 cc 8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# FAQ relative au RGPD{#gdpr-faq}

Ce document contient quelques-unes des questions les plus courantes posées par nos clients et partenaires en ce qui concerne le GDPR (Europe General Data Protection Regulation) et la manière dont Adobe Audience Manager, en tant qu'application de traitement de données, répond aux différents besoins du GDPR.

Dans cet article, nous abordons les questions relatives à la préparation GDPR dans Audience Manager. Make sure you also read the [Experience Cloud GDPR FAQ.](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

Le GDPR est arrivé en vigueur le 25 mai 2018, avec des objectifs principaux de donner aux personnes dans l'UE (sujets de données) un meilleur contrôle de leurs données personnelles tout en simplifiant l'environnement réglementaire des entreprises internationales en optimisant la réglementation au sein de l'UE. Dans le cadre de la préparation GDPR d'Adobe, l'équipe Adobe Audience Manager a amélioré les services et les processus en fonction de la nécessité de prendre en charge l'accès et la suppression de requêtes issues de sujets de données, de vos clients.

## GDPR Glossary {#gdpr-glossay}

Familiarisez-vous avec les termes clés utilisés concernant GDPR. Nous avons mis en évidence certains des termes les plus couramment utilisés ci-dessous.

<br> 

**Contrôleur de données :** GDPR définit « Contrôleur » comme « la personne morale… qui seul ou conjointement avec d'autres détermine l'objectif et les moyens du traitement des données personnelles.  » » Les clients Audience Manager sont des contrôleurs de données. Les clients contrôlent la gestion des données dans Audience Manager.

<br> 

**Processeur de données :** Le « Processeur » est « la personne morale… qui traite les données personnelles au nom du contrôleur ». Dans le contexte d'Audience Manager (plateforme de gestion des données ou DMP d'Adobe), Adobe agit comme un « processeur de données » pour toutes les données personnelles qu'il traite et stocke par le biais de la DMP. Adobe traite uniquement les données personnelles conformément aux autorisations et instructions du contrôleur de données (telles que définies dans notre accord avec le client).

<br> 

**Objet de données :** Personne à laquelle les données personnelles sont liées. Dans le contexte d'Audience Manager, les sujets de données sont les consommateurs d'Audience Manager ou la fin - utilisateurs. Si Audience Manager reçoit des requêtes directement depuis les rubriques de données, ces requêtes sont transférées aux clients Adobe respectifs.

<br> 

**Autorisation :** Le consentement signifie « une indication précise, précise, informée et sans ambiguïté des souhaits du sujet de données par laquelle il ou elle, par une action positive ou claire, signifie accepter le traitement des données personnelles qui lui sont liées ». Le consentement est la responsabilité du contrôleur de données et non d'Adobe via Audience Manager.

<br> 

**Accès :** Les sujets de données ont la possibilité d'exiger que le contrôleur de données vérifie si le contrôleur traite leurs données personnelles. Lorsque le contrôleur de données traite les données personnelles du sujet de données, il doit fournir un accès aux données personnelles et une copie des données personnelles. Les contrôleurs de données peuvent demander à Adobe d'aider à accéder aux demandes d'accès à partir des rubriques de données.

<br> 

**Supprimer :** GDPR indique le « Droit d'être oublié » ou « De droite à Gommage ».  » » Les sujets de données ont la possibilité d'exiger que les contrôleurs de données efface leurs données personnelles. Les contrôleurs de données travaillent avec leurs processeurs, y compris Adobe, pour prendre en charge les requêtes de suppression des rubriques de données.

<br> 

**Correction :** Les sujets de données ont la possibilité de demander aux contrôleurs de données de rectifier les données personnelles inexactes. Les contrôleurs de données fonctionnent avec les processeurs, y compris Adobe, pour prendre en charge les demandes de correction issues des rubriques de données.

<br> 

**Identifiants d'Audience Manager (ID) :** Adobe Audience Manager stocke différents types d'ID. The [GDPR in Audience Manager](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) page provides a summary of these IDs, their corresponding data sources, and brief descriptions. Lorsque vous fournissez des requêtes à Adobe, référencez ces identifiants pour supprimer ou accéder aux requêtes de vos sources de données.

<br> 

**Données personnelles :** GDPR développe la définition des données personnelles. Sous GDPR, les données d'Audience Manager peuvent être classées comme données personnelles selon le cas d'utilisation du client.

<br> 

**Données interdites :** Audience Manager interdit aux clients d'assimiler directement des informations identifiables telles que prénom et nom, ID de courrier électronique, identifiant de la CRM, qui peuvent être utilisées pour identifier directement une personne. Les solutions Adobe Experience Cloud interdisent également les informations sensibles. Pour plus d'informations sur ces conditions, consultez votre contrat avec Adobe. Si ces types de points de données doivent être assimilés dans Audience Manager, contactez votre équipe de conseillers Adobe pour obtenir des recommandations sur le hachage de ces identifiants avant l'assimilation.

<br> 

## Managing Individual GDPR Rights {#manage-ind-gdpr-rights}

**Gestion de la souscription/obtention du consentement**

Le GDPR ne change pas lorsque les contrôleurs de données ont besoin d'un consentement. Il change la manière d'obtenir le consentement. Dans les cas où le consentement est nécessaire pour certaines activités marketing, le consentement du consommateur doit être actif (par ex., aucune case à cocher ou silence comme approbation), non assemblé et les offres de services ne sont pas conditionnées à l'objet de données donnant le consentement. Il peut même y avoir des instances où certains consents doivent être actualisés pour pouvoir continuer à utiliser des données.

En tant qu'outil de traitement de données, Adobe n'est pas en mesure de fournir des conseils juridiques sur l'obtention du consentement. Consultez votre équipe juridique pour obtenir des conseils. We recommend that you work with a consent management solution providers such as [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) or [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) to provide better recommendations on this. Adobe s'est associé à plusieurs fournisseurs de ce type pour faciliter cette intégration via Adobe Launch.

Les clients Audience Manager peuvent stocker le consentement des utilisateurs pour divers cas d'utilisation, tels que la publicité ou la personnalisation, comme caractéristiques dans Audience Manager. La création de segments avec ces caractéristiques inclura alors uniquement les utilisateurs qui fournissent le consentement respectif pour chacun de ces cas d'utilisation. Notez que l'utilisation de cette approche n'arrête pas la collecte de données mais n'affectera que l'utilisation des données lorsque vous envoyez des segments pour activation. When users withdraw their consent, you can remove these traits from user profile using the Audience Manager [inbound batch process](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) or Audience Manager opt-out process as detailed below.

<br> 

**Gestion de l'exclusion/retrait du consentement**

Opt out can be managed for the Adobe Experience Cloud via the [Your Privacy Choices](https://www.adobe.com/privacy/opt-out.html#customeruse) page. Les fonctionnalités de clic sur 1 permettent de contrôler et d'exclure la collecte de données par les solutions de publication Adobe Experience Cloud (y compris Audience Manager). Specifically, see the [business customer section](https://www.adobe.com/privacy/opt-out.html#customeruse) of the Privacy Choices page. For Browsers that do not support third-party cookies, see [Declared ID targeting](../../features/declared-ids.md#declared-id-targeting). For mobile devices, please retrieve the relevant Audience Manager identifiers and call the Audience Manager opt-out APIs as mentioned in the [Declared ID Opt-Out examples](../../features/declared-ids.md#opt-out-examples). Following that, you can cease all data collection for those users with the opt out APIs from Mobile SDK - see [Android devices](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) and [iOS devices](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html). You can find additional details for opt-out in the [Audience Manager Opt-Out Documentation](../../overview/data-security-and-privacy/opt-out-management.md).

<br> 

**Envoi d'Audience Manager GDPR et suppression de requêtes à Adobe**

You can submit Individual GDPR requests for Access and Delete either through the [GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md) or by calling the [GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md). Any [Audience Manager identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids), can be submitted in the requests along with their respective namespace IDs (data source IDs). Si vous envoyez des identifiants de périphérique, tels que des identifiants CRM, Audience Manager agrège le profil authentifié ainsi que les ID de périphérique qui y sont liés. Il est recommandé que les clients utilisent l'ID unique Audience Manager - id (AAM UUID) lorsque cela s'avère possible.

<br> 

**Gestion des demandes d'accès**

Avant le 25 mai 2018, Audience Manager prenait en charge manuellement l'accès aux caractéristiques, aux ID de client et aux segments associés à un identifiant unique dans Audience Manager. Depuis le 25 mai 2018, nous prenons en charge ces demandes comme décrit ci-dessus avec diverses améliorations des produits et services. Outre les caractéristiques, les ID de client, les segments, une réponse à la demande d'accès comprend un résumé du nombre total de caractéristiques et de segments, du type de caractéristique, des descriptions des caractéristiques et des segments ainsi que des noms de source de données correspondants. La réponse Accès inclut également les données tierces et tierces accessibles au contrôleur de données, ainsi que les données propriétaires. See more in [Data Access Requests](../../overview/aam-gdpr/aam-gdpr-details.md#access-data).

<br> 

**Gestion des requêtes de suppression**

Avant le 25 mai 2018, Audience Manager prenait en charge la suppression manuelle des caractéristiques, des ID de client et des segments associés à un identifiant unique dans Audience Manager. Lorsque le GDPR est appliqué, nous prenons en charge ces requêtes comme décrit ci-dessus avec diverses améliorations de produit et de service. Outre l'opération de suppression, les identifiants Audience Manager correspondants pour le sujet de données seront exclus de la collecte de données et les mappages d'ID correspondants seront supprimés. See more in [Data Deletion Requests](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data).

<br> 

**Fournisseurs de données tiers et gestion du consentement**

Les fournisseurs de données tiers sont généralement des contrôleurs de données et ils possèdent le processus d'obtention de tout consentement nécessaire des données pour partager des données avec leurs partenaires de données tiers. Il appartient au client Audience Manager de déterminer si le fournisseur de données tiers a obtenu le consentement nécessaire pour votre cas d'utilisation. Vous trouverez plus de détails sur l'obtention du consentement ci-dessus.

<br> 

**Fournisseurs de données tiers et gestion du consentement**

Les fournisseurs de données sont également des contrôleurs de données et leur processus d'obtention de l'autorisation et de gestion des demandes d'accès/suppression/correction. Adobe is proactively requesting that Data Providers update their company profile information within [Adobe Audience Finder](https://www.adobe-audience-finder.com/) with additional information on user data collection. Les informations sont issues des fournisseurs de données et l'objectif est de mettre à jour l'outil par le biais du troisième trimestre 2018. Cependant, il appartient à chaque client Audience Manager de déterminer que le fournisseur de données tiers a obtenu le consentement nécessaire pour le cas d'utilisation de ce client. Adobe n'émet aucune représentation concernant la portée ou la validité du consentement obtenu ou rapporté par un fournisseur de données tiers pour un cas d'utilisation donné.

<br> 

**Impact de la suppression des requêtes pour l'activation d'audience**

Audience Manager informe les partenaires d'activation des demandes de suppression en leur envoyant des informations de non segmentation pour les sujets de données demandant la suppression de certaines données. Toutefois, certains partenaires d'activation : 1) ne peut pas prendre en charge les demandes de désegment (ou de suppression de segment) d'Adobe et/ou 2) ne sont pas en mesure de recevoir des mises à jour d'une fréquence inférieure à 30 jours. Dans ce cas, les clients Audience Manager ne peuvent pas envoyer de demandes de suppression aux partenaires activés de manière automatisée via Audience Manager. The [GDPR Partner Unsegment documentation](../../overview/aam-gdpr/aam-gdpr-partners.md) provides information about unsegment capabilities and frequency of data exchange for all activation partners.

<br> 

**Rétention des données dans Audience Manager**

L'application de stratégies de conservation des données appropriées, sécurisées et opportunes à vos données est une étape importante du respect de GDPR. Les clients Audience Manager ont la possibilité de définir des périodes de rétention personnalisées sur les caractéristiques et les segments en définissant le TTL requis (durée de vie). We have reduced the retention period for [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF]) and [!UICONTROL Batch Outbound] orders to 8 days. Nous appliquerons également une période de rétention pour les profils de gestion de la relation client inactifs et les mappages d'ID. Please find the more details about retention periods in our [Data Retention FAQ](../../faq/faq-privacy.md).

<br> 

**Gestion des requêtes de correction des données**

Dans la mesure où Audience Manager n'est pas la source des données, il existe un rôle limité pour la correction des données dans Audience Manager. La correction peut signifier que le sujet de données a demandé de ne pas être qualifié d'une caractéristique/segment incorrecte ou d'être qualifié pour la caractéristique/le segment souhaité. Les clients Audience Manager peuvent choisir de capturer les signaux/caractéristiques/segments appropriés par rapport aux profils utilisateur et d'envoyer ces informations par le biais d'ingestion de données hors ligne vers Audience Manager. Veuillez noter que l'utilisateur continuera à se familiariser avec la caractéristique et les segments d'origine s'il se répète.

<br> 

**Transferts de données cross-border**

GDPR n'interdit pas le transfert de données hors d'Europe. Elle exige que les protections de confidentialité des données européennes persistent lorsque les données sont transférées. Visit the [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) to learn more.

<br> 

## GDPR Readiness Guidance for Audience Manager Customers (Data Controllers) {#gdpr-readiness-guidance}

Nous vous recommandons d'être proactif dans les domaines de la gouvernance des données et de la préparation de l'organisation. Ainsi, vos données de consommateur seront organisées pour les processus liés à l'accès ou à la suppression des requêtes ; vos équipes seront activées et configurées pour gérer ces requêtes et vos clients (sujets de données) ont une expérience positive et différenciée avec votre marque.

Remarque : en tant qu'application de traitement de données, Adobe ne peut pas fournir de conseils juridiques sur les exigences GDPR et le processus d'obtention du consentement de vos sources de données. Contactez votre conseiller juridique pour obtenir des conseils sur la conformité GDPR de votre organisation.

<br> 

**Gouvernance des données : Commencez à penser à la gestion de vos données de consommateur dans votre instance Audience Manager.**

* Examinez les différents identifiants de client que vos équipes marketing utilisent pour identifier les utilisateurs dans Audience Manager, ainsi que les sources de données dans lesquelles elles sont stockées. Cela simplifiera le processus des requêtes (telles que la suppression ou l'accès) puisque certains types de données seront hachés par vos équipes avant d'assimilation dans Audience Manager.
* Les ID de périphérique mobile IDFA/GAID sont utilisés pour plusieurs cas d'utilisation dans Audience Manager. Si vous utilisez le SDK Adobe Mobile, veillez à envoyer l'identifiant d'expérience (MID) avec IDFA/GAID pour vous assurer que les réponses GDPR sont terminées.
* La définition des données personnelles étant plus évolutive, les adresses IP peuvent être considérées comme des données personnelles dans votre région. Contactez Adobe Consulting de manière proactive pour obscurcir le dernier octet.
* Déterminez une stratégie et un processus de validation/d'authentification pour confirmer l'identité d'un objet de données lorsqu'il effectue une demande GDPR.
* Consider using [Data Export Controls](../../features/data-export-controls.md) to block audience activation to technologies that house personal data. Par exemple, les segments avec des données tierces ne doivent pas être synchronisés aux fournisseurs de services de messagerie. Set a [!UICONTROL Data Export Control] to ensure that no one in your organization can accidentally activate this data.
* Begin utilizing [Role Based Access Controls](../../features/administration/administration-overview.md) to ensure the right teams have access to intended data.
* Consider appropriate [retention periods](../../faq/faq-privacy.md#data-retention-faq) for the data.
* Review identity linkage and privacy policies and legal requirements to see when and where it is appropriate to tie identity sets together; use appropriately via Audience Manager’s [Profile Merge Rules](../../features/profile-merge-rules/merge-rules-overview.md).

<br> 

**Préparation de l'organisation : Création d'un processus d'entreprise**

* Identifiez un processus de réception/réponse aux demandes de sujet de données. Envisagez la création d'un outil automatisé pour envoyer des requêtes à Audience Manager.
* Créez un point de contact de confidentialité au sein de votre centre d'excellence DMP. Connectez le point de contact de votre organisation à l'équipe d'utilisation des produits Audience Manager pour comprendre comment vous pouvez gérer les exigences de votre ID d'entrée.
* Effectuez une révision des données avant de le partager avec le sujet de données. Documérez les étapes que vous avez mises en place pour vous aider à établir la responsabilité.

