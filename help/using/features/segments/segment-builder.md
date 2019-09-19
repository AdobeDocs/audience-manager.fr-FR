---
description: Décrit comment créer des segments avec le créateur de segments.
seo-description: Décrit comment créer des segments avec le créateur de segments.
seo-title: Créateur de segments
solution: Audience Manager
title: Créateur de segments
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 0d0806ef2c84b4770adc29d668351ac3f2d8cc5f

---


# Créateur de segments {#segment-builder}

Décrit les étapes obligatoires et facultatives de création d’un segment dans [!UICONTROL Segment Builder].

## Démonstration vidéo

Commencez par regarder la vidéo [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Créer des segments dans Audience Manager. La vidéo vous guide tout au long du processus de création de segments. Lisez les sections ci-dessous pour en savoir plus.

## Créer un segment {#create-segment}

### Section Créateur de segments

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] se compose de trois sections distinctes : [!UICONTROL Basic Information], [!UICONTROL Traits]et [!UICONTROL Destinations Mapping]. Pour créer un segment, renseignez les champs obligatoires dans les sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] sont facultatives. Consultez les instructions ci-dessous pour obtenir une aide supplémentaire.

1. Dans la section Informations [](../../features/segments/segment-builder.md#segment-builder-controls-basics) de base :
   * Attribuez un nom au segment. La longueur maximale d’un nom de segment est de 255 caractères.
   * Définissez l’état du segment (actif par défaut).
   * Sélectionnez une source de données.
   * Sélectionnez une règle de fusion de profil à utiliser pour la qualification des segments.
   * Affectez le segment à un dossier de stockage.
1. Dans la section [Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   * Recherchez la caractéristique à ajouter à un segment et cliquez sur **[!UICONTROL Add Trait]**. Ajoutez une autre caractéristique pour créer un groupe de caractéristiques.
   * Affichez le module Recherche avancée en cliquant sur **[!UICONTROL Browse All Traits]**. Recherchez les caractéristiques par nom, ID, description ou source de données. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer les caractéristiques par type de caractéristique.
   * Obtenez des recommandations [de](trait-recommendations.md) caractéristiques en direct lorsque vous créez votre segment.
   * Cliquez et faites glisser des caractéristiques pour créer des groupes distincts.
   * Passez la souris sur des groupes pour définir des relations avec des valeurs booléennes [!UICONTROL AND], [!UICONTROL OR]et [!UICONTROL AND NOT] .
   * Passez la souris sur l’icône de l’horloge pour ajouter des règles de [récence et de fréquence](../../features/segments/recency-and-frequency.md) à la caractéristique.
   * Affichez les données de population de segments lorsque vous ajoutez ou supprimez des caractéristiques. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) l’estimation des chiffres de population. En savoir plus sur les données [de population de](../../features/segments/segment-builder-data.md#segment-populations) segments dans le créateur de segments.
   * Click **[!UICONTROL Save]** when done.
1. *(Facultatif)* Faites correspondre un segment à une destination dans la section Mappage [de](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destination :
   * Recherchez la destination et cliquez sur **[!UICONTROL Add Destination]**. Remarque : la destination doit déjà exister avant de pouvoir l’ajouter à un segment.
   * Click **[!UICONTROL Save]** when done.

## Contrôles du créateur de segments : Section des informations de base {#segment-builder-controls-basics}

Dans [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] les paramètres vous permettent de créer des caractéristiques ou de modifier des caractéristiques existantes. Pour créer un segment, nommez-le, créez une source de données et sélectionnez un dossier de stockage. Tous les autres champs sont facultatifs. Passez à la [!UICONTROL Traits] section lorsque vous avez terminé.

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
   <td colname="col2"> <p>Attribuez au segment un nom logique court qui décrit sa fonction ou son objectif. Evitez les abréviations et les caractères spéciaux. La longueur maximale d’un nom de segment est de 255 caractères. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>Champ pour obtenir des informations descriptives supplémentaires sur le segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Code d’intégration</b> </td> 
   <td colname="col2"> <p>Champ d’un ID défini par l’utilisateur ou d’autres informations propres à l’entreprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Source de données</b> </td> 
   <td colname="col2"> <p>Associe le segment à un fournisseur de données spécifique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Règle de fusion de profil</b> </td> 
   <td colname="col2"> <p>Sélectionne la règle de fusion de profils à utiliser pour la qualification des segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>État</b> </td> 
   <td colname="col2"> <p>Active ou désactive le segment (actif par défaut). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Stockage de dossiers</b> </td> 
   <td colname="col2"> <p>Détermine le dossier de stockage auquel appartient le segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contrôles du créateur de segments : Section Caractéristiques {#segment-builder-controls-traits}

Dans [!UICONTROL Segment Builder]cette [!UICONTROL Traits] section, vous pouvez gérer les caractéristiques d’un segment, créer des groupes de caractéristiques et définir des critères de qualification. Pour ajouter une caractéristique à un segment, saisissez son nom dans le champ de recherche, puis cliquez sur [!UICONTROL Add Trait]. Enregistrez la caractéristique (le cas échéant) ou passez à [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml -->

**** Conditions préalables : Renseignez les champs obligatoires de la [!UICONTROL Basic Information] section.

| Champ | Description |
|--- |--- |
| Vue de base | Cette section fournit des commandes visuelles qui vous permettent d’effectuer les opérations suivantes : <ul><li>Créez et gérez des segments existants.</li><li>Supprimez les caractéristiques d’un segment.</li><li>Ajoutez jusqu’à 50 caractéristiques (maximum) à un segment.</li><li>Faites glisser et déposez des caractéristiques pour créer des groupes.</li><li>Affichez les caractéristiques et les groupes de caractéristiques dans un segment.</li><li>Définissez des critères de qualification avec des expressions booléennes, des opérateurs de comparaison et des paramètres de récence/fréquence.</li></ul> |
| Affichage du code | Ouvre un environnement de développement qui vous permet de créer et de gérer des caractéristiques, des groupes et des exigences de qualification avec du code au lieu de l’interface visuelle. L’affichage du code est utile si vos segments : <ul><li>Contient plus de 50 caractéristiques dans un segment individuel. Remarque : Les segments sont limités à 5 000 caractéristiques (maximum).</li><li>Contiennent de nombreux groupes de caractéristiques.</li><li>Posséder des exigences de qualification complexes.</li></ul> |
| Outils | Vous aide à trouver les caractéristiques à ajouter à un segment. |
| Recommandations | Obtenez des recommandations en direct pour des caractéristiques similaires à ajouter à la règle de segmentation. Pour en savoir plus, consultez Recommandations [de](trait-recommendations.md)caractéristiques. |
| Données de taille de segment réelle et estimée | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Suppression de caractéristiques d’un segment {#remove-traits}

La gestion des caractéristiques de vos segments est un élément important de la viabilité des segments. Suivez ces étapes si vous devez supprimer des caractéristiques d’un segment.

Pour supprimer des caractéristiques d’un segment :

1. Accédez à Données **d’audience &gt; Segments**. Faites défiler la liste ou utilisez la fonction de recherche pour trouver le segment à utiliser.
2. Cliquez sur le nom du segment pour ouvrir l’écran des détails du segment.
3. Cliquez sur **Modifier** pour ouvrir le créateur de segments, puis sur **Caractéristiques** pour ouvrir le panneau Caractéristiques.
4. Passez la souris sur la caractéristique à supprimer, puis cliquez sur le X. Cette action supprime immédiatement la caractéristique de votre segment.

## Contrôles du créateur de segments : Section Mappages de destinations {#segment-builder-controls-destinations}

Dans [!UICONTROL Segment Builder]la section facultative [!UICONTROL Destinations Mapping] , vous pouvez envoyer des données de segment vers une destination tierce [!DNL cookie], [!DNL URL]ou serveur à serveur. Pour ajouter une destination, recherchez (ou parcourez) une destination, fournissez des informations spécifiques à la destination, puis cliquez sur **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Conditions préalables

Renseignez les champs obligatoires dans les sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . En outre, la destination doit déjà exister.

### Mappages de destination Outils de recherche

Le **[!UICONTROL Destination Mappings]** panneau contient des outils de recherche, comme décrit dans le tableau ci-dessous.

| Type de recherche | Description |
|---|---|
| **Rechercher par nom de destination** | Permet de rechercher une destination spécifique par son nom. Pour effectuer une recherche, commencez à taper. Le champ est renseigné automatiquement en fonction des termes recherchés. Click **[!UICONTROL Add Destination]** when done. |
| **Parcourir toutes les destinations** | Parcourez la liste de *toutes les* destinations disponibles. Sélectionnez et ajoutez des destinations à votre segment dans la liste contextuelle. |

## Champs dans la fenêtre contextuelle Correspondances de destination {#fields-in-dest-mappings}

Dans [!UICONTROL Segment Builder]la boîte de dialogue [!UICONTROL Add Destination] s’affiche une fois que vous avez sélectionné une destination. Cette fenêtre affiche des informations statiques sur la destination et les champs qui varient selon le type de destination. Fournissez les informations requises dans les champs vides pour configurer un mappage de destination.

>[!NOTE]
>
>Les dates de publication sont facultatives. Lorsqu’elle est vide, la destination devient active et n’expire jamais.

<!-- r_add_mappings_pop.xml -->

### Champs de destination du cookie

Dans les [!UICONTROL Destination Mapping] champs, spécifiez les paires clé-valeur utilisées pour envoyer les données vers la destination. Entrez la clé dans le premier champ et les valeurs dans le second. La fenêtre contextuelle de destination du cookie peut se présenter comme suit :

![](assets/cookie_modal.PNG)

### Champs de destination d’URL

Dans les champs [!UICONTROL URL] et [!UICONTROL Secure URL] , spécifiez l’adresse standard complète ou sécurisée utilisée pour envoyer les données vers la destination.

![](assets/url_modal.PNG)

### Champs de destination du serveur au serveur

Dans le [!UICONTROL Destination Value] champ, spécifiez la valeur (partie d’une paire clé-valeur) utilisée pour envoyer les données vers la destination.

![](assets/s2s_modal.PNG)

>[!MORE_LIKE_This]
>
>* [Création d’une destination de cookie](../../features/destinations/create-cookie-destination.md)
>* [Création d’une destination d’URL](../../features/destinations/create-url-destination.md)

