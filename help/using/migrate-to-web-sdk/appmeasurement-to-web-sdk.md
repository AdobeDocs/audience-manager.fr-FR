---
title: Mettez à jour votre bibliothèque de collecte de données pour Audience Manager de la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript du SDK Web.
description: Découvrez les étapes à suivre pour mettre à jour votre bibliothèque de collecte de données en vue de l’Audience Manager depuis la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript SDK Web.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: f8d8eb722e7b5cc4371f400a76fbd548a1318668
workflow-type: tm+mt
source-wordcount: '2589'
ht-degree: 0%

---


# Mettez à jour votre bibliothèque de collecte de données pour Audience Manager de la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript SDK Web

## Audience prévue {#intended-audience}

Cette page est destinée aux clients Audience Manager et Adobe Analytics qui utilisent la bibliothèque JavaScript [!DNL AppMeasurement] pour envoyer des données web à Audience Manager.

Reportez-vous au tableau ci-dessous pour plus d’informations sur les étapes de migration vers le SDK Web, en fonction de votre méthode actuelle de collecte de données.

| Votre méthode de collecte de données existante | Instructions de migration du SDK Web |
|---------|----------|
| [!DNL AppMeasurement] Bibliothèque JavaScript | Suivez les instructions de ce guide. |
| [!DNL Audience Manager] [extension de balise](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) | Suivez les instructions de la section [mise à jour de votre bibliothèque de collecte de données de l’extension de balise d’Audience Manager vers l’extension de balise SDK Web](dil-extension-to-web-sdk.md). |
| [!DNL AppMeasurement] Bibliothèque JavaScript + [!DNL Audience Manager] [Bibliothèque DIL](../dil/dil-overview.md) | Suivez les instructions de la section [mise à jour de votre bibliothèque de collecte de données de l’extension de balise d’Audience Manager vers l’extension de balise SDK Web](dil-extension-to-web-sdk.md). |

## Présentation de la migration {#overview}

La migration de [!DNL AppMeasurement] vers [SDK Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) est principalement une migration Adobe Analytics. Pour les clients d’Audience Manager, cette migration inclut également l’Audience Manager. Les deux doivent être migrées ensemble. Si vous travaillez principalement avec l’Audience Manager, veillez à impliquer l’équipe Analytics dans cette migration.

Si vous utilisez [!DNL AppMeasurement] pour la collecte de données d’Audience Manager, vous utilisez actuellement l’approche [!DNL Server-side Forwarding (SSF)] pour envoyer des données Analytics à Audience Manager. Dans cette configuration, la demande de collecte de données Analytics est transmise à Audience Manager, qui gère également la réponse de l’Audience Manager à la page.

Il s’agit de l’approche standard depuis de nombreuses années. Il s’agit probablement de votre configuration actuelle. Si votre bibliothèque [!DNL AppMeasurement] contient le module `AudienceManagement` et que vos appels de collecte de données incluent le chemin `/10/` dans la requête (`/b/ss/examplereportsuite/10/`), alors ce guide est à votre disposition.

## Transfert côté serveur (SSF) par rapport aux flux de données du SDK Web {#data-flows}

Pour obtenir les instructions ci-dessous, il est essentiel de comprendre les différences de flux de données entre Analytics et l’Audience Manager lors du passage au SDK Web (et à l’Edge Network).

Avec le transfert côté serveur, le noeud de collecte de données régionale Analytics collecte les données, les transforme en signal accepté par l’Audience Manager, les envoie à l’Audience Manager et renvoie la réponse de l’Audience Manager à la page. Le module [!DNL AudienceManagement] de la bibliothèque [!DNL AppMeasurement] gère ensuite la réponse (par exemple, la suppression des cookies et l’envoi des destinations d’URL). Ce processus est appelé transfert côté serveur, car Analytics transfère les données vers l’Audience Manager à l’aide des serveurs Adobe.

Avec le SDK Web, l’Edge Network envoie des données à Analytics et à l’Audience Manager dans des actions distinctes. Le SDK Web est une bibliothèque unique qui envoie des données à toutes les solutions et l’Edge Network transforme les points de données agnostiques en formats spécifiques aux solutions.

Dans ce nouveau flux de données, toutes les données sont envoyées à un Edge Network [datastream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview), que vous pouvez [configurer](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/configure) pour envoyer des données à des solutions Adobe si nécessaire. Pour l’Audience Manager, l’activation du service d’Audience Manager dans la banque de données transforme [!DNL XDM] et les données Analytics en signaux acceptés par l’Audience Manager. L’Edge Network renvoie également la réponse de l’Audience Manager à la page, où le SDK Web gère la réponse, comme l’ont fait [!DNL AppMeasurement] et le module [!DNL AudienceManagement].

## Migration des balises contre les balises non {#tags-vs-non-tags}

Que vous utilisiez des balises avec l’extension [!DNL AppMeasurement], la bibliothèque [!DNL AppMeasurement] dans un autre système de gestion des balises ou que vous placiez [!DNL AppMeasurement] directement sur la page, les étapes de migration de l’Audience Manager vers le SDK Web sont les mêmes. La migration des Audiences Manager dépendant de la migration d’Analytics, les étapes de migration de [!DNL AppMeasurement] vers le SDK Web sont déterminées lors de la migration d’Analytics.

Ces informations sont traitées dans la documentation Analytics pour les mises en oeuvre basées sur [Balises](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) ou [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk).

## XDM et les noeuds `data.__adobe.` {#xdm-data-nodes}

L&#39;une des principales fonctions du [SDK Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) est d&#39;envoyer des données à [Real-Time Customer Data Platform (RTCDP)](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/home). Pour ce faire et continuer à collecter des données pour d’autres solutions Experience Cloud sans remise en oeuvre complète, les données spécifiques à une solution sont compartimentées dans l’appel du serveur de collecte de données. Cet appel utilise un schéma JSON normalisé appelé [Modèle de données d’expérience (XDM)](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)

Les éléments agnostiques en matière de solution, tels que les informations sur le navigateur et l’appareil, sont envoyés à l’Edge Network dans une structure XDM prédéterminée. L’Edge Network transforme ces données en formats spécifiques à une solution. Toutefois, les données spécifiques à Target, Analytics et l’Audience Manager sont stockées dans un noeud `data.__adobe` dédié dans la payload XDM.

Par exemple :

* La variable Analytics `s.eVar1` est représentée dans la charge utile XDM sous la forme `data.__adobe.analytics.evar1`.
* Un paramètre Target associé à l’état de fidélité des clients est stocké en tant que `data.__adobe.target.loyaltyStatus`.

Les données du noeud `__adobe` sont envoyées aux solutions respectives (comme Analytics et Audience Manager) sans être envoyées à l’Experience Platform, même si le service Experience Platform est activé dans le flux de données. Cela signifie que vous pouvez conserver vos configurations actuelles pour Analytics et Audience Manager tout en ayant la possibilité de mapper tous les éléments de données nécessaires aux éléments de schéma XDM pour des cas d’utilisation en temps réel dans Experience Platform à l’aide de [Préparation de données pour la collecte de données](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/data-prep).

Par exemple, la chaîne Analytics `s.products`, utilisée pour signaler le contenu du panier lors de l’extraction, peut toujours être envoyée à Analytics et à l’Audience Manager dans son format d’origine. En même temps, vous pouvez utiliser les éléments de cette chaîne pour créer des schémas de panier XDM plus intuitifs pour les cas d’utilisation Experience Platform.

Comme la plupart des mises en oeuvre d’Audience Manager reposent sur les données Analytics transférées à l’Audience Manager, de nombreuses expressions de caractéristiques d’Audience Manager sont probablement basées sur des variables Analytics (`c_evar#`, `c_prop#` et `c_events`). Pour éviter de recréer des expressions de caractéristiques à l’aide de formats XDM lors de la migration, l’Edge Network est configuré par défaut pour transformer toutes les variables Analytics trouvées dans le noeud `data.__adobe.analytics` en signaux d’Audience Manager. Ce processus est similaire au workflow de transfert côté serveur.

L’Edge Network peut effectuer cette transformation car un seul appel de collecte de données de la page est envoyé à un seul flux de données qui alimente plusieurs solutions d’Adobe. Par conséquent, la plupart des migrations de [!DNL AppMeasurement] vers le SDK Web pour Analytics et l’Audience Manager utilisent principalement le noeud `data.__adobe.analytics`.

L’Edge Network transforme les données du périphérique et du navigateur de la charge utile XDM et des en-têtes de paquets en signaux d’Audience Manager. Cela vous permet de continuer à utiliser les clés de plateforme `h_` et `d_` dans les expressions de caractéristiques d’Audience Manager.

## Noeud `data.__adobe.audiencemanager` {#data-note}

Le noeud `data.__adobe.audiencemanager` est utilisé pour les implémentations d’Audience Manager qui ne dépendent pas d’Analytics. Il stocke des paires clé/valeur d’Audience Manager personnalisées qui ont été envoyées précédemment via la bibliothèque [ DIL library](../dil/dil-overview.md), comme décrit dans le [guide de migration de l’extension de balise](dil-extension-to-web-sdk.md).

Bien que le noeud `data.__adobe.audiencemanager` ne soit pas nécessaire pour la migration décrite dans ce guide, le nouveau flux de données expliqué ici permet d’envoyer des données à l’Audience Manager sans être enregistré dans Analytics.

Si vous devez envoyer une paire clé/valeur personnalisée à l’Audience Manager sans l’inclure dans Analytics, vous pouvez utiliser le noeud `data.__adobe.audiencemanager` . Tout jeu de données de ce noeud sera annexé aux données Analytics transformées par l’Audience Manager dans l’appel du serveur de collecte de données.

## Avantages et inconvénients de ce chemin de mise en oeuvre

L’utilisation de cette approche de migration présente des avantages et des inconvénients. Pesez soigneusement chaque option pour choisir la méthode qui convient le mieux à votre entreprise.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Utilise votre mise en oeuvre existante** : bien que cette approche nécessite des modifications de mise en oeuvre, elle ne nécessite pas une mise en oeuvre entièrement nouvelle de toutes pièces. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation.</li><li>**Ne nécessite pas de schéma** : pour cette étape de migration vers le SDK Web, vous n’avez pas besoin d’un schéma XDM. Vous pouvez à la place renseigner l’objet `data` qui envoie directement des données à l’Audience Manager. Une fois la migration vers le SDK Web terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage de flux de données pour remplir les champs XDM applicables. Si un schéma était requis à ce stade du processus de migration, votre organisation serait forcée d’utiliser un schéma XDM d’Audience Manager. L’utilisation de ce schéma rend plus difficile l’utilisation de votre propre schéma par votre entreprise à l’avenir.</li></ul> | <ul><li>**Dette technique de mise en oeuvre** : comme cette approche utilise une forme modifiée de votre mise en oeuvre existante, il peut être plus difficile de suivre la logique de mise en oeuvre et d’effectuer des modifications ultérieurement, si nécessaire.</li><li>**Nécessite un mappage pour envoyer des données à Platform** : lorsque votre organisation est prête à utiliser Real-Time CDP, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet `data` soit une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui n’implique pas d’effectuer des modifications de mise en oeuvre. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation dans les scénarios suivants :

* Vous disposez d’une mise en oeuvre existante à l’aide de la bibliothèque JavaScript Adobe Analytics AppMeasurement. Si vous disposez d’une implémentation à l’aide de l’extension de balise d’Audience Manager, suivez la section [Migration de l’extension de balise d’Audience Manager vers l’extension de balise du SDK Web](dil-extension-to-web-sdk.md) à la place.
* Vous envisagez d’utiliser Real-Time CDP à l’avenir, mais ne souhaitez pas remplacer entièrement votre mise en oeuvre d’Audience Manager par une mise en oeuvre de SDK Web. Le remplacement de votre implémentation de A à Z sur le SDK Web nécessite le plus d’efforts, mais offre également l’architecture d’implémentation à long terme la plus viable. Si votre entreprise est prête à entreprendre une mise en oeuvre propre du SDK Web, consultez la [documentation du SDK Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) pour plus d’informations.

## Procédure de migration vers le SDK Web

Suivez les étapes ci-dessous pour migrer votre intégration de collecte de données vers le SDK Web.

+++**1. Migrez votre implémentation Analytics**.

Collaborez avec votre équipe Analytics pour suivre les étapes de migration d’Analytics dans les implémentations basées sur les [balises](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/analytics-extension-to-web-sdk) ou [JavaScript](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/web-sdk/appmeasurement-to-web-sdk). Après avoir migré votre mise en oeuvre Analytics, passez à l’étape suivante.

+++

+++**2. Ajout du service d’Audience Manager à la banque de données**

Ajoutez le service d’Audience Manager au flux de données que vous avez créé à l’étape 1.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Data Collection]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionnez la banque de données que vous avez créée dans le cadre de votre migration Analytics à l’étape 1.
1. Sélectionnez **[!UICONTROL Add Service]**.
1. Dans le menu déroulant du service, sélectionnez **[!UICONTROL Audience Manager]**.
1. Vérifiez les options **[!UICONTROL Cookie Destinations Enabled]** et **[!UICONTROL URL Destinations Enabled]** . Ces options permettent à l’Edge Network de renvoyer ces types de destination d’Audience Manager dans la page.
1. Assurez-vous que le **[!UICONTROL Enable XDM Flattened Fields]** est désactivé. Cette option désactive la transformation automatique des variables Analytics en signaux d’Audience Manager. Cette option est conçue pour maintenir une rétrocompatibilité pour les utilisateurs qui ont migré vers le SDK Web avant que l’Edge Network ne transforme automatiquement les données Analytics en signaux d’Audience Manager.

   >[!NOTE]
   >
   >La migration vers le SDK Web avec l’option **[!UICONTROL Enabled XDM Flattened Fields]** activée nécessite que toutes les données nécessaires dans l’Audience Manager au format XDM et toutes les caractéristiques d’Audience Manager utilisant des props, des eVars ou des événements soient mises à jour pour rechercher à la place des données au format XDM. Adobe recommande de laisser cette option désactivée.


   ![Ajouter un service d’Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

1. Sélectionnez **[!UICONTROL Save]** pour enregistrer la configuration du flux de données.

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à l’Audience Manager. Notez l’identifiant de la banque de données, car cet identifiant est requis lors de la configuration du SDK Web dans le code.

+++

+++**3. Activez les synchronisations des identifiants tiers et définissez l’identifiant du conteneur d’Audience Manager**.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Data Collection]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionnez la banque de données que vous avez créée dans le cadre de votre migration Analytics à l’étape 1.
1. Sélectionnez **[!UICONTROL Edit]** dans le coin supérieur droit de la page de configuration du flux de données.
1. Développez le menu déroulant **[!UICONTROL Advanced Options]** et activez la fonctionnalité **[!UICONTROL Third Party ID Sync]** si elle n’est pas déjà activée. Cette option indique à l’Edge Network de renvoyer les synchronisations des identifiants de partenaire pour les partenaires de données d’Audience Manager et Experience Platform.

   ![ Activez la synchronisation des identifiants tiers.](assets/third-party-id-sync.png) {style="border:1px solid lightslategray"}

1. Dans la plupart des cas, vous pouvez laisser le champ **[!UICONTROL Third Party ID Sync Container ID]** vide. La valeur par défaut sera `0`. Cependant, si vous préférez vous assurer que le bon ID de conteneur est utilisé, procédez comme suit :
   * Ouvrez une fenêtre de navigateur en mode incognito ou privé et accédez à une page qui fait partie de la migration.
   * Utilisez les outils de développement du navigateur pour filtrer l’appel réseau à `dpm.demdex.net/id`. Cet appel ne se déclenche que sur la première page d’une première visite, raison pour laquelle un incognito ou un navigateur privé est nécessaire.
   * Affichez le payload de la requête. Si le paramètre `d_nsid` est différent de zéro, copiez-le dans le champ **[!UICONTROL Third Party ID Sync Container ID]**.

1. Sélectionnez **[!UICONTROL Save]**.

Votre flux de données est maintenant prêt à envoyer des données à l’Audience Manager et à transmettre les réponses de l’Audience Manager au SDK Web.

+++

+++**4. Ajout d’ID de client à la carte d’identité**

La plupart des mises en oeuvre d’Audience Manager utilisent des [règles de fusion de profils](../features/profile-merge-rules/merge-rules-overview.md) dans des scénarios de personnalisation multi-appareils et pour aider à contrôler les segments que les visiteurs peuvent qualifier en fonction de leur état d’authentification (connecté ou déconnecté). Les règles de fusion de profils nécessitent qu’un identifiant détenu par le client (identifiant CRM, numéro de compte, etc.) soit envoyé à l’Audience Manager à chaque appel de collecte de données après l’authentification. Auparavant, la fonction `setCustomerIDs` du service d’identification des visiteurs ([!DNL visitor.js]) était utilisée pour ajouter des ID de client à chaque appel de collecte de données Analytics, qui était ensuite transféré à l’Audience Manager.

Avec Web SDK, ces identités doivent désormais être envoyées à l’Edge Network à l’aide d’un concept XDM spécial appelé [IdentityMap](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/profile/identitymap).

La transmission correcte des identités dans un mappage d’identités nécessite la compréhension des [espaces de noms d’identité](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/namespaces) et une attention particulière aux identités à transmettre, en particulier lors de l’envoi de données à un environnement de test Experience Platform. [Cet article](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-21305) décrit ces considérations et instructions.

Une fois que vous avez déterminé les identités à transmettre et à quel moment, suivez les guides d’utilisation de l’élément de données [!UICONTROL Identity map] **[!UICONTROL Identity map]** [ ](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/data-element-types#identity-map) dans Balises ou définissez-le manuellement comme indiqué dans la [présentation des données d’identité](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/identity/overview) pour vous aligner sur votre stratégie de déploiement Web SDK.

+++

## Configuration du transfert et de l’Audience Analytics côté serveur dans l’interface utilisateur du Gestionnaire de suites de rapports Analytics {#configure-ssf-analytics}

Si vous connaissez la fonctionnalité de [ transfert côté serveur](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf) d’Analytics, vous pouvez vous demander : &quot;*Dois-je désactiver le paramètre de transfert côté serveur dans l’interface utilisateur du Gestionnaire de suites de rapports Analytics pour empêcher l’envoi de données Analytics à l’Audience Manager deux fois ?*&quot;.

La réponse est non, vous ne devez pas désactiver ce paramètre. En voici la raison :

Lorsque ce paramètre est activé et que le module [!DNL AudienceManagement] est ajouté à la bibliothèque [!DNL AppMeasurement] de votre page, toutes les données envoyées à cette suite de rapports sont également transmises à l’Audience Manager.

Pour se conformer aux réglementations de confidentialité du RGPD, il existe des scénarios où les données peuvent être collectées dans Analytics mais pas en Audience Manager. En outre, il existe des cas impliquant des suites de rapports globales et des cas d’utilisation spécifiques à une région où certains appels de collecte de données ne doivent pas être envoyés à l’Audience Manager. Pour résoudre ce problème, Adobe a introduit un &quot;bouton de désactivation&quot; du transfert côté serveur.

Comme expliqué dans la page de conformité [Analytics et RGPD axée sur le transfert côté serveur](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/server-side-forwarding/ssf-gdpr), l’ajout de la variable contextuelle `cm.ssf=1` à un serveur de collecte de données Analytics empêche que cet appel de collecte de données ne soit transféré à l’Audience Manager.

Il existe deux raisons pour lesquelles vous ne devriez pas désactiver ce paramètre.

1. Lorsque le service d’Audience Manager est activé sur un flux de données, l’Edge Network ajoute la variable `cm.ssf` à toutes les demandes de collecte de données envoyées à Analytics. Cela empêche également l’envoi des données Analytics à Audience Manager. Tous les journaux Assurance utilisés pour valider la migration Analytics affichent la variable `cm.ssf=1` lorsque le service d’Audience Manager est activé dans le flux de données.
1. Ce paramètre permet également le flux de données pour l’intégration [!DNL Audience Analytics]. Comme indiqué dans la [présentation de l’Audience Analytics](https://experienceleague.adobe.com/en/docs/analytics/integration/audience-analytics/mc-audiences-aam), le transfert côté serveur est nécessaire pour cette intégration car la réponse de l’Audience Manager au serveur de collecte de données Analytics est ajoutée à l’accès Analytics avant le traitement. Un processus similaire se produit dans l’Edge Network. Lorsque le transfert côté serveur est activé, l’Edge Network ajoute les segments nécessaires de la réponse de l’Audience Manager aux données envoyées à Analytics.

En résumé, il est important que ce paramètre reste activé afin que l’Audience Analytics continue à fonctionner avec une implémentation du SDK Web et qu’aucune donnée ne soit comptabilisée deux fois dans l’Audience Manager.
