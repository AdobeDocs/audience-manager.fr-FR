---
description: Décrit comment créer des segments à l’aide du créateur de segments.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Créateur de segments
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 2%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Décrit les étapes requises et facultatives pour créer un segment dans [!UICONTROL Segment Builder].

## Démonstration vidéo

Commencez par regarder la vidéo [Créer des segments dans l’Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). La vidéo vous guide tout au long du processus de création de segments. Pour plus d’informations, consultez les sections ci-dessous.

## Créer un [!UICONTROL Segment] {#create-segment}

### Section du créateur de segments

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] se compose de 3 sections distinctes : [!UICONTROL Basic Information], [!UICONTROL Traits] et [!UICONTROL Destinations Mapping]. Pour créer un [!UICONTROL segment], renseignez les champs requis dans les sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . Les paramètres [!UICONTROL Destinations Mapping] sont facultatifs. Pour obtenir de l’aide supplémentaire, reportez-vous aux instructions ci-dessous.

1. Dans la section [Informations de base](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![create-segment](assets/create-segment.png)

   * Nommez le [!UICONTROL segment]. La longueur maximale d’un nom [!UICONTROL segment] est de 255 caractères.
   * Définissez l’état [!UICONTROL segment] (actif par défaut).
   * Sélectionnez un [!UICONTROL data source]. Utilisez le premier menu déroulant pour filtrer entre l&#39;Audience Manager [!UICONTROL data sources], les suites de rapports Adobe Analytics ou les deux. Utilisez ensuite le deuxième menu déroulant pour choisir votre [!UICONTROL data source]. Si vous n’utilisez pas de suites de rapports Adobe Analytics, le sélecteur de type [!UICONTROL data source] est désactivé et le sélecteur par défaut est uniquement Audience Manager aux sources de données.
   * Sélectionnez un [!UICONTROL profile merge rule] à utiliser pour la qualification [!UICONTROL segment].
   * Affectez le [!UICONTROL segment] à un dossier de stockage.

1. Dans la section [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![ segment-builder-traits](assets/segment-builder-traits.png)
   * Recherchez le [!UICONTROL trait] que vous souhaitez ajouter à un segment et cliquez sur **[!UICONTROL Add Trait]**. Ajoutez un autre [!UICONTROL trait] pour créer un groupe [!UICONTROL trait].
   * Pour afficher le modal [!UICONTROL Advanced Search] en cliquant sur **[!UICONTROL Browse All Traits]**. Recherchez [!UICONTROL traits] par nom, identifiant, description ou [!UICONTROL data source]. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer [!UICONTROL traits] par [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] et [!UICONTROL Algorithmic]) ou type de population ([ID de l&#39;appareil](../../reference/ids-in-aam.md) et [ID multi-appareils](../../reference/ids-in-aam.md)).

     ![ segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Obtenez des [recommandations de caractéristiques](trait-recommendations.md) en direct lorsque vous créez votre [!UICONTROL segment].
   * Cliquez et faites glisser [!UICONTROL traits] pour créer des groupes distincts.
   * Passez la souris sur les groupes pour définir des relations avec des valeurs booléennes [!UICONTROL AND], [!UICONTROL OR] et [!UICONTROL AND NOT].
   * Passez la souris sur l’icône de l’horloge pour ajouter des règles [récence et fréquence](../../features/segments/recency-and-frequency.md) à [!UICONTROL trait].
   * Affichez les données de population de segments au fur et à mesure que vous ajoutez ou supprimez [!UICONTROL traits]. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) les nombres estimés de population. Pour en savoir plus sur les [données de population de segments](../../features/segments/segment-builder-data.md#segment-populations) dans [!UICONTROL Segment Builder].
   * Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

1. *(Facultatif)* Mappez un [!UICONTROL segment] à un [!UICONTROL destination] dans la section [Mapping de destination](../../features/segments/segment-builder.md#segment-builder-controls-destinations) :
   * Recherchez [!UICONTROL destination] et cliquez sur **[!UICONTROL Add Destination]**. Remarque : [!UICONTROL destination] doit déjà exister avant de pouvoir l’ajouter à un [!UICONTROL segment].
   * Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

Regardez la vidéo ci-dessous pour une vue détaillée du fonctionnement des mesures sur plusieurs appareils.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Contrôles : [!UICONTROL Basic Information] Section {#segment-builder-controls-basics}

Dans [!UICONTROL Segment Builder], les paramètres [!UICONTROL the Basic Information] vous permettent de créer ou de modifier des caractéristiques existantes. Pour créer un [!UICONTROL segment], indiquez un nom, un [!UICONTROL data source], et sélectionnez un dossier de stockage. Tous les autres champs sont facultatifs. Passez à la section [!UICONTROL Traits] lorsque vous avez terminé.

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
| **[!UICONTROL Name]** | Attribuez au segment un nom court et logique qui décrit sa fonction ou son objectif. Évitez les abréviations et les caractères spéciaux. La longueur maximale d’un nom de segment est de 255 caractères. |
| **[!UICONTROL Description]** | Champ permettant d’obtenir des informations descriptives supplémentaires sur le segment. |
| **[!UICONTROL Integration Code]** | Un champ pour un identifiant défini par l’utilisateur ou d’autres informations spécifiques à l’entreprise. |
| **[!UICONTROL Data Source]** | Associe le segment à un fournisseur de données spécifique. <br> Utilisez le premier menu déroulant pour filtrer entre les sources de données d’Audience Manager, les suites de rapports Adobe Analytics ou les deux. Utilisez ensuite le deuxième menu déroulant pour choisir votre source de données. <br> Si vous n’utilisez pas de suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et par défaut, les sources de données d’Audience Manager sont uniquement désactivées. |
| **[!UICONTROL Profile Merge Rule]** | Sélectionne la règle de fusion de profils à utiliser pour la qualification du segment. |
| **[!UICONTROL Status]** | Active ou désactive le segment (actif par défaut). |
| **Stockage de dossier** | Détermine le dossier de stockage auquel le segment appartient. |

## [!UICONTROL Segment Builder] Contrôles : [!UICONTROL Traits] Section {#segment-builder-controls-traits}

Dans [!UICONTROL Segment Builder], la section [!UICONTROL Traits] vous permet de gérer [!UICONTROL traits] dans un [!UICONTROL segment], de créer [!UICONTROL trait] groupes et de définir des critères de qualification. Pour ajouter un [!UICONTROL trait] à un [!UICONTROL segment], saisissez le nom [!UICONTROL trait] dans le champ de recherche et cliquez sur [!UICONTROL Add Trait]. Enregistrez le [!UICONTROL trait] (s’il est terminé) ou passez à [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Conditions préalables :** Renseignez les champs requis de la section [!UICONTROL Basic Information].

| Champ | Description |
|--- |--- |
| **[!UICONTROL Basic View]** | Cette section fournit des contrôles visuels qui permettent : <ul><li>Créez et gérez les [!UICONTROL segments] existants.</li><li>Supprimez [!UICONTROL traits] d&#39;un [!UICONTROL segment].</li><li>Ajoutez jusqu’à 50 (maximum) [!UICONTROL traits] à un [!UICONTROL segment].</li><li>Effectuez un glisser-déposer de [!UICONTROL traits] pour créer des groupes.</li><li>Affichez les groupes [!UICONTROL traits] et [!UICONTROL trait] dans un [!UICONTROL segment].</li><li>Définissez des critères de qualification avec des expressions booléennes, des opérateurs de comparaison et des paramètres de récence/fréquence.</li></ul> |
| **[!UICONTROL Code View]** | Ouvre un environnement de développement qui vous permet de créer et de gérer des [!UICONTROL traits], des groupes et des exigences de qualification avec du code au lieu de l’interface visuelle. La vue de code est utile si votre [!UICONTROL segments] : <ul><li>Contient plus de 50 [!UICONTROL traits] dans un [!UICONTROL segment] individuel. Remarque : [!UICONTROL Segments] est limité à 5 000 [!UICONTROL traits] (maximum).</li><li>Contient de nombreux groupes [!UICONTROL trait].</li><li>ont des exigences de qualification complexes ;</li></ul> |
| Outils | Permet de trouver [!UICONTROL traits] à ajouter à un [!UICONTROL segment]. |
| Recommandations | Obtenez des recommandations en direct pour des [!UICONTROL traits] similaires à partir de vos flux de données propriétaires [!UICONTROL traits] et [!UICONTROL Audience Marketplace] auxquels vous êtes abonné. Ajoutez ces recommandations à la règle [!UICONTROL segment] pour développer votre audience. En savoir plus dans [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Obtenez des recommandations en direct pour des [!UICONTROL traits] similaires à partir de flux de données [!UICONTROL Audience Marketplace] auxquels vous n’êtes pas abonné. En savoir plus dans [Trait Recommendations](trait-recommendations.md). |
| Données de taille [!UICONTROL Segment] réelles et estimées | Voir [Données sur la population de segments et de caractéristiques dans le créateur de segments](segment-builder-data.md). |

## Supprimer [!UICONTROL Traits] d’un [!UICONTROL Segment] {#remove-traits}

La gestion de [!UICONTROL traits] dans votre [!UICONTROL segments] est un élément important pour maintenir [!UICONTROL segments] viable. Suivez ces étapes si vous devez supprimer [!UICONTROL traits] d’un [!UICONTROL segment].

Pour supprimer [!UICONTROL traits] d’un [!UICONTROL segment] :

1. Accédez à **[!UICONTROL Audience Data > Segments]**. Faites défiler la liste ou utilisez la fonction de recherche pour trouver le [!UICONTROL segment] que vous souhaitez utiliser.
2. Cliquez sur le nom [!UICONTROL segment] pour ouvrir l’écran de détails [!UICONTROL segment].
3. Cliquez sur **Modifier** pour ouvrir [!UICONTROL Segment Builder], puis sur **Caractéristiques** pour ouvrir le panneau [!UICONTROL traits].
4. Pointez sur le [!UICONTROL trait] à supprimer, puis cliquez sur le X. Cette action supprime immédiatement le [!UICONTROL trait] de votre [!UICONTROL segment].

## [!UICONTROL Segment Builder] Contrôles : [!UICONTROL Destinations Mappings] Section {#segment-builder-controls-destinations}

Dans [!UICONTROL Segment Builder], la section facultative [!UICONTROL Destinations Mapping] vous permet d&#39;envoyer des données [!UICONTROL segment] à un tiers [!DNL cookie], [!DNL URL] ou [!UICONTROL server-to-server destination]. Pour ajouter un [!UICONTROL destination], recherchez (ou parcourez) un [!UICONTROL destination], fournissez des informations spécifiques à [!UICONTROL destination], puis cliquez sur **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Conditions préalables

Renseignez les champs obligatoires des sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . En outre, la destination doit déjà exister.

### [!UICONTROL Destination Mappings] Outils de recherche

Le panneau **[!UICONTROL Destination Mappings]** contient des outils de recherche comme décrit dans le tableau ci-dessous.

| Type de recherche | Description |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Permet de rechercher un [!UICONTROL destination] spécifique par nom. Pour effectuer une recherche, commencez à taper. Le champ est automatiquement renseigné en fonction de vos termes de recherche. Cliquez sur **[!UICONTROL Add Destination]** lorsque vous avez terminé. |
| **[!UICONTROL Browse All Destinations]** | Parcourez la liste de *all* [!UICONTROL destinations] disponible pour vous. Sélectionnez et ajoutez [!UICONTROL destinations] à votre [!UICONTROL segment] dans la liste déroulante. |

## Champs dans la fenêtre contextuelle [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

Dans [!UICONTROL Segment Builder], la boîte de dialogue [!UICONTROL Add Destination] s’affiche une fois que vous avez sélectionné un [!UICONTROL destination]. Cette fenêtre affiche des informations statiques sur les champs [!UICONTROL destination] et qui varient selon le type [!UICONTROL destination]. Fournissez les informations requises dans les champs vides pour configurer un [!UICONTROL destination mapping].

>[!NOTE]
>
>Les dates de publication sont facultatives. Lorsqu’elle est vide, la destination devient active et n’expire jamais.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Fields

Dans les champs [!UICONTROL Destination Mapping], spécifiez les paires clé-valeur utilisées pour envoyer des données à [!UICONTROL destination]. Saisissez la clé dans le premier champ et les valeurs dans le second. Votre pop [!UICONTROL cookie destination] peut ressembler à ceci :

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Fields

Dans les champs [!UICONTROL URL] et [!UICONTROL Secure URL] , spécifiez l’adresse standard complète ou sécurisée utilisée pour envoyer des données à [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Fields

Dans le champ [!UICONTROL Destination Value] , spécifiez la valeur (faisant partie d’une paire clé-valeur) utilisée pour envoyer des données à [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Création d’une destination de cookie](../../features/destinations/create-cookie-destination.md)
>* [Création d’une destination d’URL](../../features/destinations/create-url-destination.md)
