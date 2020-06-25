---
description: Configurez un groupe Google pour que vos fichiers de données DoubleClick Campaign Manager (DCM) soient mis en Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources DCM pour vous aider à démarrer.
seo-description: Configurez un groupe Google pour que vos fichiers de données DoubleClick Campaign Manager (DCM) soient mis en Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources DCM pour vous aider à démarrer.
seo-title: Importer des fichiers de données DCM dans l’Audience Manager
solution: Audience Manager
title: Importer des fichiers de données DCM dans l’Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 5%

---


# Import DCM Data Files Into Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurez un groupe Google pour que vos fichiers de données DoubleClick Campaign Manager (DCM) soient mis en Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources DCM pour vous aider à démarrer.

## Résumé de l’intégration

DCM est le remplacement de [!DNL Google] pour [!DNL DoubleClick for Advertisers] (DFA). Tout comme avec DFA, les clients DCM peuvent importer, visualiser et manipuler leurs données dans [!DNL Audience Manager]. Mais [!DNL Audience Manager] ne peut pas accéder directement à vos [!UICONTROL Data Transfer] fichiers et [!UICONTROL Match Table] fichiers et les importer. C’est au client qu’il incombe d’importer ces fichiers.

Cependant, la procédure de configuration est bien documentée dans l’aide [de](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456)DoubleClick Campaign Manager. Vous pouvez également passer en revue les étapes ci-dessous pour commencer.

>[!CAUTION]
>
>Les fichiers de données DCM contiennent des données pour tous vos annonceurs ou clients. Si vous devez omettre des clients spécifiques, vous devez modifier les fichiers avant de les rendre disponibles pour [!DNL Audience Manager].

## Fréquence et disponibilité des transferts de données

[!DNL Audience Manager] vérifie et transfère les données une fois par jour. Les données sont généralement disponibles en [!DNL Audience Manager] dehors de 24 heures.

## Étapes

1. [Créer un groupe](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Les groupes contrôlent l’accès à vos données DCM. Finalement, vous inviterez et ajouterez [!DNL Audience Manager] à ce groupe.

1. [Vérifiez l’état](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456)de votre Enregistrement Google Cloud.

   L’Enregistrement Google Cloud contient le compartiment de données qui contient votre [!UICONTROL Data Transfer] et [!UICONTROL Match Tables]. Vous devez configurer un compartiment ou vous assurer que votre nouveau groupe a accès à un compartiment d&#39;enregistrement de données existant.

1. [Obtenez une URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456)de fichier de données.

   Contactez votre gestionnaire de compte DCM ou votre consultant Platform Solutions. Ils vous fourniront une URL vers vos fichiers de données. [!DNL Google] peut modifier le format des noms de fichier et de compartiment dans les versions ultérieures. Là encore, demandez à votre gestionnaire de compte DCM de vous assurer que vous utilisez les formats appropriés.

1. [Définissez des autorisations](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission)de compartiment.

   Il [!DNL Cloud Storage Manager] vous permet de contrôler le partage des données et l’accès au compartiment. Donnez à votre groupe un accès en lecture au compartiment qui contient vos [!UICONTROL Data Transfer] fichiers et [!UICONTROL Match Table] fichiers.

1. [Configurez le partage](https://support.google.com/dcm/partner/answer/6206106?hl=en)des données.

   Les ID utilisateur DCM partagés sont chiffrés afin de protéger la confidentialité. Encryption ajoute 2 colonnes à la fin de votre fichier de transfert de données `PartnerId1` et `PartnerId2`. Ces colonnes contiennent des ID utilisateur codés spécifiques à chaque société qui reçoit ces fichiers.

   En tant que tiers autorisé, [!DNL Audience Manager] peut recevoir des données DCM, mais ne peut pas décoder les ID. Cependant, [!DNL Audience Manager] nous savons comment les identifiants codés correspondent à nos identifiants. Cela signifie que nous pouvons associer et synchroniser les utilisateurs avec confiance et précision.

   >[!NOTE]
   >Vous ne pouvez pas importer de fichiers DCM dans [!DNL Audience Manager] si vous partagez déjà des données avec 2 autres partenaires tiers.

1. Invitation [!DNL Audience Manager] à rejoindre le groupe.

   Après avoir créé un groupe et lui avoir donné accès à un regroupement de données, invitez [!DNL Audience Manager] à le rejoindre. Envoyez une invitation par courrier électronique à DFA-AAM@adobe.com. Veillez à inclure l’URL du fichier de données à l’étape 3. Nos équipes internes travailleront avec vous pour vérifier l&#39;accès après avoir accepté l&#39;invitation. 1. Configurez deux sources de données pour les données DCM dans l’interface [!DNL Audience Manager] utilisateur.

   Nommez les sources de données `Advertiser Analytics: DCM Platform` et `Advertiser Analytics: AAM+DCM Platform`. Dans le processus [Créer des sources](../../../features/manage-datasources.md#create-data-source) de données, définissez le type d’ID sur `Cookie`. Partagez les ID des deux nouvelles sources de données avec nos équipes internes.

1. Vous pouvez facilement créer des caractéristiques à partir des fichiers DCM dans lesquels vous importez [!DNL Audience Manager]. Voir Fichiers [journaux](../../../integration/media-data-integration/actionable-log-files.md) utilisables et demandez à votre [!DNL Audience Manager] consultant ou au service d’assistance clientèle d’activer la fonction pour vous.
