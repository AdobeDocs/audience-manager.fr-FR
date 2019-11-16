---
description: Les outils de gestion en bloc vous permettent de créer et de gérer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour travailler avec des sources de données, des signaux dérivés, des destinations, des dossiers, des segments et des caractéristiques.
keywords: baaam;BAAAM
seo-description: Les outils de gestion en bloc vous permettent de créer et de gérer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour travailler avec des sources de données, des signaux dérivés, des destinations, des dossiers, des segments et des caractéristiques.
seo-title: Prise En Main De La Gestion En Bloc
solution: Audience Manager
title: Prise En Main De La Gestion En Bloc
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
translation-type: tm+mt
source-git-commit: 963d765845dae6abe107be04d5aae2c49e7fb575

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

Les outils de gestion en bloc vous permettent de créer et de gérer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour travailler avec des sources de données, des signaux dérivés, des destinations, des dossiers, des modèles, des segments et des caractéristiques.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>Les variables ne [!UICONTROL Bulk Management Tools] sont pas *prises en charge par* [!DNL Audience Manager]. Cet outil est fourni à titre pratique et à titre de courtoisie seulement. Pour les modifications en masse, nous vous recommandons de travailler avec les API [Audience Manager](../../api/rest-api-main/aam-api-getting-started.md) à la place. [Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans [!UICONTROL Bulk Management Tools].

## Aperçu {#overview}

Cette fonctionnalité utilise une feuille de calcul Microsoft Excel avec des macros qui effectuent des appels sécurisés et authentifiés aux [!DNL Audience Manager] API. L’API fournit les méthodes et les services qui vous permettent d’effectuer des modifications en bloc. Vous n'avez pas besoin de savoir coder ou utiliser nos API pour l'utiliser. La feuille de calcul contient des en-têtes de colonne et des onglets qui exécutent des fonctions de modification en masse spécifiques. Pour effectuer des modifications en masse, vous devez simplement ajouter les en-têtes prédéfinis à des feuilles de calcul spécifiques, fournir les informations que vous souhaitez modifier en bloc, puis cliquer sur un bouton d’action. La feuille de calcul et les API font le reste du travail pour vous.

## Téléchargement {#download}

Téléchargez la dernière feuille de calcul **[ici](assets/BAAAM_V2_20191015.xlsm)**.

## Conditions préalables {#prereqs}

Pour utiliser le [!DNL Bulk Management Tools], vous devez disposer des éléments suivants :

* Votre [!DNL Experience Cloud] connexion. En tant que client, vous devez déjà disposer de ces informations d’identification.
* La [!DNL Bulk Management Tools] feuille de calcul. [Téléchargez la feuille](assets/BAAAM_V2_20191015.xlsm) de calcul pour obtenir la dernière version.
* Microsoft Excel s'exécutant sur [!DNL macOS] ou 64 bits [!DNL Microsoft Windows].
* Lors de l’ouverture de la feuille de calcul, vous devez **activer les macros** pour que la [!DNL Bulk Management Tools] feuille de calcul fonctionne.

## Exigences et options d’authentification {#auth-reqs}

Les modifications en masse nécessitent une authentification. Avant d’effectuer une action, vous devez vous connecter. Comme la feuille de calcul effectue des appels d’API, vous devez la configurer pour l’authentifier dans votre compte utilisateur.

**Exigences d’authentification API**

La deuxième version des outils de gestion en bloc, publiée en octobre 2019, simplifie le processus d’authentification. Les étapes d’authentification de cette version sont décrites ci-dessous :

1. Ouvrez la feuille de calcul et accédez à la **feuille de configuration** .
2. Suivez les étapes décrites dans la feuille.
   ![](assets/baaam-authentication.png)
3. Une fois les étapes terminées, vous êtes autorisé à effectuer des modifications en masse.

Lorsque vous apportez des modifications en masse, vous devrez quand même confirmer que vous êtes autorisé à effectuer les modifications, mais l’authentification API est automatique.

**Options d’authentification de domaine**

L’authentification de domaine vous permet de tester les requêtes en masse ou de les appliquer directement à votre compte de production. Les modifications en masse apportées à l’environnement bêta n’affecteront pas votre compte de production. Les modifications apportées à la production entrent en vigueur immédiatement. La feuille de gestion en bloc vous permet de travailler dans les environnements suivants :

* bêta
* Production

## Actions et opérations {#actions-ops}

La [!UICONTROL Bulk Management Tools] feuille de calcul se compose de boutons d’authentification, d’onglets d’action, de boutons d’action et d’un **[!UICONTROL Headers]** onglet. L’ **[!UICONTROL Headers]** onglet contient les en-têtes de colonne préformatés utilisés par les onglets d’action. Les onglets d’action contiennent des macros qui effectuent l’opération en bloc sélectionnée. Pour effectuer une opération en bloc, vous copiez un ensemble d’en-têtes dans l’onglet d’action approprié, saisissez les données d’en-tête, puis cliquez sur un bouton d’action.

Après [l’authentification](#auth-reqs), cliquez sur un bouton d’action pour commencer.

![](assets/baaam-worksheet.png)

Le tableau ci-dessous répertorie les opérations que vous pouvez effectuer et les éléments que vous pouvez manipuler avec les [!UICONTROL Bulk Management Tools] feuilles de calcul.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Actions </th> 
   <th colname="col2" class="entry"> Objets </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Les actions en bloc apparaissent dans les onglets au bas de la feuille de calcul et incluent : </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Demandes </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Mise à jour </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Créez     </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimation </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Supprimer </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Les objets que vous pouvez modifier en bloc se trouvent sous l’onglet <b><span class="uicontrol"> En-têtes</span></b> et comprennent : </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Sources de données</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Signaux dérivés</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Destinations</a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modèles</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Dossiers</a> de caractéristiques et dossiers de segments </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segments</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Caractéristiques</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple d'opération en bloc**

Prenons l'exemple de la création simultanée de plusieurs caractéristiques. Pour créer plusieurs caractéristiques dans une opération en bloc, procédez comme suit :

1. Cliquez sur l’ **[!UICONTROL Headers]** onglet et copiez toutes les étiquettes sous l’ [!UICONTROL Create a Trait] option.
2. Cliquez sur l’ **[!UICONTROL Create]** onglet et collez les étiquettes en commençant par la ligne 1, colonne A.
3. Fournissez des informations relatives à chaque en-tête de colonne et cliquez sur **[!UICONTROL Create Traits]**. Cette action vous invite à confirmer votre authentification. Votre tâche en masse s’exécute une fois que vous avez confirmé votre authentification. Vérifiez que le coin inférieur gauche de la feuille de calcul contient une notification d'état de tâche.


>[!NOTE]
>
>Lorsque vous travaillez avec des requêtes volumineuses, la feuille de calcul peut ne plus répondre et apparaître inactive. Dans ces cas, laissez-le tranquille. La feuille de calcul sera réactive une fois la demande en masse terminée. Si la feuille de calcul ne répond pas pendant une longue période, reportez-vous à la section [](../../reference/bulk-management-tools/bulk-troubleshooting.md)Dépannage.

