---
description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation algorithmique, également appelée modélisation ressemblante. Les fonctions du modèle se trouvent dans Données d’audience > Modèles.
keywords: poids relatif, ressemblance
seo-description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation algorithmique, également appelée modélisation ressemblante. Les fonctions du modèle se trouvent dans Données d’audience > Modèles.
seo-title: A propos des modèles algorithmiques
solution: Audience Manager
title: A propos des modèles algorithmiques
topic: API DIL
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: 73d670225fb4170d02428a1dd163f442540e3415

---


# A propos des modèles algorithmiques {#about-algorithmic-models}

Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation algorithmique, également appelée modélisation ressemblante. Les fonctions du modèle se trouvent dans **[!UICONTROL Audience Data > Models]**.

<!-- c_models.xml -->

## Présentation des modèles algorithmiques {#understanding-models}

Les sections ci-dessous représentent une révision de la modélisation algorithmique dans [!DNL Audience Manager]. Ils décrivent le fonctionnement de la modélisation, les avantages et le processus.

<!-- understanding-models.xml -->

## Rechercher de nouveaux utilisateurs avec la modélisation algorithmique {#find-new-users}

La modélisation algorithmique vous permet de découvrir de nouvelles audiences uniques grâce à l’analyse automatisée des données. Le processus commence lorsque vous sélectionnez une caractéristique ou un segment, un intervalle de temps et des sources de données propriétaires et tiers. Vos choix fournissent les entrées pour le modèle algorithmique. Lorsque le processus d’analyse s’exécute, il recherche les utilisateurs éligibles en fonction des caractéristiques partagées de la population sélectionnée. Une fois ces données terminées, elles sont disponibles dans le créateur de [caractéristiques](../../features/traits/about-trait-builder.md) où vous pouvez les utiliser pour créer des caractéristiques basées sur la [précision et la portée](../../features/traits/trait-accuracy-reach.md). De plus, vous pouvez créer des segments qui combinent des caractéristiques algorithmiques avec des caractéristiques basées sur des règles et ajouter d’autres exigences de qualification avec des expressions booléennes et des opérateurs de comparaison. La modélisation algorithmique vous donne une méthode dynamique pour extraire la valeur de toutes les données de caractéristiques disponibles.

## Avantages {#advantages}

Les principaux avantages de l’utilisation de la [!DNL Audience Manager] modélisation sont les suivants :

* **** Précision des données : L’algorithme s’exécute régulièrement, ce qui permet de garder les résultats à jour et pertinents.
* **** Automatisation : Vous n’êtes pas obligé de gérer un grand ensemble de règles statiques. L’algorithme trouvera des audiences pour vous.
* **** Gagnez du temps et réduisez les efforts : Avec notre processus de modélisation, vous n’avez pas à deviner quelles caractéristiques/segments peuvent fonctionner ou à consacrer du temps aux campagnes pour découvrir de nouveaux publics. Le modèle peut faire ça pour vous.
* **** Fiabilité : La modélisation fonctionne avec des processus de détection et de qualification côté serveur qui évaluent vos propres données et les données tierces sélectionnées auxquelles vous avez accès. Cela signifie que vous n’avez pas à consulter les visiteurs de votre site pour les qualifier pour une caractéristique.

## Processus{#workflow}

Vous gérez les modèles dans **[!UICONTROL Audience Data > Models]**. À un niveau général, le processus de flux de travail implique les éléments suivants :

* Sélectionnez les données de base que vous souhaitez que l’algorithme évalue. Cela inclut une caractéristique ou un segment, une période et des sources de données (vos propres données et données tierces auxquelles vous avez déjà accès par l’intermédiaire [!DNL Audience Manager]). Dans le processus de création de modèles, vous pouvez exclure les caractéristiques que vous ne souhaitez pas interférer avec votre modèle.
* Enregistrez votre modèle. Une fois enregistré, le processus d’évaluation algorithmique s’exécute automatiquement. Notez toutefois que cette procédure peut prendre jusqu’à 7 jours. [!DNL Audience Manager] vous envoie un courrier électronique lorsque l’algorithme est terminé et que les résultats sont disponibles pour la création de caractéristiques.
* Créez des caractéristiques algorithmiques dans [!UICONTROL Trait Builder].
* Combinez les caractéristiques en segments dans [!UICONTROL Segment Builder].
* Créez et envoyez des données de segment vers une destination.

## Résolution des problèmes {#troubleshooting}

Nous désactivons tout modèle algorithmique qui ne génère pas de données pour trois exécutions consécutives. Notez que vous ne pouvez pas réactiver l’état du modèle par la suite. Pour garantir que vos modèles génèrent des données, nous vous recommandons de créer des modèles à partir de sources de données avec des caractéristiques suffisantes pour accumuler des données.

>[!MORE_LIKE_This]
>
>* [Destinations](../../features/destinations/destinations.md)
>* [Caractéristiques](../../features/traits/trait-details-page.md)
>* [Segments](../../features/segments/segments-purpose.md)


## Présentation de TraitWeight {#understanding-traitweight}

[!UICONTROL TraitWeight] est un algorithme propriétaire conçu pour découvrir automatiquement de nouvelles caractéristiques. Il compare les données de caractéristiques de vos caractéristiques et segments actuels à toutes les autres données propriétaires et tierces auxquelles vous avez accès par l’intermédiaire [!DNL Audience Manager]. Reportez-vous à cette section pour une description du processus de découverte [!UICONTROL TraitWeight] algorithmique.

<!-- traitweight.xml -->

![](assets/algo_model.png)

Les étapes suivantes décrivent le processus d’ [!UICONTROL TraitWeight] évaluation.

### Étape 1 : Créer une ligne de base pour la comparaison des caractéristiques

Pour créer une ligne de base, [!UICONTROL TraitWeight] mesure toutes les caractéristiques associées à une audience pendant un intervalle de 30, 60 ou 90 jours. Ensuite, il classe les caractéristiques selon leur fréquence et leur corrélation. Le nombre de fréquences mesure la communauté. La corrélation évalue la probabilité qu’une caractéristique ne soit présente que dans l’audience de base. Les caractéristiques qui apparaissent souvent présentent des points communs élevés, une caractéristique importante utilisée pour définir un score pondéré lorsqu’il est combiné aux caractéristiques découvertes dans les sources de données sélectionnées.

### Étape 2 : Rechercher les mêmes caractéristiques dans la source de données

Après avoir créé une ligne de base à des fins de comparaison, l’algorithme recherche des caractéristiques identiques dans les sources de données sélectionnées. Au cours de cette étape, [!UICONTROL TraitWeight] effectue un décompte de fréquence de toutes les caractéristiques découvertes et les compare à la ligne de base. Cependant, contrairement à la ligne de base, les caractéristiques peu courantes sont classées plus haut que celles qui apparaissent le plus souvent. On dit que les caractères rares présentent un degré élevé de spécificité. [!UICONTROL TraitWeight] évalue les combinaisons de caractéristiques de base communes et de caractéristiques de source de données peu communes (très spécifiques) comme étant plus influentes ou souhaitables que les caractéristiques communes aux deux ensembles de données. En fait, notre modèle reconnaît ces grandes caractéristiques communes et n’accorde pas une priorité excessive aux ensembles de données présentant des corrélations élevées. Les traits rares obtiennent une priorité plus élevée parce qu’ils sont plus susceptibles de représenter de nouveaux utilisateurs uniques que les traits présentant une grande communauté dans l’ensemble.

### Étape 3 : Attribuer un poids

Dans cette étape, [!UICONTROL TraitWeight] classe les caractéristiques nouvellement découvertes par ordre d'influence ou d'opportunité. L’échelle de poids est un pourcentage qui s’étend de 0 % à 100 %. Les caractéristiques classées plus près de 100 % signifient qu’elles ressemblent davantage au public dans votre population de base. En outre, les caractéristiques fortement pondérées sont précieuses car elles représentent de nouveaux utilisateurs uniques qui peuvent se comporter de la même manière que votre audience de base établie. N’oubliez pas que [!UICONTROL TraitWeight] les caractéristiques présentant une forte communauté dans la ligne de base et une grande spécificité dans les sources de données comparées sont plus précieuses que les caractéristiques communes à chaque ensemble de données.

### Étape 4 : Score des utilisateurs

Chaque utilisateur des sources de données sélectionnées reçoit un score d’utilisateur égal à la somme de tous les poids des caractéristiques influentes sur son profil. Les scores de l’utilisateur sont alors normalisés entre 0 et 100 %.

### Étape 5 : Afficher et travailler avec les résultats

Audience Manager affiche les résultats des modèles pondérés dans [!UICONTROL Trait Builder]. Lorsque vous souhaitez créer une caractéristique algorithmique, [!UICONTROL Trait Builder] vous permet de créer des caractéristiques basées sur le score pondéré généré par l’algorithme au cours d’une exécution de données. Vous pouvez choisir une précision plus élevée afin de ne qualifier que les utilisateurs qui ont des scores utilisateur très élevés et sont donc très similaires au public de base, plutôt que le reste du public. Si vous souhaitez atteindre un public plus large (portée), vous pouvez réduire la précision.

### Étape 6 : Réévaluer la signification d’un trait sur plusieurs cycles de traitement

Régulièrement, [!UICONTROL TraitWeight] réévalue l’importance d’un trait en fonction de la taille et du changement de la population de ce trait. Cela se produit lorsque le nombre d’utilisateurs qualifiés pour cette caractéristique augmente ou diminue au fil du temps. Ce comportement est plus clairement visible dans les caractéristiques qui deviennent très grandes. Supposons, par exemple, que l’algorithme utilise la caractéristique A pour la modélisation. À mesure que la population du trait A augmente, [!UICONTROL TraitWeight] réévalue l’importance de ce trait et peut attribuer un score plus faible ou l’ignorer. Dans ce cas, le trait A est trop commun ou trop grand pour dire quoi que ce soit de significatif sur sa population. Après [!UICONTROL TraitWeight] avoir réduit la valeur du trait A (ou l’avoir ignoré dans le modèle), la population de la caractéristique algorithmique diminue. La liste des caractéristiques influentes reflète l'évolution de la population de base. Utilisez la liste des caractéristiques influentes pour comprendre pourquoi ces changements se produisent.

Liens connexes :

* [Créateur de modèles](../../features/algorithmic-models/create-model.md)
* [Précision et portée](../../features/traits/trait-accuracy-reach.md)

## Planification de la mise à jour des modèles et caractéristiques algorithmiques {#update-schedule}

Création et mise à jour des calendriers pour les modèles et caractéristiques algorithmiques nouveaux ou existants.

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
   <td colname="col1"> <b>Création ou duplication d’un modèle</b> </td>
   <td colname="col2"> <p>Pour les modèles algorithmiques nouveaux ou clonés, le processus de création s’exécute une fois par jour à l’adresse suivante : 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17 h (novembre à mars) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18h HAE (mars à novembre) </li> 
     </ul> </p> <p>Les modèles créés ou clonés après la date limite de création sont traités le lendemain. </p> <p>Si la première exécution d’un modèle ne génère aucune donnée, elle s’exécutera une deuxième fois, le lendemain. Si la deuxième tentative ne génère pas de données, il y aura une troisième tentative, le lendemain. Le modèle cessera de fonctionner si la troisième tentative ne génère aucune donnée. Dans ce cas, nous allons désactiver le modèle. Pour en savoir plus, voir <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Dépannage des modèles</a>algorithmiques. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Mettre à jour un modèle</b> </td> 
   <td colname="col2"> <p>Dans des conditions idéales, les modèles existants sont exécutés en semaine, au moins une fois tous les 7 jours. Par exemple, si vous créez un modèle (avant la date limite) le lundi, il met à jour le lundi suivant au plus tard. </p> <p>Un modèle se réexécute s’il répond à l’une des conditions suivantes : </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sa dernière course a échoué. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Il s'est exécuté avec succès avant ET il ne s'est pas exécuté du tout au cours des 7 derniers jours ET le modèle a au moins une caractéristique active qui lui est associée. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Planification de la création et de la mise à jour des caractéristiques algorithmiques

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’activité </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Créer un trait</b> </td> 
   <td colname="col2"> <p>Le processus de création de caractéristiques s’exécute tous les jours, du lundi au vendredi. En règle générale, de nouvelles caractéristiques algorithmiques apparaissent dans l’interface utilisateur dans les 48 heures. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mettre à jour un trait</b> </td> 
   <td colname="col2"> <p>Les caractéristiques existantes sont mises à jour au moins une fois tous les 7 jours et suivent le calendrier des mises à jour des modèles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Mode Liste Modèles {#models-list-view}

La vue Liste est un espace de travail central qui vous aide à créer, réviser et gérer des modèles.

<!-- c_models_list_view.xml -->

La page de liste Modèles contient des fonctionnalités et des outils qui vous aident à :

* Créez de nouveaux modèles.
* Gérez les modèles existants (modifier, suspendre, supprimer ou cloner).
* Recherchez les modèles par nom.
* Créez des caractéristiques algorithmiques à l’aide d’un modèle donné.

## Mode Résumé des modèles {#models-summary-view}

La page de résumé affiche les détails du modèle, tels que le nom, la portée/précision, l’historique de traitement et les caractéristiques créées à partir du modèle. La page comprend également des paramètres qui vous permettent de créer et de gérer des modèles. Cliquez sur le nom d’un modèle dans la liste de résumé pour en afficher les détails.

<!-- c_models_summary.xml -->

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
   <td colname="col1"> <p> <span class="wintitle"> Informations fondamentales</span> </p> </td>
   <td colname="col2"> <p>Inclut des informations de base sur le modèle, telles que son nom et sa dernière exécution. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Portée du modèle et précision</span> </p> </td> 
   <td colname="col2"> <p>Indique la <a href="../../features/traits/trait-accuracy-reach.md"> précision et la portée</a> des données pour la dernière exécution du modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historique de traitement du modèle</span> </p> </td> 
   <td colname="col2"> <p>Affiche la date et l’heure de traitement des 10 dernières exécutions et indique si des données ont été générées sur ces exécutions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques influentes</span> </p> </td> 
   <td colname="col2"> <p>Le tableau Caractéristiques <span class="wintitle"> de l’</span> influence : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Répertorie les 50 principales caractéristiques influentes les plus représentées dans la population de référence du modèle. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classe chaque trait par ordre de son poids <span class="wintitle"></span> relatif. Le <span class="wintitle"> Poids</span> Relatif trie les caractéristiques nouvellement découvertes par ordre d'influence ou d'opportunité. L’échelle de poids est un pourcentage qui s’étend de 0 % à 100 %. Les caractéristiques classées plus près de 100 % signifient qu’elles ressemblent davantage au public dans votre population de base. Voir <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Présentation du TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Affiche les valeurs uniques de 30 jours et la population totale de caractéristiques pour chaque caractéristique. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques utilisant le modèle</span> </p> </td>
   <td colname="col2"> <p>Affiche une liste des caractéristiques algorithmiques basées sur le modèle sélectionné. Cliquez sur un nom de caractéristique ou un ID de caractéristique pour plus d’informations sur la caractéristique. Sélectionnez <b><span class="uicontrol"> Créer un nouveau trait avec modèle</span></b> pour accéder au processus de création de caractéristiques algorithmiques. </p> <p>Le libellé de la section change en fonction du nom de votre modèle. Supposons, par exemple, que vous créiez un modèle et que vous le nommiez Modèle A. Lorsque vous chargez la page de résumé, le nom de cette section devient <span class="wintitle"> Caractéristiques à l’aide du modèle A</span>. </p> </td>
  </tr>
 </tbody>
</table>