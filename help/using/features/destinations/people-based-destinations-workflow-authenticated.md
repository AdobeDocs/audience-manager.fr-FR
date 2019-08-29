---
description: 'Cette page comprend des conseils détaillés sur la combinaison des données de gestion de la relation client hors ligne avec des données comportementales en temps réel pour les utilisateurs authentifiés afin de créer des segments d''audience, puis envoie ces segments d''audience aux destinations basées sur People. '
seo-description: 'Cette page comprend des conseils détaillés sur la combinaison des données de gestion de la relation client hors ligne avec des données comportementales en temps réel pour les utilisateurs authentifiés afin de créer des segments d''audience, puis envoie ces segments d''audience aux destinations basées sur People.  '
seo-title: Processus C - Personnalisation basée sur une activité authentifiée combinée avec des données hors ligne
solution: Audience Manager
title: Processus C - Personnalisation basée sur une activité authentifiée combinée avec des données hors ligne
translation-type: tm+mt
source-git-commit: 11663e962254bbcab90105d72af003b2a7056744

---


# Processus C - Personnalisation basée sur une activité authentifiée combinée avec des données hors ligne {#workflow-c}

Cette page comprend des conseils détaillés sur la combinaison des données hors ligne [!DNL CRM] avec des données comportementales en temps réel pour les utilisateurs authentifiés afin de créer des segments d'audience, puis d'envoyer [!DNL People-Based Destinations]ces segments d'audience.

## Étape 1 - Configuration des paramètres de la source de données {#configure-data-source-settings}

Selon que vos [dpuuid](../../reference/ids-in-aam.md) sont des adresses minuscules, des adresses électroniques hachées, vous devrez peut-être configurer la source de données qui stockera les adresses électroniques hachées.

**Scénario 1 : vos[dpuuid](../../reference/ids-in-aam.md)sont déjà en minuscules, adresses électroniques hachées.**

Dans ce cas, passez à [l'étape 5 - Configuration de l'authentification de plateforme basée sur les personnes](#configure-authentication).

**Scénario 2 : vos[identifiants dpuuid](../../reference/ids-in-aam.md)ne sont pas des adresses électroniques hachées.**

Dans ce cas, vous devez créer une source de données inter-périphériques qui stockera les adresses électroniques hachées. Voici comment procéder :

1. Connectez-vous à votre compte Audience Manager et accédez **[!UICONTROL Audience Data]** à -&gt; **[!UICONTROL Data Sources]**, puis cliquez **[!UICONTROL Add New]** sur.
1. Saisissez un **[!UICONTROL Name]** et **[!UICONTROL Description]** pour la nouvelle source de données.
1. Dans le **[!UICONTROL ID Type]** menu déroulant, sélectionnez **[!UICONTROL Cross Device]**.
1. Dans **[!UICONTROL Data Source Settings]** la section, sélectionnez les options **[!UICONTROL Inbound]** et **[!UICONTROL Outbound]** les options, puis activez l' **[!UICONTROL Share associated cross-device IDs in people-based destinations]** option.
1. Utilisez le menu déroulant pour sélectionner **[!UICONTROL Emails(SHA256, lowercased)]** le libellé de cette source de données.
   >[!IMPORTANT]
   >
   >Cette option considère uniquement la source de données comme contenant les données hachées avec cet algorithme spécifique. Audience Manager ne hachera pas les données à cette étape. Assurez-vous que les adresses électroniques que vous prévoyez de stocker dans cette source de données sont déjà hachées avec l [!DNL SHA256] 'algorithme. Sinon, vous ne pourrez pas l'utiliser [!DNL People-Based Destinations]pour.

   ![pbd-datasource-settings](assets/pbd-ds-config.png)

   >[!NOTE]
   >
   > Pour [plus d'informations sur la manière de placer vos données hors ligne dans Audience Manager pour les destinations basées sur un utilisateur, reportez-vous à la section Intégration des données](people-based-destinations-prerequisites.md#data-onboarding) aux questions fréquentes.

## Etape 2 : utilisation d'identifiants déclarés pour correspondre aux identifiants dpuuid avec des adresses de courriel hachées via Real - Appels HTTP temporels {#match-email-addresses}

Pour qualifier les utilisateurs authentifiés pour des caractéristiques basées sur des règles, vous devez envoyer la qualification de caractéristique à l'aide [d'ID déclarés](../declared-ids.md).

### Exemple

Imaginons que vous ayez créé les deux sources de données suivantes.

| ID de source de données | Contenu de la source de données |
|---|---|
| 999999 | DPUUID existants (identifiants CRM) |
| 987654 | Adresses électroniques hachées |

Vous souhaitez ensuite qualifier les identifiants CRM ci-dessous pour la caractéristique du tableau.

| DPUUID, ID de CRM | Adresse électronique | Adresse électronique hachée | Caractéristique |
|---|---|---|---|
| 68079982765673198504052656074456196039 | `johndoe@example.com` | 55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149 | location = US |

L'ID déclaré doit respecter cette syntaxe :

`https://yourDomain.demdex.net/event?d_cid_ic=myHashedEmailDataSourceID%01myHashedEmail&d_cid_ic=myCrmDataSourceID%01myCRMID&key=value`

Dans l'exemple ci-dessus, l'appel d'ID déclaré doit ressembler à ceci :

`https://yourDomain.demdex.net/event?d_cid_ic=987654%0155e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149&d_cid_ic=999999%0168079982765673198504052656074456196039&location=US`

## Étape 3 - Création d'une règle de fusion de profils pour la segmentation {#create-profile-merge-rule-segmentation}

L'étape suivante consiste à créer une règle de fusion qui vous aidera à créer les segments d'audience à envoyer à [!DNL People-Based Destinations]votre.

>[!IMPORTANT]
>
>Si une règle est déjà définie avec les options **[!UICONTROL Current Authenticated Profiles]** ou **[!UICONTROL Last Authenticated Profiles]** les options, vous pouvez passer à [l'étape 4 - Créer des segments d'audience](#create-audience-segments).

1. Connectez-vous à votre compte Audience Manager et accédez **[!UICONTROL Audience Data]** à -&gt; **[!UICONTROL Profile Merge Rules]**.
2. Cliquez sur **[!UICONTROL Add New Rule]**.
3. Saisissez une règle de fusion de profil **[!UICONTROL Name]** et **[!UICONTROL Description]**.
4. Dans **[!UICONTROL Profile Merge Rule Setup]** la section, sélectionnez **[!UICONTROL All Cross-Device Profiles]** la règle dans **[!UICONTROL Cross-Device Options]** la liste.
5. Dans **[!UICONTROL Cross-Device Profile Options]** la liste, sélectionnez les sources de données sur lesquelles vous souhaitez exécuter la segmentation. Il doit s'agir des sources de données contenant vos dpuuid existants.
   ![fusion-règle-configuration](assets/pbd-pmr-combined.png)

## Etape 4 - Création de segments d'audience {#create-audience-segments}

Pour créer de nouveaux segments, utilisez le [Créateur de segments](../segments/segment-builder.md). Si vous souhaitez envoyer des segments d'audience existants à [!DNL People-Based Destinations]envoyer, passez à [l'étape 5 - Configurer l'authentification des plateformes basées sur les personnes](#configure-authentication).

## Étape 5 - Configuration de l'authentification de plateforme basée sur les personnes {#configure-authentication}

1. Connectez-vous à votre compte Audience Manager et accédez **[!UICONTROL Administration]** à &gt; **[!UICONTROL Integrated Accounts]**. Si vous avez déjà configuré une intégration avec une plateforme sociale, vous devriez la voir dans cette page. Sinon, la page est vide.
   ![people-based-integration](assets/pbd-config.png)
2. Cliquez sur **[!UICONTROL Add Account]**.
3. Utilisez le menu **[!UICONTROL People-Based Platform]** déroulant pour sélectionner la plateforme à laquelle vous souhaitez configurer l'intégration.
   ![people-based-platform](assets/pbd-add.png)
4. Cliquez pour **[!UICONTROL Confirm]** être redirigé vers la page d'authentification de la plateforme sélectionnée.
5. Une fois que vous êtes authentifié sur votre compte de plateforme sociale, vous êtes redirigé vers Audience Manager, où vos comptes publicitaires associés doivent apparaître. Sélectionnez le compte publicitaire à utiliser, puis cliquez **[!UICONTROL Confirm]** sur.
6. Audience Manager affiche une notification en haut de la page pour vous informer si le compte a bien été ajouté. La notification vous permet également d'ajouter une adresse électronique de contact à laquelle recevoir des notifications lorsque l'authentification de la plateforme sociale est sur le point d'expirer.

>[!IMPORTANT]
>
>Un gestionnaire d'udience gère l'intégration à des plateformes sociales via des jetons d'authentification qui expirent après une certaine durée. Pour plus d'informations sur le renouvellement des jetons expirés, reportez-vous à la section Renouvellement du jeton d'authentification.

## Etape 6 - Création d'une destination basée sur People {#create-destination}

1. Connectez-vous à votre compte Audience Manager, accédez **[!UICONTROL Audience Data]** à &gt; **[!UICONTROL Destinations]**, puis cliquez **[!UICONTROL Create Destination]** sur.
1. Dans **[!UICONTROL Basic Information]** la section, saisissez a **[!UICONTROL Name]** et **[!UICONTROL Description]** pour la nouvelle source de données et utilisez les paramètres suivants :
   * **[!UICONTROL Category]**: Plateformes intégrées ;
   * **[!UICONTROL Type]**: Basé sur les personnes ;
   * **[!UICONTROL Platform]**: sélectionnez la plateforme basée sur people pour laquelle vous souhaitez envoyer des segments d'audience ;
   * **[!UICONTROL Account]**: sélectionnez un compte publicitaire associé à la plateforme sélectionnée.
      ![create-destination](assets/pbd-create-destination.png)
1. Cliquez sur **[!UICONTROL Next]**.
1. Choisissez la **[!UICONTROL Data Export Labels]** valeur que vous souhaitez définir pour cette destination.
1. Dans **[!UICONTROL Configuration]** la section, sélectionnez la source de données contenant vos sources de données hachées.
1. Dans **[!UICONTROL Segment Mappings]** la section, sélectionnez les segments à envoyer à cette destination. Il s'agira des segments que vous avez créés à [l'étape 4 - Création de segments d'audience](#create-audience-segments).
1. Enregistrez la destination.
