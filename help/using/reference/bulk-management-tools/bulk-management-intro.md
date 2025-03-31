---
description: Les outils de gestion en bloc vous permettent de créer et de gérer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour utiliser les sources de données, les signaux dérivés, les destinations, les dossiers, les segments et les caractéristiques.
keywords: baaam;BAAAM;télécharger baaam
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: Prise En Main De La Gestion En Bloc
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 0c9c333f4e8d6d416d497f336e3e447e2e251d47
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 1%

---


# Prise En Main De La Gestion En Bloc{#getting-started-with-bulk-management}

Les [!DNL Bulk Management Tools] vous permettent de créer et de gérer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser [!DNL Bulk Management Tools] pour travailler avec [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments] et [!UICONTROL traits].

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>Les [autorisations de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans l’interface utilisateur [!DNL Audience Manager] sont respectées dans la [!UICONTROL Bulk Management Tools].

## Présentation {#overview}

Cette fonctionnalité utilise une feuille de calcul [!DNL Microsoft Excel] avec des macros qui effectuent des appels authentifiés sécurisés vers les API [!DNL Audience Manager]. L’API fournit les méthodes et services qui vous permettent d’apporter des modifications en bloc. Vous n’avez pas besoin de savoir comment coder ou utiliser nos API pour l’utiliser. La feuille de calcul contient des en-têtes de colonne et des onglets qui exécutent des fonctions de modification en bloc spécifiques. Pour apporter des modifications en bloc, ajoutez simplement les en-têtes prédéfinis à des feuilles de calcul spécifiques, fournissez les informations à modifier en bloc, puis cliquez sur un bouton d’action. La feuille de calcul et les API effectuent le reste du travail à votre place.

## Téléchargement {#download}

Téléchargez la dernière feuille de calcul **[ici](assets/BAAAM_V2_20210609.xlsm)** (dernière mise à jour : juin 2021).

## Conditions préalables {#prereqs}

Pour utiliser le [!DNL Bulk Management Tools], vous avez besoin des éléments suivants :

* Votre identifiant de connexion [!DNL Experience Cloud]. En tant que client, vous devriez déjà disposer de ces informations d’identification.
* La feuille de calcul [!DNL Bulk Management Tools]. [Téléchargez la feuille de calcul](assets/BAAAM_V2_20210609.xlsm) pour obtenir la dernière version.
* [!DNL Microsoft Excel] s’exécutant sur des [!DNL Microsoft Windows] 64 bits. Nous vous recommandons d’utiliser la dernière version de [!DNL Microsoft Excel]. Les outils de gestion en bloc ne sont pas pris en charge sur [!DNL macOS].
* Lors de l&#39;ouverture de la feuille de calcul, vous devez **Activer les macros** pour que le [!DNL Bulk Management Tools] fonctionne.

## Exigences et options d’authentification {#auth-reqs}

Les modifications en bloc nécessitent une authentification. Avant d’effectuer toute action, vous devez vous connecter. Comme la feuille de calcul effectue des appels API, vous devez la configurer pour l’authentifier dans votre compte utilisateur.

**Exigences d’authentification des API**

La deuxième version du [!DNL Bulk Management Tools], publiée en octobre 2019, simplifie le processus d’authentification. Les étapes d’authentification de cette version sont décrites ci-dessous :

1. Ouvrez la feuille de calcul et accédez à la feuille de **[!UICONTROL Config]**.
2. Suivez les étapes décrites dans la fiche.
   ![](assets/baaam-authentication.png)
3. Une fois les étapes terminées, vous êtes autorisé à apporter des modifications en bloc.

Lors de la modification en bloc, vous devrez toujours confirmer que vous êtes autorisé à apporter les modifications, mais l’authentification de l’API est automatique.

**Options d’authentification de domaine**

L’authentification de domaine vous donne la possibilité de tester les requêtes en bloc ou de les appliquer directement à votre compte de production. Apporter des modifications en bloc à l’environnement bêta n’aura aucune incidence sur votre compte de production. Les modifications de production prennent effet immédiatement. La feuille de gestion en masse vous permet de travailler dans les environnements suivants :

* Beta
* Production

## Actions et opérations {#actions-ops}

La feuille de calcul [!UICONTROL Bulk Management Tools] se compose de boutons d’authentification, d’onglets d’action, de boutons d’action et d’un onglet **[!UICONTROL Headers]**. L’onglet **[!UICONTROL Headers]** contient les en-têtes de colonne préformatés utilisés par les onglets d’actions. Les onglets d’action contiennent des macros qui effectuent l’opération en bloc sélectionnée. Pour effectuer une opération en bloc, copiez un ensemble d’en-têtes dans l’onglet d’action approprié, saisissez les données d’en-tête, puis cliquez sur un bouton d’action.

Après l’[authentification](#auth-reqs), cliquez sur un bouton d’action pour commencer.

![](assets/baaam-worksheet.png)

Le tableau ci-dessous répertorie les opérations que vous pouvez effectuer et les éléments que vous pouvez manipuler avec les feuilles de calcul [!UICONTROL Bulk Management Tools].

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Actions </th> 
   <th colname="col2" class="entry"> Objets </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Les actions en bloc s’affichent dans les onglets au bas de la feuille de calcul et comprennent les éléments suivants : </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Demandes </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Mise à jour </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Créez     </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimation </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Supprimer </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Les objets que vous pouvez modifier en bloc se trouvent sous l’onglet En-têtes </span></b> <b><span class="uicontrol"> et comprennent : </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> des sources de données</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> signaux dérivés</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> des destinations</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> modèles </a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Dossiers de caractéristiques </a> et de segments </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> des segments</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> caractéristiques </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple d’opération en bloc**

À titre d’exemple, examinons comment créer plusieurs caractéristiques à la fois. Pour créer plusieurs caractéristiques dans une opération en bloc, vous devez :

1. Cliquez sur l’onglet **[!UICONTROL Headers]** et copiez tous les libellés sous l’option [!UICONTROL Create a Trait] .
2. Cliquez sur l’onglet **[!UICONTROL Create]** et collez les libellés en commençant par la ligne 1, colonne A.
3. Fournissez des informations relatives à chaque en-tête de colonne, puis cliquez sur **[!UICONTROL Create Traits]**. Cette action vous invite à confirmer votre authentification. Votre tâche en bloc s’exécute après avoir confirmé votre authentification. Recherchez une notification de statut de tâche dans le coin inférieur gauche de la feuille de calcul.


>[!NOTE]
>
>Lorsque vous travaillez avec des requêtes volumineuses, la feuille de calcul peut ne plus répondre et sembler inactive. Dans ce cas, ne vous en mêlez pas. La feuille de calcul devient réactive une fois la demande en bloc terminée. Si la feuille de calcul ne répond pas pendant une longue période, reportez-vous à la [section de dépannage](../../reference/bulk-management-tools/bulk-troubleshooting.md).
