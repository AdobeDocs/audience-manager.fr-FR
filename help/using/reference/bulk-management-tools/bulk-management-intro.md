---
description: Les outils de gestion en bloc vous permettent de créer et gérer simultanément plusieurs objets avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour utiliser les sources de données, les signaux dérivés, les destinations, les dossiers, les segments et les caractéristiques.
keywords: baaam ; BAAAM
seo-description: Les outils de gestion en bloc vous permettent de créer et gérer simultanément plusieurs objets avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour utiliser les sources de données, les signaux dérivés, les destinations, les dossiers, les segments et les caractéristiques.
seo-title: Prise en main de la gestion en bloc
solution: Audience Manager
title: Prise en main de la gestion en bloc
uuid: 4 bc 6 ae 0 a -315 c -4 ce 7-a 68 e-cc 0 c 6 c 6 aa 2 f 1
translation-type: tm+mt
source-git-commit: 349cc962c993b361e2dea00ba693337391b87e5e

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

Les outils de gestion en bloc vous permettent de créer et gérer simultanément plusieurs objets avec une seule opération. Vous pouvez utiliser les outils de gestion en bloc pour utiliser les sources de données, les signaux dérivés, les destinations, les dossiers, les segments et les caractéristiques.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l&#39;interface utilisateur sont respectées dans l&#39; [!UICONTROL Bulk Management Tools]interface.

## Aperçu {#overview}

This feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs. L&#39;API fournit les méthodes et les services qui vous permettent d&#39;effectuer des modifications en bloc. Vous n&#39;avez pas besoin de savoir comment coder ou utiliser nos API pour l&#39;utiliser. La feuille de calcul contient des en-têtes et des onglets de colonne qui effectuent des modifications de masse spécifiques. Pour apporter des modifications en masse, tout ce que vous faites consiste à ajouter les en-têtes prédéfinis à des feuilles de calcul spécifiques, à fournir les informations que vous souhaitez modifier en bloc, puis à cliquer sur un bouton d&#39;action. La feuille de calcul et les API font le reste du travail.

## Conditions préalables {#prereqs}

To use the [!DNL Bulk Management Tools], you need the following:

* Your [!DNL Audience Manager] user name and password. En tant que client, vous devez posséder déjà ces informations d&#39;identification.
* ID client d&#39;API et clé secrète. Votre gestionnaire de compte peut vous fournir ces informations.
* [!UICONTROL Bulk Management Tools] Feuille de calcul. **[Téléchargez la feuille de calcul](assets/BAAAM_August_2018.xlsm)** pour obtenir la dernière version.

* Microsoft Excel running on [!DNL Windows] or in a [!DNL Microsoft Windows] virtual machine running on [!DNL macOS X]. You must use 32-bit Excel for the [!UICONTROL Bulk Management Tools] to work.

## Actions and operations {#actions-ops}

The [!UICONTROL Bulk Management Tools] worksheet consists of action tabs, action buttons, and a **[!UICONTROL Headers]** tab. **[!UICONTROL Headers]** L&#39;onglet contient les en-têtes de colonne préformatés utilisés par les onglets d&#39;action. Les onglets d&#39;action contiennent des macros qui exécutent l&#39;opération en bloc sélectionnée. Pour effectuer une opération en bloc, copiez un jeu d&#39;en-têtes dans l&#39;onglet d&#39;action approprié, saisissez les données d&#39;en-tête, puis cliquez sur un bouton d&#39;action.

Ouvrez la feuille de calcul et cliquez sur un bouton d&#39;action pour commencer.

![](assets/bamwrkbk.png)

The table below lists the operations you can perform and items you can manipulate with the [!UICONTROL Bulk Management Tools] worksheets.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Actions </th> 
   <th colname="col2" class="entry"> Objets </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Les actions en masse apparaissent dans les onglets au bas de la feuille de calcul et incluent : </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Demandes </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Mise à jour </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Créez     </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Estimation </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Supprimer </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>The objects you can change in bulk are located under the <b><span class="uicontrol"> Headers</span></b> tab and include: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Sources de données</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Signaux dérivés</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Destinations</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Dossiers de caractéristiques</a> et dossiers de segment </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segments</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Caractéristiques</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exemple d&#39;opération en bloc**

Par exemple, examinons comment créer plusieurs caractéristiques simultanément. Pour créer plusieurs caractéristiques dans une opération en bloc, vous procédez comme suit :

1. Click the **[!UICONTROL Headers]** tab and copy all the labels under the [!UICONTROL Create a Trait] option.

2. Click the **[!UICONTROL Create]** tab and paste the labels starting in row 1, column A.
3. Provide information related to each column header and click **[!UICONTROL Create Traits]**. Cette action vous invite à vous connecter. Your bulk job runs after you successfully authenticate (see the [authentication requirements](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) below). Cochez l&#39;angle inférieur gauche de la feuille de calcul pour obtenir une notification d&#39;état de tâche.

>[!NOTE]
>
>Lorsque vous utilisez des requêtes volumineuses, la feuille de calcul risque de ne plus répondre et semble inactive. Dans ce cas, laissez-le seul. La feuille de calcul devient réactive lorsque la demande en masse est terminée. If the worksheet does not respond for a long period of time, see the [troubleshooting section](../../reference/bulk-management-tools/bulk-troubleshooting.md).

## Authentication requirements and options {#auth-reqs}

Les modifications en masse nécessitent une authentification. Lorsque vous sélectionnez une action, la feuille de calcul vous invite à vous connecter. Comme la feuille de calcul effectue les appels d&#39;API, vous devez la configurer pour lire votre clé secrète. And, the **[!UICONTROL Domain]** field lets you make bulk changes in a staging/test environment or against your live, production account.

![](assets/bamauth.png)

**Conditions requises pour l&#39;authentification des API**

Pour configurer l&#39;authentification de l&#39;API, vous devez :

* Copiez et enregistrez la clé secrète dans un fichier texte (.txt).
* Nommez le fichier texte avec votre ID client API. Par exemple, si votre ID client est « Utilisateur en masse », enregistrez la clé dans un fichier intitulé « Bulk-User. txt ».
* Enregistrez la clé secrète et la feuille de calcul dans le même dossier.

Lors de modifications en masse, vous devrez toujours saisir un nom d&#39;utilisateur, un mot de passe, un ID de client et un domaine, mais l&#39;authentification de l&#39;API est automatique.

**Options d&#39;authentification de domaine**

L&#39;authentification par domaine permet de tester les requêtes en masse ou de les appliquer directement à votre compte de production. La modification en bloc de l&#39;environnement de test n&#39;affecte pas votre compte de production. Les modifications de production sont effectives immédiatement. The **[!UICONTROL Domain]** field accepts the following addresses, depending on the environment you want to work in:

* Tests: `api-beta.demdex.com`
* Production: `api.demdex.com`

>[!MORE_ LIKE_ THIS]
>
>* [Télécharger la feuille de calcul de gestion en bloc](assets/BAAAM_August_2018.xlsm)

