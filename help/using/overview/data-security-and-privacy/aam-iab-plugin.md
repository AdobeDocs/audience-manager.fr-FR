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
source-wordcount: '2173'
ht-degree: 29%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Présentation

Un aspect important des obligations de confidentialité que vous pouvez avoir envers vos utilisateurs est l&#39;acquisition et la transmission des choix des utilisateurs sur la façon dont leurs données personnelles peuvent être utilisées (c.-à-d., « fins ») et par qui (c.-à-d., « entreprises »).

Adobe vous fournit les moyens de gérer et de communiquer les choix de confidentialité de vos utilisateurs via la [fonctionnalité d’accord préalable](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr) et la prise en charge du [Transparency and Consent Framework (TCF) de l’IAB](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

Cet article décrit les cas d’utilisation d’Audience Manager qui prennent en charge le TCF de l’IAB et l’implémentation de la prise en charge du TCF de l’IAB dans Audience Manager.

>[!IMPORTANT]
>
>Audience Manager est enregistré dans le [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) avec l’ID de fournisseur 565.

Le module externe Audience Manager pour IAB TCF utilise la fonctionnalité [Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html?lang=fr), qui fait elle-même partie de la bibliothèque [Adobe Experience Platform Identity Service (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).

## Portée et limites {#scope-and-limitations}

En tant qu’éditeur ou publicitaire travaillant avec Audience Manager, vous pouvez transmettre les choix des utilisateurs à Audience Manager conformément au IAB TCF.

>[!IMPORTANT]
>
>Les règlements IAB TCF s&#39;appliquent uniquement aux visiteurs situés dans l&#39;Espace économique européen.

Audience Manager vous aide à respecter les choix de confidentialité de vos utilisateurs et vous offre également un moyen facile de communiquer ces choix à tous les partenaires avec lesquels vous travaillez.

Actuellement, Audience Manager ne prend pas en charge :

* les workflows des appareils mobiles ;
* Ajout du consentement aux exportations de segments.

## Mise à niveau vers [!DNL IAB TCF v2.2] {#upgrading}

Les clients qui effectuent une mise à niveau de leur implémentation [!DNL Audience Manager Plug-in for IAB TCF] de [!DNL IAB TCF] v1.1 vers [!DNL IAB TCF] v2.2 ou qui activent [!DNL IAB TCF] v2.2 pour la première fois doivent tous suivre les mêmes instructions en matière de conditions préalables et d’implémentation, comme décrit ci-dessous.

## Conditions préalables {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager prend en charge IAB TCF v2.2.
>
>La prise en charge d’IAB TCF v1.1 prendra fin le 15 août 2020.
>
> Les clients qui souhaitent continuer à utiliser le module externe Audience Manager pour IAB TCF pour la gestion du consentement doivent effectuer la mise à niveau vers la dernière version d’[ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) pour une prise en charge continue.
>
> Après la mise à niveau vers la dernière version d’[ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases), les chaînes de consentement IAB TCF v1.1 ne seront plus prises en charge. Veillez donc à mettre à jour votre CMP avant de mettre à niveau vers la dernière version d’ECID.

Vous devez remplir les conditions préalables suivantes pour utiliser le module externe Audience Manager pour IAB TCF avec Audience Manager :

1. Vous devez utiliser la version 5 ou ultérieure d’Adobe Experience Platform Identity Service (ECID). [Téléchargez](https://github.com/Adobe-Marketing-Cloud/id-service/releases) notre dernière mise à jour d’ECID.
2. Vous devez utiliser Audience Manager [!DNL Data Integration Library] (DIL) version 9.0 ou ultérieure, téléchargeable à partir d’[ici](https://github.com/Adobe-Marketing-Cloud/dil/releases). Consultez la documentation d’Audience Manager pour en savoir plus sur [DIL](../../dil/dil-overview.md). Nous vous recommandons d’utiliser l’extension de balise [Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=fr) pour une implémentation DIL d’Audience Manager plus facile.
3. Si vous utilisez [!DNL Server-Side Forwarding] (SSF) pour importer des données dans Audience Manager, vous devez également effectuer une mise à niveau vers la dernière version d’AppMeasurement. Téléchargez AppMeasurement à l’aide du [gestionnaire de code d’Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=fr).
4. Vous devez utiliser une plateforme de gestion du consentement (CMP), commerciale ou personnelle, intégrée à IAB TCF v2.2 et enregistrée auprès de IAB TCF. Consultez la liste des [CMP enregistrées dans le framework de l’IAB](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Si vous utilisez une plateforme de gestion du consentement (CMP) qui ne prend pas en charge IAB TCF v2.2, Audience Manager envoie automatiquement le paramètre `gdpr=0` dans les synchronisations des identifiants, même si vos visiteurs se trouvent dans l’Union européenne. Pour déterminer si votre validation RGPD est active, nous vous recommandons de confirmer auprès de votre plateforme de gestion du consentement (CMP) qu’elle prend en charge IAB TCF v2.2.

## Recommandations et procédure de mise en œuvre {#recommendations}

Pour activer la prise en charge du TCF de l’IAB dans Audience Manager, lisez notre documentation sur [la configuration de l’IAB avec accord préalable](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html?lang=fr).

Le moyen le plus simple d’y parvenir consiste à utiliser [Adobe Experience Platform Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=fr) pour ajouter des [!DNL ECID Opt-in] sur vos propriétés. Lisez la documentation de l’extension [Opt-in d’ECID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=fr) pour savoir comment configurer l’extension Balises.

## Workflow de choix de l’utilisateur lors de l’utilisation du framework IAB {#user-choice-workflow}

Lors de la visite d’une propriété web, vos utilisateurs peuvent indiquer leurs choix concernant la manière dont leurs données doivent être utilisées par l’éditeur et par les fournisseurs tiers avec lesquels l’éditeur travaille.

Les utilisateurs fournissent leurs choix sous la forme d’un *consentement* à des fins d’IAB aux *fournisseurs tiers* inscrits sur la liste des fournisseurs mondiaux.

L’image ci-dessous représente un exemple de dialogue de CMP, présenté au nouveau visiteur d’un site web. Gardez à l’esprit que ce dialogue peut avoir un aspect très différent, en fonction de l’implémentation des clients.

![Dialogue de CMP](assets/cmp-example.png)

Les détails sur les différents objectifs et autorisations inclus dans IAB TCF v2.2 sont couverts dans les [politiques du cadre de transparence et de consentement IAB Europe](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Les utilisateurs peuvent accorder leur consentement à plusieurs fins et pour plusieurs fournisseurs. Par exemple, les utilisateurs pourraient accorder leur consentement pour le stockage d’informations sur un appareil, le développement et l’amélioration de produits, et accorder leur consentement à tous les fournisseurs tiers affichés par le CMP.

Ou, dans un autre exemple, ils pourraient accorder leur consentement à toutes fins, mais n’accorder leur consentement qu’à quelques-uns des fournisseurs affichés par le CMP.

Une fois que l’utilisateur a sélectionné ses choix en matière de confidentialité, les choix de l’utilisateur sont enregistrés dans la chaîne IAB TC. La chaîne IAB TC stocke la combinaison des objectifs et des fournisseurs approuvés, ainsi que d&#39;autres informations de métadonnées (voir la page [IAB](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string) pour plus d&#39;informations).

Chaque fournisseur enregistré dans le IAB TCF évalue la chaîne IAB TC et prend des décisions basées sur les choix de confidentialité des utilisateurs. Gardez à l’esprit que les choix de confidentialité des utilisateurs sont valides pour tous les fournisseurs enregistrés auprès de l’IAB TCF.

## Objectifs requis par Audience Manager {#aam-standard-purposes}

Audience Manager évalue les choix des utilisateurs stockés dans la chaîne IAB TC aux fins suivantes, définies dans les [politiques IAB Europe Transparency &amp; Consent Framework](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Objectif 1** : Stocker et/ou accéder à des informations sur un appareil ;
* **Objectif 10** : développer et améliorer les produits ;
* **Objectif spécial 1** : assurer la sécurité, prévenir la fraude et procéder au débogage.

>[!IMPORTANT]
>
>Audience Manager a besoin du consentement pour Objectif 1 et Objectif 10, ainsi que du consentement du fournisseur, pour déployer des cookies et initier ou honorer les synchronisations d’ID.
>
>Conformément aux [réglementations IAB](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_), l’objectif spécifique 1 (garantir la sécurité, prévenir les fraudes et le débogage) est toujours accepté et les utilisateurs ne peuvent pas s’y opposer.

## Le comportement d’Audience Manager dépend du consentement accordé ou non par l’utilisateur {#aam-behavior-consent}

Audience Manager fonctionne différemment selon que la chaîne IAB TC inclut ou non le consentement de l’utilisateur pour les deux objectifs (stocker et/ou accéder aux informations sur un appareil, et développer et améliorer des produits).

Nous vérifions également le consentement de l’utilisateur pour toutes les destinations que vous utilisez dans Audience Manager, à condition que ces destinations soient enregistrées auprès de l’IAB TCF.

| Lorsque votre utilisateur *donne son consentement*, Audience Manager : | Lorsque votre utilisateur *refuse de donner* son consentement, Audience Manager : |
|---|---|
| <ul><li>met en œuvre tous les cas d’utilisation d’Audience Manager que vous avez demandés ;</li><li>Transmet le consentement à des tiers dans les synchronisations des identifiants (en transmettant `gdpr = 1` et la chaîne de consentement telle qu’`gdpr_consent` dans les appels de synchronisation des identifiants).</li><li>évalue et honore le consentement transmis à partir des pixels du serveur de publicités ;</li><li>honore les synchronisations des identifiants initiées par les partenaires.</li></ul> | <ul><li>ne stocke aucune nouvelle donnée utilisateur dans votre instance. Cela inclut les identifiants des partenaires, les signaux, les caractéristiques ou les données de pixel ;</li><li>n’initie pas les synchronisations des identifiants tiers ;</li><li>n’honore pas les synchronisations des identifiants initiées par les partenaires.</li><li>Exclut l’utilisateur de la collecte d’autres données.</li></ul> |

## Cas d’utilisation Publisher {#publisher-use-case}

En implémentant le module externe Audience Manager pour IAB TCF, vous n’êtes pas tenu de gérer le code personnalisé pour la gestion du consentement sur vos propriétés web via un mécanisme différent avec Adobe ou d’autres fournisseurs tiers. Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Commencez à gauche de l’image :

1. Un utilisateur visite l’une de vos propriétés web. Tant que vous utilisez les dernières versions des bibliothèques ECID et DIL (voir [Conditions préalables](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)), le flux d’accord préalable est déclenché.
2. Audience Manager vérifie si le flux de l’IAB s’applique (`isIabContext=true`). Voir [Recommandations et méthode d’implémentation](aam-iab-plugin.md#recommendations).
3. Audience Manager vérifie si le RGPD s’applique (`gdpr = 1`) et s’il existe une CMP, enregistrée auprès de l’IAB TCF, sur votre propriété web. Par exemple, cela s’appliquerait aux utilisateurs venant de l’Union européenne. Notez qu’il vous incombe, en tant qu’éditeur, de définir l’indicateur RGPD.
4. Si le RGPD s’applique, Audience Manager vérifie la chaîne IAB TC, transmise dans le paramètre `gdpr_consent`, pour obtenir le consentement requis. Audience Manager a besoin d’un consentement pour stocker des informations et/ou y accéder sur un appareil ([objectif IAB TCF 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), développer et améliorer des produits ([objectif IAB TCF 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), ainsi que du consentement du fournisseur Audience Manager pour stocker, traiter ou activer des données.
5. Si la chaîne IAB TC est présente et contient le consentement requis, Audience Manager transmet la chaîne IAB TC à nos [serveurs de collecte de données](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager répond en définissant un cookie [demdex](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=fr) sur le navigateur et lance et honore les synchronisations des identifiants tiers.
7. Si la chaîne IAB TC transmise à l’étape 4 ne contient pas toutes les autorisations nécessaires, Audience Manager ne collecte, ne traite ni n’active aucune donnée utilisateur et n’honore ni ne lance de synchronisation des identifiants. En outre, il désactive l’utilisateur des destinations que vous utilisez.

>[!IMPORTANT]
>
>Si vous travaillez avec des partenaires de destination Audience Manager qui ont besoin des paramètres IAB TCF, mais que vous n’avez pas de CMP prenant en charge IAB TCF sur votre site web, Audience Manager envoie alors des `gdpr=0` dans les synchronisations d’identifiants. Cela signifie que le RGPD ne s’applique pas à ces utilisateurs.
>
> Si cela n’est pas souhaité, vous devez activer la fonctionnalité IAB TCF dans Audience Manager pour envoyer les chaînes IAB TC appropriées aux partenaires de destination.



![Cas d’utilisation des éditeurs](assets/publisher-use-case.png)

## Cas d’utilisation publicitaire {#advertiser-use-case}

Audience Manager évalue et honore le consentement transmis dans les [appels de pixel](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md), conformément au TCF de l’IAB.

Les pixels peuvent être placés par les clients Audience Manager sur les pages de leurs partenaires ou ils sont placés sur des serveurs de publicités à inclure dans la réponse publicitaire. Dans le premier cas, votre partenaire doit récupérer le paramètre de consentement par programmation et l’ajouter au pixel avant le déclenchement. Dans le second cas, plus courant et décrit en détail ci-dessous, les serveurs de publicités ajoutent les paramètres de consentement qu’ils reçoivent de la plateforme SSP (Supply Side Platform) ou des serveurs de publicités des éditeurs à tous les pixels.

Audience Manager utilise deux paramètres pour transmettre le consentement de l’utilisateur dans les appels de pixel :

* `gdpr` peut correspondre à 0 (le RGPD ne s’applique pas) ou 1 (le RGPD s’applique).
* `gdpr_consent` correspond à la chaîne de consentement RGPD codée en base 64 et sécurisée par URL (voir [spécification](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Un exemple d’appel pour un pixel d’impression avec les deux paramètres pourrait ressembler à ce qui suit :

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Le cas d’utilisation est décrit dans l’image et dans les étapes ci-dessous. Commencez à gauche de l’image :

1. Une impression est diffusée à votre utilisateur via un serveur de publicités. Cela se traduit par un [appel en pixels](../../integration/media-data-integration/impression-data-pixels.md) à nos serveurs de collecte de données (DCS).
2. Audience Manager vérifie si l’indicateur du RGPD s’applique. Dans le cas contraire, Audience Manager stocke les données transmises dans les variables `gdpr` et `gdpr_consent` dans des appels de pixels.
3. Si la chaîne IAB TC est présente et contient les autorisations requises, Audience Manager stocke les données transmises dans les variables `gdpr` et `gdpr_consent` dans les appels de pixels.
4. Si la chaîne IAB TC est manquante ou ne dispose pas des autorisations requises, Audience Manager supprime les données transmises dans les variables `gdpr` et `gdpr_consent` dans les appels de pixels.

![Cas d’utilisation des annonceurs](assets/advertiser-use-case.png)

## Partenaires d’activation qui prennent en charge le IAB TCF {#aam-activation-partners}

Le module externe Audience Manager pour IAB TCF vous permet de transférer la chaîne IAB TC aux partenaires d’activation tout en respectant les choix de confidentialité des utilisateurs. Pour savoir quels partenaires d’activation prennent en charge le TCF de l’IAB, consultez notre [liste de destinations basées sur les appareils](/help/using/features/destinations/device-based-destinations-list.md).

## Ajout du consentement aux URL envoyées aux destinations d’URL

L’intégration d’Audience Manager à IAB TCF v2.2 prend en charge l’ajout d’un consentement aux informations envoyées aux [destinations d’URL](../../features/destinations/create-url-destination.md) intégrées à IAB TCF v2.2. Cependant, ce processus n’est pas effectué automatiquement par Audience Manager, afin d’éviter de rompre des formats d’URL spécifiques.

Les clients qui souhaitent ajouter le consentement aux données envoyées à [!DNL URL destinations] doivent ajouter manuellement les macros `${GDPR}` et `${GDPR_CONSENT_XXXX}` à leur format d’URL, en remplaçant `XXXX` par l’identifiant de partenaire de destination.

Exemple : `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Voir [Macros de destination définies](../../features/destinations/destination-macros.md) pour plus d’informations sur les macros de destination prises en charge.

## Gestion du consentement sur l’ensemble des appareils

Le module Audience Manager pour IAB TCF désactive automatiquement les identifiants présents sur une demande, lorsque les visiteurs de votre site ne fournissent pas les autorisations appropriées. Si la requête contient un [ID entre appareils (ID CRM)](../../reference/ids-in-aam.md), Audience Manager choisit l’ID, ainsi que le dernier appareil lié à cet [ID entre appareils (ID CRM)](../../reference/ids-in-aam.md).

## Tester votre implémentation IAB {#test-iab-implementation}

Pour tester que vous avez correctement mis en œuvre le module externe Audience Manager pour IAB TCF, lisez [Cas d’utilisation 4 dans Validation du service Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html?lang=fr#section-64331998954d4892960dcecd744a6d88).

## IAB et exclusion dans Audience Manager. Ordre de priorité. {#iab-and-optout}

Vos utilisateurs ont également la possibilité de ne pas participer aux collectes de données. Pour ce faire, Adobe met à la disposition des utilisateurs les moyens nécessaires dans la page [Vos choix en matière de confidentialité](https://www.adobe.com/fr/privacy/opt-out.html#customeruse).

Audience Manager traite les demandes d’exclusion dans un [article distinct de notre documentation](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Les utilisateurs qui se sont désinscrits de toute collecte de données après avoir refusé le consentement ne peuvent pas être réinscrits.

>[!NOTE]
>
>**Ordre de priorité** : si votre utilisateur choisit de ne pas participer à la collecte de données à l’aide d’un outil d’exclusion global, comme décrit dans le lien ci-dessus, ce choix est prioritaire par rapport aux vérifications d’accord préalable et de l’IAB.

## Ressources supplémentaires {#additional-resources}

* [Accord préalable d’Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=fr)
* [RGPD Transparency and Consent Framework de l’IAB Europe](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Caractéristiques techniques du RGPD Transparency and Consent Framework de l’IAB Europe](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [Module du TCF de l’IAB : vidéo de démonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
