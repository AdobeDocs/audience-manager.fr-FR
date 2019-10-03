---
description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-title: Module externe Audience Manager pour IAB TCF
solution: Audience Manager
title: Module externe Audience Manager pour IAB TCF
translation-type: tm+mt
source-git-commit: c238a37e1a72edb0679f657d0178e04b8d848ec2

---


# Module externe Audience Manager pour IAB TCF {#aam-iab-plugin}

## Aperçu

Un aspect important des obligations de confidentialité que vous avez envers vos utilisateurs réside dans l’acquisition et le respect des choix des utilisateurs quant à la façon dont leurs données personnelles sont utilisées (c’est-à-dire les « objectifs ») et quant aux entités qui les utilisent (les « entreprises »).

Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la [fonctionnalité d’adhésion](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) et la prise en charge d’[IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager. Audience Manager is registered in the IAB TCF with the vendor ID 565.

The Audience Manager Plug-in for IAB TCF utilizes the Opt-in functionality, which is, in turn, part of the Adobe Experience Cloud ID Service (ECID) library.[](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)[](https://marketing.adobe.com/resources/help/en_US/mcvid/)

## Scope and Limitations {#scope-and-limitations}

As a Publisher or Advertiser working with Audience Manager, you are able to convey user choices to Audience Manager as per IAB TCF. Vous disposez ainsi d’une manière simple et cohérente de communiquer les choix des utilisateurs à tous les partenaires avec lesquels vous travaillez et Audience Manager peut vous aider à respecter les choix de confidentialité de vos utilisateurs.

Le soutien du CCI au TCF décrit dans cet article représente la première phase de l’appui planifié d’Audience Manager au cadre du CCI. Actuellement, Audience Manager ne prend pas en charge :

* Flux de travaux sur les dispositifs portables;
* la gestion du consentement inter-dispositifs;
* Approbation du consentement aux URL envoyées vers les destinations [](/help/using/features/destinations/create-url-destination.md)URL ;
* Approbation en attente des segments.

## Conditions préalables {#prerequisites}

Pour utiliser le TCF IAB avec Audience Manager, vous devez respecter les conditions préalables suivantes :

1. Vous devez utiliser le service d’ID d’expérience (ECID) version 4.1 ou ultérieure. [Téléchargez](https://github.com/Adobe-Marketing-Cloud/id-service/releases) notre dernière version d'ECID.
2. 
   1. Vous devez utiliser la bibliothèque d’intégration des données d’Audience Manager (DIL) version 9.0 ou ultérieure, téléchargeable [ici](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lisez la documentation [d’Audience Manager sur](/help/using/dil/dil-overview.md)DIL.
   2. Si vous utilisez le transfert côté serveur (SSF) pour importer des données dans Audience Manager, vous devez effectuer la mise à niveau vers la dernière version d’AppMeasurement. Téléchargez AppMeasurement à l’aide du Gestionnaire [de code](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.
3. Vous devez utiliser une plateforme de gestion du consentement (CMP), commerciale ou la vôtre, qui prend en charge l’IAB et est enregistrée auprès de l’IAB TCF. Voir la liste des [CMP enregistrées dans le cadre](https://advertisingconsent.eu/cmp-list/)du CCI.

## Recommandations et mise en oeuvre {#recommendations}

Pour activer la prise en charge TCF IAB dans Audience Manager, lisez notre documentation sur la [configuration d’IAB avec l’inclusion](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Pour ce faire, utilisez [Adobe Launch](https://docs.adobelaunch.com/) pour instrumenter l’inclusion ECID sur vos propriétés. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Processus de choix de l’utilisateur lors de l’utilisation de la structure IAB {#user-choice-workflow}

Lors de la visite d’une propriété Web, vos utilisateurs peuvent indiquer comment leurs données doivent être utilisées par l’éditeur et par les fournisseurs tiers avec lesquels l’éditeur travaille. Les utilisateurs fournissent leurs choix sous la forme d’objectifs *et d’autorisations* standard aux fournisseurs ** tiers enregistrés dans la liste globale des fournisseurs. L'image ci-dessous représente un exemple de dialogue CMP, présenté à un nouveau visiteur d'un site Web. Gardez à l’esprit que ce dialogue peut sembler très différent, en fonction de l’implémentation des clients.

![Dialogue du CMP](/help/using/overview/aam-gdpr/assets/cmp.png)

Les objectifs normalisés du CCI sont les suivants :

* Stockage et accès aux informations
* Personnalisation
* Sélection, diffusion et création de rapports d’annonces
* Sélection, diffusion et création de rapports de contenu
* vidéo

Refer to the IAB framework specification page for a description of the five standard purposes.[](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features)

Les utilisateurs peuvent accorder leur consentement à une combinaison d'objectifs normalisés et de fournisseurs. For example, users could grant their consent for storage, personalization, and measurement and grant their consent to all third-party vendors displayed by the CMP. Ou, dans un autre exemple, ils pourraient accorder leur consentement aux cinq fins habituelles, mais seulement à quelques-uns des fournisseurs affichés par le CMP.

Once the user selects their privacy choices, the user choice(s) are recorded in the IAB TCF consent string. The IAB TCF consent string stores the combination of approved purposes and vendors, along with other metadata information (see the IAB page for more information). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) Every vendor registered in the IAB TCF evaluates the IAB TCF consent string and makes decisions based on the users' privacy choices. Keep in mind that the users' privacy choices are valid across all approved vendors.

## Standard purposes needed by Audience Manager {#aam-standard-purposes}

Audience Manager evaluates the users' choices stored in the IAB TFC consent string for:

* Information storage and access (purpose ID 1 in the global vendor list)[](https://vendorlist.consensu.org/vendorlist.json)
* Personalization (purpose ID 2)
* Measurement (purpose ID 5)
* Audience Manager vendor consent to store, process, or activate on data for a publisher.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Audience Manager behavior depends on whether the user grants consent {#aam-behavior-consent}

Audience Manager works differently depending on whether Audience Manager detects in the IAB TCF consent string that the user has provided consent for the three purposes (storage, personalization, measurement) or not.

| Lorsque votre utilisateur *donne son consentement*, Audience Manager : | When your user declines consent, Audience Manager:** |
|---|---|
| <ul><li>exécute tous les cas d’utilisation d’Audience Manager que vous avez demandés.</li><li>Envoie le consentement à des tiers lors de la synchronisation des identifiants (en transmettant gdpr = 1 et la chaîne de consentement sous la forme gdpr_consentement lors des appels de synchronisation des identifiants).</li><li>Evalue et honore le consentement transmis à partir des pixels du serveur d’annonces.</li><li>Honore les synchronisations d’ID initiées par le partenaire.</li></ul> | <ul><li>Ne stocke aucune nouvelle donnée utilisateur dans votre instance. Cela inclut les ID de partenaire, les signaux, les caractéristiques ou les données de pixels.</li><li>Ne déclenche pas la synchronisation des identifiants tiers.</li><li>N’accepte pas les synchronisations d’ID initiées par le partenaire.</li></ul> |



## Cas d’utilisation de l’éditeur {#publisher-use-case}

En implémentant le TCF IAB, vous n’êtes pas tenu de gérer le code personnalisé pour la gestion du consentement sur vos propriétés Web par le biais d’un mécanisme différent avec Adobe ou d’autres fournisseurs tiers. Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Commence à gauche de l’image :

1. Un utilisateur visite l’une de vos propriétés Web. Tant que vous utilisez les dernières versions des bibliothèques ECID et DIL (voir [Conditions préalables](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), le flux d’inclusion est déclenché.
2. Audience Manager vérifie si le flux IAB s’applique (`isIabContext=true`). Voir [Recommandations et comment mettre en oeuvre](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager vérifie si GDPR s’applique (`gdpr = 1`) et s’il existe un CMP, enregistré auprès d’IAB, sur votre propriété Web. Par exemple, cela s’appliquerait aux utilisateurs qui visitent la région de l’Union européenne. Notez qu’il est de votre responsabilité en tant qu’éditeur de définir l’indicateur GDPR.
4. Si GDPR s’applique, Audience Manager vérifie la chaîne de consentement TCF IAB, transmise dans le paramètre `gdpr_consent`, pour les autorisations nécessaires. Audience Manager a besoin d’autorisations pour le stockage, la personnalisation, la mesure et le consentement du fournisseur Audience Manager pour stocker, traiter ou activer les données.
5. Si la chaîne de consentement TCF IAB est présente et qu’elle contient les autorisations requises, Audience Manager transmet la chaîne de consentement TCF IAB aux serveurs [de collecte de](/help/using/reference/system-components/components-data-collection.md) données (DCS).
6. Audience Manager répond en définissant un cookie [demdex](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) sur le navigateur. Audience Manager initie et honore également les synchronisations d’identifiants tiers.
7. Sinon, si la chaîne de consentement TCF IAB transmise à l’étape 5 ne contient pas toutes les autorisations nécessaires, Audience Manager ne collecte, ne traite pas ou n’active pas les données et n’honore ni ne déclenche les synchronisations d’ID.

![Cas d’utilisation de l’éditeur](assets/publisher-use-case.png)

## Cas d’utilisation d’annonceurs {#advertiser-use-case}

Audience Manager evaluates and honors consent passed in pixel calls, in accordance with the IAB TCF.[](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)

Les pixels sont généralement placés par les clients d’Audience Manager sur les pages de leurs partenaires ou sont placés sur les serveurs d’annonces pour les inclure dans la réponse de la publicité. In the first case, your partner must programmatically retrieve the consent parameter and add it to the pixel before firing. In the second case, which is more common and is described in detail below, ad servers append the consent parameters they receive from the Supply-Side Platform (SSP) or publisher ad servers to all pixels.

Audience Manager uses two parameters to pass user consent in pixel calls:

* `gdpr` peut être 0 (le RGMD ne s'applique pas) ou 1 (le RGMD s'applique);
* `gdpr_consent` is the URL-safe base64-encoded GDPR consent string (see specification). [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications) Un exemple d’appel pour un pixel d’impression avec les deux paramètres peut ressembler à ce qui suit :

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Commence à gauche de l’image :

1. Une impression est transmise à l’utilisateur via un serveur d’annonces. Cela se traduit par un appel au pixel vers nos serveurs de collecte de données (DCS).
1. Audience Manager vérifie si l’indicateur GDPR s’applique. Dans le cas contraire, Audience Manager stocke les données transmises dans des variables de macro dans des appels en pixels.
1. Si la chaîne de consentement est présente et qu’elle contient les autorisations requises, Audience Manager stocke les données transmises dans des variables de macro dans des appels en pixels.
1. Si la chaîne de consentement est manquante ou si elle ne dispose pas des autorisations requises, Audience Manager supprime les données transmises dans les variables de macro dans les appels en pixels.

![Cas d’utilisation d’annonceurs](assets/advertiser-use-case.png)

## Activation partners that support IAB TCF {#aam-activation-partners}

Le module externe Audience Manager pour IAB TCF vous permet de transférer la chaîne de consentement IAB TCF aux partenaires d’activation tout en respectant les choix de confidentialité des utilisateurs. Pour plus d'informations sur les partenaires d'activation qui prennent en charge IAB TCF (à partir du 7 juillet 2019), consultez notre fiche **[Excel de](/help/using/overview/aam-gdpr/assets/AAM-Partners-October2019.xlsx)** partenaire.

## Test de l’implémentation IAB {#test-iab-implementation}

Pour vérifier que vous avez correctement implémenté le module externe Audience Manager pour IAB TCF, consultez le cas d’ [utilisation 4 dans Méthodes de validation pour l’inclusion et l’implémentation](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html)IAB.

## IAB et exclusion dans Audience Manager. Ordre de priorité. {#iab-and-optout}

Une autre option de confidentialité à la disposition des utilisateurs est la possibilité de se désinscrire de toute collecte de données. Adobe fournit aux utilisateurs les moyens de le faire dans la page [Vos choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité.

Audience Manager aborde la gestion des exclusions dans un article [distinct de notre documentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Ordre de priorité** : si votre utilisateur choisit de ne pas participer à la collecte de données à l’aide d’un outil d’exclusion global, comme décrit dans le lien ci-dessus, cette priorité est accordée aux vérifications d’inclusion et d’IAB.

## Ressources supplémentaires {#additional-resources}

* [Experience Cloud ID Service Opt-in](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR Transparency and Consent Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR Transparency and Consent Framework Technical Specifications](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Module externe IAB TCF - démonstration vidéo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)