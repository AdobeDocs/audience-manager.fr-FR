---
description: 'Cette page comprend des instructions détaillées sur la manière de combiner les données de gestion de la relation client hors ligne avec les données comportementales dont vous disposez déjà en Audience Manager pour créer de nouveaux segments d’audience, puis envoyer ces segments d’audience vers les destinations basées sur les personnes.  '
seo-description: 'Cette page comprend des instructions détaillées sur la manière de combiner les données de gestion de la relation client hors ligne avec les données comportementales dont vous disposez déjà en Audience Manager pour créer de nouveaux segments d’audience, puis envoyer ces segments d’audience vers les destinations basées sur les personnes.   '
seo-title: 'Processus A : personnalisation basée sur toutes les activités en ligne combinées avec les données hors ligne'
solution: Audience Manager
title: 'Processus A : personnalisation basée sur toutes les activités en ligne combinées avec les données hors ligne'
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1180'
ht-degree: 7%

---


# Processus A : personnalisation basée sur toutes les activités en ligne combinées avec les données hors ligne {#workflow-a}

>[!IMPORTANT]
>Cet article contient la documentation du produit destinée à vous guider tout au long de la configuration et de l’utilisation de cette fonction. Rien dans ce document n&#39;est un conseil juridique. Veuillez consulter votre propre conseiller juridique pour obtenir des conseils juridiques.

Cette page comprend des instructions détaillées sur la manière de combiner des données [!DNL CRM] hors ligne avec des données comportementales que vous avez déjà en Audience Manager pour créer de nouveaux segments d&#39;audience, puis d&#39;envoyer ces segments d&#39;audience à [!DNL People-Based Destinations].

## Étape 1 - Configurer les paramètres de source de données {#configure-data-source-settings}

Selon que vos [DPUUID](../../reference/ids-in-aam.md) sont des adresses électroniques en minuscules hachées, vous devrez peut-être configurer la source de données qui stockera les adresses électroniques hachées.

 

**Scénario 1 : vos  [](../../reference/ids-in-aam.md) DPUUID sont déjà des adresses électroniques en minuscules hachées.**

Dans ce cas, vous devez étiqueter la source de données correspondante comme telle :

1. Accédez à [!UICONTROL Audience Data] -> [!UICONTROL Data Sources].
1. Recherchez la source de données contenant vos [DPUUID](../../reference/ids-in-aam.md), puis cliquez dessus.
1. Dans le menu déroulant **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
1. Assurez-vous que l&#39;option [!UICONTROL Cannot be tied to personally identifiable information] n&#39;est pas cochée.
1. Dans la section **[!UICONTROL Data Source Settings]**, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]** et activez l&#39;option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilisez le menu déroulant pour sélectionner le libellé **[!UICONTROL Emails(SHA256, lowercased)]** de cette source de données.
   >[!IMPORTANT]
   >
   >Cette option étiquette uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. L’Audience Manager ne hachage pas les données à cette étape. Assurez-vous que les adresses électroniques que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas l&#39;utiliser pour [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Enregistrez les paramètres de la source de données.

 

**Scénario 2 : vos  [](../../reference/ids-in-aam.md) DPUUID ne sont pas des adresses électroniques en minuscules hachées.**

Dans ce cas, vous devez créer une source de données multipériphériques qui stockera vos adresses électroniques hachées. Voici comment procéder :

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**, puis cliquez sur **[!UICONTROL Add New]**.
1. Entrez [!UICONTROL Name] et [!UICONTROL Description] pour votre nouvelle source de données.
1. Dans le menu déroulant **[!UICONTROL ID Type]**, sélectionnez **[!UICONTROL Cross Device]**.
1. Dans la section **[!UICONTROL Data Source Settings]**, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]** et activez l&#39;option **[!UICONTROL Share associated cross-device IDs in people-based destinations]**.
1. Utilisez le menu déroulant pour sélectionner le libellé **[!UICONTROL Emails(SHA256, lowercased)]** de cette source de données.
   >[!IMPORTANT]
   >
   >Cette option étiquette uniquement la source de données comme contenant des données hachées avec cet algorithme spécifique. L’Audience Manager ne hachage pas les données à cette étape. Assurez-vous que les adresses électroniques que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l’algorithme [!DNL SHA256]. Sinon, vous ne pourrez pas l&#39;utiliser pour [!DNL People-Based Destinations].

   ![pbd-datasource-settings](assets/pbd-ds-config.png)
1. Enregistrez les paramètres de la source de données.

Regardez la vidéo ci-dessous pour découvrir comment créer une source de données pour [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29006/)

>[!NOTE]
>
> Voir [Intégration de données](people-based-destinations-prerequisites.md#data-onboarding) pour obtenir des questions fréquentes sur la manière d’importer vos données hors ligne en Audience Manager pour les destinations basées sur les personnes.

## Étape 2 - Correspondance entre les DPUUID et les adresses électroniques hachées via la synchronisation des identifiants basée sur des fichiers {#match-ids-emails}

>[!IMPORTANT]
>
> Cette étape s&#39;applique uniquement au [scénario 2](people-based-destinations-workflow-combined.md#configure-data-source-settings) décrit ci-dessus. Si vos [DPUUIDs](../../reference/ids-in-aam.md) existants sont déjà des adresses électroniques hachées, passez à [Étape 3 - Créer une règle de fusion de Profils pour la segmentation](people-based-destinations-workflow-combined.md#create-merge-rule).

Supposons que vous souhaitiez faire correspondre vos [DPUUIDs](../../reference/ids-in-aam.md) existants aux adresses électroniques hachées du tableau ci-dessous (colonne de droite) et stocker les adresses électroniques hachées dans la nouvelle source de données que vous avez créée à l&#39;[étape 1 - Configurer les paramètres de source de données](people-based-destinations-workflow-combined.md#configure-data-source-settings).

| DPUUID (ID CRM) | Adresse électronique | Adresse électronique hachée |
| -------------------------------------- | --------------------- | ---------------------------------------------------------------- |
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff1504 149 |
| 6741268208341199572553870443620307584 | `janedoe@email.com` | 16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a |
| 8915902479676034373311707646026765593 | `name@mydomain.com` | feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6 |

 

Vous pouvez lier jusqu’à 10 adresses électroniques hachées à un seul [DPUUID](../../reference/ids-in-aam.md). Pour ce faire, séparez les adresses électroniques hachées par une virgule dans le fichier de synchronisation.

Dans notre exemple, vous disposez désormais de deux sources de données.

| ID de source de données | Contenu de la source de données |
| -------------- | -------------------------- |
| 999999 | Identifiants DPUUID existants (CRM ID) |
| 987654 | Adresses électroniques hachées |

 

Votre [fichier de synchronisation des identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) aurait le contenu suivant :

```
68079982765673198504052656074456196039<TAB>55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149
67412682083411995725538770443620307584<TAB>16d72e3edbeb089b299e0d12fc09522fdc5ece2d11dcb1304ecdd6fab4f7193a
89159024796760343733111707646026765593<TAB>feec5debcea411f54462a345a0d90c9975415d2d4862745ff8af00c49b6b4ae6
```

 

Le [fichier de synchronisation des identifiants](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) doit suivre la structure d’affectation de nom suivante :

`c2c_id_<DPUUID_DATA_SOURCE_ID>_<HASHED_EMAIL_DATA_SOURCE_ID>_TIMESTAMP.sync`

 

Dans l’exemple ci-dessus, le nom de fichier se présenterait comme suit :
`c2c_id_999999_987654_1560431657.sync`

[Téléchargez un exemple de fichier ici](assets/c2c_id_999999_987654_1560431657.sync).

Une fois que vous avez créé votre fichier de synchronisation des identifiants, vous devez le télécharger dans un compartiment [!DNL Amazon S3]. Pour savoir comment télécharger des fichiers de synchronisation des identifiants, voir [Envoyer des données de lot à l’Audience Manager](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md).

## Étape 3 - Création d’une règle de fusion de Profil pour la segmentation {#create-merge-rule}

L’étape suivante consiste à créer une règle de fusion qui vous aidera à créer les segments d’audience à envoyer à vos destinations basées sur les personnes.

>[!IMPORTANT]
>
> Si une règle est déjà définie avec les options [!UICONTROL Current Authenticated Profiles] ou [!UICONTROL Last Authenticated Profiles], vous pouvez passer à [Étape 4 - Créer des segments d&#39;Audience](people-based-destinations-workflow-combined.md#create-audience-segments).

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Profile Merge Rules]**.
1. Cliquez sur **[!UICONTROL Add New Rule]**.
1. Saisissez une règle de fusion de profil **[!UICONTROL Name]** et **[!UICONTROL Description]**.
1. Dans la section **[!UICONTROL Profile Merge Rule Setup]**, sélectionnez les options **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]**.
1. Dans la liste **[!UICONTROL Cross-Device Profile Options]**, sélectionnez les sources de données sur lesquelles vous souhaitez exécuter la segmentation. Il doit s’agir des sources de données contenant vos [DPUUIDs](../../reference/ids-in-aam.md) existants.

## Étape 4 - Création de segments d’Audience {#create-audience-segments}

Pour créer de nouveaux segments d’audience, utilisez le [créateur de segments](../segments/segment-builder.md). Si vous souhaitez envoyer des segments d&#39;audience existants à [!DNL People-Based Destinations], passez à l&#39;[étape 5 - Configurer l&#39;authentification de plateforme basée sur les personnes](people-based-destinations-workflow-combined.md#configure-authentication).

## Étape 5 - Configurer l&#39;authentification de plateforme basée sur les personnes {#configure-authentication}

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Administration]** > **[!UICONTROL Integrated Accounts]**. Si vous disposez d’une intégration précédemment configurée avec une plateforme sociale, vous devriez la voir répertoriée dans cette page. Sinon, la page est vide.
   ![intégration basée sur les personnes](assets/pbd-config.png)
1. Cliquez sur **[!UICONTROL Add Account]**.
1. Utilisez le menu déroulant **[!UICONTROL People-Based Platform]** pour sélectionner la plate-forme avec laquelle vous souhaitez configurer l’intégration.
   ![plate-forme à base de personnes](assets/pbd-add.png)
1. Cliquez sur **[!UICONTROL Confirm]** pour être redirigé vers la page d&#39;authentification de la plateforme sélectionnée.
1. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers l’Audience Manager où vous devriez voir vos comptes d’annonceurs associés. Sélectionnez le compte publicitaire à utiliser, puis cliquez sur **[!UICONTROL Confirm]**.
1. L’Audience Manager affiche une notification en haut de la page pour vous indiquer si le compte a bien été ajouté. La notification vous permet également d’ajouter une adresse électronique de contact pour recevoir des notifications lorsque l’authentification de la plateforme sociale est sur le point d’expirer.

>[!IMPORTANT]
>
>Un gestionnaire d’audience gère l’intégration aux plateformes sociales au moyen de jetons d’authentification qui expirent après un certain temps. Voir Renouvellement du jeton d’authentification pour en savoir plus sur la manière de renouveler les jetons expirés.

## Étape 6 - Créer une destination basée sur les personnes {#create-destination}

1. Connectez-vous à votre compte d’Audience Manager, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Destinations]**, puis cliquez sur **[!UICONTROL Create Destination]**.
1. Dans la section **[!UICONTROL Basic Information]**, saisissez **[!UICONTROL Name]** et **[!UICONTROL Description]** pour votre nouvelle source de données et utilisez les paramètres suivants :
   * **[!UICONTROL Category]**: Plateformes intégrées ;
   * **[!UICONTROL Type]**: basé sur les personnes ;
   * **[!UICONTROL Platform]**: sélectionnez la plateforme basée sur les personnes à laquelle vous souhaitez envoyer des segments d’audience ;
   * **[!UICONTROL Account]**: sélectionnez le compte publicitaire souhaité associé à la plateforme sélectionnée.
      ![create-destination](assets/pbd-create-destination.png)
1. Cliquez sur **[!UICONTROL Next]**.
1. Sélectionnez le **[!UICONTROL Data Export Labels]** que vous souhaitez définir pour cette destination.
1. Dans la section **[!UICONTROL Configuration]**, sélectionnez la source de données qui contient vos sources de données hachées.
1. Dans la section **[!UICONTROL Segment Mappings]**, sélectionnez les segments à envoyer à cette destination. Il s’agit des segments que vous avez créés à l’[étape 4 - Créer des segments d’Audience](people-based-destinations-workflow-combined.md#create-audience-segments).
1. Enregistrez la destination.
