---
description: Les outils de gestion en bloc vous permettent de créer et de gérer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour travailler avec des sources de données, des signaux dérivés, des destinations, des dossiers, des segments et des caractéristiques.
keywords: baam;BAAAM;télécharger la base
seo-description: Les outils de gestion en bloc vous permettent de créer et de gérer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour travailler avec des sources de données, des signaux dérivés, des destinations, des dossiers, des segments et des caractéristiques.
seo-title: Prise en main de la gestion en bloc
solution: Audience Manager
title: Prise en main de la gestion en bloc
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 4%

---

# Prise en main de la gestion en bloc{#getting-started-with-bulk-management}

La fonction [!DNL Bulk Management Tools] vous permet de créer et de gérer plusieurs objets à la fois avec une seule opération. Vous pouvez utiliser [!DNL Bulk Management Tools] pour utiliser [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments] et [!UICONTROL traits].

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[Les ](../../features/administration/administration-overview.md) autorisations de groupe RBAC attribuées dans l’interface  [!DNL Audience Manager] utilisateur sont honorées dans le  [!UICONTROL Bulk Management Tools].

## Présentation {#overview}

Cette fonctionnalité utilise une feuille de calcul [!DNL Microsoft Excel] avec des macros qui effectuent des appels sécurisés et authentifiés aux API [!DNL Audience Manager]. L’API fournit les méthodes et services qui vous permettent d’apporter des modifications en bloc. Vous n’avez pas besoin de savoir comment coder ou utiliser nos API pour l’utiliser. La feuille de calcul contient des en-têtes de colonne et des onglets qui exécutent des fonctions de modification en masse spécifiques. Pour effectuer des modifications en bloc, vous devez simplement ajouter les en-têtes prédéfinis à des feuilles de calcul spécifiques, fournir les informations que vous souhaitez modifier en bloc, puis cliquer sur un bouton d’action. La feuille de calcul et les API effectuent le reste du travail pour vous.

## Télécharger {#download}

Téléchargez la dernière feuille de calcul **[ici](assets/BAAAM_V2_20200502.xlsm)**.

## Conditions préalables {#prereqs}

Pour utiliser la balise [!DNL Bulk Management Tools], vous avez besoin des éléments suivants :

* Votre [!DNL Experience Cloud] connexion. En tant que client, vous devriez déjà disposer de ces informations d’identification.
* Feuille de calcul [!DNL Bulk Management Tools]. [Téléchargez la ](assets/BAAAM_V2_20200502.xlsm) feuille de calcul pour obtenir la dernière version.
* [!DNL Microsoft Excel] s’exécutant sur  [!DNL macOS] ou 64 bits  [!DNL Microsoft Windows]. Nous vous recommandons d’utiliser la dernière version de [!DNL Microsoft Excel].
* Lors de l’ouverture de la feuille de calcul, vous devez **activer les macros** pour que [!DNL Bulk Management Tools] fonctionne.

## Exigences et options d’authentification {#auth-reqs}

Les modifications en bloc nécessitent une authentification. Avant toute action, vous devez vous connecter. Étant donné que la feuille de calcul effectue des appels API, vous devez la configurer pour qu’elle s’authentifie dans votre compte utilisateur.

**Exigences d’authentification des API**

La deuxième version de [!DNL Bulk Management Tools], sortie en octobre 2019, simplifie le processus d’authentification. Les étapes d’authentification de cette version sont décrites ci-dessous :

1. Ouvrez la feuille de calcul et accédez à la **[!UICONTROL Config]** feuille.
2. Suivez les étapes décrites dans la feuille.
   ![](assets/baaam-authentication.png)
3. Une fois les étapes terminées, vous êtes autorisé à effectuer des modifications en bloc.

Lorsque vous effectuez des modifications en bloc, vous devrez toujours confirmer que vous êtes autorisé à effectuer les modifications, mais l’authentification API est automatique.

**Options d’authentification de domaine**

L’authentification de domaine vous permet de tester les demandes en bloc ou de les appliquer directement à votre compte de production. Apporter des modifications en masse à l’environnement bêta n’affecte pas votre compte de production. Les modifications apportées à la production prennent effet immédiatement. La feuille de gestion en bloc vous permet de travailler dans les environnements suivants :

* bêta
* Production

## Actions et opérations {#actions-ops}

La feuille de calcul [!UICONTROL Bulk Management Tools] se compose de boutons d’authentification, d’onglets d’action, de boutons d’action et d’un onglet **[!UICONTROL Headers]**. L’onglet **[!UICONTROL Headers]** contient les en-têtes de colonne préformatés utilisés par les onglets d’action. Les onglets Action contiennent les macros qui exécutent l’opération en bloc sélectionnée. Pour effectuer une opération en bloc, vous copiez un ensemble d’en-têtes dans l’onglet d’action approprié, saisissez des données d’en-tête et cliquez sur un bouton d’action.

Après [l’authentification](#auth-reqs), cliquez sur un bouton d’action pour commencer.

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
   <td colname="col1"> <p>Les actions en bloc s’affichent dans des onglets au bas de la feuille de calcul et incluent : </p> <p> 
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
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md">Destinations </a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modèles</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Dossiers </a> de caractéristiques et dossiers de segments </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md">Segments </a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md">Caractéristiques </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple d’opération en bloc**

Prenons l’exemple de la création simultanée de plusieurs caractéristiques. Pour créer plusieurs caractéristiques dans une opération en bloc, procédez comme suit :

1. Cliquez sur l’onglet **[!UICONTROL Headers]** et copiez tous les libellés sous l’option [!UICONTROL Create a Trait].
2. Cliquez sur l’onglet **[!UICONTROL Create]** et collez les libellés commençant à la ligne 1, colonne A.
3. Indiquez les informations relatives à chaque en-tête de colonne et cliquez sur **[!UICONTROL Create Traits]**. Cette action vous invite à confirmer votre authentification. Votre tâche en masse s’exécute une fois que vous avez confirmé votre authentification. Vérifiez que la notification d’état d’une tâche s’affiche dans le coin inférieur gauche de la feuille de calcul.


>[!NOTE]
>
>Lorsque vous utilisez des requêtes volumineuses, la feuille de calcul peut ne plus répondre et apparaître inactive. Dans ce cas, laissez-la tranquille. La feuille de calcul devient réactive une fois la requête en bloc terminée. Si la feuille de calcul ne répond pas pendant une longue période, reportez-vous à la [section de dépannage](../../reference/bulk-management-tools/bulk-troubleshooting.md).
