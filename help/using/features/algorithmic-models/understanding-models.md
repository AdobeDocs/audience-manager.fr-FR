---
description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation de l’apparence.
keywords: relative weight, lookalike
seo-description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation de l’apparence.
seo-title: A propos de la modélisation à l’apparence
solution: Audience Manager
title: A propos de la modélisation à l’apparence
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 1%

---


# Compréhension [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Rechercher de nouveaux utilisateurs avec [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] vous aide à découvrir de nouvelles audiences uniques grâce à l’analyse automatisée des données. Le processus se début lorsque vous sélectionnez un [!UICONTROL trait] ou [!UICONTROL segment], un intervalle de temps et un premier ou un tiers [!UICONTROL data sources]. Vos choix fournissent les entrées pour le modèle algorithmique. Lorsque le processus d’analyse s’exécute, il recherche les utilisateurs éligibles en fonction de caractéristiques partagées de la population sélectionnée. Une fois l’opération terminée, ces données sont disponibles dans le créateur [de](../../features/traits/about-trait-builder.md) caractéristiques où vous pouvez les utiliser pour créer des caractéristiques basées sur la [précision et la portée](../../features/traits/trait-accuracy-reach.md). De plus, vous pouvez créer des segments qui combinent des caractéristiques algorithmiques avec [!UICONTROL rules-based traits] et ajouter d’autres exigences de qualification avec [!DNL Boolean] des expressions et des opérateurs de comparaison. [!UICONTROL Look-Alike Modeling] vous permet d’extraire de la valeur de toutes les données de caractéristiques disponibles de manière dynamique.

## Avantages {#advantages}

Les principaux avantages de l&#39;utilisation [!UICONTROL Look-Alike Modeling] sont les suivants :

* **Précision des données :** L’algorithme s’exécute régulièrement, ce qui permet de garder les résultats à jour et pertinents.
* **Automatisation :** Vous n’avez pas à gérer un ensemble important de règles statiques. L&#39;algorithme trouvera des audiences pour vous.
* **Gagnez du temps et réduisez les efforts :** Avec notre processus de modélisation, vous n’avez pas à deviner ce qui [!UICONTROL traits]/[!UICONTROL segments] peut fonctionner ou passer du temps sur les campagnes pour découvrir de nouvelles audiences. Le modèle peut faire ça pour vous.
* **Fiabilité :** La modélisation fonctionne avec des processus de détection et de qualification côté serveur qui évaluent vos propres données et les données tierces sélectionnées auxquelles vous avez accès. Cela signifie que vous n’avez pas besoin de voir les visiteurs sur votre site pour les qualifier pour une caractéristique.

## Processus{#workflow}

Vous gérez les modèles dans **[!UICONTROL Audience Data > Models]**. A un niveau élevé, le processus de flux de travail implique les éléments suivants :

* Sélectionnez les données de base que l’algorithme doit évaluer. Cela inclut un ou [!UICONTROL trait][!UICONTROL segment], une plage de temps et [!UICONTROL data sources] (vos propres données et données tierces auxquelles vous avez déjà accès par [!DNL Audience Manager]le biais de). Dans le processus de création de modèle, vous pouvez exclure le [!UICONTROL traits] fait que vous ne souhaitez pas interférer avec votre modèle.
* Enregistrez votre modèle. Une fois enregistré, le processus d’évaluation algorithmique s’exécute automatiquement. Notez toutefois que cette procédure peut prendre jusqu’à 7 jours. [!DNL Audience Manager] vous envoie un courrier électronique lorsque l’algorithme est terminé et que les résultats sont disponibles pour [!UICONTROL trait] la création.
* Créez un algorithme [!UICONTROL traits] dans [!UICONTROL Trait Builder].
* Combinez [!UICONTROL traits] dans [!UICONTROL segments] dans [!UICONTROL Segment Builder].
* Créez et envoyez [!UICONTROL segment] des données à un [!UICONTROL destination]utilisateur.

## Résolution des problèmes {#troubleshooting}

Nous désactivons toutes les [!UICONTROL Look-Alike Model] qui ne génèrent pas de données pour trois exécutions consécutives. Notez que vous ne pouvez pas réactiver l&#39;état du modèle par la suite. Pour garantir que vos modèles génèrent des données, nous vous recommandons de créer des modèles à partir de sources de données avec suffisamment [!UICONTROL traits] de données pour en accumuler.

## Compréhension [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] est un algorithme propriétaire conçu pour découvrir de nouveaux [!UICONTROL traits] automatiquement. Il compare [!UICONTROL trait] les données de vos données actives [!UICONTROL traits] et [!UICONTROL segments] à toutes les autres données propriétaires et tierces auxquelles vous avez accès par le biais [!DNL Audience Manager]. Reportez-vous à cette section pour une description du processus de découverte [!UICONTROL TraitWeight] algorithmique.

![](assets/algo_model.png)

Les étapes suivantes décrivent le processus d&#39; [!UICONTROL TraitWeight] évaluation.

### Étape 1 : Créer une référence pour la [!UICONTROL Trait] comparaison

Pour établir une référence, [!UICONTROL TraitWeight] mesure tous les éléments [!UICONTROL traits] associés à une audience pour un intervalle de 30, 60 ou 90 jours. Ensuite, il se classe [!UICONTROL traits] selon leur fréquence et leur corrélation. Le décompte des fréquences mesure les points communs. La corrélation mesure la probabilité qu&#39;une [!UICONTROL trait] personne ne soit présente que dans l&#39;audience de référence. [!UICONTROL Traits] qui semblent souvent présenter des points communs élevés, une caractéristique importante utilisée pour définir un score pondéré lorsqu&#39;il est combiné avec [!UICONTROL traits] découvert dans votre [!UICONTROL data sources]choix.

### Étape 2 : Identique [!UICONTROL Traits] dans la section [!UICONTROL Data Source]

Après avoir créé une ligne de base à des fins de comparaison, l’algorithme recherche la même ligne de base [!UICONTROL traits] dans votre [!UICONTROL data sources]choix. Au cours de cette étape, [!UICONTROL TraitWeight] effectue un décompte de fréquence de toutes les [!UICONTROL traits] découvertes et les compare à la ligne de base. Cependant, contrairement à la ligne de base, les valeurs les plus rares [!UICONTROL traits] sont classées plus haut que celles qui apparaissent le plus souvent. On [!UICONTROL traits] dit que les rares ont un degré élevé de spécificité. [!UICONTROL TraitWeight] évalue les combinaisons de lignes de base communes [!UICONTROL traits] et de lignes de base inhabituelles (très spécifiques) [!UICONTROL data source] comme étant plus influentes ou souhaitables que [!UICONTROL traits] [!UICONTROL traits] communes aux deux ensembles de données. En fait, notre modèle reconnaît ces grands ensembles de données communs [!UICONTROL traits] et n&#39;accorde pas une priorité excessive aux ensembles de données présentant des corrélations élevées. Rares [!UICONTROL traits] obtiennent une priorité plus élevée parce qu’ils sont plus susceptibles de représenter de nouveaux utilisateurs uniques que [!UICONTROL traits] avec une communauté élevée dans l’ensemble.

### Étape 3 : Attribuer un Poids

Dans cette étape, [!UICONTROL TraitWeight] classe les nouveaux découverts [!UICONTROL traits] par ordre d&#39;influence ou d&#39;opportunité. L&#39;échelle de poids est un pourcentage qui s&#39;étend de 0 % à 100 %. [!UICONTROL Traits] classé plus près de 100 % signifie qu’ils ressemblent davantage à l’audience de votre population de base. En outre, les valeurs pondérées [!UICONTROL traits] sont précieuses car elles représentent de nouveaux utilisateurs uniques qui peuvent se comporter de la même manière que votre audience de base établie. N’oubliez pas que [!UICONTROL TraitWeight] les données comparées présentent [!UICONTROL traits] des points communs élevés dans la ligne de base et une grande spécificité dans les sources de données comparées, ce qui est plus intéressant que [!UICONTROL traits] commun dans chaque jeu de données.

### Étape 4 : Notation des utilisateurs

Chaque utilisateur sélectionné [!UICONTROL data sources] reçoit un score d&#39;utilisateur égal à la somme de tous les poids de l&#39;influent [!UICONTROL traits] sur son profil. Les scores de l’utilisateur sont ensuite normalisés entre 0 et 100 %.

### Étape 5 : Affichage et utilisation des résultats

[!DNL Audience Manager] affiche les résultats du modèle pondéré dans [!UICONTROL Trait Builder]. Lorsque vous souhaitez créer un [!UICONTROL algorithmic trait]algorithme, [!UICONTROL Trait Builder] vous permet de créer [!UICONTROL traits] en fonction du score pondéré généré par l’algorithme au cours d’une exécution de données. Vous pouvez choisir une précision plus élevée afin de ne qualifier que les utilisateurs dont les scores d’utilisateur sont très élevés et sont donc très similaires à l’audience de base, plutôt que le reste de l’audience. Si vous souhaitez atteindre une plus grande audience (portée), vous pouvez réduire la précision.

### Étape 6 : Réévaluer l’importance d’un cycle de traitement [!UICONTROL Trait] sur plusieurs

Régulièrement, [!UICONTROL TraitWeight] réévalue l&#39;importance d&#39;un [!UICONTROL trait] rapport en fonction de la taille et de l&#39;évolution de la population de ce [!UICONTROL trait]groupe. Cela se produit lorsque le nombre d&#39;utilisateurs qualifiés pour cela [!UICONTROL trait] augmente ou diminue au fil du temps. Ce comportement est plus clairement visible dans les caractères qui deviennent très grands. Supposons, par exemple, que l’algorithme utilise [!UICONTROL trait A] pour la modélisation. Au fur et à mesure que la population augmente, [!UICONTROL trait A] réévalue l&#39;importance de cette situation [!UICONTROL TraitWeight] [!UICONTROL trait] et peut attribuer un score plus faible ou l&#39;ignorer. Dans ce cas, [!UICONTROL trait A] il est trop courant ou trop important pour dire quoi que ce soit d&#39;important sur sa population. Après [!UICONTROL TraitWeight] avoir réduit la valeur de [!UICONTROL trait A] (ou l’avoir ignorée dans le modèle), la population de la caractéristique algorithmique diminue. La liste de l&#39;influence [!UICONTROL traits] reflète l&#39;évolution de la population de base. Utilisez la liste de l’influent [!UICONTROL traits] pour comprendre pourquoi ces changements se produisent.

Liens connexes :

* [Créateur de modèles](../../features/algorithmic-models/create-model.md)
* [Précision et portée](../../features/traits/trait-accuracy-reach.md)

## Mettre à jour le calendrier pour [!UICONTROL Look-Alike Models] et [!UICONTROL Traits] {#update-schedule}

Planification de la création et de la mise à jour pour les nouveaux programmes [!UICONTROL algorithmic models] et les programmes existants [!UICONTROL traits].

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
   <td colname="col1"> <b>Création ou duplication d’un modèle</b> </td>
   <td colname="col2"> <p>Pour les nouveaux [ !UICONTROL Look Alike Models] ou clonés, le processus de création s’exécute une fois par jour à l’adresse suivante : 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 17 h (novembre à mars) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 18h HAE (mars à novembre) </li> 
     </ul> </p> <p>Les modèles créés ou clonés après l’échéance de création sont traités le lendemain. </p> <p>Si la première exécution d'un modèle ne génère aucune donnée, elle s'exécute une deuxième fois, le lendemain. Si la deuxième tentative ne génère pas de données, il y aura une troisième tentative, le lendemain. Le modèle s'arrête si la troisième tentative ne génère pas non plus de données. Dans ce cas, nous désactiverons le modèle. Pour en savoir plus, voir <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Dépannage des modèles</a>ressemblants. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Mettre à jour un modèle</b> </td> 
   <td colname="col2"> <p>Dans des conditions idéales, les modèles existants s'exécutent en semaine, au moins une fois tous les 7 jours. Par exemple, si vous créez un modèle (avant la date limite) le lundi, il met à jour le lundi suivant au plus tard. </p> <p>Un modèle se réexécute s’il répond à l’une des conditions suivantes : </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sa dernière exécution a échoué. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Il s'est exécuté avec succès avant ET il ne s'est pas exécuté du tout au cours des 7 derniers jours ET le modèle a au moins une caractéristique active qui lui est associée. </li>
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

## Vue de Liste de modèles {#models-list-view}

La vue de liste est un espace de travail central qui vous permet de créer, de réviser et de gérer des modèles.

La page [!UICONTROL Models] liste contient des fonctionnalités et des outils qui vous aident à :

* Créez de nouveaux modèles.
* Gérer les modèles existants (modifier, suspendre, supprimer ou cloner).
* Rechercher des modèles par nom.
* Créez [!UICONTROL algorithmic traits] à l’aide de n’importe quel modèle donné.

## Vue de résumé des modèles {#models-summary-view}

La page de résumé affiche les détails du modèle tels que le nom, la portée/précision, l’historique de traitement et l’historique [!UICONTROL traits] créé à partir du modèle. La page comprend également des paramètres qui vous permettent de créer et de gérer des modèles. Cliquez sur un nom de modèle dans la liste de résumé pour en afficher les détails.

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
   <td colname="col1"> <p> <span class="wintitle"> Portée et précision du modèle</span> </p> </td> 
   <td colname="col2"> <p>Indique la précision et la portée <a href="../../features/traits/trait-accuracy-reach.md"> des données</a> pour la dernière exécution de modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historique de traitement du modèle</span> </p> </td> 
   <td colname="col2"> <p>Affiche la date et l’heure de traitement des 10 dernières exécutions et indique si des données ont été générées sur ces exécutions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques influentes</span> </p> </td> 
   <td colname="col2"> <p>Le tableau Caractéristiques <span class="wintitle"></span> influentes : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Liste les 50 principales caractéristiques influentes les mieux représentées dans la population de référence du modèle. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classe chaque trait par ordre de classement de son Poids <span class="wintitle"></span> relatif. Le Poids <span class="wintitle"></span> relatif trie les caractéristiques nouvellement découvertes par ordre d'influence ou de désirabilité. L'échelle de poids est un pourcentage qui s'étend de 0 % à 100 %. Les traits classés plus près de 100 % signifient qu’ils ressemblent davantage à l’audience de votre population de base. Voir <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Comprendre le poids</a>des caractéristiques. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Affiche les valeurs uniques de 30 jours et la population totale de caractéristiques pour chaque caractéristique. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques utilisant le modèle</span> </p> </td>
   <td colname="col2"> <p>Affiche une liste des caractéristiques algorithmiques en fonction du modèle sélectionné. Cliquez sur un nom de caractéristique ou un ID de caractéristique pour plus d’informations sur la caractéristique. Sélectionnez <b><span class="uicontrol"> Créer une nouvelle caractéristique avec modèle</span></b> pour accéder au processus de création de caractéristiques algorithmique. </p> <p>Le libellé de la section change en fonction du nom de votre modèle. Supposons, par exemple, que vous créiez un modèle et que vous le nommiez Modèle A. Lorsque vous chargez la page de résumé, le nom de cette section est remplacé par <span class="wintitle"> Caractéristiques utilisant le modèle A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinations](../../features/destinations/destinations.md)
>* [Caractéristiques](../../features/traits/trait-details-page.md)
>* [Segments](../../features/segments/segments-purpose.md)

