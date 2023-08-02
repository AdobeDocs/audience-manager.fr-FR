---
description: Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la fonctionnalité d’accord préalable et la prise en charge du Transparency and Consent Framework (TCF) de l’IAB. Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge le TCF de l’IAB et l’implémentation de la prise en charge du TCF de l’IAB dans Audience Manager.
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: Module d’Audience Manager pour le TCF de l’IAB
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: 8b370a64d80b40124abee91351cbef09711243d4
workflow-type: tm+mt
source-wordcount: '2353'
ht-degree: 35%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Présentation

Un aspect important des obligations de confidentialité que vous pouvez avoir à l’égard de vos utilisateurs est l’acquisition et la transmission des choix des utilisateurs concernant la manière dont leurs données personnelles peuvent être utilisées (c’est-à-dire, &quot;finalités&quot;) et par qui (c’est-à-dire, &quot;sociétés&quot;).

Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la [fonctionnalité d’accord préalable](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) et la prise en charge du [Transparency and Consent Framework (TCF) de l’IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge le TCF de l’IAB et l’implémentation de la prise en charge du TCF de l’IAB dans Audience Manager.

>[!IMPORTANT]
>
>L’Audience Manager est enregistrée dans la variable [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) avec l’identifiant du fournisseur 565.

Le module d’Audience Manager pour le TCF de l’IAB utilise la [fonctionnalité d’accord préalable](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html), qui fait à son tour partie de la bibliothèque [ Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html) d’Adobe.

## Portée et limites {#scope-and-limitations}

En tant qu’éditeur ou annonceur travaillant avec Audience Manager, vous pouvez transmettre les choix des utilisateurs à Audience Manager conformément au TCF de l’IAB.

>[!IMPORTANT]
>
>Les réglementations du TCF de l’IAB s’appliquent uniquement aux visiteurs situés dans l’Espace économique européen.

L’Audience Manager vous aide à respecter les choix de confidentialité de vos utilisateurs et vous permet également de communiquer facilement ces choix à tous les partenaires avec lesquels vous travaillez.

Actuellement, Audience Manager ne prend pas en charge :

* les workflows des appareils mobiles ;
* Ajout du consentement aux exportations de segments.

## Mise à niveau vers [!DNL IAB TCF v2.2] {#upgrading}

Clients qui mettent à niveau leur [!DNL Audience Manager Plug-in for IAB TCF] implémentation depuis [!DNL IAB TCF] v1.1 à [!DNL IAB TCF] v2.2 ou activation [!DNL IAB TCF] v2.2 pour la première fois, doit tous suivre les mêmes directives sur les conditions préalables et la mise en oeuvre, comme décrit ci-dessous.

## Conditions préalables {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager prend en charge IAB TCF v2.2.
>
>La prise en charge du TCF 1.1 de l’IAB prendra fin le 15 août 2020.
>
> Les clients qui souhaitent continuer à utiliser le module d’Audience Manager pour le TCF de l’IAB pour la gestion du consentement doivent effectuer une mise à niveau vers la dernière version de [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) pour un soutien continu.
>
> Après la mise à niveau vers la dernière version [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) Les chaînes de consentement IAB TCF v1.1 ne seront plus prises en charge. Veillez donc à mettre à jour votre CMP avant d’effectuer la mise à niveau vers la dernière version d’ECID.

Pour utiliser avec Audience Manager le module externe d’Audience Manager pour IAB TCF, vous devez respecter les conditions préalables suivantes :

1. Vous devez utiliser la version 5 ou ultérieure d’Adobe Experience Platform Identity Service (ECID). [Téléchargez](https://github.com/Adobe-Marketing-Cloud/id-service/releases) notre dernière mise à jour d’ECID.
2. Vous devez utiliser Audience Manager [!DNL Data Integration Library] (DIL) version 9.0 ou ultérieure, téléchargeable depuis [here](https://github.com/Adobe-Marketing-Cloud/dil/releases). Consultez la [documentation d’Audience Manager sur DIL](../../dil/dil-overview.md). Il est recommandé d’utiliser la variable [Extension de balise Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html) pour la mise en oeuvre DIL la plus simple de l’Audience Manager.
3. Si vous utilisez [!DNL Server-Side Forwarding] (SSF) pour importer des données dans Audience Manager, vous devez effectuer une mise à niveau vers la dernière version d’AppMeasurement. Téléchargez AppMeasurement à l’aide du [gestionnaire de code d’Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).
4. Vous devez utiliser une plateforme de gestion du consentement (CMP), commerciale ou personnelle, qui est intégrée à IAB TCF v2.2 et qui est enregistrée auprès du TCF de l’IAB. Consultez la liste des [CMP enregistrées dans le framework de l’IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Si vous utilisez une plateforme de gestion du consentement (CMP) qui ne prend pas en charge IAB TCF v2.2, l’Audience Manager envoie automatiquement la variable `gdpr=0` dans les synchronisations des identifiants, même si vos visiteurs se trouvent dans l’Union européenne. Pour déterminer si la validation du RGPD est principale, nous vous recommandons de confirmer auprès de votre plateforme de gestion du consentement (CMP) qu’elle prend en charge IAB TCF v2.2.

## Recommandations et méthode d’implémentation {#recommendations}

Pour activer la prise en charge du TCF de l’IAB dans Audience Manager, lisez notre documentation sur [la configuration de l’IAB avec accord préalable](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html).

Pour ce faire, la méthode la plus simple consiste à utiliser [Balises Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) ajouter [!DNL ECID Opt-in] sur vos propriétés. Lisez la documentation de la section [Extension Opt-in ECID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html) pour savoir comment configurer l’extension Balises.

## Workflow des choix des utilisateurs lors de l’utilisation du framework de l’IAB {#user-choice-workflow}

Lors de la visite d’une propriété web, vos utilisateurs peuvent indiquer leurs choix concernant l’utilisation de leurs données par l’éditeur et par les fournisseurs tiers avec lesquels l’éditeur travaille.

Les utilisateurs fournissent leurs choix sous la forme *consentement* aux fins de l’IAB : *fournisseurs tiers* enregistré dans la liste globale des fournisseurs.

L’image ci-dessous représente un exemple de dialogue de CMP, présenté au nouveau visiteur d’un site web. Gardez à l’esprit que ce dialogue peut avoir un aspect très différent, en fonction de l’implémentation des clients.

![Dialogue de CMP](assets/cmp-example.png)

Vous trouverez des informations détaillées sur les différents objectifs et autorisations inclus dans IAB TCF v2.2 dans la section [Stratégies du framework de transparence et de consentement IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Les utilisateurs peuvent accorder leur consentement pour une combinaison d’objectifs et de fournisseurs. Par exemple, les utilisateurs peuvent accorder leur consentement pour stocker des informations sur un appareil, développer et améliorer des produits, et accorder leur consentement à tous les fournisseurs tiers affichés par la CMP.

Ou, dans un autre exemple, ils peuvent accorder leur consentement à tous les usages, mais uniquement à quelques-uns des fournisseurs affichés par la CMP.

Une fois que l’utilisateur sélectionne ses choix de confidentialité, le ou les choix de l’utilisateur sont enregistrés dans la chaîne IAB TC. La chaîne IAB TC stocke la combinaison d’objectifs et de fournisseurs approuvés, ainsi que d’autres informations de métadonnées (voir [page IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) pour plus d’informations).

Chaque fournisseur enregistré dans le TCF de l’IAB évalue la chaîne du TC de l’IAB et prend des décisions en fonction des choix de confidentialité des utilisateurs. Gardez à l’esprit que les choix de confidentialité des utilisateurs sont valides pour tous les fournisseurs enregistrés auprès du TCF de l’IAB.

## Objectifs requis par l’Audience Manager {#aam-standard-purposes}

Audience Manager évalue les choix des utilisateurs stockés dans la chaîne IAB TC aux fins suivantes, définis dans la variable [Stratégies du framework de transparence et de consentement IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Objectif 1**: stocker et/ou accéder aux informations sur un appareil ;
* **Objectif 10**: développer et améliorer les produits ;
* **Objectif spécial 1**: garantissez la sécurité, évitez la fraude et déboguez.

>[!IMPORTANT]
>
>L’Audience Manager nécessite un consentement pour les points 1 et 10, ainsi que le consentement du fournisseur, afin de déployer des cookies et lancer ou honorer les synchronisations des identifiants.
>
>Par [Règlements de l’IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), Objectif spécial 1 (assurer la sécurité, prévenir la fraude et déboguer) est toujours accepté et les utilisateurs ne peuvent pas s’y opposer.

## Le comportement d’Audience Manager dépend de l’attribution ou non du consentement de l’utilisateur {#aam-behavior-consent}

L’Audience Manager fonctionne différemment selon que la chaîne IAB TC inclut ou non le consentement de l’utilisateur aux deux fins (stocker et/ou accéder aux informations sur un appareil, et développer et améliorer des produits).

Nous vérifions également le consentement de l’utilisateur pour toutes les destinations que vous utilisez en Audience Manager, à condition que ces destinations soient enregistrées auprès du TCF de l’IAB.

| Lorsque votre utilisateur *donne son consentement*, Audience Manager : | Lorsque votre utilisateur *refuse de donner* son consentement, Audience Manager : |
|---|---|
| <ul><li>met en œuvre tous les cas d’utilisation d’Audience Manager que vous avez demandés ;</li><li>Transmet le consentement aux tiers dans les synchronisations des identifiants (en transmettant `gdpr = 1` et la chaîne de consentement en tant que `gdpr_consent` lors des appels de synchronisation des identifiants).</li><li>évalue et honore le consentement transmis à partir des pixels du serveur de publicités ;</li><li>honore les synchronisations des identifiants initiées par les partenaires.</li></ul> | <ul><li>ne stocke aucune nouvelle donnée utilisateur dans votre instance. Cela inclut les identifiants des partenaires, les signaux, les caractéristiques ou les données de pixel ;</li><li>n’initie pas les synchronisations des identifiants tiers ;</li><li>n’honore pas les synchronisations des identifiants initiées par les partenaires.</li><li>Exclut l’utilisateur de la collecte de données ultérieure.</li></ul> |

## Cas d’utilisation des éditeurs {#publisher-use-case}

En mettant en oeuvre le module d’Audience Manager pour IAB TCF, vous n’êtes pas tenu de conserver un code personnalisé pour la gestion du consentement sur vos propriétés web via un mécanisme différent avec des Adobes ou d’autres fournisseurs tiers. Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Commencez à gauche de l’image :

1. Un utilisateur visite l’une de vos propriétés web. Tant que vous utilisez les dernières versions des bibliothèques ECID et DIL (voir [Conditions préalables](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), le flux d’accord préalable est déclenché.
2. Audience Manager vérifie si le flux de l’IAB s’applique (`isIabContext=true`). Voir [Recommandations et méthode d’implémentation](aam-iab-plugin.md#recommendations).
3. L’Audience Manager vérifie si le RGPD s’applique (`gdpr = 1`) et s’il existe une CMP, enregistrée auprès du TCF de l’IAB, sur votre propriété web. Cela s’applique, par exemple, aux visiteurs provenant de l’Union européenne. Notez qu’il vous incombe, en tant qu’éditeur, de définir l’indicateur du RGPD.
4. Si le RGPD s’applique, l’Audience Manager vérifie la chaîne IAB TC, transmise dans `gdpr_consent` pour le consentement requis. Audience Manager nécessite un consentement pour le stockage et/ou l’accès aux informations sur un appareil ([Objectif 1 du TCF de l’IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), développement et amélioration des produits ([Objectif 10 du TCF de l’IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), plus le consentement du fournisseur d’Audience Manager pour stocker, traiter ou activer des données.
5. Si la chaîne IAB TC est présente et contient le consentement requis, l’Audience Manager la transmet à notre [serveurs de collecte de données](../../reference/system-components/components-data-collection.md) (DCS).
6. L’Audience Manager répond en définissant une [cookie demdex](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html) sur le navigateur et initie et honore les synchronisations des identifiants tiers.
7. Si la chaîne du TC de l’IAB transmise à l’étape 4 ne contient pas toutes les autorisations nécessaires, l’Audience Manager ne collecte, ne traite ou n’active aucune donnée utilisateur et n’honore ni n’initie de synchronisation des identifiants. En outre, il exclut l’utilisateur des destinations avec lesquelles vous travaillez.

>[!IMPORTANT]
>
>Si vous travaillez avec des partenaires de destination d’Audience Manager qui ont besoin de paramètres IAB TCF, mais que vous n’avez pas de CMP prenant en charge IAB TCF sur votre site web, alors l’Audience Manager envoie `gdpr=0` dans les synchronisations des identifiants. Cela signifie que le RGPD ne s’applique pas à ces utilisateurs.
>
> Si cela n’est pas souhaité, vous devez activer la fonctionnalité IAB TCF en Audience Manager pour envoyer les chaînes IAB TC appropriées aux partenaires de destination.



![Cas d’utilisation des éditeurs](assets/publisher-use-case.png)

## Cas d’utilisation des annonceurs {#advertiser-use-case}

Audience Manager évalue et honore le consentement transmis dans les [appels de pixel](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), conformément au TCF de l’IAB.

Les clients d’Audience Manager peuvent placer des pixels sur les pages de leurs partenaires ou sur les serveurs de publicités pour les inclure dans la réponse publicitaire. Dans le premier cas, votre partenaire doit récupérer le paramètre de consentement par programmation et l’ajouter au pixel avant le déclenchement. Dans le second cas, plus courant et décrit en détail ci-dessous, les serveurs de publicités ajoutent les paramètres de consentement qu’ils reçoivent de la plateforme SSP (Supply Side Platform) ou des serveurs de publicités des éditeurs à tous les pixels.

Audience Manager utilise deux paramètres pour transmettre le consentement de l’utilisateur dans les appels de pixel :

* `gdpr` peut correspondre à 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique).
* `gdpr_consent` correspond à la chaîne de consentement RGPD codée en base 64 et sécurisée par URL (voir [spécification](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Un exemple d’appel pour un pixel d’impression avec les deux paramètres pourrait ressembler à ce qui suit :

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Commencez à gauche de l’image :

1. Une impression est diffusée à votre utilisateur via un serveur de publicités. Cela se traduit par une [appel de pixel](../../integration/media-data-integration/impression-data-pixels.md) à nos serveurs de collecte de données (DCS).
2. Audience Manager vérifie si l’indicateur du RGPD s’applique. Dans le cas contraire, l’Audience Manager stocke les données transmises dans la variable `gdpr` et `gdpr_consent` dans les appels de pixel.
3. Si la chaîne IAB TC est présente et contient les autorisations requises, l’Audience Manager stocke les données transmises dans la variable `gdpr` et `gdpr_consent` dans les appels de pixel.
4. Si la chaîne IAB TC est manquante ou ne dispose pas des autorisations requises, l’Audience Manager supprime les données transmises dans la variable `gdpr` et `gdpr_consent` dans les appels de pixel.

![Cas d’utilisation des annonceurs](assets/advertiser-use-case.png)

## Partenaires d’activation qui prennent en charge le TCF de l’IAB {#aam-activation-partners}

Le plug-in d’Audience Manager pour IAB TCF vous permet de transférer la chaîne IAB TC aux partenaires d’activation tout en respectant les choix de confidentialité des utilisateurs. Pour savoir quels partenaires d’activation prennent en charge le TCF de l’IAB, consultez notre [liste de destinations basées sur les appareils](/help/using/features/destinations/device-based-destinations-list.md).

## Ajout du consentement aux URL envoyées aux destinations d’URL

L’intégration d’Audience Manager avec IAB TCF v2.2 prend en charge l’ajout de consentement aux informations envoyées à [Destinations d’URL](../../features/destinations/create-url-destination.md) qui sont intégrés à IAB TCF v2.2. Cependant, ce processus n’est pas effectué automatiquement par Audience Manager, afin d’éviter de rompre des formats d’URL spécifiques.

Clients qui souhaitent ajouter un consentement aux données envoyées à [!DNL URL destinations] doit ajouter manuellement la variable `${GDPR}` et `${GDPR_CONSENT_XXXX}` à leur format d’URL, en remplaçant `XXXX` avec l’identifiant du partenaire de destination.

Exemple: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Voir [Macros de destination définies](../../features/destinations/destination-macros.md) pour plus d’informations sur les macros de destination prises en charge.

## Gestion du consentement entre appareils

Le module d’Audience Manager du TCF de l’IAB désinscrit automatiquement les identifiants présents sur une demande, lorsque les visiteurs de votre site ne fournissent pas les autorisations appropriées. Si la requête contient une [ID multi-appareils (ID CRM)](../../reference/ids-in-aam.md), l’Audience Manager désinscrit l’ID, ainsi que le dernier appareil associé à celui-ci. [ID multi-appareils (ID CRM)](../../reference/ids-in-aam.md).

## Test de votre implémentation de l’IAB {#test-iab-implementation}

Pour vérifier que vous avez correctement mis en oeuvre le module d’Audience Manager pour IAB TCF, lisez [Cas d’utilisation 4 de la validation du service Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html#section-64331998954d4892960dcecd744a6d88).

## IAB et exclusion dans Audience Manager. Ordre de priorité. {#iab-and-optout}

Vos utilisateurs ont également la possibilité de ne pas participer aux collectes de données. Pour ce faire, Adobe met à la disposition des utilisateurs les moyens nécessaires dans la page [Vos choix en matière de confidentialité](https://www.adobe.com/fr/privacy/opt-out.html#customeruse).

Audience Manager traite les demandes d’exclusion dans un [article distinct de notre documentation](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Les utilisateurs qui se sont désinscrits de toute collecte de données après avoir refusé de donner leur consentement ne peuvent pas y revenir.

>[!NOTE]
>
>**Ordre de priorité** : si votre utilisateur choisit de ne pas participer à la collecte de données à l’aide d’un outil d’exclusion global, comme décrit dans le lien ci-dessus, ce choix est prioritaire par rapport aux vérifications d’accord préalable et de l’IAB.

## Ressources supplémentaires {#additional-resources}

* [Accord préalable d’Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* [RGPD Transparency and Consent Framework de l’IAB Europe](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Caractéristiques techniques du RGPD Transparency and Consent Framework de l’IAB Europe](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Module du TCF de l’IAB : vidéo de démonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
