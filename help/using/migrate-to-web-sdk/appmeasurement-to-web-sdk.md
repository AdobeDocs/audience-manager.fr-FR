---
title: Mettez à jour votre bibliothèque de collecte de données pour Audience Manager de la bibliothèque AppMeasurement JavaScript vers la bibliothèque Web SDK JavaScript.
description: Découvrez les étapes à suivre pour mettre à jour votre bibliothèque de collecte de données pour Audience Manager de la bibliothèque AppMeasurement JavaScript à la bibliothèque Web SDK JavaScript.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f180e423d4bdf5535d8dcc000e1d0f908bc54d7b
workflow-type: tm+mt
source-wordcount: '3385'
ht-degree: 0%

---


# Mettre à jour votre bibliothèque de collecte de données pour Audience Manager d’AppMeasurement vers Web SDK

## Audience prévue {#intended-audience}

Cette page est destinée aux clients Audience Manager et Adobe Analytics qui utilisent la bibliothèque JavaScript [!DNL AppMeasurement] pour envoyer des données web à Audience Manager.

Reportez-vous au tableau ci-dessous pour obtenir des conseils sur les étapes de migration vers Web SDK, en fonction de votre méthode de collecte de données actuelle.

| Votre méthode de collecte de données existante | Instructions de migration vers Web SDK |
|---------|----------|
| Bibliothèque JavaScript [!DNL AppMeasurement] avec le module AudienceManagement | Suivez les instructions de ce guide. |
| [!DNL Audience Manager] [extension de balise](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Suivez les instructions de la section [mise à jour de votre bibliothèque de collecte de données de l’extension de balise Audience Manager à l’extension de balise Web SDK](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] bibliothèque JavaScript + bibliothèque DIL autonome [!DNL Audience Manager] [&#128279;](../dil/dil-overview.md) | Suivez les instructions de la section [mise à jour de votre bibliothèque de collecte de données de l’extension de balise Audience Manager à l’extension de balise Web SDK](dil-extension-to-web-sdk.md). |

## Présentation de la migration {#overview}

La migration de [!DNL AppMeasurement] vers [Web SDK](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/home) est principalement une migration Adobe Analytics. Pour les clients Audience Manager, cette migration inclut également Audience Manager. Les deux doivent être migrés ensemble. Si vous travaillez principalement avec Audience Manager, veillez à impliquer l’équipe Analytics dans cette migration.

Si vous utilisez [!DNL AppMeasurement] pour la collecte de données Audience Manager, vous utilisez actuellement l’approche [!DNL Server-side Forwarding (SSF)] pour envoyer des données Analytics à Audience Manager. Dans cette configuration, la demande de collecte de données Analytics est transmise à Audience Manager, qui gère également la réponse d’Audience Manager à la page.

Il s’agit de l’approche standard depuis de nombreuses années et il s’agit probablement de votre configuration actuelle. Si votre bibliothèque [!DNL AppMeasurement] contient le module `AudienceManagement` et que vos appels de collecte de données incluent le chemin d’accès `/10/` dans la requête (`/b/ss/examplereportsuite/10/`), ce guide est fait pour vous.

## Transfert côté serveur (SSF) par rapport aux flux de données Web SDK {#data-flows}

Il est essentiel de comprendre les différences de flux de données entre Analytics et Audience Manager lors du passage à Web SDK (et à Edge Network) pour les instructions ci-dessous.

Avec le transfert côté serveur, le nœud de collecte de données régionale d’Analytics collecte les données, les transforme en un signal accepté par Audience Manager, les envoie à Audience Manager et renvoie la réponse d’Audience Manager à la page. Le module [!DNL AudienceManagement] de la bibliothèque [!DNL AppMeasurement] gère ensuite la réponse (par exemple, l’abandon de cookies, l’envoi de destinations d’URL). Ce processus est appelé transfert côté serveur, car Analytics transfère les données vers Audience Manager à l’aide des serveurs Adobe.

Avec Web SDK, Edge Network envoie des données à Analytics et à Audience Manager par le biais d’actions distinctes. Web SDK est une bibliothèque unique qui envoie des données à toutes les solutions et Edge Network transforme les points de données indépendamment de la solution en formats spécifiques à la solution.

Dans ce nouveau flux de données, toutes les données sont envoyées à un [flux de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/overview) Edge Network, que vous pouvez [configurer](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/configure) pour envoyer des données aux solutions Adobe si nécessaire. Pour Audience Manager, l’activation du service Audience Manager sur le flux de données transforme les données [!DNL XDM] et Analytics en signaux acceptés par Audience Manager. Edge Network renvoie également la réponse Audience Manager à la page, où le SDK Web gère la réponse, de la même manière que le [!DNL AppMeasurement] et le module [!DNL AudienceManagement].

## Migration des balises ou hors balises {#tags-vs-non-tags}

Que vous utilisiez les balises avec l’extension [!DNL AppMeasurement], la bibliothèque [!DNL AppMeasurement] dans un autre système de gestion des balises ou que vous placiez les [!DNL AppMeasurement] directement sur la page, les étapes de migration d’Audience Manager vers le SDK Web sont les mêmes. Comme la migration d’Audience Manager dépend de la migration d’Analytics, les étapes de migration de [!DNL AppMeasurement] vers Web SDK sont déterminées lors de la migration d’Analytics.

Ces informations sont abordées dans la documentation Analytics pour les implémentations basées sur [Balises](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) ou [JavaScript](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).

## XDM et les nœuds `data.__adobe.` {#xdm-data-nodes}

L’une des principales fonctions de [Web SDK](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/home) est d’envoyer des données à [Real-Time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/fr/docs/experience-platform/rtcdp/home). Pour ce faire et continuer à collecter des données pour d’autres solutions Experience Cloud sans nouvelle implémentation complète, les données spécifiques à la solution sont compartimentées dans l’appel au serveur de collecte de données. Cet appel utilise un schéma JSON normalisé appelé [ Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/home)

Les éléments indépendants de la solution, tels que les informations sur le navigateur et l’appareil, sont envoyés à Edge Network dans une structure XDM prédéterminée. Edge Network transforme ces données en formats spécifiques à une solution. Toutefois, les données spécifiques à Target, Analytics et Audience Manager sont stockées dans un nœud de `data.__adobe` dédié au sein de la payload XDM.

Par exemple :

* La variable Analytics `s.eVar1` est représentée dans la payload XDM sous la forme `data.__adobe.analytics.evar1`.
* Un paramètre Target lié au statut de fidélité de la clientèle est stocké en tant que `data.__adobe.target.loyaltyStatus`.

Les données du nœud `__adobe` sont envoyées aux solutions respectives (comme Analytics et Audience Manager) sans être envoyées à Experience Platform, même si le service Experience Platform est activé sur le flux de données. Cela signifie que vous pouvez conserver vos configurations actuelles pour Analytics et Audience Manager tout en ayant la possibilité de mapper tous les éléments de données nécessaires aux éléments de schéma XDM pour les cas d’utilisation en temps réel dans Experience Platform à l’aide de la [préparation des données pour la collecte de données](https://experienceleague.adobe.com/fr/docs/experience-platform/datastreams/data-prep).

Par exemple, la chaîne de `s.products` Analytics, qui est utilisée pour signaler le contenu du panier lors du passage en caisse, peut toujours être envoyée à Analytics et Audience Manager dans son format d’origine. Dans le même temps, vous pouvez utiliser les éléments de cette chaîne pour créer des schémas de panier XDM plus intuitifs pour les cas d’utilisation d’Experience Platform.

Comme la plupart des implémentations d’Audience Manager reposent sur des données Analytics transférées à Audience Manager, de nombreuses expressions de caractéristiques Audience Manager sont probablement basées sur des variables Analytics (`c_evar#`, `c_prop#` et `c_events`). Pour éviter de reconstruire des expressions de caractéristiques à l’aide de formats XDM lors de la migration, Edge Network est configuré par défaut pour transformer toutes les variables Analytics trouvées dans le nœud `data.__adobe.analytics` en signaux Audience Manager. Un processus de transformation similaire se produit dans le workflow de transfert côté serveur.

Edge Network peut effectuer cette transformation, car un seul appel de collecte de données de la page est envoyé à un seul flux de données qui alimente plusieurs solutions Adobe. Par conséquent, la plupart des migrations de [!DNL AppMeasurement] vers Web SDK pour Analytics et Audience Manager utilisent principalement le nœud `data.__adobe.analytics`.

Edge Network transforme les données de l’appareil et du navigateur de la payload XDM et des en-têtes de paquet en signaux Audience Manager. Cela vous permet de continuer à utiliser des clés de plateforme `h_` et `d_` dans les expressions de caractéristiques Audience Manager.

## Nœud `data.__adobe.audiencemanager` {#data-note}

Le nœud `data.__adobe.audiencemanager` est utilisé pour les implémentations d’Audience Manager qui ne dépendent pas d’Analytics. Il stocke les paires clé/valeur Audience Manager personnalisées qui ont été précédemment envoyées via la bibliothèque [DIL](../dil/dil-overview.md), comme décrit dans le guide de migration de l’extension de balise [&#128279;](dil-extension-to-web-sdk.md).

Bien que le nœud `data.__adobe.audiencemanager` ne soit pas nécessaire pour la migration décrite dans ce guide, le nouveau flux de données expliqué ici permet d’envoyer des données à Audience Manager sans les enregistrer dans Analytics.

Si vous devez envoyer une paire clé/valeur personnalisée à Audience Manager sans l’inclure dans Analytics, vous pouvez utiliser le nœud `data.__adobe.audiencemanager` . Tout jeu de données de ce nœud sera ajouté aux données Analytics transformées par Audience Manager dans l’appel au serveur de collecte de données.

## Avantages et inconvénients de ce chemin de mise en œuvre

L’utilisation de cette approche de migration présente à la fois des avantages et des inconvénients. Évaluez soigneusement chaque option pour décider quelle approche est la meilleure pour votre organisation.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Utilise votre implémentation existante** : bien que cette approche nécessite certaines modifications d’implémentation, elle ne nécessite pas une implémentation entièrement nouvelle à partir de zéro. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation.</li><li>**Ne nécessite pas de schéma** : pour cette étape de la migration vers le Web SDK, vous n’avez pas besoin de schéma XDM. Vous pouvez plutôt renseigner l’objet `data` , qui envoie directement les données à Audience Manager. Une fois la migration vers Web SDK terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage des flux de données pour renseigner les champs XDM applicables. Si un schéma était requis à cette étape du processus de migration, votre organisation serait forcée d’utiliser un schéma XDM Audience Manager. L’utilisation de ce schéma rend plus difficile, pour votre organisation, l’utilisation de votre propre schéma à l’avenir.</li></ul> | <ul><li>**Dette technique d’implémentation** : étant donné que cette approche utilise une forme modifiée de votre implémentation existante, il peut être plus difficile de suivre la logique d’implémentation et d’effectuer des modifications à l’avenir si nécessaire.</li><li>**Nécessite un mappage pour envoyer des données à Platform** : lorsque votre organisation est prête à utiliser Real-Time CDP, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet `data` soit une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow et n’implique aucune modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas nécessaire lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation dans les scénarios suivants :

* Vous disposez déjà d’une implémentation utilisant la bibliothèque JavaScript Adobe Analytics AppMeasurement. Si vous disposez d’une implémentation utilisant l’extension de balise Audience Manager, suivez [Migration de l’extension de balise Audience Manager vers l’extension de balise Web SDK](dil-extension-to-web-sdk.md) à la place.
* Vous avez l’intention d’utiliser Real-Time CDP à l’avenir, mais vous ne souhaitez pas remplacer votre implémentation d’Audience Manager par une implémentation de SDK Web à partir de zéro. L’alternative consistant à remplacer entièrement votre mise en œuvre par le Web SDK demande le plus d’efforts, car vous devez recréer toutes les caractéristiques d’Audience Manager pour rechercher des données au format XDM. Cependant, il s’agit également de l’architecture de mise en œuvre à long terme la plus viable. Si votre entreprise est prête à passer par une implémentation propre de Web SDK, consultez la [documentation de Web SDK](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/home) au lieu d’utiliser ce guide, pour plus d’informations.

## Étapes requises pour migrer vers Web SDK

Suivez les étapes ci-dessous pour migrer votre intégration de collecte de données vers Web SDK.

+++**1. Planifiez votre migration Analytics**.

Contactez votre équipe Analytics pour suivre les étapes de migration d’Analytics dans les implémentations basées sur [Tags](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) ou [JavaScript](https://experienceleague.adobe.com/fr/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk). Une fois la migration d’Analytics planifiée, revenez à ce guide et suivez les étapes d’Audience Manager pour déterminer ce que vous devez faire pour Audience Manager afin de pouvoir déployer la migration d’Analytics et d’Audience Manager ensemble.

+++

+++**2. Ajoutez le service Audience Manager au flux de données**

Ajoutez le service Audience Manager au flux de données que vous utilisez dans la migration d’Analytics mentionnée à l’étape 1.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Data Collection]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionnez le flux de données que vous avez créé dans le cadre de la migration d’Analytics à l’étape 1.
1. Sélectionnez **[!UICONTROL Add Service]**.
1. Dans le menu déroulant Service, sélectionnez **[!UICONTROL Audience Manager]**.
1. Cochez les options **[!UICONTROL Cookie Destinations Enabled]** et **[!UICONTROL URL Destinations Enabled]** . Ces options permettent à Edge Network de renvoyer ces types de destination Audience Manager à la page.
1. Assurez-vous que le **[!UICONTROL Enable XDM Flattened Fields]** est désactivé. Cette option désactive la transformation automatique des variables Analytics en signaux Audience Manager. Cette option est conçue pour maintenir la rétrocompatibilité pour les utilisateurs qui ont migré vers Web SDK avant qu’Edge Network ne transforme automatiquement les données Analytics en signaux Audience Manager.

   >[!NOTE]
   >
   >La migration vers Web SDK avec l’option **[!UICONTROL Enabled XDM Flattened Fields]** activée nécessite que toutes les données nécessaires dans Audience Manager au format XDM et toutes les caractéristiques Audience Manager à l’aide de props, eVars ou événements soient mises à jour pour rechercher des données au format XDM à la place. Adobe recommande de ne pas activer cette option.


   ![Ajouter un service Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Sélectionnez **[!UICONTROL Save]** pour enregistrer la configuration du flux de données.

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à Audience Manager. Notez l’identifiant du flux de données, car il est obligatoire lors de la configuration de Web SDK dans le code.

+++

+++**3. Activez les synchronisations des identifiants tiers et définissez l’identifiant de conteneur Audience Manager**

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Data Collection]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionnez le flux de données que vous avez créé dans le cadre de la migration d’Analytics à l’étape 1.
1. Sélectionnez **[!UICONTROL Edit]** dans le coin supérieur droit de la page de configuration du flux de données.
1. Développez le menu déroulant **[!UICONTROL Advanced Options]** et activez la fonctionnalité de **[!UICONTROL Third Party ID Sync]** si elle n’est pas déjà activée. Cette option indique à Edge Network de renvoyer les synchronisations des identifiants de partenaire pour les partenaires de données Audience Manager et Experience Platform.

   ![Activer la synchronisation des identifiants tiers.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. Dans la plupart des cas, vous pouvez laisser le champ **[!UICONTROL Third Party ID Sync Container ID]** vide. Il sera défini par défaut sur `0`. Cependant, si vous préférez vous assurer que le bon ID de conteneur est utilisé, procédez comme suit :
   * Ouvrez une fenêtre de navigateur en mode privé ou en mode privé et accédez à une page qui fait partie de la migration.
   * Utilisez les outils de développement du navigateur pour filtrer l’appel réseau à `dpm.demdex.net/id`. Cet appel ne se déclenche que sur la première page d’une première visite. C’est pourquoi un navigateur incognito ou privé est nécessaire.
   * Affichez la payload de la requête. Si le paramètre `d_nsid` est différent de zéro, copiez-le dans le champ **[!UICONTROL Third Party ID Sync Container ID]** .

1. Sélectionnez **[!UICONTROL Save]**.

Votre flux de données est maintenant prêt à envoyer des données à Audience Manager et à transmettre les réponses d’Audience Manager au SDK Web.

+++

+++**4. Ajoutez les ID de client au mappage d’identités**

La plupart des implémentations d’Audience Manager utilisent des [règles de fusion de profil](../features/profile-merge-rules/merge-rules-overview.md) dans des scénarios de personnalisation entre appareils, et pour contrôler les segments pour lesquels les visiteurs peuvent être qualifiés en fonction de leur état d’authentification (connecté ou déconnecté). Les règles de fusion de profil nécessitent qu’un identifiant détenu par le client (identifiant CRM, numéro de compte, etc.) soit envoyé à Audience Manager à chaque appel de collecte de données après l’authentification. Auparavant, la fonction `setCustomerIDs` du service d’identification des visiteurs ([!DNL visitor.js]) était utilisée pour ajouter des identifiants de client à chaque appel de collecte de données Analytics, qui était ensuite transféré à Audience Manager.

Avec le Web SDK, ces identités doivent désormais être envoyées à Edge Network à l’aide d’un concept XDM spécial appelé [IdentityMap](https://experienceleague.adobe.com/fr/docs/experience-platform/xdm/field-groups/profile/identitymap).

La transmission correcte des identités dans un mappage d’identités nécessite de comprendre les [espaces de noms d’identité](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/namespaces) et de réfléchir soigneusement aux identités à transmettre, en particulier lors de l’envoi de données à un sandbox Experience Platform. [Cet article](https://experienceleague.adobe.com/fr/docs/experience-cloud-kcs/kbarticles/ka-21305) décrit ces considérations et instructions.

Une fois que vous avez déterminé les identités à transmettre et quand, suivez les guides relatifs à l’utilisation de l’[!UICONTROL Identity map] **[!UICONTROL Identity map]** [élément de données](https://experienceleague.adobe.com/fr/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) dans les balises ou définissez-le manuellement comme indiqué dans la [présentation des données d’identité](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/identity/overview) pour vous aligner sur votre stratégie de déploiement Web SDK.

+++

+++**5. (Facultatif) Définissez le cookie de `aam_uuid` propriétaire**

Une pratique courante pendant de nombreuses années consistait à placer l’UUID Audience Manager (la valeur du cookie demdex tiers) dans un cookie propriétaire généralement nommé `aam_uuid`.

Pour définir le cookie, vous devez saisir un nom de cookie dans le champ **[!UICONTROL Name]** de la section **[!UICONTROL Unique User ID Cookie]** de l’extension de balise Analytics ou dans le champ `uuidCookie` lors de la configuration du `audienceManagementModule`. Bien que généralement configuré dans le code, le cookie était rarement utilisé, car la valeur de l’UUID Audience Manager est un identifiant inter-domaines spécifique à l’appareil utilisé par les plateformes publicitaires et fournit peu de valeur en tant qu’identifiant propriétaire.

Si vous constatez que votre implémentation nécessite que ce cookie `aam_uuid` continue à être défini après la migration vers Web SDK, vous pouvez récupérer l’UUID Audience Manager de deux manières.

1. Chaque réponse du point d’entrée d’interaction [Edge Network](https://developer.adobe.com/data-collection-apis/docs/endpoints/interact/) contient une payload avec des nœuds `id`. Le nœud `id` de la payload de l’espace de noms `CORE` contient l’UUID Audience Manager.

2. Utilisez la commande [getIdentity](https://experienceleague.adobe.com/fr/docs/experience-platform/web-sdk/commands/getidentity) du SDK Web pour la récupérer. Utilisez l’espace de noms `CORE` comme indiqué dans la documentation et récupérez la valeur du champ `identity.CORE` dans la réponse.

Quelle que soit la méthode utilisée pour récupérer l’UUID Audience Manager, il revient à votre équipe de développement d’analyser la réponse, de récupérer l’UUID et de définir le cookie. Il n’existe aucun moyen automatique de définir ce cookie via le Web SDK.

+++

## Configurer le transfert côté serveur et Audience Analytics dans l’interface utilisateur du Gestionnaire de suites de rapports Analytics {#configure-ssf-analytics}

Si vous connaissez la fonctionnalité de [transfert côté serveur](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) d’Analytics, vous pouvez vous demander : « *Dois-je désactiver le paramètre de transfert côté serveur dans l’interface utilisateur du Gestionnaire de suites de rapports Analytics pour empêcher l’envoi de données Analytics à Audience Manager deux fois ?* ».

La réponse est non. Vous ne devez pas désactiver ce paramètre pour les raisons suivantes :

1. Lorsque le service Audience Manager est activé sur un flux de données, Edge Network ajoute la variable `cm.ssf` à toutes les requêtes de collecte de données envoyées à Analytics. Cela empêche également l’envoi des données Analytics à Audience Manager. Tous les journaux Assurance utilisés pour valider la migration d’Analytics affichent la variable `cm.ssf=1` lorsque le service Audience Manager est activé sur le flux de données. Pour plus d’informations, consultez la page [Analytics et conformité au RGPD axée sur le transfert côté serveur](https://experienceleague.adobe.com/fr/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr).

1. Ce paramètre permet également le flux de données pour l’intégration [!DNL Audience Analytics]. Comme indiqué dans la présentation d’[Audience Analytics](https://experienceleague.adobe.com/fr/docs/analytics/integration/audience-analytics/mc-audiences-aam), le transfert côté serveur est requis pour cette intégration, car la réponse d’Audience Manager au serveur de collecte de données Analytics est ajoutée à l’accès Analytics avant traitement. Un processus similaire se produit dans Edge Network. Lorsque le transfert côté serveur est activé, Edge Network ajoute les segments nécessaires de la réponse d’Audience Manager aux données envoyées à Analytics.

En résumé, il est important que ce paramètre reste activé pour qu’Audience Analytics continue à fonctionner avec une implémentation de Web SDK et qu’aucune donnée ne soit comptabilisée deux fois dans Audience Manager.

## Validation de la migration {#validation}

Toutes les solutions Adobe étant désormais accessibles par un seul appel de Web SDK, les étapes de validation peuvent changer en fonction des solutions fournies par Web SDK.

Si Adobe Target ou Adobe Journey Optimizer (y compris [!DNL Decisioning]) font partie de la pile de solutions gérée par votre implémentation , plusieurs appels réseau à Edge Network s’afficheront sur la page. Certaines d’entre elles sont destinées à récupérer des personnalisations et des offres, tandis que d’autres sont destinées à la collecte de données et au compte rendu des performances.

Quelle que soit votre mise en œuvre, les principes généraux ci-dessous s’appliquent pour valider le flux correct de données depuis et vers Audience Manager via Web SDK.

1. Le premier appel réseau pour un premier visiteur de première page et de première utilisation concerne le domaine `adobedc.demdex.net` et le point d’entrée `/interact`. Vous pouvez afficher les appels réseau effectués par Web SDK en ouvrant l’onglet Développeur dans votre navigateur web, en cliquant sur l’onglet Réseau , puis en filtrant les `/interact`.
Il existe d’autres types d’appels Web SDK, mais seuls les appels `interact` envoient des données à et obtiennent une payload de réponse d’Edge Network.

   ![Image d’un onglet de réseau de navigateur affichant les appels d’interaction.](assets/network.png)

1. La réponse au premier appel réseau comporte plusieurs payloads. L’un de ces nœuds de payload comprend plusieurs sous-nœuds de type `url`. Ces nœuds `url` sont les synchronisations d’identifiants tiers qui ont été historiquement déclenchées par le service [!DNL Visitor ID]. Il doit y avoir un nœud `url` pour chaque synchronisation d’identifiants tiers configurée dans votre conteneur (voir l’étape 3 ci-dessus).

   ![Image d’un onglet de réseau de navigateur affichant les payloads.](assets/payload.png)

   En outre, vous pouvez filtrer par `demdex` et constater que chacune des URL référencées dans la payload a déclenché sa propre requête réseau pour la synchronisation des identifiants, comme l’a fait le service [!DNL Visitor ID]. Ces synchronisations des identifiants ne doivent se déclencher que sur la première page d’un nouveau visiteur, puis une fois tous les 14 jours.

1. Toute requête `/interact` ultérieure utilisée pour la collecte de données Analytics et Audience Manager doit contenir les nœuds `data.__adobe.analytics` dans la payload.

   ![Image d’un onglet de réseau de navigateur affichant le nœud d’analyse dans la payload.](assets/analytics-node.png)

   Les caractéristiques d’Audience Manager qui reposent sur ces variables Analytics, ainsi que celles qui utilisent les clés de plateforme `h_` ou `d_`, doivent continuer à être renseignées.

   >[!TIP]
   >
   >Vous pouvez créer une caractéristique de test avec une expression de règle qui ne peut être exprimée que si les données de SDK Web sont collectées. Puisqu’il n’existe aucun environnement Audience Manager de développement et que plusieurs sites peuvent envoyer des données à la même instance Audience Manager, le simple fait d’examiner le nombre total de populations peut ne pas vous donner la validation nécessaire.

1. Dans le même appel `/interact` où les variables Analytics sont transmises, toutes les destinations de cookie ou d’URL se trouvent dans les nœuds de payload de la réponse. Les destinations d’URL se trouvent dans des payloads de type `url` (tout comme dans les synchronisations d’identifiants tiers) et les destinations de cookies se trouvent dans des payloads de type `cookie`.

   ![Image d’un onglet de réseau de navigateur affichant les données de payload.](assets/destinations.png)

   Vous devez également vous assurer que les cookies ont été déposés dans l’espace de stockage des cookies du navigateur.

   >[!TIP]
   >
   >Comme à l’étape de validation précédente, la qualification pour un segment qui doit renvoyer une destination de cookie est un moyen certain de s’assurer que les données circulent vers et depuis Audience Manager.

1. Si vous devez transmettre des identifiants de client supplémentaires par le biais du mappage d’identités, authentifiez-vous sur le site et assurez-vous que les identités et leurs paramètres associés sont transmis dans le nœud de mappage d’identités de la payload de requête.

   ![Image d’un onglet réseau de navigateur affichant les données identityMap.](assets/pass-customer-ids.png)

   >[!TIP]
   >
   >Si Adobe Target est l’une des solutions de réception et qu’il existe des activités Target qui reposent sur des segments Audience Manager qui nécessitent la transmission de la bonne identité, assurez-vous que le mappage d’identité est transmis dans les appels `/interact` utilisés pour récupérer les personnalisations, et pas seulement dans les appels de collecte de données. Adobe Target utilisera ces identités dans l’appel côté serveur à Audience Manager lors de la récupération des informations sur les segments.

