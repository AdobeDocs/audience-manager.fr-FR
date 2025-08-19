---
description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation similaire.
keywords: poids relatif, similaire
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: À Propos De La Modélisation Similaire
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# Comprendre les [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Rechercher de nouveaux utilisateurs avec [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] vous permet de découvrir de nouvelles audiences uniques grâce à l’analyse automatisée des données. Le processus démarre lorsque vous sélectionnez un [!UICONTROL trait] ou un [!UICONTROL segment], un intervalle de temps, ainsi qu’un [!UICONTROL data sources] propriétaire et tiers. Vos choix fournissent les entrées du modèle algorithmique. Lorsque le processus d’analyse s’exécute, il recherche les utilisateurs éligibles en fonction des caractéristiques partagées de la population sélectionnée. Une fois l’opération terminée, ces données sont disponibles dans [créateur de caractéristiques](../../features/traits/about-trait-builder.md) où vous pouvez les utiliser pour créer des caractéristiques basées sur [précision et portée](../../features/traits/trait-accuracy-reach.md). De plus, vous pouvez créer des segments qui combinent des caractéristiques algorithmiques avec [!UICONTROL rules-based traits] et ajouter d’autres exigences de qualification avec des expressions [!DNL Boolean] et des opérateurs de comparaison. [!UICONTROL Look-Alike Modeling] vous offre un moyen dynamique d’extraire de la valeur de toutes vos données de caractéristiques disponibles.

## Avantages {#advantages}

Les principaux avantages de l’utilisation de [!UICONTROL Look-Alike Modeling] sont les suivants :

* **Précision des données :** l’algorithme s’exécute régulièrement, ce qui permet de tenir les résultats à jour et pertinents.
* **Automatisation :** vous n’avez pas à gérer un grand nombre de règles statiques. L’algorithme trouvera des audiences pour vous.
* **Gagnez du temps et réduisez les efforts :** grâce à notre processus de modélisation, vous n’avez pas à deviner les [!UICONTROL traits]/[!UICONTROL segments] qui peuvent fonctionner ni à consacrer du temps aux campagnes pour découvrir de nouvelles audiences. Le modèle peut le faire pour vous.
* **Fiabilité :** la modélisation fonctionne avec des processus de découverte et de qualification côté serveur qui évaluent vos propres données et les données tierces sélectionnées auxquelles vous avez accès. Cela signifie que vous n’avez pas besoin de voir les visiteurs de votre site pour les qualifier pour une caractéristique.

## Workflow {#workflow}

Vous gérez des modèles dans **[!UICONTROL Audience Data > Models]**. À un niveau élevé, le processus de workflow implique ce qui suit :

* Sélectionnez les données de référence que l’algorithme doit évaluer. Cela inclut une [!UICONTROL trait] ou une [!UICONTROL segment], une période et une [!UICONTROL data sources] (vos propres données et les données tierces auxquelles vous avez déjà accès par le biais de [!DNL Audience Manager]). Dans le workflow de création de modèle, vous pouvez exclure les [!UICONTROL traits] que vous ne souhaitez pas interférer avec votre modèle.
* Enregistrez votre modèle. Une fois enregistré, le processus d’évaluation algorithmique s’exécute automatiquement. Notez toutefois que ce processus peut prendre jusqu’à 7 jours. [!DNL Audience Manager] vous envoie un e-mail lorsque l’algorithme est terminé et que les résultats sont disponibles pour la création de [!UICONTROL trait].
* Créer des [!UICONTROL traits] algorithmiques dans [!UICONTROL Trait Builder].
* Combinez les [!UICONTROL traits] en [!UICONTROL segments] dans les [!UICONTROL Segment Builder].
* Créer et envoyer des données [!UICONTROL segment] à un [!UICONTROL destination].

## Dépannage {#troubleshooting}

Nous désactivons toutes les [!UICONTROL Look-Alike Model] qui ne parviennent pas à générer des données pendant trois exécutions consécutives. Notez que vous ne pouvez pas redéfinir le statut du modèle sur Actif par la suite. Pour vous assurer que vos modèles génèrent des données, nous vous recommandons de créer des modèles à partir de sources de données avec une [!UICONTROL traits] suffisante pour accumuler les données.

## Comprendre les [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] est un algorithme propriétaire conçu pour découvrir automatiquement de nouveaux [!UICONTROL traits]. Il compare [!UICONTROL trait] données de votre [!UICONTROL traits] et [!UICONTROL segments] actuels à toutes les autres données propriétaires et tierces auxquelles vous avez accès par le biais de [!DNL Audience Manager]. Reportez-vous à cette section pour une description du processus de découverte algorithmique [!UICONTROL TraitWeight].

![](assets/algo_model.png)

Les étapes suivantes décrivent le processus d’évaluation [!UICONTROL TraitWeight].

### Étape 1 : créer une ligne de base pour [!UICONTROL Trait] comparaison

Pour créer une ligne de base, [!UICONTROL TraitWeight] mesure toutes les [!UICONTROL traits] associées à une audience pendant un intervalle de 30, 60 ou 90 jours. Ensuite, il classe les [!UICONTROL traits] en fonction de leur fréquence et de leur corrélation. Le nombre de fréquences mesure les points communs. La corrélation mesure la probabilité qu’un [!UICONTROL trait] soit présent uniquement dans l’audience de base. On dit que les [!UICONTROL Traits] qui apparaissent souvent ont beaucoup de points communs, une caractéristique importante utilisée pour établir un score pondéré lorsqu’ils sont combinés avec des [!UICONTROL traits] découverts dans le [!UICONTROL data sources] sélectionné.

### Étape 2 : Rechercher le même [!UICONTROL Traits] dans le [!UICONTROL Data Source]

Après avoir créé une ligne de base à comparer, l’algorithme recherche des [!UICONTROL traits] identiques dans le [!UICONTROL data sources] sélectionné. Au cours de cette étape, [!UICONTROL TraitWeight] effectue un comptage de fréquence de toutes les [!UICONTROL traits] découvertes et les compare à la ligne de base. Cependant, contrairement à la ligne de base, les [!UICONTROL traits] peu fréquents sont classés plus haut que ceux qui apparaissent plus souvent. Les [!UICONTROL traits] rares présentent un haut degré de spécificité. [!UICONTROL TraitWeight] évalue les combinaisons de [!UICONTROL traits] de base communs et de [!UICONTROL data source] de [!UICONTROL traits] peu fréquents (hautement spécifiques) comme étant plus influentes ou souhaitables que [!UICONTROL traits] communes aux deux ensembles de données. En fait, notre modèle reconnaît ces grandes [!UICONTROL traits] communes et n’attribue pas de priorité excessive aux ensembles de données présentant des corrélations élevées. Les [!UICONTROL traits] rares bénéficient d’une priorité plus élevée, car ils sont plus susceptibles de représenter de nouveaux utilisateurs uniques que les [!UICONTROL traits] ayant des points communs importants à tous les niveaux.

### Étape 3 : Attribuer un poids

Au cours de cette étape, [!UICONTROL TraitWeight] classe les nouveaux [!UICONTROL traits] découverts par ordre d’influence ou de désirabilité. L’échelle de poids est un pourcentage qui va de 0 % à 100 %. [!UICONTROL Traits] classement proche de 100 % signifie qu’ils ressemblent davantage à l’audience de votre population de référence. En outre, les [!UICONTROL traits] fortement pondérés sont utiles car ils représentent de nouveaux utilisateurs uniques qui peuvent se comporter de la même manière que votre audience de base établie. N’oubliez pas [!UICONTROL TraitWeight] considère que les [!UICONTROL traits] ayant des points communs élevés dans la ligne de base et une spécificité élevée dans les sources de données comparées ont plus de valeur que [!UICONTROL traits] courants dans chaque ensemble de données.

### Étape 4 : notation des utilisateurs

Chaque utilisateur dans le [!UICONTROL data sources] sélectionné reçoit un score d&#39;utilisateur qui est égal à la somme de tous les poids de l&#39;[!UICONTROL traits] influent sur le profil de cet utilisateur. Les scores des utilisateurs sont ensuite normalisés entre 0 et 100%.

### Étape 5 : affichage et utilisation des résultats

[!DNL Audience Manager] affiche les résultats du modèle pondéré dans [!UICONTROL Trait Builder]. Lorsque vous souhaitez créer un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] vous permet de créer des [!UICONTROL traits] en fonction du score pondéré généré par l’algorithme au cours d’une exécution de données. Vous pouvez choisir une précision plus élevée pour qualifier uniquement les utilisateurs qui ont des scores d’utilisateur très élevés et qui sont donc très similaires à l’audience de base, plutôt qu’au reste de l’audience. Si vous souhaitez atteindre une plus grande audience (portée), vous pouvez réduire la précision.

### Étape 6 : Réévaluer l’importance d’un [!UICONTROL Trait] sur l’ensemble des cycles de traitement

Périodiquement, [!UICONTROL TraitWeight] réévalue l&#39;importance d&#39;une [!UICONTROL trait] en fonction de la taille et de l&#39;évolution de la population de cette [!UICONTROL trait]. Cela se produit lorsque le nombre d’utilisateurs qualifiés pour ce [!UICONTROL trait] augmente ou diminue au fil du temps. Ce comportement est plus clairement visible dans les caractéristiques qui deviennent très grandes. Supposons, par exemple, que l’algorithme utilise [!UICONTROL trait A] pour la modélisation. À mesure que la population de [!UICONTROL trait A] augmente, [!UICONTROL TraitWeight] réévalue l’importance de ce [!UICONTROL trait] et peut attribuer un score inférieur ou l’ignorer. Dans ce cas, [!UICONTROL trait A] est trop fréquent ou trop grand pour dire quoi que ce soit de significatif sur sa population. Après [!UICONTROL TraitWeight] réduit la valeur de [!UICONTROL trait A] (ou l’ignore dans le modèle), la population de la caractéristique algorithmique diminue. La liste des [!UICONTROL traits] influents reflète l’évolution de la population de référence. Utilisez la liste des [!UICONTROL traits] d’influence pour comprendre pourquoi ces modifications se produisent.

Liens connexes :

* [Créateur de modèles](../../features/algorithmic-models/create-model.md)
* [Précision et portée](../../features/traits/trait-accuracy-reach.md)

## Mettre à jour le planning pour [!UICONTROL Look-Alike Models] et [!UICONTROL Traits] {#update-schedule}

Créer et mettre à jour des plannings pour des [!UICONTROL algorithmic models] et des [!UICONTROL traits] nouveaux ou existants.

### [!UICONTROL Look-Alike Model] de création et de mise à jour de planning

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
   <td colname="col2"> <p>Pour les [!UICONTROL Look-Alike Models] nouvelles ou clonées, le processus de création s’exécute une fois par jour à l’adresse : 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17 h EST (novembre - mars) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18 h (HAE) (mars à novembre) </li> 
     </ul> </p> <p>Les modèles créés ou clonés après l’échéance de création sont traités le jour suivant. </p> <p>Si la première exécution d’un modèle ne génère aucune donnée, elle s’exécute une seconde fois, le lendemain. Si la deuxième tentative ne génère aucune donnée, une troisième tentative aura lieu le lendemain. Le modèle s’arrête si la troisième tentative ne génère pas non plus de données. Dans ce cas, nous désactiverons le modèle. Pour en savoir plus, consultez <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> section Dépannage des modèles semblables </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Mettre à jour un modèle</b> </td> 
   <td colname="col2"> <p>Dans des conditions idéales, les modèles existants fonctionnent en semaine, au moins une fois tous les 7 jours. Par exemple, si vous créez un modèle (avant la date limite) le lundi, il est mis à jour le lundi suivant au plus tard. </p> <p>Un modèle est réexécuté s’il répond à l’une des conditions suivantes : </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sa dernière exécution a échoué. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Il a été exécuté avec succès auparavant ET il n’a pas été exécuté du tout au cours des 7 derniers jours ET le modèle est associé à au moins une caractéristique active. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] de création et de mise à jour de planning

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’activité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Créer une caractéristique</b> </td> 
   <td colname="col2"> <p>Le processus de création des caractéristiques s’exécute tous les jours, du lundi au vendredi. En règle générale, les nouvelles caractéristiques algorithmiques apparaissent dans l’interface utilisateur dans les 48 heures. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mettre à jour une caractéristique</b> </td> 
   <td colname="col2"> <p>Les caractéristiques existantes sont mises à jour au moins une fois tous les 7 jours et suivent le planning des mises à jour du modèle. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vue Liste des modèles {#models-list-view}

La vue Liste est un espace de travail central qui vous permet de créer, réviser et gérer des modèles.

La page de liste [!UICONTROL Models] contient des fonctionnalités et des outils qui vous permettent d’effectuer les opérations suivantes :

* Créez de nouveaux modèles.
* Gérer les modèles existants (modifier, suspendre, supprimer ou cloner).
* Recherchez des modèles par nom.
* Créez des [!UICONTROL algorithmic traits] à l’aide d’un modèle donné.

## Mode Résumé des modèles {#models-summary-view}

La page de résumé affiche les détails du modèle, tels que le nom, la portée/la précision, l’historique du traitement et les [!UICONTROL traits] créés à partir du modèle. La page comprend également des paramètres qui vous permettent de créer et de gérer des modèles. Cliquez sur le nom d’un modèle dans la liste récapitulative pour en afficher les détails.

La page de résumé du modèle comprend les sections suivantes.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Section </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> informations de base </span> </p> </td>
   <td colname="col2"> <p>Inclut des informations de base sur le modèle, telles que son nom et la date de sa dernière exécution. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> portée et précision du modèle</span> </p> </td> 
   <td colname="col2"> <p>Affiche <a href="../../features/traits/trait-accuracy-reach.md"> données de précision et de portée</a> pour la dernière exécution du modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> l’historique de traitement du modèle</span> </p> </td> 
   <td colname="col2"> <p>Affiche la date et l’heure de traitement des 10 dernières exécutions et si des données ont été générées sur ces exécutions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> caractéristiques d’influence </span> </p> </td> 
   <td colname="col2"> <p>Le tableau <span class="wintitle"> les caractéristiques d’influence </span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Répertorie les 50 caractéristiques les plus influentes qui sont le mieux représentées dans la population de base du modèle. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classe chaque caractéristique dans l’ordre de son <span class="wintitle"> poids relatif</span> classement. Le <span class="wintitle"> Poids relatif </span> trie les caractéristiques nouvellement découvertes par ordre d’influence ou de désirabilité. L’échelle de poids est un pourcentage qui va de 0 % à 100 %. Les caractéristiques classées plus près de 100 % correspondent davantage à l’audience de votre population de référence. Voir <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Présentation de TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Affiche les caractéristiques uniques sur 30 jours et la population totale de chaque caractéristique. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> des caractéristiques à l’aide du modèle</span> </p> </td>
   <td colname="col2"> <p>Affiche une liste des caractéristiques algorithmiques en fonction du modèle sélectionné. Cliquez sur le nom ou l’ID d’une caractéristique pour plus d’informations sur la caractéristique. Sélectionnez <b><span class="uicontrol"> Créer une caractéristique avec le modèle </span></b> pour passer au processus de création de caractéristique algorithmique. </p> <p>Le libellé de la section change en fonction du nom de votre modèle. Supposons, par exemple, que vous créiez un modèle et que vous lui donniez le nom Modèle A. Lorsque vous chargez la page de résumé, le nom de cette section est remplacé par Caractéristiques <span class="wintitle"> à l’aide du modèle A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinations](../../features/destinations/destinations.md)
>* [Caractéristiques](../../features/traits/trait-details-page.md)
>* [Segments](../../features/segments/segments-purpose.md)
