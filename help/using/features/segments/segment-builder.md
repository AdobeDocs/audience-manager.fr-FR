---
description: Décrit la création de segments avec le créateur de segments.
seo-description: Décrit la création de segments avec le créateur de segments.
seo-title: Créateur de segments
solution: Audience Manager
title: Créateur de segments
uuid: 5 ca 924 a 5-2 b 29-4802-ab 02-e 292 d 77 a 0 aae
translation-type: tm+mt
source-git-commit: f67ab906bfbd9900941649c4d9045ea94f1e7f4c

---


# Créateur de segments {#segment-builder}

Décrit les étapes obligatoires et facultatives qui créent un segment dans [!UICONTROL Segment Builder].

## Créer un segment {#create-segment}

### Section du créateur de segments

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] comprend 3 sections distinctes : [!UICONTROL Basic Information], [!UICONTROL Traits]et [!UICONTROL Destinations Mapping]. Pour créer un segment, renseignez les champs obligatoires des sections [!UICONTROL Basic Information] et [!UICONTROL Traits] des sections. [!UICONTROL Destinations Mapping] sont facultatifs. Pour obtenir une aide supplémentaire, reportez-vous aux instructions ci-dessous.

1. Dans [la section Informations](../../features/segments/segment-builder.md#segment-builder-controls-basics) de base :
   * Nommez le segment. La longueur maximale d'un nom de segment est de 255 caractères.
   * Définissez l'état du segment (actif est par défaut).
   * Choisissez une source de données.
   * Sélectionnez une règle de fusion de profil à utiliser pour la qualification des segments.
   * Affectez le segment à un dossier de stockage.
1. Dans la section [Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Recherchez la caractéristique que vous souhaitez ajouter à un segment et cliquez **[!UICONTROL Add Trait]** sur. Ajoutez une autre caractéristique pour créer un groupe de caractéristiques.
   * Affichez la fenêtre de recherche avancée en cliquant **[!UICONTROL Browse All Traits]** sur. Rechercher des caractéristiques par nom, identifiant, description ou source de données. Cliquez sur un dossier tout en cherchant à limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer les caractéristiques par type de caractéristique.
   * Obtenez des recommandations [de caractéristiques dynamiques](trait-recommendations.md) lorsque vous créez votre segment.
   * Cliquez et faites glisser des caractéristiques pour créer des groupes distincts.
   * Passez la souris entre les groupes pour définir les relations avec booléen [!UICONTROL AND], [!UICONTROL OR][!UICONTROL AND NOT] valeurs.
   * Passez la souris sur l'icône représentant une horloge pour ajouter [des règles de récence et de fréquence](../../features/segments/recency-and-frequency.md) à la caractéristique.
   * Affichez les données de population de segments au fur et à mesure que vous ajoutez ou supprimez des caractéristiques. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) le nombre estimé de population. En savoir plus sur [les données de population de segments](../../features/segments/segment-builder-data.md#segment-populations) dans le créateur de segments.
   * Click **[!UICONTROL Save]** when done.
1. *(Facultatif)* Mappez un segment à une destination dans [la section Mappage](../../features/segments/segment-builder.md#segment-builder-controls-destinations) de destination :
   * Recherchez la destination et cliquez **[!UICONTROL Add Destination]** sur. Remarque : la destination doit déjà exister avant de pouvoir l'ajouter à un segment.
   * Click **[!UICONTROL Save]** when done.

## Commandes du créateur de segments : Section Informations de base {#segment-builder-controls-basics}

Dans [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] les paramètres vous permettent de créer ou de modifier des caractéristiques existantes. Pour créer un segment, fournissez un nom, une source de données et sélectionnez un dossier de stockage. Tous les autres champs sont facultatifs. Passez à [!UICONTROL Traits] la section lorsque vous avez terminé.

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

## Commandes du créateur de segments : Section Caractéristiques {#segment-builder-controls-traits}

Dans [!UICONTROL Segment Builder], la [!UICONTROL Traits] section vous permet de gérer les caractéristiques d'un segment, de créer des groupes de caractéristiques et de définir des critères de qualification. Pour ajouter une caractéristique à un segment, entrez le nom de la caractéristique dans le champ de recherche et cliquez [!UICONTROL Add Trait]sur. Enregistrez la caractéristique (le cas échéant) ou poursuivez [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**Conditions préalables :** Renseignez les champs obligatoires de la [!UICONTROL Basic Information] section.

| Champ | Description |
|--- |--- |
| Vue de base | Cette section propose des commandes visuelles qui vous permettent d'effectuer les opérations suivantes : <ul><li>Créez et gérez des segments existants.</li><li>Supprimez les caractéristiques d'un segment.</li><li>Ajoute jusqu'à 50 caractéristiques (maximum) à un segment.</li><li>Faites glisser des caractéristiques pour créer des groupes.</li><li>Affichez les caractéristiques et les groupes de caractéristiques dans un segment.</li><li>Définissez les critères de qualification avec les expressions booléennes, les opérateurs de comparaison et les paramètres récence/fréquence.</li></ul> |
| Affichage du code | Ouvre un environnement de développement qui vous permet de créer et de gérer des caractéristiques, des groupes et des exigences de qualification avec le code au lieu de l'interface visuelle. L'affichage du code est utile si vos segments sont les suivants : <ul><li>Contient plus de 50 caractéristiques dans un segment individuel. Remarque : Les segments sont limités à 5 000 caractéristiques (maximum).</li><li>Contient de nombreux groupes de caractéristiques.</li><li>Posséder des conditions de qualification complexes.</li></ul> |
| Outils | Permet de trouver des caractéristiques à ajouter à un segment. |
| Recommandations | Obtenez des recommandations en direct pour des caractéristiques similaires à ajouter à la règle de segment. En savoir plus dans [Recommendations Recommendations](trait-recommendations.md). |
| Données de taille de segment réelles et estimées | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Supprimer des caractéristiques d'un segment {#remove-traits}

La gestion des caractéristiques dans vos segments est une étape importante de la viabilité des segments. Pour supprimer des caractéristiques d'un segment, procédez comme suit :

Pour supprimer des caractéristiques d'un segment :

1. Accédez à **Données d'audience &gt; Segments**. Faites défiler la liste ou utilisez la fonction de recherche pour trouver le segment avec lequel vous souhaitez travailler.
2. Cliquez sur le nom du segment pour ouvrir l'écran des détails du segment.
3. Cliquez **sur Modifier** pour ouvrir le créateur de segments, puis sur **Caractéristiques** pour ouvrir le panneau Caractéristiques.
4. Passez la souris sur la caractéristique que vous souhaitez supprimer, puis cliquez sur le X. Cette action supprime immédiatement la caractéristique de votre segment.

## Commandes du créateur de segments : Section Correspondances de destinations {#segment-builder-controls-destinations}

Dans [!UICONTROL Segment Builder]la, la section facultative [!UICONTROL Destinations Mapping] vous permet d'envoyer des données de segment à une destination tierce [!DNL cookie]ou [!DNL URL]serveur à serveur. Pour ajouter une destination, rechercher (ou parcourir) une destination, fournissez des informations spécifiques à la destination, puis cliquez **[!UICONTROL Add Destination]** sur.

<!-- r_segment_destinations_map.xml -->

### Conditions préalables

Renseignez les champs obligatoires dans les sections [!UICONTROL Basic Information] et [!UICONTROL Traits] les sections. De même, la destination doit déjà exister.

### Outils de recherche des correspondances de destination

**[!UICONTROL Destination Mappings]** Le panneau contient des outils de recherche comme décrit dans le tableau ci-dessous.

| Type de recherche | Description |
|---|---|
| **Recherche par nom de destination** | Permet de rechercher une destination spécifique par nom. Pour effectuer une recherche, commencez à saisir. Le champ se termine automatiquement en fonction de vos termes de recherche. Click **[!UICONTROL Add Destination]** when done. |
| **Parcourir toutes les destinations** | Parcourez la liste *de toutes* les destinations disponibles. Sélectionnez et ajoutez des destinations à votre segment dans la liste contextuelle. |

## Champs de la fenêtre contextuelle Correspondance de destination {#fields-in-dest-mappings}

Dans [!UICONTROL Segment Builder], [!UICONTROL Add Destination] le dialogue s'affiche une fois que vous avez sélectionné une destination. Cette fenêtre affiche des informations statiques sur la destination et les champs qui varient selon le type de destination. Fournissez les informations requises dans les champs vides pour configurer un mappage de destination.

>[!NOTE]
>
>Les dates de publication sont facultatives. Lorsqu'elle est vide, la destination devient active et n'expire jamais.

<!-- r_add_mappings_pop.xml -->

### Champs de destination des cookies

Dans [!UICONTROL Destination Mapping] les champs, spécifiez les paires clé-valeur utilisées pour envoyer les données à la destination. Saisissez la clé dans le premier champ et les valeurs de la seconde. La pop destination de votre cookie peut se présenter comme suit :

![](assets/cookie_modal.PNG)

### Champs de destination d'URL

Dans les [!UICONTROL URL] champs et [!UICONTROL Secure URL] les champs, indiquez l'adresse standard ou sécurisée complète utilisée pour envoyer les données à la destination.

![](assets/url_modal.PNG)

### Champs de destination serveur vers serveur

Dans [!UICONTROL Destination Value] le champ, indiquez la valeur (partie d'une paire clé-valeur) utilisée pour envoyer les données à la destination.

![](assets/s2s_modal.PNG)

>[!MORE_ LIKE_ THIS]
>
>* [Création d'une destination de cookie](../../features/destinations/create-cookie-destination.md)
>* [Création d'une destination d'URL](../../features/destinations/create-url-destination.md)

