---
description: Décrit comment créer des segments avec le créateur de segments.
seo-description: Décrit comment créer des segments avec le créateur de segments.
seo-title: Créateur de segments
solution: Audience Manager
title: Créateur de segments
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 2%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Décrit les étapes requises et facultatives permettant de créer un segment dans [!UICONTROL Segment Builder].

## Démonstration vidéo

Début en regardant la vidéo [Créer des segments dans l&#39;Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). La vidéo vous guide tout au long du processus de création de segments. Lisez les sections ci-dessous pour plus d&#39;informations.

## Créez un [!UICONTROL Segment] {#create-segment}

### Section Créateur de segments

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] se compose de 3 sections distinctes :  [!UICONTROL Basic Information],  [!UICONTROL Traits] et  [!UICONTROL Destinations Mapping]. Pour créer un [!UICONTROL segment], renseignez les champs obligatoires des sections [!UICONTROL Basic Information] et [!UICONTROL Traits]. [!UICONTROL Destinations Mapping] sont facultatifs. Consultez les instructions ci-dessous pour obtenir une aide supplémentaire.

1. Dans la section [Informations de base](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![create-segment](assets/create-segment.png)

   * Nommez [!UICONTROL segment]. La longueur maximale d&#39;un nom [!UICONTROL segment] est de 255 caractères.
   * Définissez l’état [!UICONTROL segment] (principal est la valeur par défaut).
   * Sélectionnez un [!UICONTROL data source]. Utilisez le premier menu déroulant pour filtrer entre les Report Suites d&#39;Audience Manager [!UICONTROL data sources], Adobe Analytics, ou les deux. Ensuite, utilisez le deuxième menu déroulant pour choisir votre [!UICONTROL data source]. Si vous n’utilisez pas les suites de rapports Adobe Analytics, le sélecteur de type [!UICONTROL data source] est désactivé et les sources de données d’Audience Manager par défaut uniquement sont désactivées.
   * Sélectionnez un [!UICONTROL profile merge rule] à utiliser pour la qualification [!UICONTROL segment].
   * Affectez le dossier [!UICONTROL segment] à un dossier d’enregistrement.

1. Dans la section [Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Recherchez [!UICONTROL trait] que vous souhaitez ajouter à un segment et cliquez sur **[!UICONTROL Add Trait]**. Ajoutez un autre groupe [!UICONTROL trait] pour créer un groupe [!UICONTROL trait].
   * Affichez le module [!UICONTROL Advanced Search] en cliquant sur **[!UICONTROL Browse All Traits]**. Recherchez [!UICONTROL traits] par nom, identifiant, description ou [!UICONTROL data source]. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer [!UICONTROL traits] par [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] et [!UICONTROL Algorithmic]) ou par type de population ([ID de périphérique](../../reference/ids-in-aam.md) et [ID de plusieurs périphériques](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Obtenez des [recommandations de caractéristiques](trait-recommendations.md) en direct lorsque vous créez votre [!UICONTROL segment].
   * Cliquez et faites glisser [!UICONTROL traits] pour créer des groupes distincts.
   * Passez la souris entre les groupes pour définir des relations avec les valeurs booléennes [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT].
   * Passez la souris sur l’icône d’horloge pour ajouter des règles [récence et fréquence](../../features/segments/recency-and-frequency.md) à [!UICONTROL trait].
   * Vue des données de population de segments lors de l’ajout ou de la suppression de [!UICONTROL traits]. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) l’estimation des chiffres de population. Pour en savoir plus sur [les données de population de segments](../../features/segments/segment-builder-data.md#segment-populations) dans le [!UICONTROL Segment Builder].
   * Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

1. *(Facultatif)* Faites correspondre une  [!UICONTROL segment] correspondance  [!UICONTROL destination] à une  [dans la section ](../../features/segments/segment-builder.md#segment-builder-controls-destinations) Mappage dedestination :
   * Recherchez [!UICONTROL destination] et cliquez sur **[!UICONTROL Add Destination]**. Remarque : le [!UICONTROL destination] doit déjà exister pour que vous puissiez l&#39;ajouter à un [!UICONTROL segment].
   * Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

Regardez la vidéo ci-dessous pour obtenir un aperçu détaillé du fonctionnement des mesures sur plusieurs périphériques.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] Contrôles :  [!UICONTROL Basic Information] Section  {#segment-builder-controls-basics}

Dans [!UICONTROL Segment Builder], les paramètres [!UICONTROL the Basic Information] vous permettent de créer ou de modifier des caractéristiques existantes. Pour créer un dossier [!UICONTROL segment], nommez [!UICONTROL data source] et sélectionnez un dossier d&#39;enregistrement. Tous les autres champs sont facultatifs. Passez à la section [!UICONTROL Traits] lorsque vous avez terminé.

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
| **[!UICONTROL Data Source]** | Associe le segment à un fournisseur de données spécifique. <br> Utilisez le premier menu déroulant pour filtrer entre les sources de données d’Audience Manager, les suites de rapports Adobe Analytics ou les deux. Ensuite, utilisez le deuxième menu déroulant pour choisir votre source de données. <br> Si vous n’utilisez pas les suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et les sources de données d’Audience Manager sont désactivées par défaut uniquement. |
| **[!UICONTROL Profile Merge Rule]** | Sélectionne la règle de fusion de Profils à utiliser pour la qualification de segment. |
| **[!UICONTROL Status]** | Active ou désactive le segment (principal par défaut). |
| **Enregistrement de dossier** | Détermine le dossier d’enregistrement auquel appartient le segment. |

## [!UICONTROL Segment Builder] Contrôles :  [!UICONTROL Traits] Section  {#segment-builder-controls-traits}

Dans [!UICONTROL Segment Builder], la section [!UICONTROL Traits] vous permet de gérer [!UICONTROL traits] dans un [!UICONTROL segment], de créer des groupes [!UICONTROL trait] et de définir des critères de qualification. Pour ajouter un [!UICONTROL trait] à un [!UICONTROL segment], saisissez le nom [!UICONTROL trait] dans le champ de recherche, puis cliquez sur [!UICONTROL Add Trait]. Enregistrez le [!UICONTROL trait] (s’il est terminé) ou passez à [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Conditions préalables :** renseignez les champs obligatoires de la  [!UICONTROL Basic Information] section.

| Champ | Description |
|--- |--- |
| **[!UICONTROL Basic View]** | Cette section fournit des commandes visuelles qui vous permettent d&#39;effectuer les opérations suivantes : <ul><li>Créer et gérer [!UICONTROL segments] existant.</li><li>Supprimez [!UICONTROL traits] d&#39;un [!UICONTROL segment].</li><li>Ajoutez jusqu’à 50 [!UICONTROL traits] à [!UICONTROL segment].</li><li>Faites glisser [!UICONTROL traits] pour créer de nouveaux groupes.</li><li>Vue [!UICONTROL traits] et [!UICONTROL trait] groupes dans un [!UICONTROL segment].</li><li>Définissez des critères de qualification avec des expressions booléennes, des opérateurs de comparaison et des paramètres de récence/fréquence.</li></ul> |
| **[!UICONTROL Code View]** | Ouvre un environnement de développement qui vous permet de créer et de gérer [!UICONTROL traits], les groupes et les exigences de qualification avec du code plutôt qu&#39;avec l&#39;interface visuelle. La vue de code est utile si votre [!UICONTROL segments] : <ul><li>Contenir plus de 50 [!UICONTROL traits] dans un [!UICONTROL segment] particulier. Remarque : [!UICONTROL Segments] sont limités à 5 000 [!UICONTROL traits] (maximum).</li><li>Contenir de nombreux groupes [!UICONTROL trait].</li><li>Posséder des exigences de qualification complexes.</li></ul> |
| Outils | Permet de trouver [!UICONTROL traits] à ajouter à [!UICONTROL segment]. |
| Recommandations | Obtenez des recommandations en direct pour des flux de données similaires [!UICONTROL traits], à partir de vos flux de données propriétaires [!UICONTROL traits] et [!UICONTROL Audience Marketplace] auxquels vous êtes abonné. Ajoutez ces recommandations à la règle [!UICONTROL segment] pour développer votre audience. Pour en savoir plus, voir [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obtenez des recommandations en direct pour des flux de données similaires [!UICONTROL traits] à partir de [!UICONTROL Audience Marketplace] auxquels vous n’êtes pas abonné. Pour en savoir plus, voir [Trait Recommendations](trait-recommendations.md). |
| Données de taille réelles et estimées [!UICONTROL Segment] | Voir [Données sur la population de segments et de caractéristiques dans le créateur de segments](segment-builder-data.md). |

## Supprimer [!UICONTROL Traits] d&#39;un [!UICONTROL Segment] {#remove-traits}

La gestion de [!UICONTROL traits] dans votre [!UICONTROL segments] est un élément important pour maintenir [!UICONTROL segments] viable. Suivez ces étapes si vous devez supprimer [!UICONTROL traits] d&#39;un [!UICONTROL segment].

Pour supprimer [!UICONTROL traits] d&#39;un [!UICONTROL segment] :

1. Accédez à **[!UICONTROL Audience Data > Segments]**. Faites défiler la liste ou utilisez la fonction de recherche pour trouver le [!UICONTROL segment] que vous souhaitez utiliser.
2. Cliquez sur le nom [!UICONTROL segment] pour ouvrir l&#39;écran de détails [!UICONTROL segment].
3. Cliquez sur **Modifier** pour ouvrir [!UICONTROL Segment Builder], puis sur **Caractéristiques** pour ouvrir le panneau [!UICONTROL traits].
4. Passez la souris sur [!UICONTROL trait] que vous souhaitez supprimer, puis cliquez sur le X. Cette action supprime immédiatement [!UICONTROL trait] de votre [!UICONTROL segment].

## [!UICONTROL Segment Builder] Contrôles :  [!UICONTROL Destinations Mappings] Section  {#segment-builder-controls-destinations}

Dans [!UICONTROL Segment Builder], la section facultative [!UICONTROL Destinations Mapping] vous permet d&#39;envoyer des données [!UICONTROL segment] à un tiers [!DNL cookie], [!DNL URL] ou [!UICONTROL server-to-server destination]. Pour ajouter un [!UICONTROL destination], recherchez (ou parcourez) un [!UICONTROL destination], fournissez des informations spécifiques à [!UICONTROL destination], puis cliquez sur **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Conditions préalables

Renseignez les champs obligatoires des sections [!UICONTROL Basic Information] et [!UICONTROL Traits]. En outre, la destination doit déjà exister.

### [!UICONTROL Destination Mappings] Outils de recherche

Le panneau **[!UICONTROL Destination Mappings]** contient les outils de recherche décrits dans le tableau ci-dessous.

| Type de recherche | Description |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Permet de rechercher un [!UICONTROL destination] spécifique par nom. Pour effectuer une recherche, tapez un début. Le champ est renseigné automatiquement en fonction des termes recherchés. Cliquez sur **[!UICONTROL Add Destination]** lorsque vous avez terminé. |
| **[!UICONTROL Browse All Destinations]** | Parcourez la liste *all* [!UICONTROL destinations] disponible pour vous. Sélectionnez [!UICONTROL destinations] et ajoutez [!UICONTROL segment] à votre  à partir de la liste contextuelle. |

## Champs dans la fenêtre contextuelle [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

Dans [!UICONTROL Segment Builder], la boîte de dialogue [!UICONTROL Add Destination] s&#39;affiche après avoir sélectionné un [!UICONTROL destination]. Cette fenêtre affiche des informations statiques sur [!UICONTROL destination] et les champs qui varient selon le type [!UICONTROL destination]. Fournissez les informations requises dans les champs vides pour configurer un [!UICONTROL destination mapping].

>[!NOTE]
>
>Les dates de publication sont facultatives. Lorsqu’elle est vide, la destination devient principale et n’expire jamais.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Champs

Dans les champs [!UICONTROL Destination Mapping], spécifiez les paires clé-valeur utilisées pour envoyer des données à [!UICONTROL destination]. Saisissez la clé dans le premier champ et les valeurs dans le second. Votre fichier pop [!UICONTROL cookie destination] peut ressembler à ceci :

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Champs

Dans les champs [!UICONTROL URL] et [!UICONTROL Secure URL], spécifiez l&#39;adresse standard ou sécurisée complète utilisée pour envoyer les données à [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Champs

Dans le champ [!UICONTROL Destination Value], spécifiez la valeur (faisant partie d&#39;une paire clé-valeur) utilisée pour envoyer les données à [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Créer une destination de cookie](../../features/destinations/create-cookie-destination.md)
>* [Création d’une destination d’URL](../../features/destinations/create-url-destination.md)

