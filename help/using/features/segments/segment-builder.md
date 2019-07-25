---
description: Décrit la création de segments avec le créateur de segments.
seo-description: Décrit la création de segments avec le créateur de segments.
seo-title: Créateur de segments
solution: Audience Manager
title: Créateur de segments
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: b346dbe500f1e662c7b121a18c6cc0704ef3cfac

---


# Créateur de segments {#segment-builder}

Describes the required and optional steps that create a segment in [!UICONTROL Segment Builder].

## Créer un segment {#create-segment}

### Section du créateur de segments

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] comprend 3 sections distinctes : [!UICONTROL Basic Information], [!UICONTROL Traits]et [!UICONTROL Destinations Mapping]. To create a segment, complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. [!UICONTROL Destinations Mapping] sont facultatifs. Pour obtenir une aide supplémentaire, reportez-vous aux instructions ci-dessous.

1. In the [Basic Information](../../features/segments/segment-builder.md#segment-builder-controls-basics) section:
   * Nommez le segment. La longueur maximale d'un nom de segment est de 255 caractères.
   * Définissez l'état du segment (actif est par défaut).
   * Choisissez une source de données.
   * Sélectionnez une règle de fusion de profil à utiliser pour la qualification des segments.
   * Affectez le segment à un dossier de stockage.
1. In the [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) section:
   * Search for the trait you want to add to a segment and click **[!UICONTROL Add Trait]**. Ajoutez une autre caractéristique pour créer un groupe de caractéristiques.
   * Bring up the Advanced Search modal by clicking **[!UICONTROL Browse All Traits]**. Rechercher des caractéristiques par nom, identifiant, description ou source de données. Cliquez sur un dossier tout en cherchant à limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer les caractéristiques par type de caractéristique.
   * Get live [trait recommendations](trait-recommendations.md) as you build your segment.
   * Cliquez et faites glisser des caractéristiques pour créer des groupes distincts.
   * Hover between groups to set relationships with Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] values.
   * Hover over the clock icon to add [recency and frequency](../../features/segments/recency-and-frequency.md) rules to the trait.
   * Affichez les données de population de segments au fur et à mesure que vous ajoutez ou supprimez des caractéristiques. Click **[!UICONTROL Calculate Estimates]** to see (or refresh) the estimated population numbers. Read more about [segment population data](../../features/segments/segment-builder-data.md#segment-populations) in the Segment Builder.
   * Click **[!UICONTROL Save]** when done.
1. *(Facultatif)* Mappez un segment à une destination dans [la section Mappage](../../features/segments/segment-builder.md#segment-builder-controls-destinations) de destination :
   * Search for the destination and click **[!UICONTROL Add Destination]**. Remarque : la destination doit déjà exister avant de pouvoir l'ajouter à un segment.
   * Click **[!UICONTROL Save]** when done.

## Segment Builder Controls: Basic Information Section {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] settings let you create new, or edit existing traits. Pour créer un segment, fournissez un nom, une source de données et sélectionnez un dossier de stockage. Tous les autres champs sont facultatifs. Move on to the [!UICONTROL Traits] section when done.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Nom</b> </td> 
   <td colname="col2"> <p>Donnez au segment un court nom logique décrivant sa fonction ou son rôle. Evitez les abréviations et les caractères spéciaux. La longueur maximale d'un nom de segment est de 255 caractères. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>Champ pour obtenir des informations descriptives supplémentaires sur le segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Code d’intégration</b> </td> 
   <td colname="col2"> <p>Champ pour un identifiant défini par l'utilisateur ou d'autres informations spécifiques à l'entreprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Source de données</b> </td> 
   <td colname="col2"> <p>Associe le segment à un fournisseur de données spécifique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Règle de fusion de profils</b> </td> 
   <td colname="col2"> <p>Sélectionne la règle de fusion de profils à utiliser pour la qualification des segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>État</b> </td> 
   <td colname="col2"> <p>Active ou désactive le segment (actif par défaut). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Stockage de dossier</b> </td> 
   <td colname="col2"> <p>Détermine le dossier de stockage auquel le segment appartient. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls: Traits Section {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], the [!UICONTROL Traits] section lets you manage traits in a segment, create trait groups, and set qualification criteria. To add a trait to a segment, type the trait name in the search field and click [!UICONTROL Add Trait]. Save the trait (if finished) or move on to [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**Conditions préalables :** Renseignez les champs obligatoires de la [!UICONTROL Basic Information] section.

| Champ | Description |
|--- |--- |
| Vue de base | Cette section propose des commandes visuelles qui vous permettent d'effectuer les opérations suivantes : <ul><li>Créez et gérez des segments existants.</li><li>Supprimez les caractéristiques d'un segment.</li><li>Ajoute jusqu'à 50 caractéristiques (maximum) à un segment.</li><li>Faites glisser des caractéristiques pour créer des groupes.</li><li>Affichez les caractéristiques et les groupes de caractéristiques dans un segment.</li><li>Définissez les critères de qualification avec les expressions booléennes, les opérateurs de comparaison et les paramètres récence/fréquence.</li></ul> |
| Affichage du code | Ouvre un environnement de développement qui vous permet de créer et de gérer des caractéristiques, des groupes et des exigences de qualification avec le code au lieu de l'interface visuelle. L'affichage du code est utile si vos segments sont les suivants : <ul><li>Contient plus de 50 caractéristiques dans un segment individuel. Remarque : Les segments sont limités à 5 000 caractéristiques (maximum).</li><li>Contient de nombreux groupes de caractéristiques.</li><li>Posséder des conditions de qualification complexes.</li></ul> |
| Outils | Permet de trouver des caractéristiques à ajouter à un segment. |
| Recommandations | Obtenez des recommandations en direct pour des caractéristiques similaires à ajouter à la règle de segment. Read more in [Trait Recommendations](trait-recommendations.md). |
| Données de taille de segment réelles et estimées | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Remove Traits from a Segment {#remove-traits}

La gestion des caractéristiques dans vos segments est une étape importante de la viabilité des segments. Pour supprimer des caractéristiques d'un segment, procédez comme suit :

Pour supprimer des caractéristiques d'un segment :

1. Go to **Audience Data &gt; Segments**. Faites défiler la liste ou utilisez la fonction de recherche pour trouver le segment avec lequel vous souhaitez travailler.
2. Cliquez sur le nom du segment pour ouvrir l'écran des détails du segment.
3. Click **Edit** to open Segment Builder and then click **Traits** to open the traits panel.
4. Passez la souris sur la caractéristique que vous souhaitez supprimer, puis cliquez sur le X. Cette action supprime immédiatement la caractéristique de votre segment.

## Segment Builder Controls: Destinations Mappings Section {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], the optional [!UICONTROL Destinations Mapping] section lets you send segment data to a third-party [!DNL cookie], [!DNL URL], or server-to-server destination. To add a destination, search (or browse) for a destination, provide destination specific information, and click **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Conditions préalables

Complete the required fields in the [!UICONTROL Basic Information] and [!UICONTROL Traits] sections. De même, la destination doit déjà exister.

### Outils de recherche des correspondances de destination

**[!UICONTROL Destination Mappings]** Le panneau contient des outils de recherche comme décrit dans le tableau ci-dessous.

| Type de recherche | Description |
|---|---|
| **Recherche par nom de destination** | Permet de rechercher une destination spécifique par nom. Pour effectuer une recherche, commencez à saisir. Le champ se termine automatiquement en fonction de vos termes de recherche. Click **[!UICONTROL Add Destination]** when done. |
| **Parcourir toutes les destinations** | Browse a list of *all* destinations available to you. Sélectionnez et ajoutez des destinations à votre segment dans la liste contextuelle. |

## Fields in the Destination Mappings Pop-up Windows {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], the [!UICONTROL Add Destination] dialog appears after you select a destination. Cette fenêtre affiche des informations statiques sur la destination et les champs qui varient selon le type de destination. Fournissez les informations requises dans les champs vides pour configurer un mappage de destination.

>[!NOTE]
>
>Les dates de publication sont facultatives. Lorsqu'elle est vide, la destination devient active et n'expire jamais.

<!-- r_add_mappings_pop.xml -->

### Champs de destination des cookies

In the [!UICONTROL Destination Mapping] fields, specify the key-value pairs used to send data to the destination. Saisissez la clé dans le premier champ et les valeurs de la seconde. La pop destination de votre cookie peut se présenter comme suit :

![](assets/cookie_modal.PNG)

### Champs de destination d'URL

In the [!UICONTROL URL] and [!UICONTROL Secure URL] fields, specify the complete standard or secure address used to send data to the destination.

![](assets/url_modal.PNG)

### Champs de destination serveur vers serveur

In the [!UICONTROL Destination Value] field specify the value (part of a key-value pair) used to send data to the destination.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Création d'une destination de cookie](../../features/destinations/manage-destinations.md#create-cookie-destination)
>* [Création d'une destination d'URL](../../features/destinations/manage-destinations.md#configure-url-destination)

