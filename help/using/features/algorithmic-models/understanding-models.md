---
description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation analogue.
keywords: poids relatif, socle
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: A propos de la modélisation analogue
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# Comprendre [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Rechercher de nouveaux utilisateurs avec [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] vous aide à découvrir de nouvelles audiences uniques grâce à l’analyse automatisée des données. Le processus démarre lorsque vous sélectionnez un [!UICONTROL trait] ou [!UICONTROL segment], un intervalle de temps et un [!UICONTROL data sources] propriétaire et tiers. Vos choix fournissent les entrées pour le modèle algorithmique. Lorsque le processus d’analyse s’exécute, il recherche les utilisateurs éligibles en fonction des caractéristiques partagées de la population sélectionnée. Une fois ces données terminées, elles sont disponibles dans le [créateur de caractéristiques](../../features/traits/about-trait-builder.md) où vous pouvez les utiliser pour créer des caractéristiques en fonction de la [précision et de la portée](../../features/traits/trait-accuracy-reach.md). De plus, vous pouvez créer des segments qui combinent des caractéristiques algorithmiques avec [!UICONTROL rules-based traits] et ajouter d’autres exigences de qualification avec des expressions [!DNL Boolean] et des opérateurs de comparaison. [!UICONTROL Look-Alike Modeling] vous offre un moyen dynamique d’extraire de la valeur de toutes vos données de caractéristiques disponibles.

## Avantages {#advantages}

Les principaux avantages de l’utilisation de [!UICONTROL Look-Alike Modeling] sont les suivants :

* **Précision des données :** l’algorithme s’exécute régulièrement, ce qui permet de maintenir les résultats à jour et pertinents.
* **Automatisation :** Vous n’avez pas à gérer un grand ensemble de règles statiques. L’algorithme recherche les audiences pour vous.
* **Gagnez du temps et réduisez l’effort :** Avec notre processus de modélisation, vous n’avez pas à deviner ce que [!UICONTROL traits]/[!UICONTROL segments] peut utiliser ou dépenser des ressources de temps sur les campagnes pour découvrir de nouvelles audiences. Le modèle peut le faire pour vous.
* **Fiabilité :** La modélisation fonctionne avec des processus de découverte et de qualification côté serveur qui évaluent vos propres données et les données tierces sélectionnées auxquelles vous avez accès. Cela signifie que vous n’avez pas besoin d’afficher les visiteurs de votre site pour les qualifier pour une caractéristique.

## Workflow {#workflow}

Vous gérez les modèles dans **[!UICONTROL Audience Data > Models]**. A un niveau général, le processus de workflow implique les opérations suivantes :

* Sélectionnez les données de base que l’algorithme doit évaluer. Cela inclut un [!UICONTROL trait] ou [!UICONTROL segment], une période et [!UICONTROL data sources] (vos propres données et données tierces auxquelles vous avez déjà accès via [!DNL Audience Manager]). Dans le workflow de création de modèle, vous pouvez exclure le [!UICONTROL traits] dont vous ne souhaitez pas interférer avec votre modèle.
* Enregistrez votre modèle. Une fois enregistré, le processus d’évaluation algorithmique s’exécute automatiquement. Notez toutefois que la fin de ce processus peut prendre jusqu’à 7 jours. [!DNL Audience Manager] vous envoie un courrier électronique lorsque l’algorithme est terminé et que les résultats sont disponibles pour la création de [!UICONTROL trait].
* Créez l’algorithme [!UICONTROL traits] dans [!UICONTROL Trait Builder].
* Combinez [!UICONTROL traits] en [!UICONTROL segments] dans [!UICONTROL Segment Builder].
* Créez et envoyez des données [!UICONTROL segment] à un [!UICONTROL destination].

## Dépannage {#troubleshooting}

Nous désactivons tout [!UICONTROL Look-Alike Model] qui ne parvient pas à générer des données pour trois exécutions consécutives. Notez que vous ne pouvez pas redéfinir l’état du modèle sur actif par la suite. Pour vous assurer que vos modèles génèrent des données, nous vous recommandons de créer des modèles à partir de sources de données avec un nombre suffisant de [!UICONTROL traits] pour accumuler des données.

## Comprendre [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] est un algorithme propriétaire conçu pour découvrir automatiquement le nouveau [!UICONTROL traits]. Il compare [!UICONTROL trait] données provenant de vos [!UICONTROL traits] et [!UICONTROL segments] actuels à toutes les autres données propriétaires et tierces auxquelles vous avez accès via [!DNL Audience Manager]. Reportez-vous à cette section pour une description du processus de découverte algorithmique [!UICONTROL TraitWeight].

![](assets/algo_model.png)

Les étapes suivantes décrivent le processus d’évaluation de [!UICONTROL TraitWeight].

### Étape 1 : création d’une ligne de base pour la comparaison [!UICONTROL Trait]

Pour créer une ligne de base, [!UICONTROL TraitWeight] mesure tous les [!UICONTROL traits] associés à une audience pendant un intervalle de 30, 60 ou 90 jours. Ensuite, il classe [!UICONTROL traits] en fonction de leur fréquence et de leur corrélation. Le comptage des fréquences mesure la similarité. La corrélation mesure la probabilité qu’un [!UICONTROL trait] ne soit présent que dans l’audience de base. [!UICONTROL Traits] qui apparaissent souvent présente des points communs élevés, une caractéristique importante utilisée pour définir un score pondéré lorsqu’elle est combinée avec [!UICONTROL traits] découvert dans votre [!UICONTROL data sources] sélectionné.

### Étape 2 : Rechercher le même [!UICONTROL Traits] dans le [!UICONTROL Data Source]

Une fois qu’il a créé une ligne de base pour la comparaison, l’algorithme recherche les [!UICONTROL traits] identiques dans le [!UICONTROL data sources] sélectionné. Au cours de cette étape, [!UICONTROL TraitWeight] effectue un comptage de fréquence de tous les [!UICONTROL traits] découverts et les compare à la ligne de base. Cependant, contrairement à la ligne de base, les [!UICONTROL traits] rares sont classés plus haut que ceux qui apparaissent plus souvent. On dit que les [!UICONTROL traits] rares présentent un haut degré de précision. [!UICONTROL TraitWeight] considère les combinaisons de lignes de base courantes [!UICONTROL traits] et peu courantes (hautement spécifiques) [!UICONTROL data source] [!UICONTROL traits] comme plus influentes ou souhaitables que [!UICONTROL traits] communes aux deux ensembles de données. En fait, notre modèle reconnaît ces [!UICONTROL traits] volumineux et courants et n’affecte pas une priorité excessive aux jeux de données avec des corrélations élevées. Les [!UICONTROL traits] rares ont une priorité plus élevée, car ils sont plus susceptibles de représenter de nouveaux utilisateurs uniques que [!UICONTROL traits] avec une communauté élevée dans l’ensemble.

### Étape 3 : Attribuer un poids

Au cours de cette étape, [!UICONTROL TraitWeight] classe les [!UICONTROL traits] nouvellement découverts dans l’ordre d’influence ou de pertinence. L&#39;échelle de poids est un pourcentage qui va de 0 à 100 %. [!UICONTROL Traits] classé plus près de 100 % signifie qu’ils ressemblent davantage à l’audience de votre population de base. En outre, les [!UICONTROL traits] fortement pondérés sont utiles car ils représentent de nouveaux utilisateurs uniques qui peuvent se comporter de la même manière que votre audience de base établie. N’oubliez pas que [!UICONTROL TraitWeight] considère [!UICONTROL traits] avec une grande communauté dans la ligne de base et une grande spécificité dans les sources de données comparées comme plus précieuse que [!UICONTROL traits] commune à chaque jeu de données.

### Étape 4 : Notation des utilisateurs

Chaque utilisateur du [!UICONTROL data sources] sélectionné obtient un score d’utilisateur égal à la somme de tous les poids de l’influent [!UICONTROL traits] sur son profil. Les scores de l’utilisateur sont ensuite normalisés entre 0 et 100 %.

### Étape 5 : affichage et utilisation des résultats

[!DNL Audience Manager] affiche les résultats de votre modèle pondéré dans [!UICONTROL Trait Builder]. Lorsque vous souhaitez créer un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] vous permet de créer [!UICONTROL traits] en fonction du score pondéré généré par l’algorithme au cours d’une exécution de données. Vous pouvez choisir une précision plus élevée afin de ne qualifier que les utilisateurs qui ont des scores d’utilisateur très élevés et sont donc très similaires à l’audience de base, plutôt qu’au reste de l’audience. Si vous souhaitez atteindre une plus grande audience (portée), vous pouvez réduire la précision.

### Étape 6 : réévaluer la signification d’un [!UICONTROL Trait] sur plusieurs cycles de traitement

Régulièrement, [!UICONTROL TraitWeight] réévalue l’importance d’un [!UICONTROL trait] en fonction de la taille et du changement de la population de cet [!UICONTROL trait]. Cela se produit lorsque le nombre d&#39;utilisateurs qualifiés pour cet [!UICONTROL trait] augmente ou diminue au fil du temps. Ce comportement est plus clairement visible dans les caractéristiques qui deviennent très grandes. Par exemple, supposons que l’algorithme utilise [!UICONTROL trait A] pour la modélisation. À mesure que la population de [!UICONTROL trait A] augmente, [!UICONTROL TraitWeight] réévalue l&#39;importance de cet [!UICONTROL trait] et peut attribuer un score plus faible ou l&#39;ignorer. Dans ce cas, [!UICONTROL trait A] est trop courant ou trop grand pour dire quoi que ce soit d&#39;important sur sa population. Une fois que [!UICONTROL TraitWeight] a réduit la valeur de [!UICONTROL trait A] (ou l’a ignoré dans le modèle), la population de la caractéristique algorithmique diminue. La liste des [!UICONTROL traits] influents reflète l’évolution de la population de base. Utilisez la liste des [!UICONTROL traits] influents pour comprendre pourquoi ces modifications se produisent.

Liens connexes :

* [Créateur de modèles](../../features/algorithmic-models/create-model.md)
* [Précision et portée](../../features/traits/trait-accuracy-reach.md)

## Mise à jour de la planification pour [!UICONTROL Look-Alike Models] et [!UICONTROL Traits] {#update-schedule}

Création et mise à jour des plannings pour [!UICONTROL algorithmic models] et [!UICONTROL traits] nouveaux ou existants.

### [!UICONTROL Look-Alike Model] Planification de la création et de la mise à jour

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Type d’activité </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Création ou clonage d’un modèle</b> </td>
   <td colname="col2"> <p>Pour les [!UICONTROL Look-Alike Models] nouveaux ou clonés, le processus de création s’exécute une fois par jour à l’adresse : 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17h00 (novembre à mars) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18h00 (mars à novembre) </li> 
     </ul> </p> <p>Les modèles créés ou clonés après la date limite de création sont traités le jour suivant. </p> <p>Si la première exécution d’un modèle ne génère aucune donnée, elle s’exécute une seconde fois, le lendemain. Si la deuxième tentative ne génère pas de données, il y aura une troisième tentative, le lendemain. Le modèle cessera de fonctionner si la troisième tentative ne génère aucune donnée. Dans ce cas, nous désactiverons le modèle. Pour en savoir plus, voir <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Dépannage des modèles analogue</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Mettre à jour un modèle</b> </td> 
   <td colname="col2"> <p>Dans des conditions idéales, les modèles existants s’exécutent en semaine, au moins une fois tous les 7 jours. Par exemple, si vous créez un modèle (avant la date limite) le lundi, il met à jour le lundi suivant au plus tard. </p> <p>Un modèle se réexécute s’il répond à l’une des conditions suivantes : </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sa dernière exécution a échoué. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Il s’est exécuté avec succès avant ET il ne s’est pas exécuté du tout au cours des 7 derniers jours ET le modèle comporte au moins une caractéristique active qui lui est associée. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Planification de la création et de la mise à jour

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
   <td colname="col2"> <p>Le processus de création de caractéristiques s’exécute tous les jours, du lundi au vendredi. En règle générale, de nouvelles caractéristiques algorithmiques apparaissent dans l’interface utilisateur dans les 48 heures. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mettre à jour une caractéristique</b> </td> 
   <td colname="col2"> <p>Les caractéristiques existantes sont mises à jour au moins une fois tous les 7 jours et suivent le calendrier des mises à jour des modèles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mode Liste des modèles {#models-list-view}

Le mode Liste est un espace de travail central qui vous permet de créer, de réviser et de gérer des modèles.

La page de liste [!UICONTROL Models] contient des fonctionnalités et des outils qui vous aident à :

* Créez de nouveaux modèles.
* Gérer les modèles existants (modifier, mettre en pause, supprimer ou cloner).
* Recherchez des modèles par nom.
* Créez [!UICONTROL algorithmic traits] à l’aide d’un modèle donné.

## Mode Résumé des modèles {#models-summary-view}

La page de résumé affiche les détails du modèle tels que le nom, la portée/précision, l’historique de traitement et [!UICONTROL traits] créés à partir du modèle. La page comprend également des paramètres qui vous permettent de créer et de gérer des modèles. Cliquez sur un nom de modèle dans la liste récapitulative pour afficher ses détails.

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
   <td colname="col1"> <p> <span class="wintitle"> Informations de base</span> </p> </td>
   <td colname="col2"> <p>Inclut des informations de base sur le modèle, telles que son nom et sa date de dernière exécution. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Portée et précision du modèle</span> </p> </td> 
   <td colname="col2"> <p>Affiche la précision de <a href="../../features/traits/trait-accuracy-reach.md"> et les données de portée</a> pour la dernière exécution de modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historique de traitement du modèle</span> </p> </td> 
   <td colname="col2"> <p>Affiche la date et l’heure de traitement des 10 dernières exécutions et indique si des données ont été générées sur ces exécutions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques influentes </span> </p> </td> 
   <td colname="col2"> <p>La table <span class="wintitle"> Caractéristiques influentes</span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Répertorie les 50 principales caractéristiques influentes les mieux représentées dans la population de base du modèle. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classe chaque caractéristique dans l’ordre de son rang <span class="wintitle"> Poids relatif</span>. Le <span class="wintitle"> Poids relatif</span> trie les caractéristiques nouvellement découvertes par ordre d’influence ou de pertinence. L'échelle de poids est un pourcentage qui va de 0 à 100 %. Les caractéristiques classées plus près de 100 % correspondent davantage à l’audience de votre population de base. Voir <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Présentation de TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Affiche les uniques de 30 jours et la population totale des caractéristiques pour chaque caractéristique. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques utilisant le modèle</span> </p> </td>
   <td colname="col2"> <p>Affiche une liste des caractéristiques algorithmiques basées sur le modèle sélectionné. Pour plus d’informations sur la caractéristique, cliquez sur son nom ou son identifiant. Sélectionnez <b><span class="uicontrol"> Create New Trait with Model</span></b> pour accéder au processus de création de caractéristiques algorithmiques. </p> <p>Le libellé de la section change en fonction du nom de votre modèle. Supposons, par exemple, que vous créiez un modèle et que vous le nommiez Modèle A. Lorsque vous chargez la page de résumé, le nom de cette section est remplacé par <span class="wintitle"> Caractéristiques à l’aide du modèle A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinations](../../features/destinations/destinations.md)
>* [Caractéristiques](../../features/traits/trait-details-page.md)
>* [Segments](../../features/segments/segments-purpose.md)
