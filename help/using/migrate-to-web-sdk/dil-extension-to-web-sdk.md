---
title: Migration de l’extension de balise Audience Manager vers l’extension de balise Web SDK
description: Découvrez les étapes à suivre pour mettre à jour votre bibliothèque de collecte de données pour Audience Manager de l’extension de balise Audience Manager à l’extension de balise Web SDK
exl-id: 7f0486db-4511-4311-90df-290580fdcd78
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---

# Mettez à jour votre bibliothèque de collecte de données pour Audience Manager de l’extension de balise Audience Manager vers l’extension de balise Web SDK

## Audience prévue

Cette page est destinée aux clients Audience Manager qui utilisent l’extension de balise [Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) pour importer des données de collecte web dans Audience Manager. Pour les clients qui utilisent la bibliothèque AppMeasurement JavaScript, veuillez lire le guide sur la mise à jour de votre bibliothèque de collecte de données pour Audience Manager [de la bibliothèque AppMeasurement JavaScript à la bibliothèque Web SDK JavaScript](appmeasurement-to-web-sdk.md).

## Avantages et inconvénients de ce chemin de mise en œuvre

L’utilisation de cette approche de migration présente à la fois des avantages et des inconvénients. Évaluez soigneusement chaque option pour décider quelle approche est la meilleure pour votre organisation.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Aucune modification de code sur votre site** : puisque des balises sont déjà installées dans votre implémentation, toutes les mises à jour de migration peuvent être effectuées dans l’interface des balises.</li><li>**Utilise votre implémentation existante** : cette approche ne nécessite pas de nouvelle implémentation. Bien qu’il nécessite de nouvelles actions de règle, vous pouvez réutiliser vos éléments de données et conditions de règle existants avec un minimum de modifications.</li><li>**Ne nécessite pas de schéma** : pour cette étape de la migration vers le Web SDK, vous n’avez pas besoin de schéma XDM. Vous pouvez plutôt renseigner l’objet `data` , qui envoie directement les données à Adobe Audience Manager. Une fois la migration vers Web SDK terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage des flux de données pour renseigner les champs XDM applicables. Si un schéma était requis à cette étape du processus de migration, votre organisation serait forcée d’utiliser un schéma XDM Adobe Audience Manager. L’utilisation de ce schéma rend plus difficile, pour votre organisation, l’utilisation de votre propre schéma à l’avenir.</li></ul> | <ul><li>**Dette technique d’implémentation** : étant donné que cette approche utilise une forme modifiée de votre implémentation existante, il peut être plus difficile de suivre la logique d’implémentation et d’effectuer des modifications si nécessaire. Le code personnalisé peut être particulièrement difficile à déboguer.</li><li>**Nécessite un mappage pour envoyer des données à Platform** : lorsque votre organisation est prête à utiliser Real-Time CDP, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet `data` soit une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow et n’implique aucune modification de l’implémentation. Cependant, il s’agit d’une étape supplémentaire qui n’est pas nécessaire lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation lorsque vous disposez d’une implémentation existante à l’aide de l’extension de balise Adobe Audience Manager.

## Étapes requises pour migrer vers Web SDK

Les étapes suivantes contiennent des objectifs concrets à atteindre. Sélectionnez chaque étape pour obtenir des instructions détaillées sur la manière de procéder.

+++**1. Créer et configurer un flux de données**

Suivez les instructions ci-dessous pour créer un flux de données dans la collecte de données Adobe Experience Platform. Lorsque vous envoyez des données à ce flux de données, il transfère les données vers Audience Manager. À l’avenir, ce même flux de données transfèrera des données à Real-Time CDP.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Data Collection]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionnez **[!UICONTROL New Datastream]**.
1. Saisissez le nom souhaité, puis sélectionnez **[!UICONTROL Save]**.
1. Une fois le flux de données créé, sélectionnez **[!UICONTROL Add Service]**.
1. Dans le menu déroulant Service, sélectionnez **[!UICONTROL Adobe Audience Manager]**.
1. Assurez-vous que l’option **[!UICONTROL Enable XDM Flattened Fields]** n’est pas cochée.

   ![Ajouter un service Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à Audience Manager.

+++

+++**2. Ajoutez l’extension Web SDK à la propriété de balise**

Cette section prépare votre balise pour l’essentiel de la migration effectuée à l’étape suivante.

1. Sélectionnez l’icône hamburger en haut à gauche de l’interface de Adobe Experience Platform, puis sélectionnez **[!UICONTROL Tags]**.
1. Sélectionnez la propriété de balise de votre choix.
1. Dans le volet de navigation de gauche de la propriété de balise, sélectionnez **[!UICONTROL Extensions]**.
1. Sélectionnez **[!UICONTROL Catalog]** en haut pour afficher la liste de toutes les extensions disponibles.
1. Recherchez et sélectionnez l’extension **[!UICONTROL Adobe Experience Platform Web SDK]**, puis sélectionnez **[!UICONTROL Install]** sur le côté droit.

   ![Catalogue](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Les paramètres de configuration de l’extension s’affichent. Recherchez la section **[!UICONTROL Datastreams]** et sélectionnez le sandbox que vous utilisez et le flux de données que vous avez créé à l’étape précédente.

   ![Sélection du flux de données](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Sélectionnez **[!UICONTROL Save]**.

Le SDK Web est désormais installé sur la propriété de balise.

+++

+++**3. Créez un élément de données d’objet de données**

L’élément de données d’objet de données fournit un cadre intuitif pour configurer une payload que le SDK Web utilise pour envoyer à un flux de données. La plupart des règles que vous mettez à jour à l’étape suivante interagissent avec cet élément de données.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Data Elements]**.
1. Sélectionner un **[!UICONTROL Add Data Element]**
1. Donnez à l’élément de données les paramètres suivants :
   * **[!UICONTROL Name]** : tout ce que vous souhaitez, tel que « Couche de données » ou « Objet de données »
   * **[!UICONTROL Extension]** : [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]** : [!UICONTROL Variable]
   * Les cases à cocher peuvent rester telles quelles.
1. Sur le côté droit, sélectionnez les paramètres suivants :
   * Bouton radio de propriété : **[!UICONTROL Data]**
   * **[!UICONTROL Solution]** : [!UICONTROL Adobe Audience Manager]
1. Sélectionnez **[!UICONTROL Save]**.

   ![Créer un élément de données](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Votre propriété de balise dispose désormais de tout ce dont vous avez besoin pour mettre à jour chaque règle.

+++

+++**4. Mettez à jour les règles pour utiliser l’extension Web SDK au lieu de l’extension Audience Manager**

Cette étape contient l’essentiel de l’effort requis pour migrer vers Web SDK et nécessite des connaissances sur le fonctionnement de votre implémentation. Vous trouverez ci-dessous un exemple de modification d’une règle de balise standard. Mettez à jour toutes les règles de balise dans votre mise en œuvre pour remplacer toutes les références à l’extension Audience Manager par l’extension Web SDK.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Rules]**.
1. Sélectionnez une règle à modifier.
1. Sélectionner le **[!UICONTROL Audience Manager - Set Variables]** d’action
1. Notez toutes les variables Audience Manager définies dans cette règle. Incluez les variables définies dans les menus déroulants et les variables définies dans le code personnalisé.
1. Modifiez les paramètres du [!UICONTROL Action Configuration] comme suit :
   * **[!UICONTROL Extension]** : [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]** : mettre à jour la variable
1. Assurez-vous que l’objet de données que vous avez créé à l’étape 3 est sélectionné dans la liste déroulante de droite, dans le champ **[!UICONTROL Data element]** .
1. Définissez les paires clé-valeur Audience Manager sur leurs mêmes valeurs respectives telles qu’elles ont été configurées dans l’extension Audience Manager.
1. Une fois que toute la logique des règles est répliquée à l’aide de l’extension Web SDK, sélectionnez **[!UICONTROL Keep Changes]**.
1. Répétez ces étapes pour chaque configuration d’action qui utilise l’extension de balise Audience Manager pour définir des valeurs.

Les étapes ci-dessus s’appliquent uniquement aux règles qui définissent des valeurs. Les étapes suivantes remplacent toutes les actions qui utilisent le [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Sélectionnez une règle qui envoie un événement Web SDK.
1. Sélectionnez le type d’action **[!UICONTROL Send Event]**.
1. Modifiez les paramètres du [!UICONTROL Action Configuration] comme suit :
   * **[!UICONTROL Extension]** : [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]** : [!UICONTROL Send event]
1. Sur la droite, modifiez les paramètres d’action comme suit :
   * **[!UICONTROL Type]** : utilisez **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]** : sélectionnez l’objet de données que vous avez créé à l’étape 3.
1. Sélectionnez **[!UICONTROL Keep Changes]**.
1. Répétez ces étapes pour chaque configuration d’action qui utilise Audience Manager pour envoyer un événement.

+++

+++**5. Publiez les règles mises à jour**

La publication des règles mises à jour suit le même workflow que toute autre modification de votre configuration de balises.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Publishing Flow]**.
1. Sélectionnez **[!UICONTROL Add Library]**.
1. Attribuez un nom à cette validation de balise, par exemple « Mettre à niveau vers Web SDK ».
1. Sélectionnez **[!UICONTROL Add All Changed Resources]**.
1. Sélectionnez **[!UICONTROL Save]**.
1. Le workflow de publication affiche un point orange, indiquant qu’il est en cours de création. Une fois le point vert affiché, vos modifications sont disponibles dans votre environnement de développement.
1. Testez les modifications apportées à votre environnement de développement pour vous assurer que toutes les règles se déclenchent correctement et que l’objet de données est renseigné avec les valeurs attendues.
1. Une fois prête, envoyez la bibliothèque pour approbation, créez-la vers l’évaluation, puis approuvez-la et publiez-la en production.

   ![ Flux de publication ](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Désactivez l’extension Audience Manager**

Une fois la migration complète de votre implémentation de balises vers le Web SDK terminée, vous pouvez désactiver l’extension Audience Manager.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Extensions]**.
1. Recherchez et sélectionnez l’extension [!UICONTROL Audience Manager]. Sur la droite, sélectionnez **[!UICONTROL Disable]**.
1. Suivez le même workflow de publication ci-dessus pour publier la suppression de l’extension [!UICONTROL Audience Manager].
1. Une fois l’extension désactivée en production, vous pouvez la désinstaller entièrement. Sélectionnez l’extension, puis le menu à trois points sur la droite, puis sélectionnez **[!UICONTROL Uninstall]**.
1. Suivez le même workflow de publication ci-dessus pour publier ces modifications en production.

+++

À ce stade, votre mise en œuvre Audience Manager est entièrement migrée vers Web SDK et est prête à passer à Real-Time CDP à l’avenir.
