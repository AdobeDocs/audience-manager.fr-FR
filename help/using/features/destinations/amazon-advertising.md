---
description: Cet article explique comment configurer Amazon Advertising pour les intégrations nouvelles et existantes.
solution: Audience Manager
title: Configuration d’Amazon Advertising en tant que destination basée sur un appareil en libre-service
exl-id: 049af52a-b425-493d-9e77-9ced7ba6d168
source-git-commit: bac3167927af0957e7081e1ea653464101affcb8
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 1%

---

# Configurer [!DNL Amazon Advertising] comme destination en libre-service basée sur un appareil {#configure-amazon}

Cet article explique comment configurer une intégration avec [Amazon Advertising](https://advertising.amazon.com/API/docs/en-us).

## Conditions préalables {#prerequisites}

Avant de configurer votre destination [!DNL Amazon Advertising], assurez-vous de respecter les conditions préalables suivantes.

* Votre compte [!DNL Amazon] doit être éligible à la publicité.
* Lors de la création de la première destination [!DNL Amazon Advertising] dans votre instance d’Audience Manager, contactez Adobe Consulting ou l’assistance clientèle pour activer la synchronisation des identifiants [!DNL Amazon] (identifiant de Source de données = 139200) pour votre compte. Ceci est requis pour la synchronisation correcte entre l’Audience Manager et [!DNL Amazon].
* Une fois les nouvelles audiences du fournisseur de données créées, vous devez [mettre à jour leurs métadonnées](https://advertising.amazon.com/API/docs/en-us/data-provider/openapi#tag/Metadata/paths/~1v2~1dp~1audiencemetadata~1%7BaudienceId%7D/put) et ajouter le **[!DNL audience fees]**. Pour cette opération, vous pouvez utiliser l’[ API Amazon Ads](https://advertising.amazon.com/API/docs/en-us/guides/onboarding/apply-for-access) ou l’ [ interface utilisateur d’Amazon Advertising](https://advertising.amazon.com/).

## Ajout d’une nouvelle destination [!DNL Amazon Advertising] {#add-new-amazon-destination}

Cette section décrit les étapes à suivre lors de la configuration d’une nouvelle destination basée sur un appareil pour [!DNL Amazon Advertising]. Ce scénario suppose qu’aucune destination [!DNL Amazon Advertising] existante n’est configurée par l’intermédiaire de votre conseiller en Adobe ou de l’assistance clientèle.

### Étape 1 : Authentification avec [!DNL Amazon Advertising] {#step1-authenticate-with-amazon}

Avant de pouvoir ajouter la destination basée sur l’appareil, vous devez lier l’Audience Manager à votre compte [!DNL Amazon Advertising]. Procédez comme suit :

1. Connectez-vous à votre compte d’Audience Manager et accédez à **[!UICONTROL Administration > Integrated Accounts]**. Si vous disposez d’une intégration configurée précédemment avec une plateforme de destination, elle doit apparaître dans cette page. Sinon, la page est vide.
1. Sélectionnez **[!UICONTROL Add Account]**.
1. Sélectionnez [!UICONTROL Amazon Data Provider].

   ![integrated-platforms](assets/dbd-amazon-without-options.png)

1. Sélectionnez l’une des options **[!UICONTROL Amazon Data Provider]** en fonction de la région dans laquelle votre compte [!DNL Amazon Ads] est créé (Amérique du Nord, Europe ou Extrême-Orient) et cliquez sur **[!DNL Confirm]** pour être redirigé vers la page d’authentification.

   ![integrated-platforms](assets/dbd-amazon-with-options.png)

1. Une fois que vous êtes authentifié, vous êtes redirigé vers l’Audience Manager dans laquelle vos comptes publicitaires associés doivent apparaître. Sélectionnez le compte de l&#39;annonceur que vous souhaitez utiliser et cliquez sur **[!UICONTROL Confirm]**. Ce faisant, vous autorisez l’accès pour l’Audience Manager à envoyer des mises à jour pour vos audiences.

### Étape 2 : Création d’une destination basée sur un appareil {#step2-create-new-destination}

Après avoir lié l’Audience Manager et votre compte [!DNL Amazon Advertising], vous pouvez créer la nouvelle destination. Procédez comme suit :

>[!NOTE]
>
>Vous ne pouvez pas modifier le nom d’une destination existante basée sur un appareil. Veillez à fournir un nom qui vous aidera à identifier correctement la destination.

1. Connectez-vous à votre compte d’Audience Manager, accédez à **[!UICONTROL Audience Data > Destinations]** et sélectionnez **[!UICONTROL Create Destination]**.
1. Dans la section **[!UICONTROL Basic Information]** , saisissez un **[!UICONTROL Name]** et un **[!UICONTROL Description]** pour votre nouvelle destination, puis utilisez les paramètres ci-dessous :

   ![setup](assets/dbd-new-account-amazon.png)

1. Sélectionnez **[!UICONTROL Next]**.
1. Sélectionnez les [libellés d’exportation de données](/help/using/features/data-export-controls.md#controls-labels) que vous souhaitez définir pour cette destination.
1. Sélectionnez **[!UICONTROL Save]**.
1. Dans la section **[!UICONTROL Segment Mappings]** , sélectionnez les segments d’audience que vous souhaitez envoyer à cette destination.
1. Enregistrez la destination.

## Considérations sur les taux de correspondance {#match-rates-considerations}

L’intégration entre l’Audience Manager et [!DNL Amazon Advertising] prend en charge les renvoi d’audience historiques. Toutes les qualifications de segment sont envoyées à [!DNL Amazon] lorsque vous créez la destination.

## Dépannage {#troubleshooting}

Lors de la configuration ou de l’envoi de données à la destination [!DNL Amazon Advertising], vous pouvez rencontrer les erreurs décrites ci-dessous. Cette section explique ce qui peut entraîner des erreurs et comment les corriger.

| Message d’erreur | Occurrence/raison | Résolution |
|---|---|---|
| `Internal server error` | Ce message d’erreur s’affiche dans l’interface utilisateur d’Audience Manager lorsque vous essayez d’ajouter un nouveau compte [!DNL Amazon] à l’aide d’une version obsolète de l’API Amazon. | Contactez l’assistance clientèle d’Adobe. |
| `Amazon Error: Account XXXXXXXXX was not found` | Ce message d’erreur s’affiche dans l’interface utilisateur de l’Audience Manager lorsque les informations d’identification configurées pour la destination ne sont pas autorisées à accéder au compte Amazon Ads correspondant. | <ul><li>Assurez-vous que les informations d’identification du compte que vous utilisez répondent aux [conditions préalables](#prerequisites).</li><li>Accédez à l’interface utilisateur d’Amazon Ads à l’aide des mêmes informations d’identification et vérifiez si les audiences correctes sont affichées sous le compte correspondant. </li></ul> |
