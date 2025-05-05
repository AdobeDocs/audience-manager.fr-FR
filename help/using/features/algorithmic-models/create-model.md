---
description: Décrit les étapes requises et facultatives qui vous permettent de créer un modèle algorithmique dans le créateur de modèles.
keywords: fonctionnement d'algo
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: Création d’un modèle algorithmique
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Création d’un modèle analogue {#create-an-algorithmic-model}

Décrit les étapes requises et facultatives qui vous permettent de créer un [!UICONTROL Look-Alike Model].

## Section du créateur de modèles

[!UICONTROL Model Builder] se compose des sections [!UICONTROL Basic Information] et [!UICONTROL Configuration] . Pour créer un modèle, renseignez les champs obligatoires de ces deux sections. Enregistrez votre modèle pour démarrer l’algorithme. [!DNL Audience Manager] vous envoie une notification automatisée une fois la première exécution des données terminée. Une fois que vous avez reçu l’e-mail, vous pouvez accéder à [Trait Builder](../../features/traits/about-trait-builder.md) et créer des caractéristiques algorithmiques.

>[!NOTE]
>
>* Le processus de modélisation ne s’exécute qu’une seule fois si vous créez un modèle et n’en créez aucune caractéristique.
>* Créez des modèles à partir de sources de données qui contiennent une quantité significative d’informations. Les modèles avec des données insuffisantes s’exécuteront, mais ils ne renverront pas de résultats.
>* *Ne créez pas* de modèles avec d’autres caractéristiques ou segments algorithmiques.
>* La notification électronique automatisée est envoyée une seule fois (après la première exécution des données).

## Création du modèle

Suivez les étapes ci-dessous pour créer un [!UICONTROL Look-Alike Model] :

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** et cliquez sur **[!UICONTROL Add New]** dans la section [!UICONTROL Look-Alike Modeling] .
   ![look-alike-add](assets/look-alike-add.png)
1. Dans la section [Informations de base](../../features/algorithmic-models/create-model.md#basic-information)
   * Nommez le modèle.
   * *(Facultatif)* Fournissez une brève description du modèle.
   * Définissez l’état du modèle sur **[!UICONTROL Active]** ou **[!UICONTROL Inactive]**. Les modèles inactifs ne s’exécuteront pas et ne produiront aucune donnée.

     ![look-alike-basic](assets/look-alike-basic.png)
1. Dans la section [Configuration](../../features/algorithmic-models/create-model.md#configuration) :
   * Cliquez sur **[!UICONTROL Browse All Traits]** ou **[!UICONTROL Browse All Segments]** pour sélectionner une caractéristique ou un segment à modéliser. Recherchez des caractéristiques par nom, identifiant, description ou source de données. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer les caractéristiques par type de caractéristique ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] et [!UICONTROL Algorithmic]) ou type de population ([ID de périphérique](../../reference/ids-in-aam.md) et [ID multi-appareils](../../reference/ids-in-aam.md)).

     ![browse-traits](assets/browse-traits.png)
   * Choisissez une période de recherche arrière de 30, 60 ou 90 jours. Cela définit une période pour le modèle.
   * L’algorithme [!UICONTROL TraitWeight] est sélectionné par défaut.
   * Sélectionnez une source de données dans la liste [!UICONTROL Available Data].
   * Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.

     ![configuration analogue](assets/look-alike-configuration.png)

Regardez la vidéo ci-dessous pour une vue détaillée du fonctionnement des mesures sur plusieurs appareils.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=fr)

## Informations de base des modèles algorithmiques {#basic-information}

<!-- r_model_basic.xml -->

Dans [!UICONTROL Model Builder], les paramètres [!UICONTROL Basic Information] vous permettent de créer ou de modifier des modèles existants. Pour créer un modèle, attribuez un nom et passez aux paramètres [!UICONTROL Configuration]. Le champ de description est facultatif.

| Champ | Description |
|---|---|
| **[!UICONTROL Name]** | Donnez à votre modèle un nom court et logique qui décrit sa fonction ou son objectif. Évitez les abréviations, les caractères spéciaux et les accents. |
| **[!UICONTROL Description]** | Champ permettant d’obtenir des informations descriptives supplémentaires sur le modèle. |
| **[!UICONTROL Status]** | Active ou désactive le modèle (actif par défaut). |

## Configuration {#configuration}

Dans [!UICONTROL Model Builder], la section [!UICONTROL Configuration] vous permet d’ajouter des caractéristiques ou des segments au modèle. Dans cette section, sélectionnez une caractéristique ou un segment de base, une période de recherche en amont et des données provenant de vos sources de données propriétaires et tierces.

<!-- r_model_configuration.xml -->

### Conditions préalables

Renseignez d’abord les champs requis de la section [!UICONTROL Basic Information].

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Champ </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionner une caractéristique ou un segment de ligne de base (1)</b> </p> </td> 
   <td colname="col2"> <p>Cliquez sur le bouton caractéristique ou segment pour afficher la liste de toutes vos caractéristiques ou segments. Votre segment ou caractéristique sélectionné devient la ligne de base que les algorithmes système utilisent pour la modélisation. </p> <p> <p><b>Remarque</b> : sélectionnez une caractéristique intégrée, une caractéristique basée sur des règles ou un segment comme ligne de base. Sinon, vos modèles ne s’exécuteront pas. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionnez Période de recherche en amont (2)</b> </p> </td> 
   <td colname="col2"> <p>Définit une période pour le modèle. Selon votre sélection, l’algorithme inclut et évalue les données des 30, 60 ou 90 jours précédents. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionner l’algorithme (3)</b> </p> </td> 
   <td colname="col2"> <p>Actuellement, Model Builder fonctionne uniquement avec notre algorithme propriétaire <span class="keyword"> Trait Weight</span>. <span class="keyword"> Audience Manager</span> peut ajouter d’autres fonctions algorithmiques dans les versions suivantes. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Sélectionner des données de modèle à partir de Data Source (4)</b> </p> </td> 
   <td colname="col2"> <p>Permet de sélectionner les sources de données propriétaires et tierces que vous souhaitez utiliser dans le modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions (5)</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez exclure des caractéristiques des sources de données que vous avez sélectionnées pour la modélisation. Utilisez la liste <span class="wintitle"> Exclusions</span> et lisez <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Modèles algorithmiques : Exclusion de caractéristiques</a> pour en savoir plus. </p> </td>
  </tr> 
 </tbody>
</table>

Regardez la vidéo ci-dessous pour savoir comment créer un modèle analogue propriétaire, afin que vous puissiez trouver d’autres visiteurs qui ressemblent à vos convertisseurs.

>[!VIDEO](https://video.tv.adobe.com/v/328091?captions=fre_fr)

>[!MORELIKETHIS]
>
>* [Comprendre TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)
