---
description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-title: Module externe Audience Manager pour IAB TCF
solution: Audience Manager
title: Module externe Audience Manager pour IAB TCF
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Module externe Audience Manager pour IAB TCF {#aam-iab-plugin}

## Aperçu

Un aspect important des obligations de confidentialité que vous avez envers vos utilisateurs réside dans l’acquisition et le respect des choix des utilisateurs quant à la façon dont leurs données personnelles sont utilisées (c’est-à-dire les « objectifs ») et quant aux entités qui les utilisent (les « entreprises »).

Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la [fonctionnalité d’adhésion](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) et la prise en charge d’[IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager. Audience Manager est enregistré dans l'IAB TCF avec l'ID de fournisseur 565.

Le module externe Audience Manager pour IAB TCF utilise la [fonctionnalité de souscription](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html), qui fait à son tour partie de la bibliothèque Adobe [Experience Cloud ID Service (ECID)](https://marketing.adobe.com/resources/help/en_US/mcvid/) .

## Portée et limites {#scope-and-limitations}

En tant qu'éditeur ou annonceur travaillant avec Audience Manager, vous pouvez transmettre les choix d'utilisateurs à Audience Manager selon l'IAB TCF. Vous disposez ainsi d'un moyen facile et cohérent de communiquer les choix des utilisateurs à tous les partenaires que vous collaborez et Audience Manager peut vous aider à respecter les choix de confidentialité de vos utilisateurs.

La prise en charge de l'IAB TCF décrite dans cet article représente la première phase de la prise en charge prévue par Audience Manager pour la structure IAB. Actuellement, Audience Manager ne prend pas en charge :

* Processus des périphériques mobiles ;
* Gestion des autorisations inter-périphériques ;
* Ajout de l'autorisation aux URL envoyées aux [destinations URL](/help/using/features/destinations/create-url-destination.md);
* Ajout de l'autorisation aux segments.

## Conditions préalables {#prerequisites}

Pour utiliser l'IAB TCF avec Audience Manager, vous devez respecter les conditions préalables suivantes :

1. Vous devez utiliser le service ECID (Experience Cloud ID) version 4.1 ou ultérieure. [Téléchargez](https://github.com/Adobe-Marketing-Cloud/id-service/releases) notre dernière version d'ECID.
2. 
   1. Vous devez utiliser la bibliothèque d'intégration des données Audience Manager (DIL) version 9.0 ou ultérieure, téléchargeable [ici](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lisez la documentation [relative à DIL dans la documentation d'Audience Manager](/help/using/dil/dil-overview.md).
   2. Si vous utilisez le transfert côté serveur (SSF) pour importer des données dans Audience Manager, vous devez effectuer la mise à niveau vers la dernière version d'appmeasurement. Téléchargez appmeasurement à l'aide du Gestionnaire de code [Analytics](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html).
3. Vous devez utiliser une plateforme de gestion de l'approbation (CMP), commerciale ou vôtre, qui prend en charge l'IAB et est enregistrée auprès de l'IAB TCF. Reportez-vous à la liste [des fichiers CMPS enregistrés dans la structure IAB](https://advertisingconsent.eu/cmp-list/).

## Recommandations et mise en œuvre {#recommendations}

Pour activer la prise en charge de l'IAB TCF dans Audience Manager, consultez notre documentation sur [la configuration de l'IAB avec souscription](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html).

Cela est le plus simple grâce à [Adobe Launch](https://docs.adobelaunch.com/) pour l'instrumentation d'un appel ECID sur vos propriétés. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Processus de choix utilisateur lors de l'utilisation de la structure IAB {#user-choice-workflow}

Lors de la visite d'une propriété Web, vos utilisateurs peuvent définir leurs choix quant à l'utilisation de leurs données par l'éditeur et par les fournisseurs tiers avec lesquels l'éditeur travaille. Les utilisateurs fournissent leurs choix sous forme *de fonctions standard* et d'autorisations auprès *des fournisseurs tiers* enregistrés dans la liste des fournisseurs globaux. L'image ci-dessous représente un exemple de dialogue CMP, présenté à un nouveau visiteur d'un site Web. Gardez à l'esprit que ce dialogue peut être très différent, selon la mise en œuvre des clients.

![Dialogue CMP](/help/using/overview/aam-gdpr/assets/cmp.png)

Les objectifs standard de la structure IAB sont les suivants :

* Stockage d'informations et accès
* Personnalisation
* Sélection, diffusion et création de rapports publicitaires
* Sélection de contenu, diffusion et création de rapports
* vidéo

Pour obtenir une description des cinq fins standard, reportez-vous à [la page](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) de spécification de structure IAB.

Les utilisateurs peuvent accorder leur consentement à une combinaison d'objectifs standard et de fournisseurs. Par exemple, les utilisateurs peuvent accorder leur consentement à un stockage, à une personnalisation et à une mesure et accorder leur autorisation à tous les fournisseurs tiers affichés par le CMP. Ou, dans un autre exemple, ils peuvent accorder leur autorisation aux cinq objectifs standard, mais seulement accorder le consentement à quelques fournisseurs affichés par le CMP.

Une fois que l'utilisateur sélectionne son choix de confidentialité, le ou les choix utilisateur sont enregistrés dans la chaîne de consentement IAB TCF. La chaîne de consentement IAB TCF stocke la combinaison des objectifs et des fournisseurs approuvés, ainsi que d'autres informations de métadonnées (voir la page [IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) pour plus d'informations). Chaque fournisseur enregistré dans l'IAB TCF évalue la chaîne de consentement de l'IAB TCF et décide en fonction des choix de confidentialité des utilisateurs. Gardez à l'esprit que les choix de confidentialité des utilisateurs sont valides pour tous les fournisseurs approuvés.

## Objectifs standard requis par Audience Manager {#aam-standard-purposes}

Audience Manager évalue les choix des utilisateurs stockés dans la chaîne de consentement de l'IAB TFC pour :

* Stockage d'informations et accès (ID 1 dans la liste des fournisseurs [globaux](https://vendorlist.consensu.org/vendorlist.json))
* Personnalisation (ID 2)
* Mesure (ID d'objectif 5)
* Le fournisseur d'Audience Manager consent à stocker, traiter ou activer les données pour un éditeur.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Le comportement d'Audience Manager varie selon que l'utilisateur accorde le consentement {#aam-behavior-consent}

Audience Manager fonctionne différemment selon qu'Audience Manager détecte dans la chaîne de consentement IAB TCF que l'utilisateur a fourni le consentement à trois fins (stockage, personnalisation, mesure) ou non.

| Lorsque votre utilisateur *fournit le consentement*, Audience Manager : | Lorsque votre utilisateur *refuse* le consentement, Audience Manager : |
|---|---|
| <ul><li>exécute tous les cas d'utilisation d'Audience Manager que vous avez demandés.</li><li>Envoie le consentement à des tiers dans les synchronisations de l'ID (en transmettant gdpr = 1 et la chaîne d'autorisation comme gdpr_ permission sur les appels de synchronisation des identifiants).</li><li>Evalue et respecte le consentement transmis à partir des pixels du serveur d'annonces.</li><li>Respecte les synchronisations des identifiants initiés par le partenaire.</li></ul> | <ul><li>Ne stocke aucune donnée utilisateur dans votre instance. Cela inclut les ID de partenaire, les signaux, les caractéristiques ou les données de pixels.</li><li>Ne déclenche pas la synchronisation des identifiants tiers.</li><li>Ne respecte pas les synchronisations d'ID lancées par le partenaire.</li></ul> |



## Cas d'utilisation de l'éditeur {#publisher-use-case}

En implémentant l'IAB TCF, vous n'êtes pas tenu de conserver le code personnalisé pour la gestion des autorisations sur vos propriétés Web via un mécanisme différent avec Adobe ou d'autres fournisseurs tiers. Le cas d'utilisation est décrit dans l'image et dans les étapes ci-dessous. Commence à gauche de l'image :

1. Un utilisateur visite l'une de vos propriétés Web. Tant que vous utilisez les dernières versions des bibliothèques ECID et DIL (voir [Conditions préalables](/help/using/overview/aam-gdpr/aam-iab-plugin.md#prerequisites)), le flux de souscription est déclenché.
2. Audience Manager vérifie si le flux IAB s'applique (`isIabContext=true`). Voir [Recommandations et comment implémenter](/help/using/overview/aam-gdpr/aam-iab-plugin.md#recommendations).
3. Audience Manager vérifie si GDPR s'applique (`gdpr = 1`) et s'il existe un CMP, enregistré avec IAB, sur votre propriété Web. Par exemple, cela s'applique aux utilisateurs qui visitent la région Union européenne. Notez qu'il appartient à l'éditeur de définir l'indicateur GDPR.
4. Si GDPR s'applique, Audience Manager vérifie la chaîne de consentement IAB TCF transmise dans le paramètre `gdpr_consent`pour les autorisations requises. Audience Manager requiert des autorisations pour le stockage, la personnalisation, la mesure et le consentement du fournisseur d'Audience Manager pour stocker, traiter ou activer les données.
5. Si la chaîne de consentement de l'IAB TCF est présente et qu'elle contient les autorisations requises, Audience Manager transmet la chaîne de consentement IAB TCF à nos [serveurs de collecte de données](/help/using/reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager répond en définissant un [cookie demdex](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) dans le navigateur. Audience Manager démarre et respecte également les synchronisations d'identifiants tiers.
7. Sinon, si la chaîne de consentement IAB TCF transmise à l'étape 5 ne contient pas toutes les autorisations nécessaires, Audience Manager ne collecte, ne traite ou n'active pas les données et ne procède pas à la synchronisation des identifiants.

![Cas d'utilisation de l'éditeur](assets/publisher-use-case.png)

## Cas d'utilisation des annonceurs {#advertiser-use-case}

Audience Manager évalue et respecte le consentement transmis dans [les appels](/help/using/integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)en pixels, conformément à l'IAB TCF.

Les pixels sont généralement placés par les clients Audience Manager sur leurs pages partenaires ou sont placés dans des serveurs d'annonces à inclure dans la réponse publicitaire. Dans le premier cas, votre partenaire doit récupérer le paramètre de consentement par programmation et l'ajouter au pixel avant de le déclencher. Dans le second cas, qui est plus fréquent et décrit en détail ci-dessous, les serveurs d'annonces ajoutent les paramètres de consentement qu'ils reçoivent de la plateforme SSP (Supply-Side Platform) ou des serveurs d'annonces de l'éditeur à tous les pixels.

Audience Manager utilise deux paramètres pour transmettre le consentement de l'utilisateur aux appels de pixels :

* `gdpr` peut être 0 (GDPR ne s'applique pas) ou 1 (GDPR s'applique) ;
* `gdpr_consent` est la chaîne de consentement GDPR 64 codées sans URL (voir [spécifications](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Exemple d'appel pour un pixel d'impression, avec les deux paramètres ressemblant à :

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Le cas d'utilisation est décrit dans l'image et dans les étapes ci-dessous. Commence à gauche de l'image :

1. Votre utilisateur reçoit une impression via un serveur d'annonces. Ceci traduit par un appel de pixels à nos serveurs de collecte de données.
1. Audience Manager vérifie si l'indicateur GDPR s'applique. Dans le cas contraire, Audience Manager stocke les données transmises dans les variables de macro dans les appels de pixels.
1. Si la chaîne de consentement est présente et qu'elle contient les autorisations requises, Audience Manager stocke les données transmises dans les variables de macro dans les appels de pixels.
1. Si la chaîne de consentement manque ou ne dispose pas des autorisations requises, Audience Manager abandonne les données transmises dans les variables de macro dans les appels de pixels.

![Cas d'utilisation des annonceurs](assets/advertiser-use-case.png)

## Partenaires activation qui prennent en charge l'IAB TCF {#aam-activation-partners}

Le module externe Audience Manager pour IAB TCF permet de transférer la chaîne de consentement IAB TCF aux partenaires d'activation tout en respectant les choix de confidentialité des utilisateurs. Pour plus d'informations sur les partenaires d'activation prenant en charge l'IAB TCF (précision à compter du 7 juillet 2019), consultez notre **[feuille de partenaire Excel](/help/using/overview/aam-gdpr/assets/AAM-Partners-July2019.xlsx)**.

## Tester votre implémentation IAB {#test-iab-implementation}

Pour tester la mise en œuvre correcte du module Audience Manager pour l'IAB TCF, lisez la case [d'utilisation 4 dans les méthodes de validation pour l'implémentation et l'implémentation IAB](https://marketing.adobe.com/resources/help/en_US/mcvid/testing-optin-and-iab-plugin.html).

## IAB et exclusion dans Audience Manager. Ordre de priorité. {#iab-and-optout}

Une autre option de confidentialité à la disposition des utilisateurs est la possibilité de désactiver toutes les collectes de données. Adobe offre aux utilisateurs les moyens de le faire dans la page [Votre choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité.

Audience Manager traite la gestion d'exclusion dans un [article distinct dans notre documentation](/help/using/overview/data-security-and-privacy/opt-out-management.md).

>[!NOTE]
>
>**Ordre de priorité** : si votre utilisateur choisit de ne pas collecter de données à l'aide d'un outil d'exclusion global, comme décrit dans le lien ci-dessus, il prévaut sur les vérifications de souscription et d'IAB.

## Ressources supplémentaires {#additional-resources}

* [Souscription du service Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe GDPR Transparence et structure de consentement](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Spécifications techniques de la structure de l'IAB Europe GDPR et du cadre de consentement](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Module externe IAB TCF - démonstration vidéo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)