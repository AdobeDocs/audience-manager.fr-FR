---
description: Décrit comment créer des segments avec le créateur de segments.
seo-description: Décrit comment créer des segments avec le créateur de segments.
seo-title: Créateur de segments
solution: Audience Manager
title: Créateur de segments
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Décrit les étapes requises et facultatives de création d’un segment dans [!UICONTROL Segment Builder].

## Démonstration vidéo

Début en regardant la vidéo [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Créer des segments dans l’Audience Manager. La vidéo vous guide tout au long du processus de création de segments. Lisez les sections ci-dessous pour plus d&#39;informations.

## Créez un [!UICONTROL Segment] {#create-segment}

### Section Créateur de segments

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] se compose de 3 sections distinctes : [!UICONTROL Basic Information], [!UICONTROL Traits]et [!UICONTROL Destinations Mapping]. Pour créer un [!UICONTROL segment], renseignez les champs obligatoires des [!UICONTROL Basic Information] et [!UICONTROL Traits] sections. [!UICONTROL Destinations Mapping] sont facultatifs. Consultez les instructions ci-dessous pour obtenir une aide supplémentaire.

1. Dans la section Informations [](../../features/segments/segment-builder.md#segment-builder-controls-basics) de base :

   ![create-segment](assets/create-segment.png)

   * Nommez le [!UICONTROL segment]. La longueur maximale d’un [!UICONTROL segment] nom est de 255 caractères.
   * Définissez l’ [!UICONTROL segment] état (actif par défaut).
   * Choisis un [!UICONTROL data source]. Utilisez le premier menu déroulant pour filtrer les Audiences Manager [!UICONTROL data sources], les suites de rapports Adobe Analytics, ou les deux. Ensuite, utilisez le deuxième menu déroulant pour choisir votre [!UICONTROL data source]option. Si vous n’utilisez pas les suites de rapports Adobe Analytics, le sélecteur de [!UICONTROL data source] type est désactivé et les sources de données d’Audience Manager par défaut uniquement sont désactivées.
   * Sélectionnez un [!UICONTROL profile merge rule] à utiliser pour [!UICONTROL segment] la qualification.
   * Affectez-la [!UICONTROL segment] à un dossier d’enregistrement.

1. Dans la section [Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Recherchez le [!UICONTROL trait] que vous souhaitez ajouter à un segment et cliquez sur **[!UICONTROL Add Trait]**. Ajoutez un autre [!UICONTROL trait] pour créer un [!UICONTROL trait] groupe.
   * Affichez la [!UICONTROL Advanced Search] modale en cliquant sur **[!UICONTROL Browse All Traits]**. Recherchez [!UICONTROL traits] par nom, identifiant, description ou [!UICONTROL data source]. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer [!UICONTROL traits] par type [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based][!UICONTROL Onboarded]et [!UICONTROL Algorithmic]) ou de population (ID de[périphérique et ID de plusieurs périphériques).](../../reference/ids-in-aam.md)[](../../reference/ids-in-aam.md)
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Obtenez des recommandations [](trait-recommendations.md) de caractéristiques en direct lorsque vous créez votre [!UICONTROL segment]profil.
   * Cliquez et faites glisser [!UICONTROL traits] pour créer des groupes distincts.
   * Passez la souris sur des groupes pour définir des relations avec des [!UICONTROL AND]valeurs booléennes [!UICONTROL OR][!UICONTROL AND NOT] et booléennes.
   * Passez la souris sur l’icône de l’horloge pour ajouter des règles de [récence et de fréquence](../../features/segments/recency-and-frequency.md) au [!UICONTROL trait].
   * Vue des données de population de segments au fur et à mesure que vous ajoutez ou supprimez [!UICONTROL traits]. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) l’estimation des chiffres de population. En savoir plus sur les données [de population de](../../features/segments/segment-builder-data.md#segment-populations) segments dans le [!UICONTROL Segment Builder].
   * Cliquez **[!UICONTROL Save]** une fois terminé.

1. *(Facultatif)* Faites correspondre un [!UICONTROL segment] à un [!UICONTROL destination] dans la section Mappage [de](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destination :
   * Recherchez l’élément [!UICONTROL destination] et cliquez sur **[!UICONTROL Add Destination]**. Notez que le [!UICONTROL destination] doit déjà exister pour que vous puissiez l’ajouter à un [!UICONTROL segment].
   * Cliquez **[!UICONTROL Save]** une fois terminé.

Regardez la vidéo ci-dessous pour obtenir un aperçu détaillé du fonctionnement des mesures sur plusieurs périphériques.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] Contrôles : [!UICONTROL Basic Information] Section {#segment-builder-controls-basics}

Dans [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] les paramètres vous permettent de créer ou de modifier des caractéristiques existantes. Pour créer un dossier [!UICONTROL segment], indiquez un nom, un [!UICONTROL data source]et sélectionnez un dossier d’enregistrement. Tous les autres champs sont facultatifs. Passez à la [!UICONTROL Traits] section lorsque vous avez terminé.

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| Champ | Description |
---------|----------
| **[!UICONTROL Name]** | Attribuez au segment un nom court et logique qui décrit sa fonction ou son objectif. Evitez les abréviations et les caractères spéciaux. La longueur maximale d’un nom de segment est de 255 caractères. |
| **[!UICONTROL Description]** | Un champ pour obtenir des informations descriptives supplémentaires sur le segment. |
| **[!UICONTROL Integration Code]** | Champ d’un identifiant défini par l’utilisateur ou d’autres informations spécifiques à une société. |
| **[!UICONTROL Data Source]** | Associe le segment à un fournisseur de données spécifique. <br> Utilisez le premier menu déroulant pour filtrer entre les sources de données d’Audience Manager, les Report Suites Adobe Analytics, ou les deux. Ensuite, utilisez le deuxième menu déroulant pour choisir votre source de données. <br> Si vous n’utilisez pas les suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et les sources de données d’Audience Manager par défaut sont désactivées uniquement. |
| **[!UICONTROL Profile Merge Rule]** | Sélectionne la règle de fusion de Profils à utiliser pour la qualification de segment. |
| **[!UICONTROL Status]** | Active ou désactive le segment (actif par défaut). |
| **Enregistrement de dossier** | Détermine le dossier d’enregistrement auquel appartient le segment. |

## [!UICONTROL Segment Builder] Contrôles : [!UICONTROL Traits] Section {#segment-builder-controls-traits}

Dans [!UICONTROL Segment Builder]la [!UICONTROL Traits] section, vous pouvez gérer [!UICONTROL traits] dans un [!UICONTROL segment]groupe, créer [!UICONTROL trait] des groupes et définir des critères de qualification. Pour ajouter un élément [!UICONTROL trait] à un [!UICONTROL segment], entrez le [!UICONTROL trait] nom dans le champ de recherche, puis cliquez sur [!UICONTROL Add Trait]. Enregistrez la [!UICONTROL trait] (si vous avez terminé) ou passez à [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Conditions préalables :** Renseignez les champs obligatoires de la [!UICONTROL Basic Information] section.

| Champ | Description |
|--- |--- |
| **[!UICONTROL Basic View]** | Cette section fournit des commandes visuelles qui vous permettent d&#39;effectuer les opérations suivantes : <ul><li>Créer et gérer les éléments existants [!UICONTROL segments].</li><li>Supprimez [!UICONTROL traits] d&#39;un [!UICONTROL segment].</li><li>Ajoutez jusqu’à 50 (maximum) [!UICONTROL traits] à un [!UICONTROL segment].</li><li>Faites glisser et déposez [!UICONTROL traits] pour créer des groupes.</li><li>Vue [!UICONTROL traits] et [!UICONTROL trait] groupes dans un [!UICONTROL segment].</li><li>Définissez des critères de qualification avec des expressions booléennes, des opérateurs de comparaison et des paramètres de récence/fréquence.</li></ul> |
| **[!UICONTROL Code View]** | Ouvre un environnement de développement qui vous permet de créer et de gérer [!UICONTROL traits], des groupes et des exigences de qualification à l’aide du code plutôt que de l’interface visuelle. La vue de code est utile si votre [!UICONTROL segments]: <ul><li>Contient plus de 50 [!UICONTROL traits] dans un individu [!UICONTROL segment]. Remarque : [!UICONTROL Segments] sont limitées à 5000 [!UICONTROL traits] (maximum).</li><li>Contient de nombreux [!UICONTROL trait] groupes.</li><li>Posséder des exigences de qualification complexes.</li></ul> |
| Outils | Permet de trouver [!UICONTROL traits] à ajouter à un [!UICONTROL segment]. |
| Recommandations | Obtenez des recommandations en direct pour des flux similaires [!UICONTROL traits], issus de vos flux de données [!UICONTROL traits] et [!UICONTROL Audience Marketplace] propriétaires auxquels vous êtes abonné. Ajoutez ces recommandations à la [!UICONTROL segment] règle pour développer votre audience. Pour en savoir plus, consultez Recommandations [de](trait-recommendations.md)caractéristiques. |
| **[!UICONTROL Marketplace Recommendations]** | Obtenez des recommandations en direct pour des flux de données similaires [!UICONTROL traits], à partir [!UICONTROL Audience Marketplace] desquels vous n’êtes pas abonné. Pour en savoir plus, consultez Recommandations [de](trait-recommendations.md)caractéristiques. |
| Données de taille réelle et estimée [!UICONTROL Segment] des données | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Supprimer [!UICONTROL Traits] d’un [!UICONTROL Segment] {#remove-traits}

La gestion des [!UICONTROL traits] ressources dans votre [!UICONTROL segments] entreprise est un élément important pour maintenir [!UICONTROL segments] la viabilité. Suivez ces étapes si vous devez supprimer [!UICONTROL traits] d’un [!UICONTROL segment].

Pour supprimer [!UICONTROL traits] d&#39;un [!UICONTROL segment]:

1. Allez à **[!UICONTROL Audience Data > Segments]**. Faites défiler la liste ou utilisez la fonction de recherche pour trouver le [!UICONTROL segment] que vous souhaitez utiliser.
2. Cliquez sur le [!UICONTROL segment] nom pour ouvrir l’écran [!UICONTROL segment] de détails.
3. Cliquez sur **Modifier** pour ouvrir [!UICONTROL Segment Builder] , puis sur **Caractéristiques** pour ouvrir le [!UICONTROL traits] panneau.
4. Passez la souris sur le [!UICONTROL trait] que vous souhaitez supprimer, puis cliquez sur le X. Cette action supprime immédiatement le [!UICONTROL trait] de votre [!UICONTROL segment]nom.

## [!UICONTROL Segment Builder] Contrôles : [!UICONTROL Destinations Mappings] Section {#segment-builder-controls-destinations}

Dans [!UICONTROL Segment Builder]la [!UICONTROL Destinations Mapping] section facultative, vous pouvez envoyer [!UICONTROL segment] des données à un tiers [!DNL cookie], [!DNL URL]ou [!UICONTROL server-to-server destination]. Pour ajouter une [!UICONTROL destination], recherchez (ou parcourez) une [!UICONTROL destination], fournissez des informations [!UICONTROL destination] spécifiques, puis cliquez sur **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Conditions préalables

Renseignez les champs obligatoires des sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . En outre, la destination doit déjà exister.

### [!UICONTROL Destination Mappings] Outils de recherche

Le **[!UICONTROL Destination Mappings]** panneau contient des outils de recherche, comme décrit dans le tableau ci-dessous.

| Type de recherche | Description |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Permet de rechercher un nom spécifique [!UICONTROL destination] par nom. Pour effectuer une recherche, tapez un début. Le champ est renseigné automatiquement en fonction des termes recherchés. Cliquez **[!UICONTROL Add Destination]** une fois terminé. |
| **[!UICONTROL Browse All Destinations]** | Parcourez une liste de *toutes les*[!UICONTROL destinations] informations disponibles. Sélectionnez et ajoutez [!UICONTROL destinations] à votre fichier [!UICONTROL segment] à partir de la liste contextuelle. |

## Champs dans les fenêtres [!UICONTROL Destination Mappings] contextuelles {#fields-in-dest-mappings}

Dans [!UICONTROL Segment Builder], la boîte de dialogue [!UICONTROL Add Destination] s’affiche après avoir sélectionné un [!UICONTROL destination]élément. Cette fenêtre affiche des informations statiques sur les champs [!UICONTROL destination] et les champs qui varient selon le [!UICONTROL destination] type. Fournissez les informations requises dans les champs vides pour configurer une [!UICONTROL destination mapping]variable.

>[!NOTE]
>
>Les dates de publication sont facultatives. Lorsqu’elle est vide, la destination devient active et n’expire jamais.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Champs

Dans les [!UICONTROL Destination Mapping] champs, spécifiez les paires clé-valeur utilisées pour envoyer les données au [!UICONTROL destination]. Saisissez la clé dans le premier champ et les valeurs dans le second. Votre [!UICONTROL cookie destination] pop pourrait ressembler à ceci :

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Champs

Dans les [!UICONTROL URL] champs et [!UICONTROL Secure URL] , spécifiez l’adresse standard complète ou sécurisée utilisée pour envoyer les données au [!UICONTROL destination]serveur.

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Champs

Dans le [!UICONTROL Destination Value] champ, indiquez la valeur (qui fait partie d’une paire clé-valeur) utilisée pour envoyer les données au [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Créer une destination de cookie](../../features/destinations/create-cookie-destination.md)
>* [Création d’une destination d’URL](../../features/destinations/create-url-destination.md)

