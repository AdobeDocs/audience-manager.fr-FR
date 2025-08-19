---
description: Cette page comprend des conseils détaillés sur la manière de combiner des données CRM hors ligne avec des données comportementales que vous avez déjà dans Audience Manager pour créer des segments d’audience, puis envoyer ces segments d’audience vers des destinations basées sur les personnes.
seo-description: This page includes step-by-step guidance on how to combine offline CRM data with behavioral data that you already have in Audience Manager to create new audience segments, then send these audience segments to People-Based Destinations.
seo-title: Workflow A - Personalization Based on All Online Activity Combined with Offline Data
solution: Audience Manager
title: 'Workflow A : Personalization basé sur l’ensemble des activités en ligne combinées aux données hors ligne'
feature: People-based Destinations
exl-id: 1f906955-8fe7-4cce-95d6-0e4275d523e8
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1108'
ht-degree: 0%

---

# Workflow A : Personalization basé sur l’ensemble des activités en ligne combinées aux données hors ligne {#workflow-a}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonctionnalité. Rien dans le présent document n&#39;est un avis juridique. Veuillez consulter votre propre service juridique pour obtenir des conseils juridiques.

Cette page contient des conseils détaillés sur la manière de combiner des données de [!DNL CRM] hors ligne avec des données comportementales que vous avez déjà dans Audience Manager afin de créer des segments d’audience, puis d’envoyer ces segments d’audience à [!DNL People-Based Destinations].

## Étape 1 - Configurer les paramètres de Source de données {#configure-data-source-settings}

Selon que vos [DPUUID](../../reference/ids-in-aam.md) sont des adresses e-mail hachées en minuscules ou non, vous devrez peut-être configurer la source de données qui stockera les adresses e-mail hachées.

 

**Scénario 1 : vos [DPUUID](../../reference/ids-in-aam.md) sont déjà des adresses e-mail hachées en minuscules.**

Dans ce cas, vous devez étiqueter la source de données correspondante comme telle :

1. Accédez à [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Recherchez la source de données qui contient vos [DPUUID](../../reference/ids-in-aam.md), puis cliquez dessus.
1. Dans le menu déroulant **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
1. Assurez-vous que l’option [!UICONTROL Cannot be tied to personally identifiable information] n’est pas cochée.
1. Dans la section **[!UICONTROL Data Source Settings]**, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]**, puis activez l’option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilisez le menu déroulant pour sélectionner le libellé de **[!UICONTROL Emails(SHA256, lowercased)]** de cette source de données.
   >[!IMPORTANT]
   >
   >Cette option étiquette uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. Audience Manager ne hache pas les données à cette étape. Assurez-vous que les adresses e-mail que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas l&#39;utiliser pour les [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Enregistrez les paramètres de la source de données.

 

**Scénario 2 : vos [DPUUID](../../reference/ids-in-aam.md) ne sont pas des adresses e-mail hachées en minuscules.**

Dans ce cas, vous devez créer une nouvelle source de données inter-appareils qui stockera vos adresses e-mail hachées. Procédez comme suit :

1. Connectez-vous à votre compte Audience Manager, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**, puis cliquez sur **[!UICONTROL Add New]**.
1. Saisissez un [!UICONTROL Name] et une [!UICONTROL Description] pour votre nouvelle source de données.
1. Dans le menu déroulant **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
1. Dans la section **[!UICONTROL Data Source Settings]**, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]**, puis activez l’option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilisez le menu déroulant pour sélectionner le libellé de **[!UICONTROL Emails(SHA256, lowercased)]** de cette source de données.
   >[!IMPORTANT]
   >
   >Cette option étiquette uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. Audience Manager ne hache pas les données à cette étape. Assurez-vous que les adresses e-mail que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas l&#39;utiliser pour les [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Enregistrez les paramètres de la source de données.

Regardez la vidéo ci-dessous pour un tutoriel vidéo sur la création d’une source de données pour [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Consultez [ Intégration de données ](people-based-destinations-prerequisites.md#data-onboarding) pour obtenir des questions fréquentes sur la manière d’importer vos données hors ligne dans Audience Manager pour les destinations basées sur les personnes.

## Étape 2 - Correspondance des DPUUID aux adresses e-mail hachées via la synchronisation d’identifiants basée sur des fichiers {#match-ids-emails}

>[!IMPORTANT]
>
> Cette étape s’applique uniquement au [scénario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) décrit ci-dessus. Si vos [DPUUID](../../reference/ids-in-aam.md) existants sont déjà des adresses e-mail hachées, passez à l’[Étape 3 - Créer une règle de fusion de profil pour la segmentation](people-based-destinations-workflow-combined.md#create-merge-rule).

Supposons que vous souhaitiez faire correspondre vos [DPUUID](../../reference/ids-in-aam.md) existants aux adresses e-mail hachées du tableau ci-dessous (colonne de droite) et stocker les adresses e-mail hachées dans la nouvelle source de données que vous avez créée à l’[Étape 1 - Configurer les paramètres de Source de données](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID CRM) | Adresse e-mail | Adresse e-mail hachée |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 |
| 67412682083411995725538770443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 89159024796760343733111707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Vous pouvez lier jusqu’à 10 adresses e-mail hachées à un seul [DPUUID](../../reference/ids-in-aam.md). Pour ce faire, séparez les adresses e-mail hachées avec un `<TAB>`, dans le fichier de synchronisation.

Dans notre exemple, vous auriez désormais deux sources de données.

| Identifiant de la source de données | Contenu de la source de données |
| -------------- | -------------------------- |
| 999999 | DPUUID existants (ID CRM) |
| 987654 | Adresses e-mail hachées |

 

Le contenu de votre fichier de synchronisation [ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) serait le suivant :

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Le fichier de synchronisation des [ID](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) doit suivre la structure de dénomination suivante :

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Dans l’exemple ci-dessus, le nom du fichier se présente comme suit :
`c2c_id_999999_987654_1560431657.sync`

[Téléchargez l’exemple de fichier ici](assets/c2c_id_999999_987654_1560431657.sync).

Une fois le fichier de synchronisation des identifiants créé, vous devez le charger dans un compartiment [!DNL Amazon S3]. Pour savoir comment télécharger des fichiers de synchronisation des identifiants, voir [Envoyer des données par lot à Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Étape 3 - Créer une règle de fusion de profil pour la segmentation {#create-merge-rule}

L’étape suivante consiste à créer une règle de fusion qui vous aidera à créer les segments d’audience à envoyer à vos destinations basées sur les personnes.

>[!IMPORTANT]
>
> Si vous avez déjà défini une règle avec les options [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles], vous pouvez passer à l’[Étape 4 - Créer des segments d’audience](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Cliquez sur **[!UICONTROL Add New Rule]**.
1. Saisissez un **[!UICONTROL Name]** et une **[!UICONTROL Description]** de règle de fusion de profil.
1. Dans la section **[!UICONTROL Profile Merge Rule Setup]**, sélectionnez les options **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.
1. Dans la liste **[!UICONTROL Cross-Device Profile Options]**, sélectionnez les sources de données sur lesquelles vous souhaitez exécuter la segmentation. Il doit s’agir des sources de données contenant vos [DPUUID](../../reference/ids-in-aam.md) existants.

## Étape 4 - Créer Des Segments D’Audience {#create-audience-segments}

Pour créer des segments d’audience, utilisez le [créateur de segments](../segments/segment-builder.md). Si vous souhaitez envoyer des segments d’audience existants à [!DNL People-Based Destinations], passez à l’[Étape 5 - Configurer l’authentification de la plateforme basée sur les personnes](people-based-destinations-workflow-combined.md#configure-authentication).

## Étape 5 - Configurer L&#39;Authentification De La Plateforme Basée Sur Les Personnes {#configure-authentication}

1. Connectez-vous à votre compte Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si vous avez configuré précédemment une intégration à une plateforme sociale, elle est répertoriée sur cette page. Dans le cas contraire, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
1. Cliquez sur **[!UICONTROL Add Account]**.
1. Utilisez le menu déroulant **[!UICONTROL People-Based Platform]** pour sélectionner la plateforme avec laquelle vous souhaitez configurer l’intégration.
   ![plateforme basée sur les personnes](assets/pbd-add.png)
1. Cliquez sur **[!UICONTROL Confirm]** pour être redirigé vers la page d’authentification de la plateforme sélectionnée.
1. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers Audience Manager où vous devriez voir les comptes publicitaires associés. Sélectionnez le compte publicitaire que vous souhaitez utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
1. Audience Manager affiche une notification en haut de la page pour vous informer que le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse e-mail de contact pour recevoir des notifications lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

>[!IMPORTANT]
>
>Audience Manager gère l’intégration aux plateformes sociales par le biais de jetons d’authentification qui expirent après un certain temps. Consultez Renouvellement du jeton d’authentification pour plus d’informations sur le renouvellement des jetons expirés.

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
1. Dans la section **[!UICONTROL Segment Mappings]** , sélectionnez les segments que vous souhaitez envoyer à cette destination. Il s’agit des segments que vous avez créés à l’[Étape 4 - Créer des segments ciblés](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Enregistrez la destination.
