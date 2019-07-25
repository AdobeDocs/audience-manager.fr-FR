---
description: La qualification des caractéristiques ou la concrétisation des caractéristiques est traitée différemment dans Audience Manager, selon le type de caractéristique. Pour plus d'informations sur la qualification des caractéristiques, reportez-vous au tableau ci-dessous.
keywords: qualification des caractéristiques ; la réalisation des caractéristiques ; Realizations de caractéristiques uniques ; UTR ; Population totale de caractéristiques ; TTP
seo-description: La qualification des caractéristiques ou la concrétisation des caractéristiques est traitée différemment dans Audience Manager, selon le type de caractéristique. Pour plus d'informations sur la qualification des caractéristiques, reportez-vous au tableau ci-dessous.
seo-title: Référence de qualification des traits
solution: Audience Manager
title: Référence de qualification des traits
uuid: 07 e 0 a 639-2 fb 2-45 d 8-bad 7-10 fb 46 b 08 ba 9
translation-type: tm+mt
source-git-commit: 0921cd69ffcb75768acee99685b0d80b8bef0be6

---


# Référence de qualification des traits {#trait-qualification-reference}

La qualification des caractéristiques ou la concrétisation des caractéristiques est traitée différemment dans Audience Manager, selon le type de caractéristique. Pour plus d'informations sur la qualification des caractéristiques, reportez-vous au tableau ci-dessous.

## Trait Qualification by Trait Type {#trait-type}

<table id="table_14CD705F376B44EEA9A6C011984356F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de caractéristique </th> 
   <th colname="col2" class="entry"> Critères de qualification </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques basées sur des règles </p> </td> 
   <td colname="col2"> <p>La qualification des caractéristiques se produit en temps réel, car les utilisateurs remplissent une caractéristique dans leur navigateur. Your users will start qualifying for a rule-based trait approximately 4 hours after you <a href="../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits"> create the trait</a> in the UI. </p> <p>Rule-based traits allow you to use <a href="../../features/segments/recency-and-frequency.md"> recency and frequency</a> controls for ad frequency capping and other use cases. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques intégrées </p> </td> 
   <td colname="col2"> <p>Trait qualification happens after an inbound file is processed, i.e. the inbound file is <a href="../../faq/faq-inbound-data-ingestion.md"> imported into Audience Manager</a> and that is when the trait qualification happens. </p> <p> Pour les caractéristiques intégrées, le nombre maximal de qualifications pour un profil utilisateur est 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques algorithmiques </p> </td> 
   <td colname="col2"> <p>Pour les caractéristiques algorithmiques, le nombre maximal de qualifications pour un profil utilisateur est 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractéristiques du dossier </p> </td> 
   <td colname="col2"> <p>Une caractéristique de dossier additionne les caractéristiques des caractéristiques des caractéristiques qu'elle contient. </p> <p>Read <a href="../../features/traits/about-folder-traits.md"> Folder Traits: About</a> for more information. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Caractéristiques de public actives et caractéristiques synchronisées Source de données </p> </td> 
   <td colname="col2"> <p>An <span class="wintitle"> Active Audience</span> trait contains all of the devices under management in your <span class="wintitle"> Audience Manager</span> account. </p> <p><span class="wintitle"> Les caractéristiques synchronisées Source de données</span> effectuent le suivi de tous les utilisateurs associés à une source de données. </p> <p>Read more about <a href="../../features/traits/client-activity-synced-audience-traits.md"> Active Audience Traits and Data Source Synced Traits</a>. </p> </td>
  </tr>
 </tbody>
</table>

## Unique Trait Realizations and Total Trait Population {#unique-trait-realizations}

![](assets/utr-ttp1.png)

The **[!UICONTROL Unique Trait Realizations]** count the number of your visitors that have added the trait to their profile, within different time ranges.

The **[!UICONTROL Total Trait Population]** represents the number of your visitors that have this trait on their profile.

Considérez les nombres de cette manière. In the image above, from the [Trait Details](../../features/traits/trait-details-page.md) view, 181 represents the number of active devices, that visited your properties yesterday. The [!UICONTROL Total Trait Population] of 1,595 represents the amount of users currently qualified for this trait. [!UICONTROL Total Trait Population] Cette illustration indique le nombre total d'utilisateurs qui peuvent être utilisés pour la segmentation/le ciblage. En règle générale, les utilisateurs resteront dans une caractéristique pendant 120 jours.

Because we run two different computational jobs to calculate the two populations, the [!UICONTROL Total Trait Population] always lags behind the [!UICONTROL Unique Trait Realizations] by 24 hours. In the graph above, you can see 175 [!UICONTROL Unique Trait Realizations] and a [!UICONTROL Total Trait Population] of 6 for February 11. The 175 profiles are added to the [!UICONTROL Total Trait Population] on the following day.

To further drive the point home, if you experienced a spike of 10,000 visitors right now, they would show up in tomorrow's [!UICONTROL Unique Trait Realizations], but would only show up 24 hours later in the [!UICONTROL Total Trait Population].

## Trait Qualification Limit {#trait-qualification-limit}

We enforce a limit of 150,000 trait qualifications for each user profile, whether it is an authenticated profile ( [DPUUID](../../reference/ids-in-aam.md)) or a device ID ( [UUID](../../reference/ids-in-aam.md)). Note that while the DPUUIDs are unique to a specific instance of [!DNL Audience Manager], UUIDs are shared across the [!DNL Audience Manager] platform. For [!UICONTROL UUID]s, we impose a fairness policy when storing trait qualifications. An algorithm ensures that an equal share of the [!UICONTROL UUID] profile is made available for every instance of [!DNL Audience Manager].
