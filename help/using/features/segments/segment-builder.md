---
description: Décrit comment créer des segments avec le créateur de segments.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Créateur de segments
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Décrit les étapes obligatoires et facultatives de création d’un segment dans [!UICONTROL Segment Builder].

## Démonstration vidéo

Commencez par regarder la [vidéo Créer des segments dans Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). La vidéo vous guide tout au long du processus de création de segment. Lisez les sections ci-dessous pour plus d’informations.

## Création d’un [!UICONTROL Segment] {#create-segment}

### Section du créateur de segments

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] se compose de 3 sections distinctes : [!UICONTROL Basic Information], [!UICONTROL Traits] et [!UICONTROL Destinations Mapping]. Pour créer un [!UICONTROL segment], renseignez les champs requis dans les sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] paramètres sont facultatifs. Consultez les instructions ci-dessous pour obtenir une aide supplémentaire.

1. Dans la section [Informations de base](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![create-segment](assets/create-segment.png)

   * Nommez le [!UICONTROL segment] . La longueur maximale d’un nom de [!UICONTROL segment] est de 255 caractères.
   * Définissez le statut du [!UICONTROL segment] (actif est la valeur par défaut).
   * Choisissez un [!UICONTROL data source]. Utilisez le premier menu déroulant pour filtrer entre les [!UICONTROL data sources] Audience Manager, les suites de rapports Adobe Analytics ou les deux. Utilisez ensuite le deuxième menu déroulant pour choisir votre [!UICONTROL data source]. Si vous n’utilisez pas de suites de rapports Adobe Analytics, le sélecteur de type de [!UICONTROL data source] est désactivé et correspond par défaut uniquement aux sources de données Audience Manager.
   * Sélectionnez un [!UICONTROL profile merge rule] à utiliser pour la qualification du [!UICONTROL segment].
   * Attribuez le [!UICONTROL segment] à un dossier de stockage.

1. Dans la section [Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![caractéristiques-créatrices-de-segments](assets/segment-builder-traits.png)
   * Recherchez le [!UICONTROL trait] à ajouter à un segment et cliquez sur **[!UICONTROL Add Trait]**. Ajoutez un autre [!UICONTROL trait] pour créer un groupe de [!UICONTROL trait].
   * Pour afficher la boîte de dialogue modale [!UICONTROL Advanced Search], cliquez sur **[!UICONTROL Browse All Traits]**. Recherchez des [!UICONTROL traits] par nom, ID, description ou [!UICONTROL data source]. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer les [!UICONTROL traits] par [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] et [!UICONTROL Algorithmic]) ou type de population ([ID d’appareil](../../reference/ids-in-aam.md) et [ID sur l’ensemble des appareils](../../reference/ids-in-aam.md)).
     ![caractéristiques du navigateur du créateur de segments](assets/segment-builder-browse-traits.png)
   * Obtenez des [recommandations de caractéristiques](trait-recommendations.md) en direct lors de la création de votre [!UICONTROL segment].
   * Cliquez et faites glisser [!UICONTROL traits] pour créer des groupes distincts.
   * Passez la souris entre les groupes pour définir les relations avec les valeurs booléennes [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL AND NOT].
   * Pointez sur l’icône d’horloge pour ajouter des règles [récence et fréquence](../../features/segments/recency-and-frequency.md) à la [!UICONTROL trait].
   * Affichez les données de population de segments lorsque vous ajoutez ou supprimez des [!UICONTROL traits]. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) les estimations de population. Pour en savoir plus sur les [données de population de segments](../../features/segments/segment-builder-data.md#segment-populations), consultez la [!UICONTROL Segment Builder].
   * Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

1. *(Facultatif)* Mappez un [!UICONTROL segment] à un [!UICONTROL destination] dans la section [Mappage de destination](../../features/segments/segment-builder.md#segment-builder-controls-destinations) :
   * Recherchez le [!UICONTROL destination] et cliquez sur **[!UICONTROL Add Destination]**. Notez que le [!UICONTROL destination] doit déjà exister avant de pouvoir l’ajouter à un [!UICONTROL segment].
   * Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

Regardez la vidéo ci-dessous pour un aperçu détaillé du fonctionnement des mesures inter-appareils.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## Contrôles [!UICONTROL Segment Builder] : section [!UICONTROL Basic Information] {#segment-builder-controls-basics}

En [!UICONTROL Segment Builder], les paramètres [!UICONTROL the Basic Information] vous permettent de créer des caractéristiques ou de modifier des caractéristiques existantes. Pour créer un nouveau [!UICONTROL segment], indiquez un nom et un [!UICONTROL data source], puis sélectionnez un dossier de stockage. Tous les autres champs sont facultatifs. Passez à la section [!UICONTROL Traits] lorsque vous avez terminé.

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
|---------|----------|
| **[!UICONTROL Name]** | Attribuez au segment un nom court et logique qui décrit sa fonction ou son objectif. Évitez les abréviations et les caractères spéciaux. La longueur maximale d’un nom de segment est de 255 caractères. |
| **[!UICONTROL Description]** | Champ permettant d’obtenir des informations descriptives supplémentaires sur le segment. |
| **[!UICONTROL Integration Code]** | Champ pour un ID défini par l’utilisateur ou d’autres informations spécifiques à la société. |
| **[!UICONTROL Data Source]** | Associe le segment à un fournisseur de données spécifique. <br> Utilisez le premier menu déroulant pour filtrer entre les sources de données Audience Manager, les suites de rapports Adobe Analytics ou les deux. Utilisez ensuite le deuxième menu déroulant pour choisir votre source de données. <br> Si vous n’utilisez pas de suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et correspond par défaut aux sources de données Audience Manager uniquement. |
| **[!UICONTROL Profile Merge Rule]** | Sélectionne la règle de fusion de profils à utiliser pour la qualification du segment. |
| **[!UICONTROL Status]** | Active ou désactive le segment (actif par défaut). |
| **Stockage de dossiers** | Détermine à quel dossier de stockage le segment appartient. |

## Contrôles [!UICONTROL Segment Builder] : section [!UICONTROL Traits] {#segment-builder-controls-traits}

Dans [!UICONTROL Segment Builder], la section [!UICONTROL Traits] vous permet de gérer les [!UICONTROL traits] dans un [!UICONTROL segment], de créer des groupes de [!UICONTROL trait] et de définir des critères de qualification. Pour ajouter un [!UICONTROL trait] à un [!UICONTROL segment], saisissez le nom du [!UICONTROL trait] dans le champ de recherche, puis cliquez sur [!UICONTROL Add Trait]. Enregistrez le [!UICONTROL trait] (s’il est terminé) ou passez à l’[!UICONTROL Destinations Mapping] .

<!-- r_segment_traits_section.xml-->

**Conditions préalables** : renseignez les champs requis de la section [!UICONTROL Basic Information] .

| Champ | Description |
|--- |--- |
| **[!UICONTROL Basic View]** | Cette section propose des commandes visuelles qui vous permettent d’effectuer les opérations suivantes : <ul><li>Créez de nouveaux [!UICONTROL segments] et gérez les existants.</li><li>Supprimez le [!UICONTROL traits] d’un [!UICONTROL segment].</li><li>Ajoutez jusqu’à 50 [!UICONTROL traits] (maximum) à un [!UICONTROL segment].</li><li>Effectuez un glisser-déposer des [!UICONTROL traits] pour créer des groupes.</li><li>Affichez les groupes de [!UICONTROL traits] et de [!UICONTROL trait] dans un [!UICONTROL segment].</li><li>Définissez des critères de qualification avec des expressions booléennes, des opérateurs de comparaison et des paramètres de récence/fréquence.</li></ul> |
| **[!UICONTROL Code View]** | Ouvre un environnement de développement qui vous permet de créer et de gérer des [!UICONTROL traits], des groupes et des exigences de qualification avec du code au lieu de l’interface visuelle. L’affichage du code est utile si votre [!UICONTROL segments] : <ul><li>Contiennent plus de 50 [!UICONTROL traits] par [!UICONTROL segment]. Remarque : les [!UICONTROL Segments] sont limitées à 5 000 [!UICONTROL traits] (maximum).</li><li>Contiennent de nombreux groupes de [!UICONTROL trait].</li><li>avoir des exigences de qualification complexes ;</li></ul> |
| Outils | Permet de trouver des [!UICONTROL traits] à ajouter à une [!UICONTROL segment]. |
| Recommandations | Obtenez des recommandations en direct pour des [!UICONTROL traits] similaires, à partir de vos flux de données [!UICONTROL traits] et [!UICONTROL Audience Marketplace] auxquels vous êtes abonné. Ajoutez ces recommandations à la règle de [!UICONTROL segment] pour étendre votre audience. En savoir plus dans [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obtenez des recommandations en direct pour des [!UICONTROL traits] similaires, à partir de flux de données [!UICONTROL Audience Marketplace] auxquels vous n’êtes pas abonné. En savoir plus dans [Trait Recommendations](trait-recommendations.md). |
| Données de taille de [!UICONTROL Segment] réelle et estimée | Voir [Données sur la population de segments et de caractéristiques dans le créateur de segments](segment-builder-data.md). |

## Supprimer le [!UICONTROL Traits] d’un [!UICONTROL Segment] {#remove-traits}

La gestion des [!UICONTROL traits] dans votre [!UICONTROL segments] est un élément important pour assurer la viabilité de [!UICONTROL segments]. Suivez ces étapes si vous devez supprimer des [!UICONTROL traits] d’un [!UICONTROL segment].

Pour supprimer des [!UICONTROL traits] d’un [!UICONTROL segment] :

1. Accédez à **[!UICONTROL Audience Data > Segments]**. Faites défiler la liste ou utilisez la fonction de recherche pour trouver les [!UICONTROL segment] que vous souhaitez utiliser.
2. Cliquez sur le nom du [!UICONTROL segment] pour ouvrir l’écran des détails du [!UICONTROL segment].
3. Cliquez sur **Modifier** pour ouvrir le [!UICONTROL Segment Builder], puis sur **Caractéristiques** pour ouvrir le panneau [!UICONTROL traits].
4. Pointez sur le [!UICONTROL trait] à supprimer, puis cliquez sur le X. Cette action supprime immédiatement le [!UICONTROL trait] de votre [!UICONTROL segment].

## Contrôles [!UICONTROL Segment Builder] : section [!UICONTROL Destinations Mappings] {#segment-builder-controls-destinations}

Dans [!UICONTROL Segment Builder], la section facultative [!UICONTROL Destinations Mapping] vous permet d’envoyer des données [!UICONTROL segment] à un [!DNL cookie], un [!DNL URL] ou un [!UICONTROL server-to-server destination] tiers. Pour ajouter un [!UICONTROL destination], recherchez (ou parcourez) un [!UICONTROL destination], fournissez [!UICONTROL destination] informations spécifiques, puis cliquez sur **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Conditions préalables

Renseignez les champs requis dans les sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . En outre, la destination doit déjà exister.

### Outils de recherche [!UICONTROL Destination Mappings]

Le panneau **[!UICONTROL Destination Mappings]** contient des outils de recherche, comme décrit dans le tableau ci-dessous.

| Type de recherche | Description |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Permet de rechercher un [!UICONTROL destination] spécifique par nom. Pour effectuer une recherche, commencez à saisir. Le champ sera automatiquement renseigné en fonction de vos termes de recherche. Cliquez sur **[!UICONTROL Add Destination]** lorsque vous avez terminé. |
| **[!UICONTROL Browse All Destinations]** | Parcourez une liste de *tous* [!UICONTROL destinations] disponibles. Sélectionnez et ajoutez des [!UICONTROL destinations] à votre [!UICONTROL segment] dans la liste contextuelle. |

## Champs dans les fenêtres pop-up [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

Dans [!UICONTROL Segment Builder], la boîte de dialogue [!UICONTROL Add Destination] s’affiche après avoir sélectionné un [!UICONTROL destination]. Cette fenêtre affiche des informations statiques sur les [!UICONTROL destination] et les champs qui varient en fonction du type de [!UICONTROL destination]. Fournissez les informations requises dans les champs vides pour configurer un [!UICONTROL destination mapping].

>[!NOTE]
>
>Les dates de publication sont facultatives. Lorsqu’elle est vide, la destination devient active et n’expire jamais.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Fields

Dans les champs [!UICONTROL Destination Mapping], spécifiez les paires clé-valeur utilisées pour envoyer des données au [!UICONTROL destination] . Saisissez la clé dans le premier champ et les valeurs dans le second. Votre pop [!UICONTROL cookie destination] pourrait ressembler à ceci :

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Fields

Dans les champs [!UICONTROL URL] et [!UICONTROL Secure URL] , indiquez l’adresse standard ou sécurisée complète utilisée pour envoyer des données au [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Fields

Dans le champ [!UICONTROL Destination Value] , spécifiez la valeur (partie d’une paire clé-valeur) utilisée pour envoyer des données au [!UICONTROL destination] .

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Créer une destination de cookie](../../features/destinations/create-cookie-destination.md)
>* [Créer une destination d’URL](../../features/destinations/create-url-destination.md)
