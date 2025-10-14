---
description: Décrit les étapes obligatoires et facultatives qui vous permettent de créer un modèle algorithmique dans Model Builder.
keywords: Fonctionnement d’algo how
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

Décrit les étapes obligatoires et facultatives permettant de créer un [!UICONTROL Look-Alike Model].

## Section du créateur de modèles

[!UICONTROL Model Builder] comprend les sections [!UICONTROL Basic Information] et [!UICONTROL Configuration]. Pour créer un modèle, renseignez les champs requis dans ces deux sections. Enregistrez votre modèle pour démarrer l’algorithme. [!DNL Audience Manager] vous envoie une notification automatisée une fois la première exécution de données terminée. Après avoir reçu l’e-mail, vous pouvez accéder au [créateur de caractéristiques](../../features/traits/about-trait-builder.md) et créer des caractéristiques algorithmiques.

>[!NOTE]
>
>* Le processus de modélisation s’exécute une seule fois si vous créez un modèle et ne créez aucune caractéristique avec celui-ci.
>* Créer des modèles à partir de sources de données qui contiennent une quantité significative d’informations. Les modèles contenant des données insuffisantes s’exécutent, mais ne renvoient pas de résultats.
>* *Ne créez pas* modèles avec d’autres caractéristiques ou segments algorithmiques.
>* La notification électronique automatisée est envoyée une seule fois (après la première exécution des données).

## Création du modèle

Pour créer un [!UICONTROL Look-Alike Model], procédez comme suit :

1. Accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** et cliquez sur **[!UICONTROL Add New]** dans la section [!UICONTROL Look-Alike Modeling] .
   ![ajout-similaire](assets/look-alike-add.png)
1. Dans la section [&#x200B; Informations de base &#x200B;](../../features/algorithmic-models/create-model.md#basic-information)
   * Nommez le modèle.
   * *(Facultatif)* Fournissez une brève description du modèle.
   * Définissez le statut du modèle sur **[!UICONTROL Active]** ou **[!UICONTROL Inactive]**. Les modèles inactifs ne s’exécutent pas et ne produisent aucune donnée.
     ![look-alike-basic](assets/look-alike-basic.png)
1. Dans la section [Configuration](../../features/algorithmic-models/create-model.md#configuration) :
   * Cliquez sur **[!UICONTROL Browse All Traits]** ou **[!UICONTROL Browse All Segments]** pour sélectionner une caractéristique ou un segment en fonction duquel vous souhaitez effectuer le modèle. Recherchez des caractéristiques par nom, ID, description ou source de données. Cliquez sur un dossier lors de la recherche pour limiter les résultats à ce dossier et à ses sous-dossiers. Vous pouvez également filtrer les caractéristiques par type de caractéristique ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] et [!UICONTROL Algorithmic]) ou par type de population ([ID d’appareil](../../reference/ids-in-aam.md) et [ID sur plusieurs appareils](../../reference/ids-in-aam.md)).
     ![caractéristiques de navigation](assets/browse-traits.png)
   * Choisissez une période d’analyse de 30, 60 ou 90 jours. Cette option permet de définir une période pour le modèle.
   * L’algorithme [!UICONTROL TraitWeight] est sélectionné par défaut.
   * Sélectionnez une source de données dans la liste [!UICONTROL Available Data].
   * Cliquez sur **[!UICONTROL Save]** lorsque vous avez terminé.
     ![configuration-similaire](assets/look-alike-configuration.png)

Regardez la vidéo ci-dessous pour un aperçu détaillé du fonctionnement des mesures inter-appareils.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=fr)

## Informations de base pour les modèles algorithmiques {#basic-information}

<!-- r_model_basic.xml -->

Dans [!UICONTROL Model Builder], les paramètres [!UICONTROL Basic Information] vous permettent de créer des modèles ou de modifier des modèles existants. Pour créer un nouveau modèle, donnez un nom et passez aux paramètres [!UICONTROL Configuration]. Le champ de description est facultatif.

| Champ | Description |
|---|---|
| **[!UICONTROL Name]** | Donnez à votre modèle un nom court et logique qui décrit sa fonction ou son objectif. Évitez les abréviations, les caractères spéciaux et les accents. |
| **[!UICONTROL Description]** | Un champ pour des informations descriptives supplémentaires sur le modèle. |
| **[!UICONTROL Status]** | Active ou désactive le modèle (actif par défaut). |

## Configuration {#configuration}

Dans [!UICONTROL Model Builder], la section [!UICONTROL Configuration] vous permet d’ajouter des caractéristiques ou des segments au modèle. Dans cette section, sélectionnez une caractéristique ou un segment de ligne de base, une période de recherche en amont et les données de vos sources de données propriétaires et tierces.

<!-- r_model_configuration.xml -->

### Conditions préalables

Renseignez d’abord les champs obligatoires de la section [!UICONTROL Basic Information] .

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
   <td colname="col2"> <p>Cliquez sur le bouton de caractéristique ou de segment pour afficher la liste de toutes vos caractéristiques ou de tous vos segments. Le segment ou la caractéristique sélectionné devient la ligne de base que les algorithmes système utilisent pour la modélisation. </p> <p> <p><b>Remarque </b> : sélectionnez une caractéristique intégrée, une caractéristique basée sur une règle ou un segment comme ligne de base. Sinon, vos modèles ne s’exécuteront pas. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionner la période de recherche en amont (2)</b> </p> </td> 
   <td colname="col2"> <p>Définit une période pour le modèle. En fonction de votre sélection, l’algorithme inclut et évalue les données des 30, 60 ou 90 jours précédents. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Sélectionner l’algorithme (3)</b> </p> </td> 
   <td colname="col2"> <p>Actuellement, Model Builder fonctionne uniquement avec notre algorithme propriétaire <span class="keyword"> Trait Weight</span>. <span class="keyword"> Audience Manager</span> peut ajouter d’autres fonctions algorithmiques dans les versions ultérieures. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Sélection des données de modèle à partir de la Source de données (4)</b> </p> </td> 
   <td colname="col2"> <p>Permet de sélectionner les sources de données propriétaires et tierces à utiliser dans le modèle. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exclusions (5)</b> </p> </td> 
   <td colname="col2"> <p>Vous pouvez exclure des caractéristiques des sources de données que vous avez sélectionnées pour la modélisation. Utilisez la liste <span class="wintitle"> exclusions </span> et lisez <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Modèles algorithmiques : Exclusion de caractéristique </a> pour en savoir plus. </p> </td>
  </tr> 
 </tbody>
</table>

Regardez la vidéo ci-dessous pour savoir comment créer un modèle similaire propriétaire, afin que vous puissiez trouver davantage de vos propres visiteurs qui ressemblent à vos convertisseurs.

>[!VIDEO](https://video.tv.adobe.com/v/328091?captions=fre_fr)

>[!MORELIKETHIS]
>
>* [Présentation de TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)
