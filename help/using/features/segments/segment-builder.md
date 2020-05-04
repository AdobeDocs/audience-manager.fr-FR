---
description: Décrit comment créer des segments avec le créateur de segments.
seo-description: Décrit comment créer des segments avec le créateur de segments.
seo-title: Créateur de segments
solution: Audience Manager
title: Créateur de segments
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 859e55fa5d93c7c56cef4bf2a112cdd4ff318d97

---


# Créateur de segments {#segment-builder}

Décrit les étapes requises et facultatives de création d’un segment dans [!UICONTROL Segment Builder].

## Démonstration vidéo

Début en regardant la vidéo [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Créer des segments dans Audience Manager. La vidéo vous guide tout au long du processus de création de segments. Lisez les sections ci-dessous pour plus d&#39;informations.

## Créer un segment {#create-segment}

### Section Créateur de segments

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] se compose de 3 sections distinctes : [!UICONTROL Basic Information], [!UICONTROL Traits]et [!UICONTROL Destinations Mapping]. Pour créer un segment, renseignez les champs obligatoires des sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . [!UICONTROL Destinations Mapping] sont facultatifs. Consultez les instructions ci-dessous pour obtenir une aide supplémentaire.

1. Dans la section Informations [](../../features/segments/segment-builder.md#segment-builder-controls-basics) de base :

   ![create-segment](assets/create-segment.png)

   * Nommez le segment. La longueur maximale d’un nom de segment est de 255 caractères.
   * Définissez l’état du segment (actif par défaut).
   * Sélectionnez une source de données. Utilisez le premier menu déroulant pour filtrer entre les sources de données d’Audience Manager, les suites de rapports Adobe Analytics ou les deux. Ensuite, utilisez le deuxième menu déroulant pour choisir votre source de données. Si vous n’utilisez pas les suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et les sources de données d’Audience Manager sont désactivées par défaut uniquement.
   * Sélectionnez une règle de fusion de profil à utiliser pour la qualification des segments.
   * Affectez le segment à un dossier d’enregistrement.

1. Dans la section [Caractéristiques](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Recherchez la caractéristique à ajouter à un segment et cliquez sur **[!UICONTROL Add Trait]**. Ajouter une autre caractéristique pour créer un groupe de caractéristiques.
   * Affichez le module Recherche avancée en cliquant sur **[!UICONTROL Browse All Traits]**. Recherchez des caractéristiques par nom, identifiant, description ou source de données. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer les caractéristiques par type de caractéristique ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]et [!UICONTROL Algorithmic]) ou type de population (ID[](../../reference/ids-in-aam.md) de périphérique et ID [inter-périphériques).](../../reference/ids-in-aam.md)
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Obtenez des recommandations [de](trait-recommendations.md) caractéristiques en direct lorsque vous créez votre segment.
   * Cliquez et faites glisser les caractéristiques pour créer des groupes distincts.
   * Passez la souris sur des groupes pour définir des relations avec des [!UICONTROL AND]valeurs booléennes [!UICONTROL OR][!UICONTROL AND NOT] et booléennes.
   * Passez la souris sur l’icône de l’horloge pour ajouter des règles de [récence et de fréquence](../../features/segments/recency-and-frequency.md) à la caractéristique.
   * Vue des données de population de segments au fur et à mesure que vous ajoutez ou supprimez des caractéristiques. Cliquez sur **[!UICONTROL Calculate Estimates]** pour afficher (ou actualiser) l’estimation des chiffres de population. En savoir plus sur les données [de population de](../../features/segments/segment-builder-data.md#segment-populations) segments dans le créateur de segments.
   * Cliquez **[!UICONTROL Save]** une fois terminé.

1. *(Facultatif)* Faites correspondre un segment à une destination dans la section Mappage [de](../../features/segments/segment-builder.md#segment-builder-controls-destinations) destination :
   * Recherchez la destination et cliquez sur **[!UICONTROL Add Destination]**. Remarque : la destination doit déjà exister pour que vous puissiez l’ajouter à un segment.
   * Cliquez **[!UICONTROL Save]** une fois terminé.

Regardez la vidéo ci-dessous pour obtenir un aperçu détaillé du fonctionnement des mesures sur plusieurs périphériques.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Contrôles du créateur de segments : Section des informations de base {#segment-builder-controls-basics}

Dans [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] les paramètres vous permettent de créer ou de modifier des caractéristiques existantes. Pour créer un segment, nommez-le, définissez une source de données et sélectionnez un dossier d’enregistrement. Tous les autres champs sont facultatifs. Passez à la [!UICONTROL Traits] section lorsque vous avez terminé.

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
   <td colname="col2"> <p>Attribuez au segment un nom court et logique qui décrit sa fonction ou son objectif. Evitez les abréviations et les caractères spéciaux. La longueur maximale d’un nom de segment est de 255 caractères. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>Un champ pour obtenir des informations descriptives supplémentaires sur le segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Code d’intégration</b> </td> 
   <td colname="col2"> <p>Champ d’un identifiant défini par l’utilisateur ou d’autres informations spécifiques à une société. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Source de données</b> </td> 
   <td colname="col2"> <p>Associe le segment à un fournisseur de données spécifique. <p>Utilisez le premier menu déroulant pour filtrer entre les sources de données d’Audience Manager, les suites de rapports Adobe Analytics ou les deux. Ensuite, utilisez le deuxième menu déroulant pour choisir votre source de données.</p><p> Si vous n’utilisez pas les suites de rapports Adobe Analytics, le sélecteur de type de source de données est désactivé et les sources de données d’Audience Manager sont désactivées par défaut uniquement.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Règle de fusion de Profils</b> </td> 
   <td colname="col2"> <p>Sélectionne la règle de fusion de Profils à utiliser pour la qualification de segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>État</b> </td> 
   <td colname="col2"> <p>Active ou désactive le segment (actif par défaut). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Enregistrement de dossier</b> </td> 
   <td colname="col2"> <p>Détermine le dossier d’enregistrement auquel appartient le segment. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Contrôles du créateur de segments : Section Traits {#segment-builder-controls-traits}

Dans [!UICONTROL Segment Builder]la [!UICONTROL Traits] section, vous pouvez gérer les caractéristiques d’un segment, créer des groupes de caractéristiques et définir des critères de qualification. Pour ajouter une caractéristique à un segment, entrez son nom dans le champ de recherche, puis cliquez sur [!UICONTROL Add Trait]. Enregistrez la caractéristique (si vous avez terminé) ou passez à [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Conditions préalables :** Renseignez les champs obligatoires de la [!UICONTROL Basic Information] section.

| Champ | Description |
|--- |--- |
| Vue de base | Cette section fournit des commandes visuelles qui vous permettent d&#39;effectuer les opérations suivantes : <ul><li>Créez et gérez des segments existants.</li><li>Supprimez les caractéristiques d’un segment.</li><li>Ajouter jusqu’à 50 caractéristiques (maximum) à un segment.</li><li>Faites glisser et déposez les caractéristiques pour créer de nouveaux groupes.</li><li>Caractéristiques de la Vue et groupes de caractéristiques dans un segment.</li><li>Définissez des critères de qualification avec des expressions booléennes, des opérateurs de comparaison et des paramètres de récence/fréquence.</li></ul> |
| Vue de code | Ouvre un environnement de développement qui vous permet de créer et de gérer des caractéristiques, des groupes et des exigences de qualification à l’aide du code plutôt que de l’interface visuelle. La vue de code est utile si vos segments : <ul><li>Contiennent plus de 50 caractéristiques dans un segment individuel. Remarque : Les segments sont limités à 5 000 caractéristiques (maximum).</li><li>Contient de nombreux groupes de caractéristiques.</li><li>Posséder des exigences de qualification complexes.</li></ul> |
| Outils | Permet de trouver des caractéristiques à ajouter à un segment. |
| Recommandations | Obtenez des recommandations en direct pour des caractéristiques similaires, à partir des caractéristiques propriétaires et des flux de données auxquels vous êtes abonné. [!UICONTROL Audience Marketplace] Ajouter ces recommandations à la règle de segmentation pour développer votre audience. Pour en savoir plus, consultez Recommandations [de](trait-recommendations.md)caractéristiques. |
| Recommandations pour le marché | Obtenez des recommandations en direct pour des caractéristiques similaires, à partir de flux de [!UICONTROL Audience Marketplace] données auxquels vous n’êtes pas abonné. Pour en savoir plus, consultez Recommandations [de](trait-recommendations.md)caractéristiques. |
| Données de taille de segment réelles et estimées | See [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Suppression de caractéristiques d’un segment {#remove-traits}

La gestion des caractéristiques de vos segments est un élément important de la viabilité des segments. Suivez ces étapes si vous devez supprimer des caractéristiques d’un segment.

Pour supprimer des caractéristiques d’un segment :

1. Accédez à Données **d’Audience > Segments**. Faites défiler la liste ou utilisez la fonction de recherche pour trouver le segment à utiliser.
2. Cliquez sur le nom du segment pour ouvrir l’écran des détails du segment.
3. Cliquez sur **Modifier** pour ouvrir le créateur de segments, puis sur **Caractéristiques** pour ouvrir le panneau Caractéristiques.
4. Passez la souris sur la caractéristique à supprimer, puis cliquez sur le X. Cette action supprime immédiatement la caractéristique de votre segment.

## Contrôles du créateur de segments : Section Mappages des destinations {#segment-builder-controls-destinations}

Dans [!UICONTROL Segment Builder]la [!UICONTROL Destinations Mapping] section facultative, vous pouvez envoyer des données de segment vers une destination tierce [!DNL cookie], [!DNL URL]ou de serveur à serveur. Pour ajouter une destination, recherchez (ou parcourez) une destination, fournissez des informations spécifiques à la destination, puis cliquez sur **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Conditions préalables

Renseignez les champs obligatoires des sections [!UICONTROL Basic Information] et [!UICONTROL Traits] . En outre, la destination doit déjà exister.

### Mappages des destinations Outils de recherche

Le **[!UICONTROL Destination Mappings]** panneau contient des outils de recherche, comme décrit dans le tableau ci-dessous.

| Type de recherche | Description |
|---|---|
| **Rechercher par nom de destination** | Permet de rechercher une destination spécifique par son nom. Pour effectuer une recherche, tapez un début. Le champ est renseigné automatiquement en fonction des termes recherchés. Cliquez **[!UICONTROL Add Destination]** une fois terminé. |
| **Parcourir toutes les destinations** | Parcourez une liste de *toutes les* destinations disponibles. Sélectionnez et ajoutez des destinations à votre segment à partir de la liste contextuelle. |

## Champs dans la fenêtre contextuelle Correspondances de destination {#fields-in-dest-mappings}

Dans [!UICONTROL Segment Builder], la boîte de dialogue [!UICONTROL Add Destination] s’affiche après avoir sélectionné une destination. Cette fenêtre affiche des informations statiques sur la destination et les champs qui varient en fonction du type de destination. Fournissez les informations requises dans les champs vides pour configurer un mappage de destination.

>[!NOTE]
>
>Les dates de publication sont facultatives. Lorsqu’elle est vide, la destination devient active et n’expire jamais.

<!-- r_add_mappings_pop.xml -->

### Champs de destination du cookie

Dans les [!UICONTROL Destination Mapping] champs, spécifiez les paires clé-valeur utilisées pour envoyer les données à la destination. Saisissez la clé dans le premier champ et les valeurs dans le second. La fenêtre contextuelle de destination du cookie peut se présenter comme suit :

![](assets/cookie_modal.PNG)

### Champs de destination d’URL

Dans les [!UICONTROL URL] champs et [!UICONTROL Secure URL] , spécifiez l’adresse standard complète ou sécurisée utilisée pour envoyer les données à la destination.

![](assets/url_modal.PNG)

### Champs de destination serveur à serveur

Dans le [!UICONTROL Destination Value] champ, indiquez la valeur (qui fait partie d’une paire clé-valeur) utilisée pour envoyer les données à la destination.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Créer une destination de cookie](../../features/destinations/create-cookie-destination.md)
>* [Création d’une destination d’URL](../../features/destinations/create-url-destination.md)

