---
title: Migration de l’extension de balise d’Audience Manager vers l’extension de balise du SDK Web
description: Découvrez les étapes à suivre pour mettre à jour votre bibliothèque de collecte de données en vue de l’Audience Manager depuis l’extension de balise d’Audience Manager vers l’extension de balise du SDK Web.
source-git-commit: 1cf6a80bd5b7f583ea2511becf415b430ce2889e
workflow-type: tm+mt
source-wordcount: '1309'
ht-degree: 0%

---


# Mettez à jour votre bibliothèque de collecte de données pour l’Audience Manager de l’extension de balise d’Audience Manager vers l’extension de balise du SDK Web.

## Audience prévue

Cette page est destinée aux clients d’Audience Manager qui utilisent la variable [Extension de balise d’Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview) pour importer des données de collecte web dans Audience Manager. Pour les clients qui utilisent la bibliothèque JavaScript AppMeasurement, veuillez lire le guide sur la mise à jour de votre bibliothèque de collecte de données pour Audience Manager. [de la bibliothèque JavaScript d’AppMeasurement à la bibliothèque JavaScript du SDK Web](appmeasurement-to-web-sdk.md).

## Avantages et inconvénients de ce chemin de mise en oeuvre

L’utilisation de cette approche de migration présente des avantages et des inconvénients. Pesez soigneusement chaque option pour choisir la méthode qui convient le mieux à votre entreprise.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Aucune modification du code sur votre site**: puisque votre mise en oeuvre comporte déjà des balises installées, toutes les mises à jour de migration peuvent être effectuées dans l’interface des balises.</li><li>**Utilise votre mise en oeuvre existante**: cette approche ne nécessite pas de nouvelle mise en oeuvre. Bien qu’il nécessite de nouvelles actions de règle, vous pouvez réutiliser vos éléments de données et conditions de règle existants avec des modifications minimales.</li><li>**Ne nécessite pas de schéma**: pour cette étape de la migration vers le SDK Web, vous n’avez pas besoin d’un schéma XDM. Vous pouvez plutôt renseigner la variable `data` , qui envoie directement des données à Adobe Audience Manager. Une fois la migration vers le SDK Web terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage de flux de données pour remplir les champs XDM applicables. Si un schéma était requis à ce stade du processus de migration, votre organisation serait forcée d’utiliser un schéma XDM Adobe Audience Manager. L’utilisation de ce schéma rend plus difficile l’utilisation de votre propre schéma par votre entreprise à l’avenir.</li></ul> | <ul><li>**Dette technique de mise en oeuvre**: comme cette approche utilise une forme modifiée de votre mise en oeuvre existante, il peut être plus difficile de suivre la logique de mise en oeuvre et d’effectuer des modifications si nécessaire. Le code personnalisé peut être particulièrement difficile à déboguer.</li><li>**Nécessite un mapping pour envoyer des données à Platform**: lorsque votre entreprise est prête à utiliser Real-Time CDP, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action requiert que chaque champ de la variable `data` être une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM ; Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui n’implique pas d’effectuer des modifications de mise en oeuvre. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation lorsque vous disposez d’une implémentation existante à l’aide de l’extension de balise Adobe Audience Manager.

## Procédure de migration vers le SDK Web

Les étapes suivantes contiennent des objectifs concrets. Sélectionnez chaque étape pour obtenir des instructions détaillées sur la manière d’y parvenir.

+++**1. Création et configuration d’un flux de données**

Suivez les instructions ci-dessous pour créer un flux de données dans la collecte de données Adobe Experience Platform. Lorsque vous envoyez des données à ce flux de données, elles sont transférées à l’Audience Manager. À l’avenir, ce même flux de données transfère les données vers Real-Time CDP.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Data Collection]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionner **[!UICONTROL New Datastream]**.
1. Saisissez le nom de votre choix, puis sélectionnez **[!UICONTROL Save]**.
1. Une fois le flux de données créé, sélectionnez **[!UICONTROL Add Service]**.
1. Dans le menu déroulant du service, sélectionnez **[!UICONTROL Adobe Audience Manager]**.
1. Assurez-vous que la variable **[!UICONTROL Enable XDM Flattened Fields]** n’est pas cochée.

   ![Ajout d’un service Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à l’Audience Manager.

+++

+++**2. Ajout de l’extension SDK Web à la propriété de balise**

Cette section prépare votre balise pour l’essentiel de l’effort de migration qui se déroulera à l’étape suivante.

1. Sélectionnez l’icône de hamburger en haut à gauche de l’interface de Adobe Experience Platform, puis sélectionnez **[!UICONTROL Tags]**.
1. Sélectionnez la propriété de balise de votre choix.
1. Dans le volet de navigation de gauche de la propriété de balise, sélectionnez **[!UICONTROL Extensions]**.
1. Sélectionner **[!UICONTROL Catalog]** près de la partie supérieure pour afficher une liste de toutes les extensions disponibles.
1. Recherchez et sélectionnez le **[!UICONTROL Adobe Experience Platform Web SDK]** extension, puis sélectionnez **[!UICONTROL Install]** à droite.

   ![Catalogue](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Les paramètres de configuration de l’extension s’affichent. Recherchez la variable **[!UICONTROL Datastreams]** et sélectionnez l’environnement de test que vous utilisez et le flux de données que vous avez créé à l’étape précédente.

   ![Sélection des flux de données](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Sélectionner **[!UICONTROL Save]**.

Le SDK Web est désormais installé pour votre propriété de balise.

+++

+++**3. Création d’un élément de données d’objet de données**

L’élément de données d’objet de données fournit une structure intuitive pour configurer une charge utile que le SDK Web utilise pour envoyer à un flux de données. La plupart des règles que vous mettez à jour à l’étape suivante interagissent avec cet élément de données.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Data Elements]**.
1. Sélectionner **[!UICONTROL Add Data Element]**
1. Définissez les paramètres suivants pour l’élément de données :
   * **[!UICONTROL Name]**: tout ce que vous souhaitez, par exemple &quot;Couche de données&quot; ou &quot;Objet de données&quot;
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Data Element Type]**: [!UICONTROL Variable]
   * Les cases à cocher peuvent rester telles quelles.
1. Sur le côté droit, sélectionnez les paramètres suivants :
   * Bouton radio Propriété : **[!UICONTROL Data]**
   * **[!UICONTROL Solution]**: [!UICONTROL Adobe Audience Manager]
1. Sélectionner **[!UICONTROL Save]**.

   ![Création d’un élément de données](assets/create-data-element.png) {style="border:1px solid lightslategray"}

Votre propriété de balise dispose désormais de tous les éléments nécessaires pour mettre à jour chaque règle.

+++

+++**4. Mettez à jour les règles pour utiliser l’extension SDK Web au lieu de l’extension d’Audience Manager.**

Cette étape représente l’essentiel des efforts nécessaires pour migrer vers le SDK Web et nécessite des connaissances sur le fonctionnement de votre mise en oeuvre. Vous trouverez ci-dessous un exemple de modification d’une règle de balise standard. Mettez à jour toutes les règles de balise dans votre implémentation pour remplacer toutes les références à l’extension d’Audience Manager par l’extension SDK Web.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Rules]**.
1. Sélectionnez une règle à modifier.
1. Sélectionner l’action **[!UICONTROL Audience Manager - Set Variables]**
1. Notez toutes les variables d’Audience Manager définies dans cette règle. Incluez les deux variables définies dans les menus déroulants et les variables définies dans le code personnalisé.
1. Modifiez la variable [!UICONTROL Action Configuration] aux paramètres suivants :
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: variable de mise à jour
1. Assurez-vous que l’objet de données que vous avez créé à l’étape 3 est sélectionné dans la liste déroulante de droite, dans la variable **[!UICONTROL Data element]** champ .
1. Définissez les paires clé-valeur d’Audience Manager sur leurs valeurs respectives telles qu’elles ont été configurées dans l’extension d’Audience Manager.
1. Une fois que toute la logique de règle est répliquée à l’aide de l’extension SDK Web, sélectionnez **[!UICONTROL Keep Changes]**.
1. Répétez ces étapes pour chaque configuration d’action qui utilise l’extension de balise d’Audience Manager pour définir des valeurs.

Les étapes ci-dessus s’appliquent uniquement aux règles qui définissent des valeurs. Les étapes suivantes remplacent toutes les actions qui utilisent la fonction [!UICONTROL Action Configuration] [!UICONTROL Send Event].

1. Sélectionnez une règle qui envoie un événement SDK Web.
1. Sélection du type d’action **[!UICONTROL Send Event]**.
1. Modifiez la variable [!UICONTROL Action Configuration] aux paramètres suivants :
   * **[!UICONTROL Extension]**: [!UICONTROL Adobe Experience Platform Web SDK]
   * **[!UICONTROL Action type]**: [!UICONTROL Send event]
1. À droite, définissez les paramètres de l’action sur les éléments suivants :
   * **[!UICONTROL Type]**: utilisez **[!UICONTROL Web Webpagedetails Page Views]**.
   * **[!UICONTROL Data]**: sélectionnez l’objet de données que vous avez créé à l’étape 3.
1. Sélectionner **[!UICONTROL Keep Changes]**.
1. Répétez ces étapes pour chaque configuration d’action qui utilise l’Audience Manager pour envoyer un événement.

+++

+++**5. Publier les règles mises à jour**

La publication des règles mises à jour suit le même processus que toute autre modification apportée à la configuration des balises.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Publishing Flow]**.
1. Sélectionner **[!UICONTROL Add Library]**.
1. Donnez à cette balise un nom, par exemple &quot;Mettre à niveau vers le SDK Web&quot;.
1. Sélectionner **[!UICONTROL Add All Changed Resources]**.
1. Sélectionner **[!UICONTROL Save]**.
1. Le processus de publication affiche un point orange, indiquant qu’il est en cours de création. Une fois que le point devient vert, vos modifications sont disponibles dans votre environnement de développement.
1. Testez vos modifications dans votre environnement de développement pour vous assurer que toutes les règles se déclenchent correctement et que l’objet de données est rempli avec les valeurs attendues.
1. Une fois prête, envoyez la bibliothèque pour approbation, créez-la pour l’évaluation, puis approuvez et publiez-la pour la production.

   ![Flux de publication](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Désactiver l’extension d’Audience Manager**

Une fois la mise en oeuvre de votre balise entièrement migrée vers le SDK Web, vous pouvez désactiver l’extension d’Audience Manager.

1. Dans le volet de navigation de gauche de l’interface des balises, sélectionnez **[!UICONTROL Extensions]**.
1. Recherchez et sélectionnez le [!UICONTROL Audience Manager] extension . À droite, sélectionnez **[!UICONTROL Disable]**.
1. Suivez le même processus de publication ci-dessus pour publier la suppression de la [!UICONTROL Audience Manager] extension .
1. Une fois l’extension désactivée en production, vous pouvez la désinstaller entièrement. Sélectionnez l’extension, sélectionnez le menu à trois points à droite, puis sélectionnez **[!UICONTROL Uninstall]**.
1. Suivez le même processus de publication ci-dessus pour publier ces modifications en production.

+++

À ce stade, la mise en oeuvre de votre Audience Manager est entièrement migrée vers le SDK Web et est prête à passer à Real-Time CDP à l’avenir.
