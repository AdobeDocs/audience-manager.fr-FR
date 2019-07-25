---
description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation algorithmique, également appelés modélisation ressemblante. Les fonctionnalités du modèle se trouvent dans Données d'audience > Modèles.
keywords: poids relatif
seo-description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation algorithmique, également appelés modélisation ressemblante. Les fonctionnalités du modèle se trouvent dans Données d'audience > Modèles.
seo-title: A propos des modèles algorithmiques
solution: Audience Manager
title: A propos des modèles algorithmiques
topic: API DIL
uuid: 39441 e 72-5316-453 d -9 aff -0 e 0 b 633 aabcd
translation-type: tm+mt
source-git-commit: 157e70906b80bd0a23ba6e7721d2c456d378ffb5

---


# About Algorithmic Models {#about-algorithmic-models}

Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation algorithmique, également appelés modélisation ressemblante. Model features are located in **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Understanding Algorithmic Models {#understanding-models}

The sections below represent a review of algorithmic modeling in [!DNL Audience Manager]. Ils décrivent le fonctionnement de la modélisation, les avantages et le flux de travaux.

<!-- understanding-models.xml -->

## Find New Users with Algorithmic Modeling {#find-new-users}

La modélisation algorithmique permet de découvrir de nouvelles audiences uniques grâce à l'analyse automatisée des données. Le processus commence lorsque vous sélectionnez une caractéristique ou un segment, un intervalle de temps et des sources de données propriétaires et tierces. Vos choix fournissent les entrées du modèle algorithmique. Lorsque le processus d'analyse est exécuté, il recherche les utilisateurs éligibles en fonction des caractéristiques partagées de la population sélectionnée. Upon completion, this data is available in [Trait Builder](../../features/traits/about-trait-builder.md) where you can use it to create traits based on [accuracy and reach](../../features/traits/trait-accuracy-reach.md). De plus, vous pouvez créer des segments qui combinent des caractéristiques algorithmiques à des caractéristiques basées sur des règles et ajouter d'autres exigences de qualification à l'aide d'expressions booléennes et d'opérateurs de comparaison. La modélisation algorithmique permet d'extraire une valeur dynamique de toutes les données de caractéristiques disponibles.

## Avantages {#advantages}

The major benefits of using [!DNL Audience Manager] modeling include:

* **Précision des données :** L'algorithme s'exécute régulièrement, ce qui permet de conserver les résultats à jour et pertinents.
* **Automatisation :** Vous n'avez pas besoin de gérer un jeu important de règles statiques. L'algorithme recherche les audiences.
* **Gagnez du temps et réduisez l'effort :** Avec notre processus de modélisation, il n'est pas nécessaire de déterminer les caractéristiques/segments susceptibles de fonctionner ou de consacrer du temps aux campagnes pour découvrir de nouvelles audiences. Le modèle peut le faire pour vous.
* **Fiabilité :** La modélisation fonctionne avec les processus de détection et de qualification côté serveur qui évaluent vos propres données et les données tierces sélectionnées auxquelles vous avez accès. Cela signifie que vous n'avez pas besoin de voir les visiteurs de votre site pour les qualifier pour une caractéristique.

## Processus{#workflow}

You manage models in **[!UICONTROL Audience Data > Models]**. À un niveau élevé, le processus implique ce qui suit :

* Sélectionnez les données de base que l'algorithme doit évaluer. This includes a trait or segment, time range, and data sources (your own data and third-party data you already have access to through [!DNL Audience Manager]). Dans le processus de création de modèle, vous pouvez exclure les caractéristiques que vous ne souhaitez pas affecter avec votre modèle.
* Enregistrez votre modèle. Une fois enregistrée, le processus d'évaluation algorithmique s'exécute automatiquement. Notez toutefois que cette procédure peut prendre jusqu'à 7 jours. [!DNL Audience Manager] vous envoie un courriel lorsque l'algorithme est terminé et que des résultats sont disponibles pour la création de caractéristiques.
* Build algorithmic traits in [!UICONTROL Trait Builder].
* Combine traits into segments in [!UICONTROL Segment Builder].
* Créez et envoyez des données de segment à une destination.

## Résolution des problèmes {#troubleshooting}

Nous désactivons tout modèle algorithmique qui ne génère pas de données pour trois exécutions consécutives. Notez que vous ne pouvez pas redéfinir l'état du modèle sur Actif après. Pour vous assurer que les modèles génèrent des données, nous vous recommandons de créer des modèles à partir des sources de données avec des caractéristiques suffisantes pour accumuler des données.

>[!MORE_ LIKE_ THIS]
>
>* [Destinations](../../features/destinations/destinations.md)
>* [Caractéristiques](../../features/traits/trait-details-page.md)
>* [Segments](../../features/segments/segments-purpose.md)


## Understanding TraitWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] est un algorithme propriétaire conçu pour découvrir automatiquement de nouvelles caractéristiques. It compares trait data from your current traits and segments against all other first and third-party data that you have access to through [!DNL Audience Manager]. Refer to this section for a description of the [!UICONTROL TraitWeight] algorithmic discovery process.

<!-- traitweight.xml -->

![](assets/algo_model.png)

The following steps describe the [!UICONTROL TraitWeight] evaluation process.

### Étape 1 : Créer une ligne de base pour la comparaison des caractéristiques

To build a baseline, [!UICONTROL TraitWeight] measures all the traits associated with an audience for a 30, 60, or 90 day interval. Ensuite, il classe les caractéristiques en fonction de leur fréquence et de leur corrélation. Le nombre de fréquences mesure la common. La corrélation mesure la probabilité qu'une caractéristique soit présente uniquement dans l'audience de ligne de base. Les caractéristiques qui semblent souvent présenter un fort taux de similitude, une caractéristique importante utilisée pour définir un score pondéré, sont associées à des caractéristiques découvertes dans les sources de données sélectionnées.

### Étape 2 : Rechercher les mêmes caractéristiques dans la source de données

Après avoir créé une ligne de base pour la comparaison, l'algorithme recherche des caractéristiques identiques dans les sources de données sélectionnées. In this step, [!UICONTROL TraitWeight] performs a frequency count of all discovered traits and compares them to the baseline. Cependant, contrairement à la ligne de base, les caractéristiques peu courantes sont classées plus souvent que celles qui apparaissent plus souvent. On dit que des caractéristiques rares présentent un degré élevé de spécificité. [!UICONTROL TraitWeight] évalue les combinaisons de caractéristiques de ligne de base communes et de caractéristiques de source de données peu courantes (très spécifiques) comme des caractéristiques plus influentes ou souhaitables que les caractéristiques communes aux deux ensembles de données. En fait, notre modèle reconnaît ces grandes caractéristiques communes et n'attribue pas de priorité excessive aux ensembles de données avec des corrélations élevées. Les caractéristiques rares obtiennent une priorité plus élevée car elles sont plus susceptibles de représenter de nouveaux utilisateurs uniques que les caractéristiques présentant un fort taux de similitude entre le panorama.

### Étape 3 : Attribuer une pondération

In this step, [!UICONTROL TraitWeight] ranks newly discovered traits in order of influence or desirability. L'échelle de poids est un pourcentage qui s'exécute de 0 à 100 %. Les caractéristiques plus proches de 100 % signifient qu'elles correspondent davantage à l'audience de la population de ligne de base. En outre, les caractéristiques lourdement pondérées sont précieuses car elles représentent de nouveaux utilisateurs uniques qui peuvent se comporter de la même manière que l'audience de ligne de base établie. Remember, [!UICONTROL TraitWeight] considers traits with high commonality in the baseline and high specificity in the compared data sources to be more valuable than traits common in each data set.

### Étape 4 : Utilisateurs scores

Chaque utilisateur des sources de données sélectionnées reçoit un score d'utilisateur égal à la somme de tous les poids des caractéristiques influentes sur le profil de l'utilisateur. Les scores utilisateur sont ensuite normalisés entre 0 et 100 %.

### Étape 5 : Affichage et utilisation des résultats

Audience Manager displays your weighted model results in [!UICONTROL Trait Builder]. When you want to build an algorithmic trait, [!UICONTROL Trait Builder] lets you create traits based on the weighted score generated by the algorithm during a data run. Vous pouvez choisir une précision plus élevée pour ne qualifier que les utilisateurs qui ont des scores d'utilisateur très élevés et qui sont donc très semblables à l'audience de ligne de base, plutôt qu'au reste du public. Si vous souhaitez atteindre une audience plus large (portée), vous pouvez réduire la précision.

### Étape 6 : Réévaluer la signification d'une caractéristique dans les cycles de traitement

Periodically, [!UICONTROL TraitWeight] re-evaluates the importance of a trait based on the size and change in the population of that trait. Cela se produit lorsque le nombre d'utilisateurs qualifiés pour cette caractéristique augmente ou diminue au fil du temps. Ce comportement est clairement visible dans les caractéristiques qui deviennent très volumineuses. Par exemple, supposons que l'algorithme utilise la caractéristique A pour la modélisation. As the population of trait A increases, [!UICONTROL TraitWeight] re-evaluates the importance of that trait and may assign a lower score or ignore it. Dans ce cas, la caractéristique A est trop courante ou trop grande pour dire quelque chose de significatif sur sa population. After [!UICONTROL TraitWeight] reduces the value of Trait A (or ignores it in the model), the population of the algorithmic trait decreases. La liste des caractéristiques influentes reflète l'évolution de la population de ligne de base. Utilisez la liste des caractéristiques influentes pour comprendre pourquoi ces modifications ont lieu.

Liens connexes :

* [Créateur de modèles](../../features/algorithmic-models/create-model.md)
* [Précision et portée](../../features/traits/trait-accuracy-reach.md)

## Update Schedule for Algorithmic Models and Traits {#update-schedule}

Planification de la création et de la mise à jour des planifications pour les modèles et caractéristiques algorithmiques nouveaux ou existants.

<!-- c_model_update_schedule.xml -->

### Planification de la création et de la mise à jour du modèle algorithmique

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Type d’activité </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Créer ou cloner un modèle</b> </td>
   <td colname="col2"> <p>Pour les modèles d'algorithme nouveaux ou clonés, le processus de création s'exécute une fois par jour à : 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (novembre à mars) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 h EDT (mars - novembre) </li> 
     </ul> </p> <p>Les modèles créés ou clonés après l'échéance de création sont traités le jour suivant. </p> <p>Si le premier exécution d'un modèle ne génère aucune donnée, elle s'exécutera une seconde fois, le lendemain. Si la deuxième tentative ne génère pas de données, il y aura une troisième tentative, le jour suivant. Le modèle s'arrête si la troisième tentative ne génère pas de données. Dans ce cas, nous désactivera le modèle. See more in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Troubleshooting Algorithmic Models</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Mettre à jour un modèle</b> </td> 
   <td colname="col2"> <p>Dans des conditions idéales, les modèles existants s'exécutent au moins une fois tous les 7 jours. Par exemple, si vous créez un modèle (par échéance) le lundi, il se met à jour le lundi suivant. </p> <p>Un modèle réexécute s'il répond à l'une des conditions suivantes : </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sa dernière exécution n'a pas réussi. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Il s'est exécuté avec succès avant ET il n'a pas été exécuté au cours des 7 derniers jours ET le modèle comporte au moins une caractéristique active associée. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Création et mise à jour de caractéristiques algorithmiques

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’activité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Création d'une caractéristique</b> </td> 
   <td colname="col2"> <p>Le processus de création de caractéristiques s'exécute tous les jours, du lundi au vendredi. En règle générale, de nouvelles caractéristiques algorithmiques apparaissent dans l'interface utilisateur dans les 48 heures. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mettre à jour une caractéristique</b> </td> 
   <td colname="col2"> <p>Les caractéristiques existantes sont mises à jour au moins une fois tous les 7 jours et suivent la planification des mises à jour du modèle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Models List View {#models-list-view}

La vue Liste est un espace de travail central qui vous aide à créer, réviser et gérer des modèles.

<!-- c_models_list_view.xml -->

La page de liste Modèles contient des fonctionnalités et des outils qui vous aident à :

* Créez de nouveaux modèles.
* Gérez les modèles existants (modification, pause, suppression ou cloner).
* Rechercher des modèles par nom.
* Créez des caractéristiques algorithmiques à l'aide d'un modèle donné.

## Models Summary View {#models-summary-view}

La page de résumé affiche les détails du modèle, tels que le nom, la portée/la précision, l'historique de traitement et les caractéristiques créées à partir du modèle. La page comprend également des paramètres vous permettant de créer et de gérer des modèles. Cliquez sur un nom de modèle dans la liste récapitulative pour en afficher les détails.

<!-- c_models_summary.xml -->

La page Résumé du modèle comprend les sections suivantes.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Section </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Informations fondamentales</span> </p> </td>
   <td colname="col2"> <p>Inclut des informations de base sur le modèle, telles que son nom et sa dernière exécution. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Portée et précision du modèle</span> </p> </td> 
   <td colname="col2"> <p>Shows <a href="../../features/traits/trait-accuracy-reach.md"> accuracy and reach</a> data for the last model run. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historique de traitement du modèle</span> </p> </td> 
   <td colname="col2"> <p>Affiche la date et l'heure de traitement des 10 dernières exécutions et indique si les données ont été générées sur ces exécutions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques influentes</span> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> Influential Traits</span> table: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Répertorie les 50 principales caractéristiques influentes qui sont les mieux représentées dans la population de ligne de base du modèle. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Ranks each trait in order of its <span class="wintitle"> Relative Weight</span> rank. The <span class="wintitle"> Relative Weight</span> sorts newly discovered traits in order of influence or desirability. L'échelle de poids est un pourcentage qui s'exécute de 0 à 100 %. Les caractéristiques plus proches de 100 % signifient qu'elles correspondent davantage à l'audience de la population de ligne de base. See <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Understanding TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Indique les dimensions uniques de 30 jours et la population totale de caractéristiques pour chaque caractéristique. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques utilisant un modèle</span> </p> </td>
   <td colname="col2"> <p>Affiche la liste des caractéristiques algorithmiques basées sur le modèle sélectionné. Cliquez sur un nom de caractéristique ou un ID de caractéristique pour plus d'informations sur la caractéristique. Select <b><span class="uicontrol"> Create New Trait with Model</span></b> to go to the algorithmic trait creation process. </p> <p>Le libellé de la section change en fonction du nom du modèle. For example, say you create a model and name it Model A. When you load the summary page, the name of this section gets changed to <span class="wintitle"> Traits Using Model A</span>. </p> </td>
  </tr>
 </tbody>
</table>