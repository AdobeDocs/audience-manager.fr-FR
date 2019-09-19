---
description: Ce document contient quelques-unes des questions les plus courantes posées par nos clients et partenaires au sujet du Règlement général européen sur la protection des données (RGMD) et de la manière dont Adobe Audience Manager, en tant que processeur de données, répond aux diverses exigences du RGMD.
seo-description: Ce document contient quelques-unes des questions les plus courantes posées par nos clients et partenaires au sujet du Règlement général européen sur la protection des données (RGMD) et de la manière dont Adobe Audience Manager, en tant que processeur de données, répond aux diverses exigences du RGMD.
seo-title: FAQ relative au RGPD
solution: Audience Manager
title: FAQ relative au RGPD
uuid: e52cad27-6a44-45ee-8524-6080adb86cc8
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# FAQ relative au RGPD{#gdpr-faq}

Ce document contient quelques-unes des questions les plus courantes posées par nos clients et partenaires au sujet du Règlement général européen sur la protection des données (RGMD) et de la manière dont Adobe Audience Manager, en tant que processeur de données, répond aux diverses exigences du RGMD.

Dans cet article, nous abordons des questions sur l’état de préparation au RMMD dans Audience Manager. Consultez également la FAQ sur le RDDC [Experience Cloud.](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-faq.md)

Le RDPC est entré en vigueur le 25 mai 2018 avec pour objectif principal de donner aux individus dans l'UE (Data Subjects) un plus grand contrôle de leurs données personnelles tout en simplifiant l'environnement réglementaire pour les entreprises internationales en améliorant la réglementation au sein de l'UE. Dans le cadre de l’état de préparation du rapport GDPR d’Adobe, l’équipe d’Adobe Audience Manager a amélioré les services et les processus si nécessaire afin de prendre en charge les demandes d’accès et de suppression des objets de données, vos clients.

## Glossaire du RDPR {#gdpr-glossay}

Familiarisez-vous avec les termes clés utilisés en rapport avec le RMPC. Nous avons mis en évidence quelques-uns des termes les plus utilisés ci-dessous.

<br> 

**** Contrôleur de données : Le RDPC définit le "contrôleur" comme "la personne morale ... qui, seule ou conjointement avec d'autres, détermine les buts et les moyens du traitement des données à caractère personnel". Les clients d’Audience Manager sont des contrôleurs de données. Les clients contrôlent la gestion des données dans Audience Manager.

<br> 

**** Processeur de données : Le "Processeur" est "la ... personne morale ... qui traite les données personnelles pour le compte du contrôleur". Dans le contexte d’Audience Manager (plate-forme de gestion des données ou DMP d’Adobe), Adobe agit en tant que "processeur de données" pour toutes les données à caractère personnel qu’il traite, stocke et services via le DMP. Adobe traite uniquement les données à caractère personnel conformément aux instructions et aux autorisations du contrôleur de données (par exemple, conformément à notre accord avec le client).

<br> 

**** Data Subject : La personne à laquelle les données personnelles se rapportent. Dans le contexte d’Audience Manager, les objets de données sont les consommateurs ou les utilisateurs finaux d’Audience Manager. Si Audience Manager reçoit des requêtes directement des objets de données, ces requêtes sont transférées aux clients Adobe respectifs.

<br> 

**** Consentement : Consentement signifie "toute indication librement donnée, spécifique, informée et sans ambiguïté des souhaits de la personne concernée, par laquelle elle ou elle, par une déclaration ou par une discrimination positive claire, signifie son accord au traitement de ses données personnelles". Le consentement est la responsabilité du contrôleur de données, et non celle d’Adobe par le biais d’Audience Manager.

<br> 

**** Accès : Les sujets de données ont le droit d'exiger du contrôleur de données qu'il vérifie si le contrôleur traite leurs données personnelles. Lorsque le contrôleur de données traite les données personnelles de la personne concernée, il doit fournir un accès aux données personnelles et une copie de celles-ci. Les contrôleurs de données peuvent demander à Adobe de les aider dans leurs demandes d’accès à partir des objets de données.

<br> 

**** Supprimer : Le GDPR souligne le "Droit à l'oubli" ou "Droit à l'effacement". Les objets de données ont le droit d’exiger des contrôleurs de données qu’ils effacent leurs données personnelles. Les contrôleurs de données travaillent avec leurs processeurs, y compris Adobe, pour prendre en charge les demandes de suppression des objets de données.

<br> 

**** Correction : Les sujets de données ont le droit d’exiger des contrôleurs de données qu’ils rectifient les données personnelles inexactes. Les contrôleurs de données travaillent avec les processeurs, y compris Adobe, pour prendre en charge les demandes de correction des objets de données.

<br> 

**** Identifiants (ID) d’Audience Manager : Adobe Audience Manager stocke différents types d’ID. La page [GDPR d’Audience Manager](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids) fournit un résumé de ces identifiants, de leurs sources de données correspondantes et une brève description. Lorsque vous fournissez des requêtes à Adobe, référencez ces identifiants pour effectuer des requêtes de suppression ou d’accès pour vos sujets de données.

<br> 

**** Données personnelles : GDPR étend la définition des données personnelles. Dans le cadre du RGMD, toute donnée d’Audience Manager peut être classée comme donnée personnelle en fonction du cas d’utilisation du client.

<br> 

**** Données interdites : Audience Manager interdit aux clients d’ingérer des informations directement identifiables, telles que le prénom et le nom, l’ID de courrier électronique et l’ID de gestion de la relation client, qui peuvent être utilisés pour identifier directement une personne. Les solutions Adobe Experience Cloud interdisent également les informations sensibles. Consultez votre contrat avec Adobe pour plus d’informations sur ces conditions. Si ces types de points de données doivent être assimilés dans Audience Manager, consultez votre équipe de conseillers Adobe pour obtenir des recommandations sur le hachage de ces identifiants avant l’assimilation.

<br> 

## Gestion des droits GDPR individuels {#manage-ind-gdpr-rights}

**Gestion de l’inclusion / Obtention du consentement**

Le RDMD ne change pas lorsque les contrôleurs de données ont besoin de consentement, il change la façon d’obtenir le consentement. Dans les cas où le consentement est nécessaire pour certaines activités de marketing, le consentement du consommateur doit être actif (p. ex., aucune case à cocher ou silence en tant qu’avis conforme), dégroupé et les offres de services ne peuvent être subordonnés au consentement de la personne concernée. Il peut même arriver que certains consentements doivent être actualisés pour pouvoir continuer à utiliser les données.

En tant que traitement de données, Adobe n’est pas en mesure de fournir des conseils juridiques sur l’obtention du consentement. Consultez votre équipe juridique pour obtenir des conseils. Nous vous recommandons de travailler avec des fournisseurs de solutions de gestion du consentement, comme [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) ou [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/) , afin de fournir de meilleures recommandations à ce sujet. Adobe s’est associé à plusieurs fournisseurs de ce type pour faciliter cette intégration via Adobe Launch.

Les clients d’Audience Manager peuvent stocker le consentement de l’utilisateur pour divers cas d’utilisation, tels que la publicité ou la personnalisation en tant que caractéristiques dans Audience Manager. La création de segments avec ces caractéristiques inclut alors uniquement les utilisateurs qui donnent leur consentement pour chacun de ces cas d’utilisation. Notez que l’utilisation de cette approche n’arrête pas la collecte des données, mais n’affecte l’utilisation des données que lorsque vous envoyez des segments pour activation. Lorsque les utilisateurs retirent leur consentement, vous pouvez supprimer ces caractéristiques du profil utilisateur à l’aide du processus [de traitement par lots](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) entrant d’Audience Manager ou du processus d’exclusion d’Audience Manager, comme indiqué ci-dessous.

<br> 

**Gestion des exclusions / Retrait du consentement**

La désinscription peut être gérée pour Adobe Experience Cloud via la page [Vos choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité. Les fonctionnalités d’un clic permettent aux utilisateurs finaux de contrôler la collecte de données et de s’exclure de celle-ci par les solutions publicitaires Adobe Experience Cloud (y compris Audience Manager). En particulier, consultez la section [clients](https://www.adobe.com/privacy/opt-out.html#customeruse) professionnels de la page Choix de confidentialité. Pour les navigateurs qui ne prennent pas en charge les cookies tiers, voir Ciblage des identifiants [déclarés](../../features/declared-ids.md#declared-id-targeting). Pour les périphériques mobiles, récupérez les identifiants Audience Manager appropriés et appelez les API d’exclusion d’Audience Manager comme indiqué dans les exemples [d’exclusion d’ID](../../features/declared-ids.md#opt-out-examples)déclarés. Par la suite, vous pouvez mettre fin à la collecte de données pour les utilisateurs qui utilisent les API d’exclusion du kit SDK Mobile - voir Périphériques [](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) Android et périphériques [](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html)iOS. Vous trouverez des informations supplémentaires sur l’exclusion dans la documentation [d’exclusion d’](../../overview/data-security-and-privacy/opt-out-management.md)Audience Manager.

<br> 

**Envoi de demandes d’accès au répertoire de stockage global de documents Audience Manager et de suppression à Adobe**

Vous pouvez envoyer des demandes d’accès et de suppression à un RGD individuel par l’intermédiaire de l’interface utilisateur [des services à la clientèle](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) RGD ou en appelant l’API [](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-id-onboarding.md)RGD. Les identifiants [](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)Audience Manager peuvent être envoyés dans les requêtes avec leurs identifiants d’espace de noms respectifs (ID de source de données). Si vous envoyez des identifiants de plusieurs périphériques, tels que des identifiants CRM, Audience Manager effectuera une action sur le profil authentifié ainsi que sur les identifiants de périphérique qui y sont liés. Il est recommandé aux clients d’utiliser autant que possible l’identifiant utilisateur unique d’Audience Manager (UUID AAM).

<br> 

**Gestion des demandes d’accès**

Avant le 25 mai 2018, Audience Manager prenait en charge manuellement l’accès aux caractéristiques, aux ID de client et aux segments associés à un ID unique dans Audience Manager. Depuis le 25 mai 2018, nous soutenons ces demandes de la manière décrite ci-dessus avec diverses améliorations des produits et services. Outre les caractéristiques, les ID de client, les segments et une réponse à la demande d’accès incluent un résumé du nombre total de caractéristiques et de segments, du type de caractéristique, des descriptions des caractéristiques et des segments, ainsi que des noms de source de données respectifs. La réponse Access inclut également des données tierces et tierces accessibles au contrôleur de données, ainsi que les données propriétaires. Pour en savoir plus, voir Demandes [d’accès aux](../../overview/aam-gdpr/aam-gdpr-details.md#access-data)données.

<br> 

**Gestion des demandes de suppression**

Avant le 25 mai 2018, Audience Manager prenait en charge la suppression manuelle des caractéristiques, des ID de client et des segments associés à un ID unique dans Audience Manager. Dès l'entrée en vigueur du RMR, nous appuyons ces demandes de la manière décrite ci-dessus avec diverses améliorations des produits et des services. En plus de l’opération de suppression, les identifiants Audience Manager respectifs pour la personne concernée seront désactivés de la collecte de données ultérieure et les mappages d’ID respectifs seront supprimés. Pour en savoir plus, voir Demandes [de suppression de](../../overview/aam-gdpr/aam-gdpr-details.md#delete-data)données.

<br> 

**Fournisseurs de données tiers et gestion du consentement**

Les fournisseurs de données tiers sont généralement également des contrôleurs de données et sont propriétaires du processus permettant d'obtenir le consentement nécessaire de la personne concernée pour partager les données avec leurs partenaires de données tiers. Il incombe au Client d’Audience Manager de déterminer si le Fournisseur de données tiers a obtenu le consentement nécessaire pour votre cas d’utilisation. Plus de détails sur l'obtention du consentement sont traités ci-dessus.

<br> 

**Fournisseurs de données tiers et gestion du consentement**

Les fournisseurs de données sont également des contrôleurs de données et sont propriétaires de leur processus d’obtention du consentement et de gestion des demandes d’accès, de suppression et de correction. Adobe demande de manière proactive aux fournisseurs de données de mettre à jour les informations de profil de leur entreprise dans [Adobe Audience Finder](https://www.adobe-audience-finder.com/) avec des informations supplémentaires sur la collecte de données utilisateur. L’information sera obtenue auprès des fournisseurs de données et l’objectif est de mettre à jour l’outil d’ici le 2e trimestre 2018. Toutefois, il appartient à chaque client Audience Manager de déterminer que le fournisseur de données tiers a obtenu le consentement nécessaire pour le cas d’utilisation de ce client. Adobe ne fait aucune déclaration sur la portée ou la validité du consentement obtenu ou rapporté par un fournisseur de données tiers pour un cas d’utilisation donné.

<br> 

**Impact de la suppression des requêtes pour l’activation de l’audience**

Audience Manager informe les partenaires d’activation des demandes de suppression en leur envoyant des informations de non-segmentation pour les objets de données demandant la suppression de certaines données. Cependant, certains partenaires d’activation : 1) ne peuvent pas prendre en charge les demandes de non-segmentation (ou de suppression de segment) d’Adobe et/ou 2) ne peuvent pas recevoir de mises à jour de notre part avec une fréquence inférieure à 30 jours. Dans ce cas, les clients d’Audience Manager ne peuvent pas envoyer de requêtes de suppression aux partenaires d’activation de manière automatisée via Audience Manager. La documentation [sur le désegmentation des partenaires](../../overview/aam-gdpr/aam-gdpr-partners.md) GDPR fournit des informations sur les capacités de désegmentation et la fréquence des échanges de données pour tous les partenaires d’activation.

<br> 

**Rétention des données dans Audience Manager**

L'application de politiques appropriées, sécurisées et opportunes de conservation des données à vos données est un élément important du respect du RGMD. Les clients d’Audience Manager peuvent définir des périodes de rétention personnalisées sur les caractéristiques et les segments en définissant le TTL (durée de vie) requis. Nous avons réduit la période de rétention pour [!UICONTROL Customer Data Feeds] ( [!UICONTROL CDF]) et les [!UICONTROL Batch Outbound] commandes à 8 jours. Nous appliquerons également une période de rétention pour les profils CRM inactifs et les mappages d’ID. Pour plus d'informations sur les périodes de rétention, consultez notre FAQ [sur la rétention des](../../faq/faq-privacy.md)données.

<br> 

**Gestion des requêtes de correction des données**

Dans la mesure où Audience Manager n’est pas la source des données, il existe un rôle limité pour la correction des données dans Audience Manager. La correction peut signifier que la personne concernée a demandé soit d'être disqualifiée d'une caractéristique/segment incorrecte, soit d'être qualifiée d'une caractéristique/segment désirée. Les clients d’Audience Manager peuvent choisir de capturer les signaux/caractéristiques/segments pertinents par rapport aux profils utilisateur et d’envoyer ces informations par l’assimilation de données hors ligne à Audience Manager. Veuillez noter que l’utilisateur continuera à être qualifié pour la caractéristique d’origine et les segments s’il répète son comportement.

<br> 

**Transferts de données transfrontaliers**

Le RDPC n’interdit pas le transfert de données en dehors de l’Europe. Elle exige que les protections de la vie privée sur les données européennes persistent partout où les données sont transférées. Consultez le Centre [de confidentialité](https://www.adobe.com/privacy/eudatatransfers.html) Adobe pour en savoir plus.

<br> 

## Guide de préparation GDPR pour les clients d’Audience Manager (contrôleurs de données) {#gdpr-readiness-guidance}

Nous recommandons d'être proactif dans les domaines de la gouvernance des données et de la préparation de l'organisation. Ainsi, vos données clients seront organisées pour les processus liés aux demandes d’accès ou de suppression, vos équipes seront autorisées à gérer ces demandes et vos clients (objets de données) auront une expérience positive et différenciée de votre marque.

Veuillez noter qu’en tant que processeur de données, Adobe ne peut pas fournir de conseils juridiques sur les exigences du RMMD ni sur le processus d’obtention du consentement de vos sujets de données. Veuillez consulter votre conseiller juridique pour obtenir des conseils sur la conformité aux RMR pour votre organisation.

<br> 

**Gouvernance des données : Commencez à réfléchir à la manière dont vos données de consommation sont gérées dans votre instance d’Audience Manager.**

* Examinez les différents ID de client utilisés par vos équipes marketing pour identifier les utilisateurs dans Audience Manager, ainsi que les sources de données dans lesquelles ils sont stockés. Cela simplifiera le processus des demandes (suppression ou accès, par exemple), car certains types de données seront hachés par vos équipes avant leur assimilation dans Audience Manager.
* Les ID de périphérique mobile IDFA/GAID sont utilisés pour plusieurs cas d’utilisation dans Audience Manager. Si vous utilisez Adobe Mobile SDK, veillez à envoyer le MID (Experience Cloud ID) avec IDFA/GAID pour vous assurer que les réponses au GDPR sont complètes.
* La définition des données personnelles devenant de plus en plus étendue, les adresses IP peuvent être considérées comme des données personnelles dans votre région. Collaborez de manière proactive avec le service de conseil d’Adobe pour obscurcir le dernier octet.
* Déterminez une politique et un processus de validation/authentification pour confirmer l'identité d'un sujet de données lorsqu'il fait une demande de RDMD.
* Envisagez d’utiliser des contrôles [d’exportation de](../../features/data-export-controls.md) données pour bloquer l’activation de l’audience sur les technologies qui hébergent des données personnelles. Par exemple, les segments contenant des données tierces ne doivent pas être regroupés en réseaux avec les fournisseurs de services de messagerie. Définissez un [!UICONTROL Data Export Control] afin de vous assurer que personne dans votre entreprise ne peut activer accidentellement ces données.
* Commencez à utiliser les contrôles [d'accès basés sur les](../../features/administration/administration-overview.md) rôles pour vous assurer que les équipes appropriées ont accès aux données prévues.
* Tenez compte des périodes [de](../../faq/faq-privacy.md#data-retention-faq) rétention appropriées pour les données.
* Examiner les politiques et les exigences juridiques relatives au lien entre l'identité et la vie privée afin de déterminer quand et où il convient de lier les ensembles d'identité; utilisez correctement via les règles [de fusion de](../../features/profile-merge-rules/merge-rules-overview.md)profil d’Audience Manager.

<br> 

**Préparation organisationnelle : Établir un processus d’entreprise**

* Identifiez un processus pour recevoir ou répondre aux demandes des sujets de données. Envisagez de créer un outil automatisé pour envoyer des requêtes à Audience Manager.
* Nommez un point de contact de confidentialité au sein de votre centre d’excellence DMP. Connectez le point de contact de confidentialité de votre entreprise à votre équipe d’utilisation du produit d’Audience Manager pour comprendre comment vous pouvez gérer vos besoins en ID d’entrée.
* Effectuez un examen des données avant de les partager avec la personne concernée. Documentez les étapes que vous avez mises en place, pour vous aider à établir la responsabilisation.

