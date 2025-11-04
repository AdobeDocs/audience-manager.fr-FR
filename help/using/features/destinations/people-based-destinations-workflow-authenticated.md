---
description: Cette page comprend des conseils détaillés sur la manière de combiner des données CRM hors ligne avec des données comportementales en temps réel pour que les utilisateurs authentifiés puissent créer des segments d’audience, puis envoyer ces segments d’audience aux destinations basées sur les personnes.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with real-time behavioral data for authenticated users to create audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow C - Personalization Based on Authenticated Activity Combined with Offline Data
solution: Audience Manager
title: 'Workflow C : Personalization basé sur l’activité authentifiée associée aux données hors ligne'
feature: People-based Destinations
exl-id: 24f877ce-089e-484c-9a70-8fce1a10a649
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 1%

---

# Workflow C : Personalization basé sur l’activité authentifiée associée aux données hors ligne {#workflow-c}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Cette page comprend des conseils détaillés sur la manière de combiner des données de [!DNL CRM] hors ligne avec des données comportementales en temps réel pour que les utilisateurs authentifiés puissent créer des segments d’audience, puis envoyer ces segments d’audience à [!DNL People-Based Destinations].

## Étape 1 - Configurer les paramètres de Source de données {#configure-data-source-settings}

Selon que vos [DPUUID](../../reference/ids-in-aam.md) sont des adresses e-mail hachées en minuscules ou non, vous devrez peut-être configurer la source de données qui stockera les adresses e-mail hachées.

 

**Scénario 1 : vos [DPUUID](../../reference/ids-in-aam.md) sont déjà des adresses e-mail hachées en minuscules.**

Dans ce cas, passez à l’[Étape 5 - Configurer l’authentification de la plateforme basée sur les personnes](#configure-authentication).

 

**Scénario 2 : vos [DPUUID](../../reference/ids-in-aam.md) ne sont pas des adresses e-mail hachées en minuscules.**

Dans ce cas, vous devez créer une nouvelle source de données inter-appareils qui stockera vos adresses e-mail hachées. Procédez comme suit :

1. Connectez-vous à votre compte Audience Manager, accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]**, puis cliquez sur **[!UICONTROL Add New]**.
1. Saisissez un **[!UICONTROL Name]** et une **[!UICONTROL Description]** pour votre nouvelle source de données.
1. Dans le menu déroulant **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
1. Dans la section **[!UICONTROL Data Source Settings]**, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]**, puis activez l’option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilisez le menu déroulant pour sélectionner le libellé de **[!UICONTROL Emails(SHA256, lowercased)]** de cette source de données.

   >[!IMPORTANT]
   >
   >Cette option étiquette uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. Audience Manager ne hache pas les données à cette étape. Assurez-vous que les adresses e-mail que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas l&#39;utiliser pour les [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Consultez [ Intégration de données ](people-based-destinations-prerequisites.md#data-onboarding) pour obtenir des questions fréquentes sur la manière d’importer vos données hors ligne dans Audience Manager pour les destinations basées sur les personnes.

Regardez la vidéo ci-dessous pour un tutoriel vidéo sur la création d’une source de données pour [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

## Étape 2 - Utilisation des identifiants déclarés pour faire correspondre les DPUUID aux adresses e-mail hachées via des appels HTTP en temps réel {#match-email-addresses}

Pour qualifier des utilisateurs authentifiés pour des caractéristiques basées sur des règles, vous devez envoyer la qualification de la caractéristique via des [identifiants déclarés](../declared-ids.md).

### Exemple

Supposons que vous ayez créé les deux sources de données suivantes.

| Identifiant de la source de données | Contenu de la source de données |
| -------------- | -------------------------- |
| 999999 | DPUUID existants (ID CRM) |
| 987654 | Adresses e-mail hachées |

 

Ensuite, vous devez qualifier les identifiants CRM ci-dessous pour la caractéristique du tableau.

| DPUUID (ID CRM) | Adresse e-mail | Adresse e-mail hachée | Caractéristique |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- | ------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

 

Votre ID déclaré doit respecter la syntaxe suivante :

`https://yourDomain.demdex.net/event?d_cid_ic=HashedEmailDataSourceIntegrationCode%01myHashedEmail&d_cid_ic=CRMDataSourceIntegrationCode%01myCRMID&key=value`

 

Dans l’exemple ci-dessus, l’appel d’ID déclaré doit se présenter comme suit :

`https://yourDomain.demdex.net/event?d_cid_ic=MyHashedEmailDataSource%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=MyCRMDataSource%0168079982765673198504052656074456196039&location=US`

## Étape 3 - Créer une règle de fusion de profil pour la segmentation {#create-profile-merge-rule-segmentation}

L’étape suivante consiste à créer une règle de fusion pour vous aider à créer les segments d’audience à envoyer à votre [!DNL People-Based Destinations].

>[!IMPORTANT]
>
>Si vous avez déjà défini une règle avec les options **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**, vous pouvez passer à l’[Étape 4 - Créer des segments d’audience](#create-audience-segments).

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Audience Data]** -> **[!UICONTROL Profile Merge Rules]**.
2. Cliquez sur **[!UICONTROL Add New Rule]**.
3. Saisissez un **[!UICONTROL Name]** et une **[!UICONTROL Description]** de règle de fusion de profil.
4. Dans la section **[!UICONTROL Profile Merge Rule Setup]** , sélectionnez la règle de **[!UICONTROL Current Authenticated Profiles]** ou de **[!UICONTROL Last Authenticated Profiles]** dans la liste **[!UICONTROL Cross-Device Options]** .
5. Dans la liste **[!UICONTROL Cross-Device Profile Options]**, sélectionnez les sources de données sur lesquelles vous souhaitez exécuter la segmentation. Il doit s’agir des sources de données contenant vos DPUUID existants.
   ![merge-rule-setup](assets/pbd-pmr-combined.png)

## Étape 4 - Créer Des Segments D’Audience {#create-audience-segments}

Pour créer des segments, utilisez le [Créateur de segments](../segments/segment-builder.md). Si vous souhaitez envoyer des segments d’audience existants à [!DNL People-Based Destinations], passez à l’[Étape 5 - Configurer l’authentification de la plateforme basée sur les personnes](#configure-authentication).

## Étape 5 - Configurer L&#39;Authentification De La Plateforme Basée Sur Les Personnes {#configure-authentication}

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si vous avez configuré précédemment une intégration à une plateforme sociale, elle est répertoriée sur cette page. Dans le cas contraire, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
2. Cliquez sur **[!UICONTROL Add Account]**.
3. Utilisez le menu déroulant **[!UICONTROL People-Based Platform]** pour sélectionner la plateforme avec laquelle vous souhaitez configurer l’intégration.
   ![plateforme basée sur les personnes](assets/pbd-add.png)
4. Cliquez sur **[!UICONTROL Confirm]** pour être redirigé vers la page d’authentification de la plateforme sélectionnée.
5. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
6. Audience Manager affiche une notification en haut de la page pour vous informer que le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse e-mail de contact pour recevoir des notifications lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

>[!IMPORTANT]
>
>Audience Manager gère l’intégration avec les plateformes sociales par le biais de jetons d’authentification qui expirent après un certain temps. Consultez Renouvellement du jeton d’authentification pour plus d’informations sur le renouvellement des jetons expirés.

## Étape 6 - Créer une destination basée sur les personnes {#create-destination}

1. Connectez-vous à votre compte Audience Manager, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**, puis cliquez sur **[!UICONTROL Create Destination]**.
1. Dans la section **[!UICONTROL Basic Information]** , saisissez un **[!UICONTROL Name]** et un **[!UICONTROL Description]** pour votre nouvelle source de données, puis utilisez les paramètres suivants :
   * **[!UICONTROL Category]** : Plateformes intégrées
   * **[!UICONTROL Type]** : Fondé Sur Les Personnes ;
   * **[!UICONTROL Platform]** : sélectionnez la plateforme basée sur les personnes à laquelle vous souhaitez envoyer des segments d’audience ;
   * **[!UICONTROL Account]** : sélectionnez le compte de l’annonceur souhaité associé à la plateforme sélectionnée.
     ![création-destination](assets/pbd-create-destination.png)
1. Cliquez sur **[!UICONTROL Next]**.
1. Choisissez la **[!UICONTROL Data Export Labels]** que vous souhaitez définir pour cette destination.
1. Dans la section **[!UICONTROL Configuration]** , sélectionnez la source de données qui contient vos sources de données hachées.
1. Dans la section **[!UICONTROL Segment Mappings]** , sélectionnez les segments que vous souhaitez envoyer à cette destination. Il s’agit des segments que vous avez créés à l’[Étape 4 - Créer des segments ciblés](#create-audience-segments).
1. Enregistrez la destination.
