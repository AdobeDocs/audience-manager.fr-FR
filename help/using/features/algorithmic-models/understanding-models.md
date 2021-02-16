---
description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation de l’apparence.
keywords: poids relatif, ressemblant
seo-description: Créez et gérez les caractéristiques ou les segments utilisés dans la modélisation de l’apparence.
seo-title: A propos de la modélisation à l’apparence
solution: Audience Manager
title: A propos de la modélisation à l’apparence
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1593'
ht-degree: 1%

---


# Comprendre [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Rechercher de nouveaux utilisateurs avec [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] vous aide à découvrir de nouvelles audiences uniques grâce à l’analyse automatisée des données. Le processus se début lorsque vous sélectionnez [!UICONTROL trait] ou [!UICONTROL segment], un intervalle de temps, et [!UICONTROL data sources] premier et tiers. Vos choix fournissent les entrées pour le modèle algorithmique. Lorsque le processus d’analyse s’exécute, il recherche les utilisateurs éligibles en fonction de caractéristiques partagées de la population sélectionnée. Une fois les données terminées, elles sont disponibles dans [Trait Builder](../../features/traits/about-trait-builder.md) où vous pouvez les utiliser pour créer des caractéristiques basées sur [la précision et la portée](../../features/traits/trait-accuracy-reach.md). De plus, vous pouvez créer des segments qui combinent des caractéristiques algorithmiques avec [!UICONTROL rules-based traits] et ajouter d’autres exigences de qualification avec des expressions et des opérateurs de comparaison [!DNL Boolean]. [!UICONTROL Look-Alike Modeling] vous permet d’extraire de la valeur de toutes les données de caractéristiques disponibles de manière dynamique.

## Avantages {#advantages}

Les principaux avantages de l&#39;utilisation de [!UICONTROL Look-Alike Modeling] sont les suivants :

* **Précision des données :** l’algorithme s’exécute régulièrement, ce qui permet de garder les résultats à jour et pertinents.
* **Automatisation :** vous n’avez pas à gérer un ensemble important de règles statiques. L&#39;algorithme trouvera des audiences pour vous.
* **Gagnez du temps et réduisez les efforts :** grâce à notre processus de modélisation, vous n’avez pas à deviner ce qui  [!UICONTROL traits]/[!UICONTROL segments] peut fonctionner ou consacrer du temps aux campagnes pour découvrir de nouvelles audiences. Le modèle peut faire ça pour vous.
* **Fiabilité :** la modélisation fonctionne avec des processus de détection et de qualification côté serveur qui évaluent vos propres données et les données tierces sélectionnées auxquelles vous avez accès. Cela signifie que vous n’avez pas besoin de voir les visiteurs sur votre site pour les qualifier pour une caractéristique.

## Processus{#workflow}

Vous gérez les modèles dans **[!UICONTROL Audience Data > Models]**. A un niveau élevé, le processus de flux de travail implique les éléments suivants :

* Sélectionnez les données de base que l’algorithme doit évaluer. Cela inclut une plage de temps [!UICONTROL trait] ou [!UICONTROL segment] et [!UICONTROL data sources] (vos propres données et données tierces auxquelles vous avez déjà accès par [!DNL Audience Manager]). Dans le processus de création de modèle, vous pouvez exclure le [!UICONTROL traits] que vous ne souhaitez pas interférer avec votre modèle.
* Enregistrez votre modèle. Une fois enregistré, le processus d’évaluation algorithmique s’exécute automatiquement. Notez toutefois que cette procédure peut prendre jusqu’à 7 jours. [!DNL Audience Manager] vous envoie un courrier électronique lorsque l’algorithme est terminé et que les résultats sont disponibles pour  [!UICONTROL trait] la création.
* Créez l’algorithme [!UICONTROL traits] dans [!UICONTROL Trait Builder].
* Combinez [!UICONTROL traits] en [!UICONTROL segments] dans [!UICONTROL Segment Builder].
* Créez et envoyez des données [!UICONTROL segment] à un [!UICONTROL destination].

## Résolution des problèmes {#troubleshooting}

Nous désactivons toute [!UICONTROL Look-Alike Model] qui ne parvient pas à générer des données pour trois exécutions consécutives. Notez que vous ne pouvez pas redéfinir l&#39;état du modèle sur principal après. Pour nous assurer que vos modèles génèrent des données, nous vous recommandons de créer des modèles à partir de sources de données avec un [!UICONTROL traits] suffisant pour accumuler des données.

## Comprendre [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] est un algorithme propriétaire conçu pour découvrir  [!UICONTROL traits] automatiquement les nouveaux. Il compare les données [!UICONTROL trait] de vos [!UICONTROL traits] et [!UICONTROL segments] actuels à toutes les autres données propriétaires et tierces auxquelles vous avez accès par [!DNL Audience Manager]. Reportez-vous à cette section pour une description du processus de découverte algorithmique [!UICONTROL TraitWeight].

![](assets/algo_model.png)

Les étapes suivantes décrivent le processus d&#39;évaluation de [!UICONTROL TraitWeight].

### Étape 1 : Créer une ligne de base pour la comparaison [!UICONTROL Trait]

Pour créer une ligne de base, [!UICONTROL TraitWeight] mesure tous les [!UICONTROL traits] associés à une audience pour un intervalle de 30, 60 ou 90 jours. Ensuite, il classe [!UICONTROL traits] en fonction de leur fréquence et de leur corrélation. Le décompte des fréquences mesure les points communs. La corrélation mesure la probabilité qu&#39;un [!UICONTROL trait] ne soit présent que dans l&#39;audience de référence. [!UICONTROL Traits] qui semblent souvent présenter des points communs élevés, une caractéristique importante utilisée pour définir un score pondéré lorsqu&#39;il est combiné avec  [!UICONTROL traits] découvert dans votre  [!UICONTROL data sources]choix.

### Étape 2 : Rechercher la même [!UICONTROL Traits] dans le [!UICONTROL Data Source]

Après avoir créé une ligne de base à des fins de comparaison, l’algorithme recherche [!UICONTROL traits] identique dans le [!UICONTROL data sources]  sélectionné. Au cours de cette étape, [!UICONTROL TraitWeight] effectue un décompte de fréquence de tous les [!UICONTROL traits] découverts et les compare à la ligne de base. Cependant, contrairement à la ligne de base, [!UICONTROL traits] rare est classé plus haut que ceux qui apparaissent plus souvent. On dit que les [!UICONTROL traits] rares présentent un haut degré de spécificité. [!UICONTROL TraitWeight] évalue les combinaisons de lignes de base communes  [!UICONTROL traits] et de lignes de base inhabituelles (très spécifiques)  [!UICONTROL data source] [!UICONTROL traits] comme étant plus influentes ou souhaitables que  [!UICONTROL traits] communes aux deux ensembles de données. En fait, notre modèle reconnaît ces grandes [!UICONTROL traits] communes et n&#39;accorde pas une priorité excessive aux ensembles de données présentant des corrélations élevées. Rare [!UICONTROL traits] a une priorité plus élevée parce qu&#39;ils sont plus susceptibles de représenter de nouveaux utilisateurs uniques que [!UICONTROL traits] avec une communauté élevée dans l&#39;ensemble.

### Étape 3 : Attribuer un Poids

À cette étape, [!UICONTROL TraitWeight] classe [!UICONTROL traits] les nouveaux  par ordre d&#39;influence ou d&#39;opportunité. L&#39;échelle de poids est un pourcentage qui s&#39;étend de 0 % à 100 %. [!UICONTROL Traits] classé plus près de 100 % signifie qu’ils ressemblent davantage à l’audience de votre population de base. En outre, les [!UICONTROL traits] fortement pondérés sont utiles parce qu&#39;ils représentent de nouveaux utilisateurs uniques qui peuvent se comporter de la même manière que votre audience de base établie. N&#39;oubliez pas que [!UICONTROL TraitWeight] considère [!UICONTROL traits] que la ligne de base présente des points communs élevés et que la grande spécificité des sources de données comparées est plus précieuse que [!UICONTROL traits] que ce qui est commun à chaque jeu de données.

### Étape 4 : Notation des utilisateurs

Chaque utilisateur de l’élément [!UICONTROL data sources] sélectionné reçoit un score d’utilisateur égal à la somme de tous les poids de l’élément [!UICONTROL traits] influent sur son profil. Les scores de l’utilisateur sont ensuite normalisés entre 0 et 100 %.

### Étape 5 : Affichage et utilisation des résultats

[!DNL Audience Manager] affiche les résultats du modèle pondéré dans  [!UICONTROL Trait Builder]. Lorsque vous souhaitez créer un [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] vous permet de créer [!UICONTROL traits] en fonction du score pondéré généré par l’algorithme au cours d’une exécution de données. Vous pouvez choisir une précision plus élevée afin de ne qualifier que les utilisateurs dont les scores d’utilisateur sont très élevés et sont donc très similaires à l’audience de base, plutôt que le reste de l’audience. Si vous souhaitez atteindre une plus grande audience (portée), vous pouvez réduire la précision.

### Étape 6 : Réévaluer l&#39;importance d&#39;un [!UICONTROL Trait] sur plusieurs cycles de traitement

Périodiquement, [!UICONTROL TraitWeight] réévalue l&#39;importance d&#39;un [!UICONTROL trait] en fonction de la taille et du changement de la population de ce [!UICONTROL trait]. Cela se produit lorsque le nombre d’utilisateurs qualifiés pour ce [!UICONTROL trait] augmente ou diminue au fil du temps. Ce comportement est plus clairement visible dans les caractères qui deviennent très grands. Par exemple, supposons que l’algorithme utilise [!UICONTROL trait A] pour la modélisation. À mesure que la population de [!UICONTROL trait A] augmente, [!UICONTROL TraitWeight] réévalue l&#39;importance de [!UICONTROL trait] et peut attribuer un score inférieur ou l&#39;ignorer. Dans ce cas, [!UICONTROL trait A] est trop courant ou trop grand pour dire quoi que ce soit d&#39;important sur sa population. Une fois [!UICONTROL TraitWeight] réduit la valeur de [!UICONTROL trait A] (ou l&#39;ignore dans le modèle), la population de la caractéristique algorithmique diminue. La liste de [!UICONTROL traits] influent reflète l&#39;évolution de la population de base. Utilisez la liste de l&#39;influent [!UICONTROL traits] pour comprendre pourquoi ces changements se produisent.

Liens connexes :

* [Créateur de modèles](../../features/algorithmic-models/create-model.md)
* [Précision et portée](../../features/traits/trait-accuracy-reach.md)

## Calendrier de mise à jour pour [!UICONTROL Look-Alike Models] et [!UICONTROL Traits] {#update-schedule}

Planifications de création et de mise à jour pour [!UICONTROL algorithmic models] et [!UICONTROL traits] nouveaux ou existants.

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
     </ul> </p> <p>Les modèles créés ou clonés après l’échéance de création sont traités le lendemain. </p> <p>Si la première exécution d'un modèle ne génère aucune donnée, elle s'exécute une deuxième fois, le lendemain. Si la deuxième tentative ne génère pas de données, il y aura une troisième tentative, le lendemain. Le modèle s'arrête si la troisième tentative ne génère pas non plus de données. Dans ce cas, nous désactiverons le modèle. Pour en savoir plus, voir <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Dépannage des modèles ressemblant à un look</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Mettre à jour un modèle</b> </td> 
   <td colname="col2"> <p>Dans des conditions idéales, les modèles existants s'exécutent en semaine, au moins une fois tous les 7 jours. Par exemple, si vous créez un modèle (avant la date limite) le lundi, il met à jour le lundi suivant au plus tard. </p> <p>Un modèle se réexécute s’il répond à l’une des conditions suivantes : </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">Sa dernière exécution a échoué. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Il s'est exécuté avec succès avant ET il ne s'est pas exécuté du tout au cours des 7 derniers jours ET le modèle a au moins un trait principal qui lui est associé. </li>
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
   <td colname="col1"> <b>Mettre à jour un trait</b> </td> 
   <td colname="col2"> <p>Les caractéristiques existantes sont mises à jour au moins une fois tous les 7 jours et suivent le calendrier des mises à jour des modèles. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vue de Liste de modèles {#models-list-view}

La vue de liste est un espace de travail central qui vous permet de créer, de réviser et de gérer des modèles.

La page de liste [!UICONTROL Models] contient des fonctionnalités et des outils qui vous aident à :

* Créez de nouveaux modèles.
* Gérer les modèles existants (modifier, suspendre, supprimer ou cloner).
* Rechercher des modèles par nom.
* Créez [!UICONTROL algorithmic traits] à l&#39;aide d&#39;un modèle donné.

## Vue de résumé des modèles {#models-summary-view}

La page de résumé affiche les détails du modèle tels que le nom, la portée/précision, l&#39;historique de traitement et [!UICONTROL traits] créés à partir du modèle. La page comprend également des paramètres qui vous permettent de créer et de gérer des modèles. Cliquez sur un nom de modèle dans la liste de résumé pour en afficher les détails.

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
   <td colname="col2"> <p>Affiche la précision <a href="../../features/traits/trait-accuracy-reach.md"> et les données </a> de portée pour la dernière exécution du modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Historique de traitement du modèle</span> </p> </td> 
   <td colname="col2"> <p>Affiche la date et l’heure de traitement des 10 dernières exécutions et indique si des données ont été générées sur ces exécutions. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques influentes</span> </p> </td> 
   <td colname="col2"> <p>Le tableau <span class="wintitle"> Caractéristiques d'influence</span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Liste les 50 principales caractéristiques influentes les mieux représentées dans la population de référence du modèle. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Classe chaque trait dans l'ordre de son classement <span class="wintitle"> Poids relatif</span>. Le <span class="wintitle"> Poids relatif</span> trie les caractéristiques nouvellement découvertes par ordre d'influence ou de désirabilité. L'échelle de poids est un pourcentage qui s'étend de 0 % à 100 %. Les traits classés plus près de 100 % signifient qu’ils ressemblent davantage à l’audience de votre population de base. Voir <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Présentation de TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Affiche les valeurs uniques de 30 jours et la population totale de caractéristiques pour chaque caractéristique. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Caractéristiques utilisant le modèle</span> </p> </td>
   <td colname="col2"> <p>Affiche une liste des caractéristiques algorithmiques en fonction du modèle sélectionné. Cliquez sur un nom de caractéristique ou un ID de caractéristique pour plus d’informations sur la caractéristique. Sélectionnez <b><span class="uicontrol"> Créer une caractéristique avec le modèle</span></b> pour accéder au processus de création de caractéristiques algorithmiques. </p> <p>Le libellé de la section change en fonction du nom de votre modèle. Supposons, par exemple, que vous créiez un modèle et que vous le nommiez Modèle A. Lorsque vous chargez la page de résumé, le nom de cette section est remplacé par <span class="wintitle"> Caractéristiques utilisant le modèle A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Destinations ](../../features/destinations/destinations.md)
>* [Caractéristiques ](../../features/traits/trait-details-page.md)
>* [Segments ](../../features/segments/segments-purpose.md)

