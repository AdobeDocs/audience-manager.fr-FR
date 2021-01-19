---
description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’accord préalable et la prise en charge du Transparency and Consent Framework (TCF) de l’IAB. Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge le TCF de l’IAB et l’implémentation de la prise en charge du TCF de l’IAB dans Audience Manager.
seo-description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’accord préalable et la prise en charge du Transparency and Consent Framework (TCF) de l’IAB. Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge le TCF de l’IAB et l’implémentation de la prise en charge du TCF de l’IAB dans Audience Manager.
seo-title: Module d’Audience Manager pour le TCF de l’IAB
solution: Audience Manager
title: Module d’Audience Manager pour le TCF de l’IAB
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: ab72f0875b132eaf333d1e5308322490ac035de3
workflow-type: tm+mt
source-wordcount: '2449'
ht-degree: 40%

---


# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Présentation

Un aspect important des obligations de confidentialité que vous pouvez avoir envers vos utilisateurs est l&#39;acquisition et la transmission de choix d&#39;utilisateurs sur la façon dont leurs données personnelles peuvent être utilisées (c.-à-d. &quot;fins&quot;) et par qui (c.-à-d. &quot;sociétés&quot;).

Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la [fonctionnalité d’accord préalable](https://docs.adobe.com/content/help/fr-FR/id-service/using/implementation/opt-in-service/optin-overview.html) et la prise en charge du [Transparency and Consent Framework (TCF) de l’IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge le TCF de l’IAB et l’implémentation de la prise en charge du TCF de l’IAB dans Audience Manager.

>[!IMPORTANT]
>
>L&#39;Audience Manager est enregistrée dans le [TCF](https://iabeurope.eu/tcf-for-vendors/) IAB avec l&#39;ID de fournisseur 565.

Le module d’Audience Manager pour le TCF de l’IAB utilise la [fonctionnalité d’accord préalable](https://docs.adobe.com/content/help/fr-FR/id-service/using/implementation/opt-in-service/iab.html), qui fait à son tour partie de la bibliothèque [ Experience Platform Identity Service (ECID)](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html) d’Adobe.

## Portée et limites {#scope-and-limitations}

En tant qu’éditeur ou annonceur travaillant avec Audience Manager, vous pouvez transmettre les choix des utilisateurs à Audience Manager conformément au TCF de l’IAB.

>[!IMPORTANT]
>
>La réglementation du CCI relative au TCF ne s&#39;applique qu&#39;aux visiteurs situés dans l&#39;Espace économique européen.

L&#39;Audience Manager vous aide à respecter les choix de confidentialité de vos utilisateurs et vous permet également de communiquer facilement ces choix à tous les partenaires avec lesquels vous travaillez.

Actuellement, Audience Manager ne prend pas en charge :

* les workflows des appareils mobiles ;
* Approbation imminente des exportations de segments.

## Mise à niveau vers [!DNL IAB TCF v2.0] {#upgrading}

Les clients qui effectuent la mise à niveau de leur implémentation [!DNL Audience Manager Plug-in for IAB TCF] de [!DNL IAB TCF] v1.1 vers [!DNL IAB TCF] v2.0, ou qui activent [!DNL IAB TCF] v2.0 pour la première fois, doivent tous suivre les mêmes instructions sur les conditions préalables et la mise en oeuvre, comme décrit ci-dessous.

## Conditions préalables {#prerequisites}

>[!IMPORTANT]
>
>L’Audience Manager prend en charge IAB TCF v2.0.
>
>La prise en charge d’IAB TCF v1.1 prendra fin le 15 août 2020.
>
> Les clients qui souhaitent continuer à utiliser le module externe d’Audience Manager pour IAB TCF pour la gestion du consentement doivent effectuer la mise à niveau vers la dernière version de [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) pour une prise en charge continue.
>
> Après la mise à niveau vers la dernière version [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases), les chaînes de consentement IAB TCF v1.1 ne seront plus prises en charge. Veillez donc à mettre à jour votre CMP avant de procéder à la mise à niveau vers la dernière version ECID.

Pour utiliser le module externe d’Audience Manager pour IAB TCF avec Audience Manager, vous devez respecter les conditions préalables suivantes :

1. Vous devez utiliser la version 5 ou ultérieure d’Adobe Experience Platform Identity Service (ECID). [Téléchargez](https://github.com/Adobe-Marketing-Cloud/id-service/releases) notre dernière mise à jour d’ECID.
2. Vous devez utiliser l&#39;Audience Manager [!DNL Data Integration Library] (DIL) version 9.0 ou ultérieure, téléchargeable à partir de [ici](https://github.com/Adobe-Marketing-Cloud/dil/releases). Consultez la [documentation d’Audience Manager sur DIL](../../dil/dil-overview.md). Nous vous recommandons d’utiliser [Adobe Launch](https://docs.adobe.com/content/help/fr-FR/launch/using/extensions-ref/adobe-extension/adobe-audience-manager-extension.html) pour la mise en oeuvre DIL la plus simple pour l’Audience Manager.
3. Si vous utilisez [!DNL Server-Side Forwarding] (SSF) pour importer des données dans l’Audience Manager, vous devez également effectuer la mise à niveau vers la dernière version d’AppMeasurement. Téléchargez AppMeasurement à l’aide du [gestionnaire de code d’Analytics](https://docs.adobe.com/content/help/fr-FR/analytics/admin/admin-tools/code-manager-admin.html).
4. Vous devez utiliser une plateforme de gestion du consentement (CMP), commerciale ou la vôtre, qui est intégrée avec IAB TCF v2.0 et est enregistrée avec IAB TCF. Consultez la liste des [CMP enregistrées dans le framework de l’IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Si vous utilisez une plateforme de gestion du consentement (CMP) qui ne prend pas en charge IAB TCF v.2.0, l’Audience Manager envoie automatiquement le paramètre `gdpr=0` dans les synchronisations d’ID, même si vos visiteurs se trouvent dans l’Union européenne. Pour déterminer si votre validation GDPR est principale, nous vous recommandons de confirmer auprès de votre plateforme de gestion du consentement (CMP) qu’elle prend en charge IAB TCF v2.0.

## Recommandations et méthode d’implémentation {#recommendations}

Pour activer la prise en charge du TCF de l’IAB dans Audience Manager, lisez notre documentation sur [la configuration de l’IAB avec accord préalable](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/iab.html).

La méthode la plus simple consiste à utiliser [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) pour ajouter [!DNL ECID Opt-in] à vos propriétés. Lisez la documentation de l’[extension d’accord préalable d’ECID](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) pour apprendre à configurer l’extension Launch.

## Workflow des choix des utilisateurs lors de l’utilisation du framework de l’IAB {#user-choice-workflow}

Lors de la visite d’une propriété web, vos utilisateurs peuvent indiquer leurs choix concernant l’utilisation de leurs données par l’éditeur et par les fournisseurs tiers avec lesquels l’éditeur travaille.

Les utilisateurs fournissent leurs choix sous la forme *consentement* et *intérêt légitime* aux fins de l&#39;IAB à *fournisseurs tiers* enregistrés dans la liste fournisseur globale.

L’image ci-dessous représente un exemple de dialogue de CMP, présenté au nouveau visiteur d’un site web. Gardez à l’esprit que ce dialogue peut avoir un aspect très différent, en fonction de l’implémentation des clients.

![Dialogue de CMP](assets/cmp-example.png)

Les détails sur les différents objectifs et autorisations inclus dans IAB TCF v2.0 sont traités dans les [Politiques du cadre de transparence et de consentement d&#39;IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Les utilisateurs peuvent accorder leur consentement ou des intérêts légitimes (s&#39;ils sont disponibles) à une combinaison d&#39;objectifs et de fournisseurs. Par exemple, les utilisateurs pourraient accorder leur consentement pour stocker des informations sur un appareil, développer et améliorer des produits, et accorder leur consentement à tous les fournisseurs tiers affichés par le CMP.

Ou, dans un autre exemple, ils pourraient accorder leur consentement ou des intérêts légitimes à toutes fins, mais seulement accorder le consentement ou des intérêts légitimes à quelques-uns des fournisseurs affichés par le CMP.

Une fois que l’utilisateur sélectionne ses choix de confidentialité, les choix d’utilisateur sont enregistrés dans la chaîne TC IAB. La chaîne CCI de l&#39;IAB stocke la combinaison d&#39;objectifs et de fournisseurs approuvés, ainsi que d&#39;autres informations de métadonnées (voir la [page IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) pour plus d&#39;informations).

Chaque fournisseur enregistré dans le TCF de l’IAB évalue la chaîne TC de l’IAB et prend des décisions en fonction des choix de confidentialité des utilisateurs. N’oubliez pas que les choix de confidentialité des utilisateurs sont valides pour tous les fournisseurs enregistrés auprès d’IAB TCF.

## Objectifs requis par l&#39;Audience Manager {#aam-standard-purposes}

L&#39;Audience Manager évalue les choix des utilisateurs stockés dans la chaîne TC de l&#39;IAB aux fins suivantes, définies dans les [Stratégies de cadre de transparence et de consentement d&#39;IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes). De plus, vous pouvez également trouver les objectifs dans la [liste fournisseur globale](https://vendorlist.consensu.org/vendorlist.json).

* **Objectif 1** : Stocker et/ou accéder aux informations sur un appareil ;
* **But 10** : Développer et améliorer les produits ;
* **But spécial 1** : Assurer la sécurité, prévenir les fraudes et déboguer.

>[!IMPORTANT]
>
>L&#39;Audience Manager a besoin du consentement pour l&#39;objectif 1 et l&#39;objectif 10, plus le consentement du fournisseur, pour déployer des cookies et initier ou honorer la synchronisation des identifiants.
>
>Conformément aux [règlements du CCI](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), l&#39;objectif spécial 1 (assurer la sécurité, prévenir la fraude et déboguer) est toujours accepté et les utilisateurs ne peuvent s&#39;y opposer.

## Le comportement d’Audience Manager dépend de l’attribution ou non du consentement de l’utilisateur {#aam-behavior-consent}

L&#39;Audience Manager fonctionne différemment selon que la chaîne de CT IAB inclut le consentement de l&#39;utilisateur aux deux fins (stocker et/ou accéder à l&#39;information sur un appareil, et développer et améliorer les produits) ou non.

Nous vérifions également le consentement de l’utilisateur pour toutes les destinations que vous utilisez en Audience Manager, tant que ces destinations sont enregistrées auprès d’IAB TCF.

| Lorsque votre utilisateur *donne son consentement*, Audience Manager : | Lorsque votre utilisateur *refuse de donner* son consentement, Audience Manager : |
|---|---|
| <ul><li>met en œuvre tous les cas d’utilisation d’Audience Manager que vous avez demandés ;</li><li>Transmet le consentement à des tiers dans les synchronisations d’identifiants (en transmettant `gdpr = 1` et la chaîne de consentement sous la forme `gdpr_consent` dans les appels de synchronisation d’identifiants).</li><li>évalue et honore le consentement transmis à partir des pixels du serveur de publicités ;</li><li>honore les synchronisations des identifiants initiées par les partenaires.</li></ul> | <ul><li>ne stocke aucune nouvelle donnée utilisateur dans votre instance. Cela inclut les identifiants des partenaires, les signaux, les caractéristiques ou les données de pixel ;</li><li>n’initie pas les synchronisations des identifiants tiers ;</li><li>n’honore pas les synchronisations des identifiants initiées par les partenaires.</li><li>Permet d’exclure l’utilisateur de la collecte de données ultérieure.</li></ul> |

## Cas d’utilisation des éditeurs {#publisher-use-case}

En implémentant le module d’Audience Manager pour le TCF d’IAB, vous n’êtes pas tenu de conserver un code personnalisé pour la gestion du consentement sur vos propriétés Web par le biais d’un mécanisme différent avec un Adobe ou d’autres fournisseurs tiers. Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Commencez à gauche de l’image :

1. Un utilisateur visite l’une de vos propriétés web. Tant que vous utilisez les dernières versions des bibliothèques ECID et DIL (voir [Conditions préalables](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), le flux d’accord préalable est déclenché.
2. Audience Manager vérifie si le flux de l’IAB s’applique (`isIabContext=true`). Voir [Recommandations et méthode d’implémentation](aam-iab-plugin.md#recommendations).
3. L’Audience Manager vérifie si GDPR s’applique (`gdpr = 1`) et s’il existe un CMP, enregistré auprès d’IAB TCF, sur votre propriété Web. Par exemple, cela s’appliquerait aux utilisateurs qui visitent l’Union européenne. Notez qu&#39;il vous incombe, en tant qu&#39;éditeur, de définir l&#39;indicateur GDPR.
4. Si le RGPD s&#39;applique, l&#39;Audience Manager vérifie la chaîne TC de l&#39;IAB, transmise dans le paramètre `gdpr_consent`, pour obtenir le consentement requis. L&#39;Audience Manager a besoin du consentement pour stocker et/ou accéder à des informations sur un périphérique ([objet TCF IAB 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), pour développer et améliorer des produits ([objet TCF IAB 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), plus le consentement du fournisseur de l&#39;Audience Manager pour stocker, traiter ou activer des données.
5. Si la chaîne CCI de l&#39;IAB est présente et contient le consentement requis, l&#39;Audience Manager transmet la chaîne TC de l&#39;IAB à nos [serveurs de collecte de données](../../reference/system-components/components-data-collection.md) (DCS).
6. L’Audience Manager répond en définissant un [cookie demdex](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-am.html) sur le navigateur et initie et honore la synchronisation des identifiants tiers.
7. Sinon, si la chaîne TC IAB transmise à l’étape 4 ne contient pas toutes les autorisations nécessaires, l’Audience Manager ne collecte, ne traite ou n’active aucune donnée utilisateur et n’honore ni ne déclenche aucune synchronisation des identifiants. De plus, il exclut l’utilisateur des destinations avec lesquelles vous travaillez.

>[!IMPORTANT]
>
>Si vous travaillez avec des partenaires de destination d’Audience Manager qui nécessitent des paramètres TCF IAB, mais que vous n’avez pas de CMP prenant en charge le TCF IAB sur votre site Web, l’Audience Manager envoie `gdpr=0` dans les synchronisations d’ID. Cela signifie que le RGPD ne s&#39;applique pas à ces utilisateurs.
>
> Si cela n’est pas souhaité, vous devez activer la fonctionnalité TCF de l’IAB en Audience Manager pour envoyer les chaînes TC appropriées de l’IAB aux partenaires de destination.



![Cas d’utilisation des éditeurs](assets/publisher-use-case.png)

## Cas d’utilisation des annonceurs {#advertiser-use-case}

Audience Manager évalue et honore le consentement transmis dans les [appels de pixel](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), conformément au TCF de l’IAB.

Les pixels peuvent être placés par les clients de l’Audience Manager sur les pages de leurs partenaires ou placés sur des serveurs d’annonces pour les inclure dans la réponse publicitaire. Dans le premier cas, votre partenaire doit récupérer le paramètre de consentement par programmation et l’ajouter au pixel avant le déclenchement. Dans le second cas, plus courant et décrit en détail ci-dessous, les serveurs de publicités ajoutent les paramètres de consentement qu’ils reçoivent de la plateforme SSP (Supply Side Platform) ou des serveurs de publicités des éditeurs à tous les pixels.

Audience Manager utilise deux paramètres pour transmettre le consentement de l’utilisateur dans les appels de pixel :

* `gdpr` peut correspondre à 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique).
* `gdpr_consent` correspond à la chaîne de consentement RGPD codée en base 64 et sécurisée par URL (voir [spécification](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Un exemple d’appel pour un pixel d’impression avec les deux paramètres pourrait ressembler à ce qui suit :

```
http://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Commencez à gauche de l’image :

1. Une impression est diffusée à votre utilisateur via un serveur de publicités. Cela se traduit par un appel [pixel](../../integration/media-data-integration/impression-data-pixels.md) à nos serveurs de collecte de données (DCS).
2. Audience Manager vérifie si l’indicateur du RGPD s’applique. Dans le cas contraire, l’Audience Manager stocke les données transmises dans les variables `gdpr` et `gdpr_consent` dans des appels de pixels.
3. Si la chaîne CCI IAB est présente et contient les autorisations requises, l’Audience Manager stocke les données transmises dans les variables `gdpr` et `gdpr_consent` dans des appels en pixels.
4. Si la chaîne TC IAB est manquante ou ne dispose pas des autorisations requises, l’Audience Manager supprime les données transmises dans les variables `gdpr` et `gdpr_consent` dans les appels en pixels.

![Cas d’utilisation des annonceurs](assets/advertiser-use-case.png)

## Partenaires d’activation qui prennent en charge le TCF de l’IAB {#aam-activation-partners}

Le module externe Audience Manager pour IAB TCF vous permet de transférer la chaîne CI IAB aux partenaires d’activation tout en respectant les choix de confidentialité des utilisateurs. Pour savoir quels partenaires d’activation prennent en charge le TCF de l’IAB, consultez notre [liste de destinations basées sur les appareils](/help/using/features/destinations/device-based-destinations-list.md).

## Approbation du consentement aux URL envoyées aux destinations URL

L’intégration des Audiences Manager à l’IAB TCF v2.0 prend en charge l’ajout du consentement aux informations envoyées à [destinations URL](../../features/destinations/create-url-destination.md) qui sont intégrées à l’IAB TCF v2.0. Cependant, ce processus n’est pas effectué automatiquement par Audience Manager, afin d’éviter de rompre des formats d’URL spécifiques.

Les clients qui souhaitent ajouter le consentement aux données envoyées à [!DNL URL destinations] doivent ajouter manuellement les macros `${GDPR}` et `${GDPR_CONSENT_XXXX}` à leur format d&#39;URL, en remplaçant `XXXX` par l&#39;identifiant du partenaire de destination.

Exemple: `http://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Voir [Macros de destination définies](../../features/destinations/destination-macros.md) pour plus d&#39;informations sur les macros de destination prises en charge.

## Gestion du consentement entre plusieurs périphériques

Le module Audience Manager Plug-in pour IAB TCF désactive automatiquement les identifiants présents sur une requête, lorsque les visiteurs de votre site ne fournissent pas les autorisations appropriées. Si la requête contient un [identifiant de plusieurs périphériques (ID de gestion de la relation client)](../../reference/ids-in-aam.md), l’Audience Manager choisit cet identifiant, ainsi que le dernier périphérique associé à cet [identifiant de plusieurs périphériques (ID de gestion de la relation client)](../../reference/ids-in-aam.md).

## Test de votre implémentation de l’IAB {#test-iab-implementation}

Pour vérifier que vous avez correctement mis en oeuvre le module d’Audience Manager pour le TCF IAB, consultez [Cas d’utilisation 4 dans la validation du service d’inclusion](https://docs.adobe.com/content/help/fr-FR/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB et exclusion dans Audience Manager. Ordre de priorité. {#iab-and-optout}

Vos utilisateurs ont également la possibilité de ne pas participer aux collectes de données. Pour ce faire, Adobe met à la disposition des utilisateurs les moyens nécessaires dans la page [Vos choix en matière de confidentialité](https://www.adobe.com/fr/privacy/opt-out.html#customeruse).

Audience Manager traite les demandes d’exclusion dans un [article distinct de notre documentation](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Les utilisateurs qui sont désactivés de toute collecte de données après avoir refusé leur consentement ne peuvent pas être réactivés.

>[!NOTE]
>
>**Ordre de priorité** : si votre utilisateur choisit de ne pas participer à la collecte de données à l’aide d’un outil d’exclusion global, comme décrit dans le lien ci-dessus, ce choix est prioritaire par rapport aux vérifications d’accord préalable et de l’IAB.

## Ressources supplémentaires {#additional-resources}

* [Accord préalable d’Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html)
* [RGPD Transparency and Consent Framework de l’IAB Europe](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Caractéristiques techniques du RGPD Transparency and Consent Framework de l’IAB Europe](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Module du TCF de l’IAB : vidéo de démonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)