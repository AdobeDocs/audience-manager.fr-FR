---
description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-title: Module externe Audience Manager pour IAB TCF
solution: Audience Manager
title: Module externe Audience Manager pour IAB TCF
translation-type: tm+mt
source-git-commit: 5fff9315558d3088f68268f32681842bb8d5e7d3

---


# Module externe Audience Manager pour IAB TCF {#aam-iab-plugin}

## Aperçu

Un aspect important des obligations de confidentialité que vous avez envers vos utilisateurs réside dans l’acquisition et le respect des choix des utilisateurs quant à la façon dont leurs données personnelles sont utilisées (c’est-à-dire les « objectifs ») et quant aux entités qui les utilisent (les « entreprises »).

Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la [fonctionnalité d’adhésion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) et la prise en charge d’[IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager. Audience Manager est enregistré dans le TCF IAB avec l’ID de fournisseur 565.

Le module externe Audience Manager pour IAB TCF utilise la fonctionnalité [d’](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)inclusion, qui fait à son tour partie de la bibliothèque Adobe [Adobe Experience Platform Identity Service (ECID)](https://docs.adobe.com/content/help/en/id-service/using/home.html) .

## Portée et limites {#scope-and-limitations}

En tant qu’éditeur ou annonceur travaillant avec Audience Manager, vous pouvez transmettre les choix des utilisateurs à Audience Manager conformément à la norme TCF de l’IAB. Vous disposez ainsi d’un moyen simple et cohérent de communiquer les choix des utilisateurs à tous les partenaires avec lesquels vous travaillez et Audience Manager peut vous aider à respecter les choix de confidentialité de vos utilisateurs.

Le soutien du CCI au titre du TCF décrit dans le présent article représente la première phase du soutien planifié du gestionnaire des Audiences au cadre du CCI. Actuellement, Audience Manager ne prend pas en charge :

* workflows de dispositifs portables ;
* la gestion du consentement entre les différents dispositifs ;
* Approbation imminente du consentement aux URL envoyées aux destinations [](../../features/destinations/create-url-destination.md)URL ;
* Approbation imminente des segments.

## Conditions préalables {#prerequisites}

Pour utiliser le TCF IAB avec Audience Manager, vous devez respecter les conditions préalables suivantes :

1. Vous devez utiliser Adobe Experience Platform Identity Service (ECID) version 4.1 ou ultérieure. [Téléchargez](https://github.com/Adobe-Marketing-Cloud/id-service/releases) notre dernière version d&#39;ECID.
1. Vous devez utiliser la bibliothèque d’intégration des données d’Audience Manager version 9.0 ou ultérieure, téléchargeable [ici](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lisez la documentation [sur](../..//dil/dil-overview.md)DIL dans Audience Manager.
1. Si vous utilisez le transfert côté serveur pour importer des données dans Audience Manager, vous devez effectuer la mise à niveau vers la dernière version d’AppMeasurement. Téléchargez AppMeasurement à l’aide du Gestionnaire [de code](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)Analytics.
1. Vous devez utiliser une plateforme de gestion du consentement (CMP), commerciale ou la vôtre, qui prend en charge le TCF de l’IAB et qui est enregistrée auprès du TCF de l’IAB. Voir la liste des [CMP enregistrées dans le cadre](https://iabeurope.eu/cmp-list/)du CCI.

## Recommandations et comment mettre en oeuvre {#recommendations}

Pour activer la prise en charge du TCF IAB dans Audience Manager, lisez notre documentation sur [la configuration d’IAB avec l’inclusion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

Pour ce faire, il est plus facile d’utiliser le lancement [d’](https://docs.adobelaunch.com/) Adobe Experience Platform pour activer l’option ECID sur vos propriétés. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Processus de choix d’utilisateur lors de l’utilisation de la structure IAB {#user-choice-workflow}

Lors de la visite d’une propriété Web, vos utilisateurs peuvent indiquer comment leurs données doivent être utilisées par l’éditeur et par les fournisseurs tiers avec lesquels l’éditeur travaille. Les utilisateurs fournissent leurs choix sous la forme d’objectifs *et d’autorisations* standard aux fournisseurs ** tiers enregistrés dans la liste de fournisseurs globale. L&#39;image ci-dessous représente un exemple de dialogue CMP, présenté à un nouveau visiteur d&#39;un site Web. N’oubliez pas que ce dialogue peut avoir un aspect très différent, en fonction de l’implémentation des clients.

![Dialogue de la CMP](assets/cmp.png)

Les objectifs standard du cadre du CCI sont les suivants :

* enregistrement d&#39;informations et accès
* Personnalisation
* Sélection, diffusion et rapports des publicités
* Sélection du contenu, diffusion et rapports
* vidéo

Consultez la page [des spécifications de la structure](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) IAB pour une description des cinq objectifs standard.

Les utilisateurs peuvent accorder leur consentement à une combinaison d&#39;objectifs normalisés et de fournisseurs. Par exemple, les utilisateurs peuvent accorder leur consentement pour l’enregistrement, la personnalisation et la mesure et accorder leur consentement à tous les fournisseurs tiers affichés par le CMP. Ou, dans un autre exemple, ils pourraient accorder leur consentement pour les cinq buts standard, mais seulement accorder le consentement à quelques-uns des fournisseurs affichés par le CMP.

Une fois que l’utilisateur sélectionne ses choix de confidentialité, les choix d’utilisateur sont enregistrés dans la chaîne de consentement TCF IAB. La chaîne de consentement TCF de l’IAB stocke la combinaison d’objectifs et de fournisseurs approuvés, ainsi que d’autres informations de métadonnées (voir la page [de l’](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) IAB pour plus d’informations). Chaque fournisseur enregistré dans le TCF de l’IAB évalue la chaîne de consentement du TCF de l’IAB et prend des décisions en fonction des choix de confidentialité des utilisateurs. Gardez à l’esprit que les choix de confidentialité des utilisateurs sont valides pour tous les fournisseurs approuvés.

## Objectifs standard requis par Audience Manager {#aam-standard-purposes}

Audience Manager évalue les choix des utilisateurs stockés dans la chaîne de consentement TCF IAB pour :

* enregistrement d&#39;informations et accès (ID d&#39;objectif 1 dans la liste [](https://vendorlist.consensu.org/vendorlist.json)globale du fournisseur)
* Personnalisation (ID d’objectif 2)
* Mesure (ID d&#39;objectif 5)
* Le fournisseur d’Audience Manager consent à stocker, traiter ou activer des données pour un éditeur.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

## Le comportement du Gestionnaire d&#39;Audiences dépend du fait que l&#39;utilisateur autorise ou non le consentement {#aam-behavior-consent}

Audience Manager fonctionne différemment selon que Audience Manager détecte dans la chaîne de consentement TCF IAB que l’utilisateur a donné son consentement pour les trois buts (enregistrement, personnalisation, mesure) ou non.

| Lorsque votre utilisateur *donne son consentement*, Audience Manager : | Lorsque votre utilisateur *refuse* le consentement, Audience Manager : |
|---|---|
| <ul><li>exécute tous les cas d’utilisation d’Audience Manager que vous avez demandés.</li><li>Envoie le consentement à des tiers dans les synchronisations d’identifiants (en transmettant gdpr = 1 et la chaîne de consentement sous la forme gdpr_consentement lors des appels de synchronisation d’identifiants).</li><li>Evalue et honore le consentement transmis à partir des pixels du serveur d’annonces.</li><li>Fait honneur aux synchronisations d’identifiants initiées par le partenaire.</li></ul> | <ul><li>Ne stocke aucune nouvelle donnée utilisateur dans votre instance. Cela inclut les identifiants de partenaire, les signaux, les caractéristiques ou les données de pixels.</li><li>Ne déclenche pas la synchronisation des identifiants tiers.</li><li>N’accepte pas les synchronisations d’identifiants initiées par le partenaire.</li></ul> |

## Cas d’utilisation de l’éditeur {#publisher-use-case}

En implémentant le TCF d’IAB, vous n’êtes pas tenu de conserver un code personnalisé pour la gestion du consentement sur vos propriétés Web par le biais d’un mécanisme différent avec Adobe ou d’autres fournisseurs tiers. Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Début à gauche de l&#39;image :

1. Un utilisateur visite l’une de vos propriétés Web. Tant que vous utilisez les dernières versions des bibliothèques ECID et DIL (voir [Conditions préalables](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), le flux d’inclusion est déclenché.
2. Audience Manager vérifie si le flux IAB s’applique (`isIabContext=true`). Voir [Recommandations et comment mettre en oeuvre](aam-iab-plugin.md#recommendations).
3. Audience Manager vérifie si GDPR s’applique (`gdpr = 1`) et s’il existe un CMP, enregistré auprès d’IAB, sur votre propriété Web. Par exemple, cela s’appliquerait aux utilisateurs qui visitent la région de l’Union européenne. Notez qu&#39;il vous incombe, en tant qu&#39;éditeur, de définir l&#39;indicateur GDPR.
4. Si GDPR s’applique, Audience Manager vérifie la chaîne de consentement TCF de l’IAB, transmise dans le paramètre `gdpr_consent`, pour connaître les autorisations nécessaires. Audience Manager a besoin d’autorisations pour l’enregistrement, la personnalisation, la mesure et le consentement du fournisseur Audience Manager pour stocker, traiter ou activer des données.
5. Si la chaîne de consentement TCF IAB est présente et contient les autorisations requises, Audience Manager transmet la chaîne de consentement TCF IAB à nos serveurs [de collecte de](../../reference/system-components/components-data-collection.md) données (DCS).
6. Audience Manager répond en définissant un cookie [](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) demdex sur le navigateur. Audience Manager initie et honore également les synchronisations d’identifiants tiers.
7. Sinon, si la chaîne de consentement TCF de l’IAB transmise à l’étape 5 ne contient pas toutes les autorisations nécessaires, Audience Manager ne collecte, ne traite pas ou n’active pas les données et n’honore pas ni ne déclenche les synchronisations d’ID.

![Cas d’utilisation de l’éditeur](assets/publisher-use-case.png)

## Cas d’utilisation de publicitaire {#advertiser-use-case}

Audience Manager évalue et honore le consentement transmis dans les appels [de](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)pixels, conformément au TCF de l’IAB.

Les pixels sont généralement placés par les clients d’Audience Manager sur les pages de leurs partenaires ou sont placés sur les serveurs d’annonces pour être inclus dans la réponse publicitaire. Dans le premier cas, votre partenaire doit récupérer par programme le paramètre de consentement et l’ajouter au pixel avant de se déclencher. Dans le second cas, qui est plus courant et est décrit en détail ci-dessous, les serveurs d’annonces ajoutent à tous les pixels les paramètres de consentement qu’ils reçoivent de la plate-forme d’approvisionnement côté (SSP) ou des serveurs d’annonces d’éditeur.

Audience Manager utilise deux paramètres pour transmettre le consentement de l’utilisateur dans les appels de pixels :

* `gdpr` peut être 0 (RGPD ne s&#39;applique pas) ou 1 (RGPD s&#39;applique);
* `gdpr_consent` est la chaîne de consentement GDPR codée en base 64 et compatible avec les URL (voir [spécification](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Un exemple d’appel pour un pixel d’impression, avec les deux paramètres, peut se présenter comme suit :

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Début à gauche de l&#39;image :

1. Votre utilisateur reçoit une impression via un serveur d’annonces. Cela se traduit par un appel pixel à nos serveurs de collecte de données (DCS).
2. Audience Manager vérifie si l’indicateur GDPR s’applique. Dans le cas contraire, Audience Manager stocke les données transmises dans des variables de macro dans des appels en pixels.
3. Si la chaîne de consentement est présente et contient les autorisations requises, Audience Manager stocke les données transmises dans les variables de macro dans des appels de pixels.
4. Si la chaîne de consentement est manquante ou ne dispose pas des autorisations requises, Audience Manager supprime les données transmises dans les variables de macro dans les appels de pixels.

![Cas d’utilisation de publicitaire](assets/advertiser-use-case.png)

## Partenaires Activations qui prennent en charge le TCF IAB {#aam-activation-partners}

Le module externe Audience Manager pour IAB TCF vous permet de transférer la chaîne de consentement IAB TCF aux partenaires d’activation tout en respectant les choix de confidentialité des utilisateurs. Pour savoir quels partenaires d&#39;activation prennent en charge le TCF IAB, consultez notre [liste de destinations](/help/using/features/destinations/device-based-destinations-list.md)basées sur les dispositifs.

## Test de votre mise en oeuvre IAB {#test-iab-implementation}

Pour vérifier que vous avez correctement mis en oeuvre le module Audience Manager pour le TCF IAB, consultez la section [Cas d’utilisation 4 dans Méthodes de validation pour l’inclusion et l’implémentation](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)IAB.

## IAB et exclusion dans Audience Manager. Ordre de priorité. {#iab-and-optout}

Une autre option de confidentialité à la disposition de vos utilisateurs est la possibilité de opt-out de toute collecte de données. Adobe fournit aux utilisateurs les moyens de le faire dans la page [Vos choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité.

Audience Manager traite les demandes d’exclusion dans un article [distinct de notre documentation](data-privacy-requests.md).

>[!NOTE]
>
>**Ordre de priorité** : si votre utilisateur choisit de ne pas participer à la collecte de données à l’aide d’un outil d’exclusion global, comme décrit dans le lien ci-dessus, cette priorité est accordée aux vérifications d’inclusion et d’IAB.

## Ressources supplémentaires {#additional-resources}

* [Adobe Experience Platform Identity Service - Ouverture de session](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Cadre de transparence et de consentement de l&#39;IAB Europe GDPR](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Cadre de transparence et de consentement IAB Europe GDPR Spécifications techniques](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Module externe IAB TCF - démonstration vidéo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)