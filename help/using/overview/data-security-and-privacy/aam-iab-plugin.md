---
description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’adhésion et la prise en charge d’IAB Transparency and Consent Framework (TCF). Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.
seo-title: Module externe Audience Manager pour IAB TCF
solution: Audience Manager
title: Module externe Audience Manager pour IAB TCF
translation-type: tm+mt
source-git-commit: b5c56453a7278573dec2b80be7baa9833a847a4a
workflow-type: tm+mt
source-wordcount: '2432'
ht-degree: 7%

---


# Module externe Audience Manager pour IAB TCF {#aam-iab-plugin}

## Aperçu

Un aspect important des obligations de confidentialité que vous pouvez avoir envers vos utilisateurs est l&#39;acquisition et la transmission de choix d&#39;utilisateurs sur la façon dont leurs données personnelles peuvent être utilisées (c.-à-d. &quot;fins&quot;) et par qui (c.-à-d. &quot;sociétés&quot;).

Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la [fonctionnalité d’adhésion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) et la prise en charge d’[IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge IAB TCF et l’implémentation de la prise en charge d’IAB TCF dans Audience Manager.

>[!IMPORTANT]
>
>Audience Manager est enregistré dans le TCF [](https://iabeurope.eu/tcf-for-vendors/) IAB avec l’ID de fournisseur 565.

Le module externe Audience Manager pour IAB TCF utilise la fonctionnalité [d’](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html)inclusion, qui fait, à son tour, partie de la bibliothèque ECID ( [Adobe Experience Platform Identity Service)](https://docs.adobe.com/content/help/en/id-service/using/home.html) .

## Portée et limites {#scope-and-limitations}

En tant qu’éditeur ou annonceur travaillant avec Audience Manager, vous pouvez transmettre les choix des utilisateurs à Audience Manager conformément à la norme TCF de l’IAB.

>[!IMPORTANT]
>
>La réglementation du CCI relative au TCF ne s&#39;applique qu&#39;aux visiteurs situés dans l&#39;Espace économique européen.

Audience Manager vous aide à respecter les choix de confidentialité de vos utilisateurs et vous permet également de communiquer facilement ces choix à tous les partenaires avec lesquels vous travaillez.

Actuellement, Audience Manager ne prend pas en charge :

* workflows de dispositifs portables ;
* Approbation imminente des exportations de segments.

## Conditions préalables {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager prend en charge IAB TCF v2.0.
>
>La prise en charge d’IAB TCF v1.1 prendra fin le 15 août 2020.
>
> Les clients qui souhaitent continuer à utiliser le module Audience Manager pour le TCF d’IAB pour la gestion du consentement doivent effectuer la mise à niveau vers la dernière version d’ [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) pour une prise en charge continue.
>
> Après la mise à niveau vers la dernière version [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) , les chaînes de consentement IAB TCF v1.1 ne seront plus prises en charge. Veillez donc à mettre à jour votre CMP avant la mise à niveau vers la dernière version ECID.

Pour utiliser le module Audience Manager pour le TCF IAB avec Audience Manager, vous devez respecter les conditions préalables suivantes :

1. Vous devez utiliser Adobe Experience Platform Identity Service (ECID) version 5 ou ultérieure. [Téléchargez](https://github.com/Adobe-Marketing-Cloud/id-service/releases) notre dernière version d&#39;ECID.
2. Vous devez utiliser la bibliothèque d’intégration des données d’Audience Manager version 9.0 ou ultérieure, téléchargeable [ici](https://github.com/Adobe-Marketing-Cloud/dil/releases). Lisez la documentation [sur](../..//dil/dil-overview.md)DIL dans Audience Manager. Nous vous recommandons d’utiliser [Adobe Launch](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) pour la mise en oeuvre DIL la plus simple pour Audience Manager.
3. Si vous utilisez le transfert côté serveur pour importer des données dans Audience Manager, vous devez effectuer la mise à niveau vers la dernière version d’AppMeasurement. Téléchargez AppMeasurement à l’aide du Gestionnaire [de code](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html)Analytics.
4. Vous devez utiliser une plateforme de gestion du consentement (CMP), commerciale ou la vôtre, qui est intégrée avec IAB TCF v2.0 et est enregistrée avec IAB TCF. Voir la liste des [CMP enregistrées dans le cadre](https://iabeurope.eu/cmp-list/)du CCI.

>[!WARNING]
>
>Si vous utilisez une plateforme de gestion du consentement (CMP) qui ne prend pas en charge IAB TCF v.2.0, Audience Manager enverra automatiquement le `gdpr=0` paramètre dans les synchronisations d’ID, même si vos visiteurs se trouvent dans l’Union européenne. Pour déterminer si votre validation GDPR est active, nous vous recommandons de confirmer auprès de votre plateforme de gestion du consentement (CMP) qu’elle prend en charge IAB TCF v2.0.

## Recommandations et comment mettre en oeuvre {#recommendations}

Pour activer la prise en charge du TCF IAB dans Audience Manager, lisez notre documentation sur [la configuration d’IAB avec l’inclusion](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

La méthode la plus simple pour y parvenir consiste à utiliser le lancement [de la plateforme](https://docs.adobe.com/content/help/en/launch/using/overview.html) Adobe Experience Platform pour ajouter une inclusion ECID à vos propriétés. Read the documentation for the [ECID Opt-in extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) to learn how to set up the Launch extension.

## Processus de choix d’utilisateur lors de l’utilisation de la structure IAB {#user-choice-workflow}

Lors de la visite d’une propriété Web, vos utilisateurs peuvent indiquer comment leurs données doivent être utilisées par l’éditeur et par les fournisseurs tiers avec lesquels l’éditeur travaille.

Les utilisateurs fournissent leurs choix sous la forme d&#39;un *consentement* et d&#39;intérêts ** légitimes aux fins de l&#39;IAB à des fournisseurs ** tiers enregistrés dans la liste globale des fournisseurs.

L&#39;image ci-dessous représente un exemple de dialogue CMP, présenté à un nouveau visiteur d&#39;un site Web. N’oubliez pas que ce dialogue peut avoir un aspect très différent, en fonction de l’implémentation des clients.

![Dialogue de la CMP](assets/cmp-example.png)

Les détails sur les différents objectifs et autorisations inclus dans IAB TCF v2.0 sont traités dans les politiques [du cadre de transparence et de consentement d’](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)IAB Europe.

Les utilisateurs peuvent accorder leur consentement ou des intérêts légitimes (s&#39;ils sont disponibles) à une combinaison d&#39;objectifs et de fournisseurs. Par exemple, les utilisateurs pourraient accorder leur consentement pour stocker des informations sur un appareil, développer et améliorer des produits, et accorder leur consentement à tous les fournisseurs tiers affichés par le CMP.

Ou, dans un autre exemple, ils pourraient accorder leur consentement ou des intérêts légitimes à toutes fins, mais seulement accorder le consentement ou des intérêts légitimes à quelques-uns des fournisseurs affichés par le CMP.

Une fois que l’utilisateur sélectionne ses choix de confidentialité, les choix d’utilisateur sont enregistrés dans la chaîne TC IAB. La chaîne TC de l’IAB stocke la combinaison d’objectifs et de fournisseurs approuvés, ainsi que d’autres informations de métadonnées (voir la page [de l’](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) IAB pour plus d’informations).

Chaque fournisseur enregistré dans le TCF de l’IAB évalue la chaîne TC de l’IAB et prend des décisions en fonction des choix de confidentialité des utilisateurs. N’oubliez pas que les choix de confidentialité des utilisateurs sont valides pour tous les fournisseurs enregistrés auprès d’IAB TCF.

## Objectifs requis par le gestionnaire d’Audiences {#aam-standard-purposes}

Audience Manager évalue les choix des utilisateurs stockés dans la chaîne TC de l’IAB aux fins suivantes, définies dans les stratégies [de transparence et de consentement d’](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)IAB Europe. En outre, vous pouvez également trouver les objectifs dans la liste [](https://vendorlist.consensu.org/vendorlist.json)globale des fournisseurs.

* **Objectif 1**: Stocker et/ou accéder aux informations sur un appareil ;
* **But 10**: Développer et améliorer les produits ;
* **But spécial 1**: Assurer la sécurité, prévenir les fraudes et déboguer.

>[!IMPORTANT]
>
>Le gestionnaire des Audiences doit obtenir le consentement pour les fins 1 et 10, plus le consentement du fournisseur, afin de déployer des cookies et de lancer ou d’honorer la synchronisation des identifiants.
>
>Conformément aux règlements [du](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_)CCI, la fonction spéciale 1 (assurer la sécurité, prévenir la fraude et déboguer) est toujours acceptée et les utilisateurs ne peuvent s&#39;y opposer.

## Le comportement du Gestionnaire d&#39;Audiences dépend du fait que l&#39;utilisateur autorise ou non le consentement {#aam-behavior-consent}

Audience Manager fonctionne différemment selon que la chaîne TC d’IAB inclut ou non le consentement de l’utilisateur pour les deux buts (stocker et/ou accéder aux informations sur un périphérique et développer et améliorer des produits).

Nous vérifions également le consentement de l’utilisateur pour toutes les destinations avec lesquelles vous travaillez dans Audience Manager, tant que ces destinations sont enregistrées auprès d’IAB TCF.

| Lorsque votre utilisateur *donne son consentement*, Audience Manager : | Lorsque votre utilisateur *refuse* le consentement, Audience Manager : |
|---|---|
| <ul><li>exécute tous les cas d’utilisation d’Audience Manager que vous avez demandés.</li><li>Envoie le consentement à des tiers lors de la synchronisation des identifiants (en transmettant `gdpr = 1` et la chaîne de consentement comme `gdpr_consent` lors des appels de synchronisation des identifiants).</li><li>Evalue et honore le consentement transmis à partir des pixels du serveur d’annonces.</li><li>Fait honneur aux synchronisations d’identifiants initiées par le partenaire.</li></ul> | <ul><li>Ne stocke aucune nouvelle donnée utilisateur dans votre instance. Cela inclut les identifiants de partenaire, les signaux, les caractéristiques ou les données de pixels.</li><li>Ne déclenche pas la synchronisation des identifiants tiers.</li><li>N’accepte pas les synchronisations d’identifiants initiées par le partenaire.</li><li>Permet d’exclure l’utilisateur de la collecte de données ultérieure.</li></ul> |

## Cas d’utilisation de l’éditeur {#publisher-use-case}

En implémentant le module externe Audience Manager pour IAB TCF, vous n’êtes pas tenu de conserver un code personnalisé pour la gestion du consentement sur vos propriétés Web par le biais d’un mécanisme différent avec Adobe ou d’autres fournisseurs tiers. Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Début à gauche de l&#39;image :

1. Un utilisateur visite l’une de vos propriétés Web. Tant que vous utilisez les dernières versions des bibliothèques ECID et DIL (voir [Conditions préalables](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), le flux d’inclusion est déclenché.
2. Audience Manager vérifie si le flux IAB s’applique (`isIabContext=true`). Voir [Recommandations et comment mettre en oeuvre](aam-iab-plugin.md#recommendations).
3. Audience Manager vérifie si GDPR s’applique (`gdpr = 1`) et s’il existe un CMP, enregistré auprès d’IAB TCF, sur votre propriété Web. Par exemple, cela s’appliquerait aux utilisateurs qui visitent l’Union européenne. Notez qu&#39;il vous incombe, en tant qu&#39;éditeur, de définir l&#39;indicateur GDPR.
4. Si le RGMD s’applique, Audience Manager vérifie la chaîne TC de l’IAB, transmise dans le `gdpr_consent` paramètre, pour obtenir le consentement requis. Audience Manager a besoin du consentement pour stocker et/ou accéder à l&#39;information sur un appareil ([IAB TCF objectif 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), pour développer et améliorer des produits ([IAB TCF objectif 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), plus le consentement du fournisseur Audience Manager pour stocker, traiter ou activer des données.
5. Si la chaîne CCI IAB est présente et contient le consentement requis, Audience Manager la transmet à nos serveurs [de collecte de](../../reference/system-components/components-data-collection.md) données (DCS).
6. Audience Manager répond en définissant un cookie [](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) demdex sur le navigateur et initie et honore la synchronisation des identifiants tiers.
7. Sinon, si la chaîne TC IAB transmise à l’étape 4 ne contient pas toutes les autorisations nécessaires, Audience Manager ne collecte, ne traite pas ou n’active aucune donnée utilisateur et n’honore ni ne déclenche aucune synchronisation des identifiants. De plus, il exclut l’utilisateur des destinations avec lesquelles vous travaillez.

>[!IMPORTANT]
>
>Si vous travaillez avec des partenaires de destination d’Audience Manager qui nécessitent des paramètres TCF IAB, mais que vous n’avez pas de CMP qui prenne en charge le TCF IAB sur votre site Web, Audience Manager envoie `gdpr=0` des synchronisations d’ID. Cela signifie que le RGPD ne s&#39;applique pas à ces utilisateurs.
>
> Si cela n’est pas souhaité, vous devez activer la fonctionnalité TCF de l’IAB dans Audience Manager pour envoyer les chaînes TC appropriées de l’IAB aux partenaires de destination.



![Cas d’utilisation de l’éditeur](assets/publisher-use-case.png)

## Cas d’utilisation de publicitaire {#advertiser-use-case}

Audience Manager évalue et honore le consentement transmis dans les appels [de](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md)pixels, conformément au TCF de l’IAB.

Les pixels peuvent être placés par les clients d’Audience Manager sur les pages de leurs partenaires ou être placés sur des serveurs d’annonces pour les inclure dans la réponse publicitaire. Dans le premier cas, votre partenaire doit récupérer par programme le paramètre de consentement et l’ajouter au pixel avant de se déclencher. Dans le second cas, qui est plus courant et est décrit en détail ci-dessous, les serveurs d’annonces ajoutent à tous les pixels les paramètres de consentement qu’ils reçoivent de la plateforme d’approvisionnement côté (SSP) ou des serveurs d’annonces d’éditeurs.

Audience Manager utilise deux paramètres pour transmettre le consentement de l’utilisateur dans les appels de pixels :

* `gdpr` peut être 0 (RGPD ne s&#39;applique pas) ou 1 (RGPD s&#39;applique);
* `gdpr_consent` est la chaîne de consentement GDPR codée en base 64 et compatible avec les URL (voir [spécification](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Un exemple d’appel pour un pixel d’impression, avec les deux paramètres, peut se présenter comme suit :

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Début à gauche de l&#39;image :

1. Votre utilisateur reçoit une impression via un serveur d’annonces. Cela se traduit par un appel [](../../integration/media-data-integration/impression-data-pixels.md) pixel vers nos serveurs de collecte de données (DCS).
2. Audience Manager vérifie si l’indicateur GDPR s’applique. Dans le cas contraire, Audience Manager stocke les données transmises dans les variables `gdpr` et `gdpr_consent` dans des appels en pixels.
3. Si la chaîne CCI IAB est présente et contient les autorisations requises, Audience Manager stocke les données transmises dans les variables `gdpr` et `gdpr_consent` dans les appels en pixels.
4. Si la chaîne CCI IAB est manquante ou ne dispose pas des autorisations requises, Audience Manager supprime les données transmises dans les variables `gdpr` et `gdpr_consent` dans les appels en pixels.

![Cas d’utilisation de publicitaire](assets/advertiser-use-case.png)

## Partenaires Activations qui prennent en charge le TCF IAB {#aam-activation-partners}

Le module externe Audience Manager pour IAB TCF vous permet de transférer la chaîne CI IAB aux partenaires d’activation tout en respectant les choix de confidentialité des utilisateurs. Pour savoir quels partenaires d&#39;activation prennent en charge le TCF IAB, consultez notre [liste de destinations](/help/using/features/destinations/device-based-destinations-list.md)basées sur les dispositifs.

## Approbation du consentement aux URL envoyées aux destinations URL

L’intégration d’Audience Manager à IAB TCF v2.0 prend en charge l’ajout de consentement aux informations envoyées aux destinations [d’](../../features/destinations/create-url-destination.md) URL qui sont intégrées à IAB TCF v2.0. Toutefois, ce processus n’est pas effectué automatiquement par Audience Manager, afin d’éviter de rompre certains formats d’URL spécifiques.

Les clients qui souhaitent ajouter le consentement aux données envoyées vers les destinations URL doivent ajouter manuellement les `${GDPR}` et `${GDPR_CONSENT_XXXX}` les macros à leur format d’URL, en les remplaçant `XXXX` par l’identifiant du partenaire de destination.

Exemple: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Voir Définition [des macros de](../../features/destinations/destination-macros.md) destination pour plus d’informations sur les macros de destination prises en charge.

## Gestion du consentement entre plusieurs périphériques

Le module Audience Manager pour le TCF IAB désactive automatiquement les ID présents sur une demande, lorsque les visiteurs de votre site ne fournissent pas les autorisations appropriées. Si la requête contient un ID de gestion de la relation client (CRM ID) [](../../reference/ids-in-aam.md)entre plusieurs périphériques, Audience Manager désactive l’ID, ainsi que le dernier périphérique associé à cet ID de gestion de la relation client (CRM ID) [](../../reference/ids-in-aam.md)entre les périphériques.

## Test de votre mise en oeuvre IAB {#test-iab-implementation}

Pour vérifier que vous avez correctement mis en oeuvre le module externe Audience Manager pour le TCF IAB, consultez le cas d’ [utilisation 4 dans la validation du service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88)d’inclusion.

## IAB et exclusion dans Audience Manager. Ordre de priorité. {#iab-and-optout}

Une autre option de confidentialité à la disposition de vos utilisateurs est la possibilité de opt-out de toute collecte de données. Adobe fournit aux utilisateurs les moyens de le faire dans la page [Vos choix](https://www.adobe.com/privacy/opt-out.html#customeruse) de confidentialité.

Audience Manager traite les demandes d’exclusion dans un article [distinct de notre documentation](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Les utilisateurs qui sont désactivés de toute collecte de données après avoir refusé leur consentement ne peuvent pas être réactivés.

>[!NOTE]
>
>**Ordre de priorité** : si votre utilisateur choisit de ne pas participer à la collecte de données à l’aide d’un outil d’exclusion global, comme décrit dans le lien ci-dessus, cette priorité est accordée aux vérifications d’inclusion et d’IAB.

## Ressources supplémentaires {#additional-resources}

* [Inscription au service d’identité de la plateforme d’expérience Adobe](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [Cadre de transparence et de consentement de l&#39;IAB Europe GDPR](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Cadre de transparence et de consentement IAB Europe GDPR Spécifications techniques](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Module externe IAB TCF - démonstration vidéo](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)