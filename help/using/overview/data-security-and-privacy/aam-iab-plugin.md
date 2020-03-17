---
description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-title: Module externe Audience Manager pour IAB TCF
solution: Audience Manager
title: Module externe Audience Manager pour IAB TCF
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Module externe Audience Manager pour IAB TCF {#aam-iab-plugin}

## Aperçu

Un aspect important des obligations de confidentialité que vous avez envers vos utilisateurs réside dans l’acquisition et le respect des choix des utilisateurs quant à la façon dont leurs données personnelles sont utilisées (c’est-à-dire les « objectifs ») et quant aux entités qui les utilisent (les « entreprises »).

Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la [fonctionnalité d’adhésion](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html) et la prise en charge d’[IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.  Gestionnaire de est enregistré dans le TCF IAB avec l’ID de fournisseur 565.

Le module  Gestionnaire de  de pour IAB TCF utilise la fonctionnalité [d’inclusion, qui fait partie à son tour de la bibliothèque Adobe](https://marketing.adobe.com/resources/help/en_US/mcvid/iab.html)Adobe Experience Platform Identity Service (ECID) [](https://marketing.adobe.com/resources/help/en_US/mcvid/) .

## Portée et limites {#scope-and-limitations}

En tant qu’éditeur ou annonceur travaillant avec  Gestionnaire de  de, vous pouvez transmettre les choix des utilisateurs au Gestionnaire de de la  selon les directives TCF de l’IAB. Vous disposez ainsi d’une manière simple et cohérente de communiquer les choix des utilisateurs à tous les partenaires avec lesquels vous travaillez et  Gestionnaire de  de peut vous aider à respecter les choix de confidentialité de vos utilisateurs.

L&#39;appui du CCI au TCF décrit dans le présent article représente la première phase de l&#39;appui planifié du directeur de   pour le cadre du CCI.  Gestionnaire de  de ne prend actuellement pas en charge :

*  des périphériques mobiles ;
* la gestion du consentement inter-dispositifs;
* Approbation du consentement aux URL envoyées vers les destinations [](../../features/destinations/create-url-destination.md)URL ;
* Approbation en attente des segments.

## Conditions préalables {#prerequisites}

Vous devez respecter les conditions préalables suivantes pour utiliser le TCF IAB avec  Gestionnaire de  :

1. Vous devez utiliser Adobe Experience Platform Identity Service (ECID) version 4.1 ou ultérieure. [Téléchargez](https://github.com/Adobe-Marketing-Cloud/id-service/releases) notre dernière version d&#39;ECID.
1. Vous devez utiliser  bibliothèque d’intégration des données (DIL) de Manager version 9.0 ou ultérieure, téléchargeable [ici](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lisez la documentation [DIL dans la documentation](../..//dil/dil-overview.md)  Manager.
1. Si vous utilisez le transfert côté serveur (SSF) pour importer des données dans  Gestionnaire de  de, vous devez effectuer la mise à niveau vers la dernière version d’AppMeasurement. Téléchargez AppMeasurement à l’aide du Gestionnaire [de code](https://marketing.adobe.com/resources/help/en_US/reference/code_manager_admin.html)Analytics.
1. Vous devez utiliser une plateforme de gestion du consentement (CMP), commerciale ou la vôtre, qui prend en charge le TCF IAB et est enregistrée auprès du TCF IAB. Voir le  des [CMP enregistrées dans le cadre](https://advertisingconsent.eu/cmp-list/)du CCI.

## Recommandations et mise en oeuvre {#recommendations}

Pour activer la prise en charge TCF du CCI dans  Gestionnaire de  de, lisez notre documentation sur la [configuration d’IAB avec l’inclusion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

Pour ce faire, utilisez [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) pour instrumenter l’inclusion ECID sur vos propriétés. Read the documentation for the [ECID Opt-in extension](https://docs.adobelaunch.com/extension-reference/web/experience-cloud-id-service-extension#opt-in) to learn how to set up the Launch extension.

## Processus de choix de l’utilisateur lors de l’utilisation de la structure IAB {#user-choice-workflow}

Lors de la visite d’une propriété Web, vos utilisateurs peuvent indiquer comment leurs données doivent être utilisées par l’éditeur et par les fournisseurs tiers avec lesquels l’éditeur travaille. Les utilisateurs fournissent leurs choix sous la forme d’objectifs *et d’autorisations* standard aux fournisseurs ** tiers enregistrés dans le fournisseur global. L&#39;image ci-dessous représente un exemple de dialogue CMP, affiché pour un premier d&#39;un site Web. Gardez à l’esprit que ce dialogue peut sembler très différent, en fonction de l’implémentation des clients.

![Dialogue de la CMP](assets/cmp.png)

Les objectifs normalisés du CCI sont les suivants :

*  d&#39;informations  et accès
* Personnalisation
* Sélection des publicités,  et  de
* Sélection du contenu,  et 
* vidéo

Consultez la page [des spécifications de la structure](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#purposes-features) IAB pour obtenir une description des cinq objectifs de la norme.

Les utilisateurs peuvent accorder leur consentement à une combinaison d&#39;objectifs normalisés et de fournisseurs. Par exemple, les utilisateurs peuvent accorder leur consentement pour  , la personnalisation et la mesure et accorder leur consentement à tous les fournisseurs tiers affichés par le CMP. Ou, dans un autre exemple, ils pourraient accorder leur consentement aux cinq fins habituelles, mais seulement à quelques-uns des fournisseurs affichés par le CMP.

Une fois que l’utilisateur sélectionne ses choix de confidentialité, les choix de l’utilisateur sont enregistrés dans la chaîne de consentement TCF IAB. La chaîne de consentement TCF IAB stocke la combinaison des objectifs approuvés et des fournisseurs, ainsi que d’autres informations de métadonnées (voir la page [](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md#Consent-string-and-vendor-list-format) IAB pour plus d’informations). Chaque fournisseur inscrit au CCI TCF évalue la chaîne de consentement du CCI et prend des décisions en fonction des choix de confidentialité des utilisateurs. Gardez à l’esprit que les choix de confidentialité des utilisateurs sont valides pour tous les fournisseurs approuvés.

## Objectifs standard requis par  Gestionnaire {#aam-standard-purposes}

 Gestionnaire  des évalue les choix des utilisateurs stockés dans la chaîne de consentement TFC IAB pour :

* Informations   et accès (ID d&#39;objectif 1 dans le [global de fournisseurs](https://vendorlist.consensu.org/vendorlist.json))
* Personnalisation (ID d’objectif 2)
* Mesure (ID objectif 5)
*  fournisseur du Gestionnaire de  de consent à stocker, traiter ou activer des données pour un éditeur.

>[!IMPORTANT]
>
>Audience Manager needs consent for *all three purposes, plus vendor consent* in order to deploy cookies and initiate or honor ID syncs.

##  comportement de  Manager dépend du fait que l&#39;utilisateur accorde son consentement {#aam-behavior-consent}

 Gestionnaire de  de fonctionne différemment selon que le Gestionnaire de  détecte dans la chaîne de consentement TCF IAB que l’utilisateur a donné son consentement pour les trois buts (le, la personnalisation, la mesure) ou non.

| Lorsque votre utilisateur *donne son consentement*,  Gestionnaire de  de : | Lorsque votre utilisateur *refuse* le consentement,  Gestionnaire de  de : |
|---|---|
| <ul><li>Effectue tous les cas d’utilisation   Manager que vous avez demandés.</li><li>Envoie le consentement à des tiers lors de la synchronisation des identifiants (en transmettant gdpr = 1 et la chaîne de consentement sous la forme gdpr_consentement lors des appels de synchronisation des identifiants).</li><li>Evalue et honore le consentement transmis à partir des pixels du serveur d’annonces.</li><li>Honore les synchronisations d’ID initiées par le partenaire.</li></ul> | <ul><li>Ne stocke aucune nouvelle donnée utilisateur dans votre instance. Cela inclut les identifiants des partenaires, les signaux, les caractéristiques ou les données de pixels.</li><li>Ne déclenche pas la synchronisation des identifiants tiers.</li><li>N’accepte pas les synchronisations d’ID initiées par le partenaire.</li></ul> |

## Cas d’utilisation de l’éditeur {#publisher-use-case}

En implémentant le TCF IAB, vous n’êtes pas tenu de gérer le code personnalisé pour la gestion du consentement sur vos propriétés Web par le biais d’un mécanisme différent avec Adobe ou d’autres fournisseurs tiers. Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous.  à gauche de l’image :

1. Un utilisateur visite l’une de vos propriétés Web. Tant que vous utilisez les dernières versions des bibliothèques ECID et DIL (voir [Conditions préalables](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), le flux d’inclusion est déclenché.
2.  Gestionnaire  de vérifie si le flux IAB s’applique (`isIabContext=true`). Voir [Recommandations et comment mettre en oeuvre](aam-iab-plugin.md#recommendations).
3.  Gestionnaire de  vérifie si le RDMD s’applique (`gdpr = 1`) et s’il existe un CMP, enregistré auprès d’IAB, sur votre propriété Web. Par exemple, cela s’appliquerait aux utilisateurs qui visitent la région  de la  européenne. Notez qu’il est de votre responsabilité en tant qu’éditeur de définir l’indicateur GDPR.
4. Si GDPR s’applique,  Gestionnaire  vérifie la chaîne de consentement TCF IAB, transmise dans le paramètre `gdpr_consent`, pour connaître les autorisations nécessaires.  Gestionnaire de  de a besoin d’autorisations pour , la personnalisation, la mesure, plus le consentement du fournisseur du Gestionnaire de, pour stocker, traiter ou activer les données.
5. Si la chaîne de consentement TCF IAB est présente et qu’elle contient les autorisations requises,  Gestionnaire de  transmet la chaîne de consentement TCF IAB à nos serveurs [de collecte de](../../reference/system-components/components-data-collection.md) données (DCS).
6.  Gestionnaire  de répond en définissant un cookie [](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) demdex sur le navigateur.  Gestionnaire de initie et honore également les synchronisations d’identifiants tiers.
7. Si la chaîne de consentement TCF IAB transmise à l’étape 5 ne contient pas toutes les autorisations requises,  Gestionnaire de  de ne collecte, ne traite pas ou n’active pas les données et n’honore ni ne déclenche les synchronisations d’ID.

![Cas d’utilisation de l’éditeur](assets/publisher-use-case.png)

## Cas d’utilisation d’annonceurs {#advertiser-use-case}

 Gestionnaire de  évalue et honore le consentement transmis dans les appels [de](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)pixels, conformément au TCF IAB.

Les pixels sont généralement placés par  clients du Gestionnaire de  de sur leurs pages de partenaires ou sont placés sur des serveurs d’annonces pour être inclus dans la réponse de la publicité. Dans le premier cas, votre partenaire doit, par programmation, récupérer le paramètre de consentement et l’ajouter au pixel avant le déclenchement. Dans le second cas, qui est plus fréquent et est décrit en détail ci-dessous, les serveurs d’annonces ajoutent à tous les pixels les paramètres de consentement qu’ils reçoivent de la plateforme côté approvisionnement (SSP) ou des serveurs d’annonces d’éditeurs.

 Gestionnaire de  de utilise deux paramètres pour transmettre le consentement de l’utilisateur dans les appels de pixels :

* `gdpr` peut être 0 (le RGMD ne s&#39;applique pas) ou 1 (le RGMD s&#39;applique);
* `gdpr_consent` est la chaîne de consentement du RDDC codée en base 64 et compatible avec les URL (voir [spécification](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications)). Un exemple d’appel pour un pixel d’impression, avec les deux paramètres, peut ressembler à ce qui suit :

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous.  à gauche de l’image :

1. Une impression est transmise à l’utilisateur par l’intermédiaire d’un serveur d’annonces. Cela se traduit par un appel au pixel vers nos serveurs de collecte de données (DCS).
2.  Gestionnaire de  vérifie si l’indicateur GDPR s’applique. Si ce n’est pas le cas,  Gestionnaire de  de stocke les données transmises dans des variables de macro dans des appels en pixels.
3. Si la chaîne de consentement est présente et qu’elle contient les autorisations requises,  Gestionnaire de  de stocke les données transmises dans les variables de macro dans des appels de pixels.
4. Si la chaîne de consentement est manquante ou si elle ne dispose pas des autorisations requises,  Gestionnaire de  supprime les données transmises dans les variables de macro dans les appels de pixels.

![Cas d’utilisation d’annonceurs](assets/advertiser-use-case.png)

##  partenaires  qui prennent en charge le TCF IAB {#aam-activation-partners}

Le module  Gestionnaire de  pour IAB TCF vous permet de transmettre la chaîne de consentement IAB TCF aux partenaires tout en respectant les choix de confidentialité des utilisateurs. Pour plus d&#39;informations sur  partenaires  de l&#39;IAB TCF, reportez-vous à notre [](/help/using/features/destinations/device-based-destinations-list.md)de destinationsbasées sur un dispositif.

## Test de l’implémentation IAB {#test-iab-implementation}

Pour vérifier que vous avez correctement mis en oeuvre le module  Gestionnaire  de pour le TCF IAB, reportez-vous à la section Cas d’ [utilisation 4 des Méthodes de validation pour l’inclusion et l’implémentation](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)IAB.

## IAB et exclusion dans  Gestionnaire de  de. Ordre de priorité. {#iab-and-optout}

Une autre option de confidentialité à la disposition de vos utilisateurs est la possibilité de opt-out de toute collecte de données. Adobe fournit aux utilisateurs les moyens de le faire dans la page [Vos choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité.

 Gestionnaire de  de traite les demandes d’exclusion dans un article [distinct de notre documentation](data-privacy-requests.md).

>[!NOTE]
>
>**Ordre de priorité** : si votre utilisateur choisit de ne pas participer à la collecte de données à l’aide d’un outil d’exclusion global, comme décrit dans le lien ci-dessus, cette priorité est accordée aux vérifications d’inclusion et d’IAB.

## Ressources supplémentaires {#additional-resources}

* [Adobe Experience Platform Identity Service - Ouverture de session](https://marketing.adobe.com/resources/help/en_US/mcvid/overview.html)
* [IAB Europe Cadre de transparence et de consentement du GDPR](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [IAB Europe GDPR Transparence et cadre de consentement Spécifications techniques](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Module externe IAB TCF - démonstration vidéo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)