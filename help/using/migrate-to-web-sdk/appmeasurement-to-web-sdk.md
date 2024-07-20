---
title: Mettez à jour votre bibliothèque de collecte de données pour Audience Manager de la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript du SDK Web.
description: Découvrez les étapes à suivre pour mettre à jour votre bibliothèque de collecte de données en vue de l’Audience Manager depuis la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript SDK Web.
exl-id: 9c771d6c-4cfa-4929-9a79-881d4e8643e4
source-git-commit: a50aaeb5e384685100dc3ecc1d6d45f1c41461d0
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---

# Mettez à jour votre bibliothèque de collecte de données pour Audience Manager de la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript SDK Web

## Audience prévue {#intended-audience}

Cette page est destinée aux clients d’Audience Manager qui utilisent AppMeasurement pour importer des données de collecte web dans Audience Manager. Pour les clients qui utilisent l’[ extension de balise d’Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), veuillez lire le guide sur la mise à jour de votre bibliothèque de collecte de données pour l’Audience Manager [ depuis l’extension de balise d’Audience Manager vers l’extension de balise du SDK Web](dil-extension-to-web-sdk.md).

## Avantages et inconvénients de ce chemin de mise en oeuvre

L’utilisation de cette approche de migration présente des avantages et des inconvénients. Pesez soigneusement chaque option pour choisir la méthode qui convient le mieux à votre entreprise.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Utilise votre mise en oeuvre existante** : bien que cette approche nécessite des modifications de mise en oeuvre, elle ne nécessite pas une mise en oeuvre entièrement nouvelle de toutes pièces. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation.</li><li>**Ne nécessite pas de schéma** : pour cette étape de migration vers le SDK Web, vous n’avez pas besoin d’un schéma XDM. Vous pouvez à la place renseigner l’objet `data` qui envoie directement des données à l’Audience Manager. Une fois la migration vers le SDK Web terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage de flux de données pour remplir les champs XDM applicables. Si un schéma était requis à ce stade du processus de migration, votre organisation serait forcée d’utiliser un schéma XDM d’Audience Manager. L’utilisation de ce schéma rend plus difficile l’utilisation de votre propre schéma par votre entreprise à l’avenir.</li></ul> | <ul><li>**Dette technique de mise en oeuvre** : comme cette approche utilise une forme modifiée de votre mise en oeuvre existante, il peut être plus difficile de suivre la logique de mise en oeuvre et d’effectuer des modifications ultérieurement, si nécessaire.</li><li>**Nécessite un mappage pour envoyer des données à Platform** : lorsque votre organisation est prête à utiliser Real-Time CDP, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action nécessite que chaque champ de l’objet `data` soit une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM. Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui n’implique pas d’effectuer des modifications de mise en oeuvre. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation dans les scénarios suivants :

* Vous disposez d’une mise en oeuvre existante à l’aide de la bibliothèque JavaScript Adobe Analytics AppMeasurement. Si vous disposez d’une implémentation à l’aide de l’extension de balise d’Audience Manager, suivez la section [Migration de l’extension de balise d’Audience Manager vers l’extension de balise du SDK Web](dil-extension-to-web-sdk.md) à la place.
* Vous envisagez d’utiliser Real-Time CDP à l’avenir, mais ne souhaitez pas remplacer entièrement votre mise en oeuvre d’Audience Manager par une mise en oeuvre de SDK Web. Le remplacement de votre implémentation de A à Z sur le SDK Web nécessite le plus d’efforts, mais offre également l’architecture d’implémentation à long terme la plus viable. Si votre entreprise est prête à entreprendre une mise en oeuvre propre du SDK Web, consultez la [documentation du SDK Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) pour plus d’informations.

## Procédure de migration vers le SDK Web

Les étapes suivantes contiennent des objectifs concrets. Cliquez sur chaque étape pour obtenir des instructions détaillées sur la manière d’y parvenir.

+++**1. Création et configuration d’un flux de données**

Créez un flux de données dans la collecte de données Adobe Experience Platform. Lorsque vous envoyez des données à ce flux de données, elles sont transférées à l’Audience Manager. À l’avenir, ce même flux de données transfère les données vers Real-Time CDP.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Data Collection]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionnez **[!UICONTROL New Datastream]**.
1. Saisissez le nom de votre choix, puis sélectionnez **[!UICONTROL Save]**.
1. Une fois le flux de données créé, sélectionnez **[!UICONTROL Add Service]**.
1. Dans le menu déroulant du service, sélectionnez **[!UICONTROL Audience Manager]**.

   ![Ajouter un service d’Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à l’Audience Manager. Notez l’identifiant de la banque de données, car cet identifiant est requis lors de la configuration du SDK Web dans le code.

+++

+++**2. Installation de la bibliothèque JavaScript du SDK Web**

Voir [Installation du SDK Web à l’aide de la bibliothèque JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) pour plus d’informations et les blocs de code à utiliser. Référencez la dernière version de `alloy.js` afin que ses appels de méthode puissent être utilisés.

+++

+++**3. Configuration du SDK Web**

Configurez votre mise en oeuvre pour qu’elle pointe vers le flux de données créé à l’étape 1 à l’aide de la commande SDK Web [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) . La commande `configure` doit être définie sur chaque page afin que vous puissiez l’inclure avec le code d’installation de la bibliothèque.

Utilisez les propriétés [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) et [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) dans la commande du SDK Web `configure` :

* Définissez le `edgeConfigId` sur l’identifiant de la banque de données récupéré à l’étape précédente.
* Définissez le `orgId` sur l’ID d’organisation IMS de votre organisation.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Vous pouvez éventuellement définir d’autres propriétés dans la commande [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) en fonction des exigences d’implémentation de votre entreprise.

+++

+++**4. Mise à jour de la logique de code pour utiliser une charge utile JSON**

Modifiez la mise en oeuvre de votre Audience Manager afin qu’elle ne repose pas sur `AppMeasurement.js` ou l’objet `s`. Définissez plutôt des variables dans un objet JavaScript correctement formaté, qui est converti en objet JSON lorsqu’il est envoyé à l’Adobe. Disposer d’une [couche de données](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) sur votre site aide considérablement lors de la définition de valeurs, car vous pouvez continuer à référencer ces mêmes valeurs.

Pour envoyer des données à Audience Manager, la charge utile du SDK Web doit utiliser `data.__adobe.audiencemanager` avec toutes les variables d’analyse définies dans cet objet. Les variables de cet objet partagent les mêmes noms et formats que leurs équivalents de variable d’AppMeasurement. Par exemple, si vous définissez la variable `products`, ne la divisez pas en objets individuels comme vous le feriez avec XDM. Au lieu de cela, incluez-le comme chaîne si vous définissez la variable `s.products` :

```json
{
  "data": {
    "__adobe": {
      "audiencemanager": {
        "products": "Shoes,Men's sneakers,1,49.99"
      }
    }
  }
}
```

En fin de compte, cette payload contient toutes les valeurs souhaitées et toutes les références à l’objet `s` dans votre mise en oeuvre sont supprimées. Vous pouvez utiliser n’importe quelle ressource fournie par JavaScript pour définir cet objet de charge utile, y compris la notation par points pour définir des valeurs individuelles.

```js
// Define the payload and set objects within it
var dataObj = {data: {__adobe: {audiencemanager: {}}}};
dataObj.data.__adobe.audiencemanager.pageName = window.document.title;
dataObj.data.__adobe.audiencemanager.eVar1 = "Example value";

// Alternatively, set values in an object and use a spread operator to achieve identical results
var a = new Object;
a.pageName = window.document.title;
a.eVar1 = "Example value";
var dataObj = {data:{__adobe:{audiencemanager:{...a}}}};
```

+++

+++**5. Mise à jour des appels de méthode pour utiliser le SDK Web**

Mettez à jour toutes les instances où vous appelez [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) et [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), en les remplaçant par la commande [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) . Trois scénarios sont à prendre en compte :

* **Suivi des pages vues** : remplacez l’appel de suivi des pages vues par la commande SDK Web `sendEvent` :

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Suivi automatique des liens** : la propriété de configuration [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) est activée par défaut. Il définit automatiquement les variables de suivi des liens correctes pour envoyer des données à l’Audience Manager. Si vous souhaitez désactiver le suivi automatique des liens, définissez cette propriété sur `false` dans la commande [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview).

* **Suivi manuel des liens** : le SDK Web ne comporte pas de commandes distinctes entre les appels pageview et non pageview. Précisez cette distinction dans l’objet de charge utile.

  ```js
  // If your current implementation has this line of code:
  s.tl(true,"o","Example custom link");
  
  // Replace it with these lines of code. Add the required fields to the dataObj object.
  dataObj.data.__adobe.audiencemanager.linkName = "Example custom link";
  dataObj.data.__adobe.audiencemanager.linkType = "o";
  dataObj.data.__adobe.audiencemanager.linkURL = "https://example.com";
  alloy("sendEvent", dataObj);
  ```

+++

+++**6. Validation et publication des modifications**

Une fois que vous avez supprimé toutes les références à AppMeasurement et à l’objet `s`, publiez vos modifications dans votre environnement de développement pour vérifier que la nouvelle mise en oeuvre fonctionne. Une fois que vous avez vérifié que tout fonctionne correctement, vous pouvez publier vos mises à jour en production.

Si la migration est effectuée correctement, `AppMeasurement.js` n’est plus nécessaire sur votre site et toutes les références à ce script peuvent être supprimées.

+++

À ce stade, la mise en oeuvre de votre Audience Manager est entièrement migrée vers le SDK Web et est prête à passer à Real-Time CDP à l’avenir.
