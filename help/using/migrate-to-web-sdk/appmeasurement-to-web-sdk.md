---
title: Mettez à jour votre bibliothèque de collecte de données pour Audience Manager de la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript du SDK Web.
description: Découvrez les étapes à suivre pour mettre à jour votre bibliothèque de collecte de données en vue de l’Audience Manager depuis la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript du SDK Web.
source-git-commit: b0c35d79a07b481e332ddf8f4aedab5484416a51
workflow-type: tm+mt
source-wordcount: '1168'
ht-degree: 0%

---


# Mettez à jour votre bibliothèque de collecte de données pour Audience Manager de la bibliothèque JavaScript AppMeasurement vers la bibliothèque JavaScript SDK Web.

## Audience prévue {#intended-audience}

Cette page est destinée aux clients d’Audience Manager qui utilisent AppMeasurement pour importer des données de collecte web dans Audience Manager. Pour les clients qui utilisent la variable [Extension de balise d’Audience Manager](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/audience-manager/overview), veuillez lire le guide sur la mise à jour de votre bibliothèque de collecte de données pour l’Audience Manager [de l’extension de balise d’Audience Manager à l’extension de balise SDK Web](dil-extension-to-web-sdk.md).

## Avantages et inconvénients de ce chemin de mise en oeuvre

L’utilisation de cette approche de migration présente des avantages et des inconvénients. Pesez soigneusement chaque option pour choisir la méthode qui convient le mieux à votre entreprise.

| Avantages | Inconvénients |
| --- | --- |
| <ul><li>**Utilise votre mise en oeuvre existante**: bien que cette approche nécessite quelques modifications de mise en oeuvre, elle ne nécessite pas une mise en oeuvre entièrement nouvelle de toutes pièces. Vous pouvez utiliser votre couche de données et votre code existants avec un minimum de modifications de la logique d’implémentation.</li><li>**Ne nécessite pas de schéma**: pour cette étape de la migration vers le SDK Web, vous n’avez pas besoin d’un schéma XDM. Vous pouvez plutôt renseigner la variable `data` , qui envoie directement des données à l’Audience Manager. Une fois la migration vers le SDK Web terminée, vous pouvez créer un schéma pour votre organisation et utiliser le mappage de flux de données pour remplir les champs XDM applicables. Si un schéma était requis à ce stade du processus de migration, votre organisation serait forcée d’utiliser un schéma XDM d’Audience Manager. L’utilisation de ce schéma rend plus difficile l’utilisation de votre propre schéma par votre entreprise à l’avenir.</li></ul> | <ul><li>**Dette technique de mise en oeuvre**: comme cette approche utilise une forme modifiée de votre mise en oeuvre existante, il peut être plus difficile de suivre la logique de mise en oeuvre et d’effectuer des modifications ultérieurement, si nécessaire.</li><li>**Nécessite un mapping pour envoyer des données à Platform**: lorsque votre entreprise est prête à utiliser Real-Time CDP, vous devez envoyer des données à un jeu de données dans Adobe Experience Platform. Cette action requiert que chaque champ de la variable `data` être une entrée dans l’outil de mappage de flux de données qui l’affecte à un champ de schéma XDM ; Le mappage ne doit être effectué qu’une seule fois pour ce workflow, ce qui n’implique pas d’effectuer des modifications de mise en oeuvre. Cependant, il s’agit d’une étape supplémentaire qui n’est pas requise lors de l’envoi de données dans un objet XDM.</li></ul> |

Adobe recommande de suivre ce chemin d’implémentation dans les scénarios suivants :

* Vous disposez d’une mise en oeuvre existante à l’aide de la bibliothèque JavaScript Adobe Analytics AppMeasurement. Si vous disposez d’une mise en oeuvre à l’aide de l’extension de balise d’Audience Manager, suivez [Migration de l’extension de balise d’Audience Manager vers l’extension de balise du SDK Web](dil-extension-to-web-sdk.md) au lieu de .
* Vous envisagez d’utiliser Real-Time CDP à l’avenir, mais ne souhaitez pas remplacer entièrement votre mise en oeuvre d’Audience Manager par une mise en oeuvre de SDK Web. Le remplacement de votre implémentation de A à Z sur le SDK Web nécessite le plus d’efforts, mais offre également l’architecture d’implémentation à long terme la plus viable. Si votre entreprise est disposée à entreprendre une implémentation propre du SDK Web, reportez-vous à la section [Documentation du SDK Web](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/home) pour plus d’informations.

## Procédure de migration vers le SDK Web

Les étapes suivantes contiennent des objectifs concrets. Cliquez sur chaque étape pour obtenir des instructions détaillées sur la manière d’y parvenir.

+++**1. Création et configuration d’un flux de données**

Créez un flux de données dans la collecte de données Adobe Experience Platform. Lorsque vous envoyez des données à ce flux de données, elles sont transférées à l’Audience Manager. À l’avenir, ce même flux de données transfère les données vers Real-Time CDP.

1. Accédez à [experience.adobe.com](https://experience.adobe.com) et connectez-vous à l’aide de vos informations d’identification.
1. Utilisez la page d’accueil ou le sélecteur de produits en haut à droite pour accéder à **[!UICONTROL Data Collection]**.
1. Dans le volet de navigation de gauche, sélectionnez **[!UICONTROL Datastreams]**.
1. Sélectionner **[!UICONTROL New Datastream]**.
1. Saisissez le nom de votre choix, puis sélectionnez **[!UICONTROL Save]**.
1. Une fois le flux de données créé, sélectionnez **[!UICONTROL Add Service]**.
1. Dans le menu déroulant du service, sélectionnez **[!UICONTROL Audience Manager]**.

   ![Ajout d’un service Audience Manager](assets/add-service.png) {style="border:1px solid lightslategray"}

Votre flux de données est maintenant prêt à recevoir et à transmettre des données à l’Audience Manager. Notez l’identifiant de la banque de données, car cet identifiant est requis lors de la configuration du SDK Web dans le code.

+++

+++**2. Installation de la bibliothèque JavaScript du SDK Web**

Voir [Installation du SDK Web à l’aide de la bibliothèque JavaScript](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/install/library) pour plus de détails et des blocs de code à utiliser. Référencez la dernière version de `alloy.js` ses appels de méthode peuvent donc être utilisés.

+++

+++**3. Configuration du SDK Web**

Configurez votre mise en oeuvre pour qu’elle pointe vers le flux de données créé à l’étape 1 à l’aide du SDK Web. [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) . La variable `configure` doit être définie sur chaque page afin que vous puissiez l’inclure avec le code d’installation de la bibliothèque.

Utilisez la variable [`edgeConfigId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/edgeconfigid) et [`orgId`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid) propriétés dans le SDK Web `configure` command :

* Définissez la variable `edgeConfigId` à l’identifiant du flux de données récupéré à l’étape précédente.
* Définissez la variable `orgId` à l’ID d’organisation IMS de votre entreprise.

```js
alloy("configure", {
    "edgeConfigId": "ebebf826-a01f-4458-8cec-ef61de241c93",
    "orgId": "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Vous pouvez éventuellement définir d’autres propriétés dans la variable [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) en fonction des exigences de mise en oeuvre de votre entreprise.

+++

+++**4. Mise à jour de la logique de code pour utiliser une payload JSON**

Modifier la mise en oeuvre de votre Audience Manager afin qu’elle ne repose pas sur `AppMeasurement.js` ou le `s` . Définissez plutôt des variables dans un objet JavaScript correctement formaté, qui est converti en objet JSON lorsqu’il est envoyé à Adobe. Pour [couche de données](https://experienceleague.adobe.com/en/docs/analytics/implementation/prepare/data-layer) sur votre site vous aide considérablement lors de la définition de valeurs, car vous pouvez continuer à référencer ces mêmes valeurs.

Pour envoyer des données à Audience Manager, la charge utile du SDK Web doit utiliser `data.__adobe.audiencemanager` avec toutes les variables analytics définies dans cet objet. Les variables de cet objet partagent les mêmes noms et formats que leurs équivalents de variable d’AppMeasurement. Par exemple, si vous définissez la variable `products` , ne le divisez pas en objets individuels comme vous le feriez avec XDM. Au lieu de cela, incluez-le comme chaîne si vous avez défini la variable `s.products` variable :

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

En fin de compte, cette payload contient toutes les valeurs souhaitées et toutes les références au `s` dans votre mise en oeuvre sont supprimés. Vous pouvez utiliser n’importe quelle ressource fournie par JavaScript pour définir cet objet de payload, y compris la notation par points pour définir des valeurs individuelles.

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

Mettre à jour toutes les instances où vous appelez [`s.t()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/t-method) et [`s.tl()`](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/functions/tl-method), en les remplaçant par [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) . Trois scénarios sont à prendre en compte :

* **Suivi des pages vues**: remplacez l’appel de suivi des pages vues par le SDK Web. `sendEvent` command :

  ```js
  // If your current implementation has this line of code:
  s.t();
  
  // Replace it with this line of code. The dataObj object contains the variables to send.
  alloy("sendEvent", dataObj);
  ```

* **Suivi automatique des liens**: la variable [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) La propriété de configuration est activée par défaut. Il définit automatiquement les variables de suivi des liens correctes pour envoyer des données à l’Audience Manager. Pour désactiver le suivi automatique des liens, définissez cette propriété sur `false` dans la fonction [`configure`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) .

* **Suivi manuel des liens**: le SDK Web ne comporte pas de commandes distinctes entre les appels pageview et non pageview. Précisez cette distinction dans l’objet de charge utile.

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

Une fois que vous avez supprimé toutes les références à AppMeasurement et au `s` , publiez vos modifications dans votre environnement de développement pour vérifier que la nouvelle mise en oeuvre fonctionne. Une fois que vous avez vérifié que tout fonctionne correctement, vous pouvez publier vos mises à jour en production.

Si la migration est correcte, `AppMeasurement.js` n’est plus nécessaire sur votre site et toutes les références à ce script peuvent être supprimées.

+++

À ce stade, la mise en oeuvre de votre Audience Manager est entièrement migrée vers le SDK Web et est prête à passer à Real-Time CDP à l’avenir.
