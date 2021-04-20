---
description: Configurez un groupe Google pour que vos fichiers de données Google Campaign Manager soient mis en Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources Google Campaign Manager pour vous aider à démarrer.
seo-description: Configurez un groupe Google pour que vos fichiers de données Google Campaign Manager soient mis en Audience Manager. Le contenu de cette section résume le processus d’intégration et vous fournit des liens vers les ressources Google Campaign Manager pour vous aider à démarrer.
seo-title: Importer les fichiers de données Google Campaign Manager dans l’Audience Manager
solution: Audience Manager
title: Importer les fichiers de données Google Campaign Manager dans l’Audience Manager
uuid: 3578cfe1-6d30-4a73-ab75-8d272bebcd60
feature: Audience Optimization Reports
exl-id: 045eed94-100f-460d-83bb-78fbd7beb51c
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 3%

---

# Importer les fichiers de données Google Campaign Manager dans l’Audience Manager {#import-dcm-data-files-into-audience-manager}

Configurez un groupe [!DNL Google] pour que vos fichiers de données [!DNL Google Campaign Manager] soient mis en Audience Manager. Le contenu de cette section résume le processus d&#39;intégration et vous fournit des liens vers des ressources [!DNL Google Campaign Manager] pour vous aider à démarrer.

## Résumé de l’intégration

[!DNL Google Campaign Manager] est le remplacement de [!DNL Google] pour [!DNL DoubleClick for Advertisers] (DFA). Tout comme DFA, les clients [!DNL Google Campaign Manager] peuvent importer, vue et utiliser leurs données dans [!DNL Audience Manager]. Mais [!DNL Audience Manager] ne peut pas accéder directement à vos fichiers [!UICONTROL Data Transfer] et [!UICONTROL Match Table] et les importer. C’est au client qu’il incombe d’importer ces fichiers.

Cependant, la procédure de configuration est bien documentée dans l&#39;[Aide de DoubleClick Campaign Manager](https://support.google.com/dcm/partner/answer/2941575?hl=en&amp;ref_topic=6107456). Vous pouvez également passer en revue les étapes ci-dessous pour commencer.

>[!CAUTION]
>
>[!DNL Google Campaign Manager] les fichiers de données contiennent des données pour tous vos annonceurs ou clients. Si vous devez omettre des clients spécifiques, vous devez modifier les fichiers avant de les rendre disponibles pour [!DNL Audience Manager].

## Fréquence et disponibilité des transferts de données

[!DNL Audience Manager] vérifie et transfère les données une fois par jour. Les données sont généralement disponibles dans [!DNL Audience Manager] après 24 heures.

## Étapes

1. [Créer un groupe](https://support.google.com/dcm/partner/answer/3370419?hl=en&amp;ref_topic=6107456).

   Les groupes contrôlent l&#39;accès à vos données [!DNL Google Campaign Manager]. Vous inviterez et ajouterez éventuellement [!DNL Audience Manager] à ce groupe.

1. [Vérifiez l’état](https://support.google.com/dcm/partner/answer/3370481?hl=en&amp;ref_topic=6107456) de votre Enregistrement Google Cloud.

   L’Enregistrement Google Cloud contient le compartiment de données qui contient vos [!UICONTROL Data Transfer] et [!UICONTROL Match Tables]. Vous devez configurer un compartiment ou vous assurer que votre nouveau groupe a accès à un compartiment d&#39;enregistrement de données existant.

1. [Obtenez une URL](https://support.google.com/dcm/partner/answer/3370482?hl=en&amp;ref_topic=6107456) de fichier de données.

   Contactez votre [!DNL Google Campaign Manager] gestionnaire de compte ou votre consultant en solutions de plateformes. Ils vous fourniront une URL vers vos fichiers de données. [!DNL Google] peut modifier le format des noms de fichier et de compartiment dans les versions ultérieures. Là encore, demandez à votre gestionnaire de compte [!DNL Google Campaign Manager] de vous assurer que vous utilisez les bons formats.

1. [Définissez des autorisations](https://cloud.google.com/storage/docs/cloud-console?csw=1#_bucketpermission) de compartiment.

   [!DNL Cloud Storage Manager] permet de contrôler le partage des données et l&#39;accès au compartiment. Donnez à votre groupe un accès en lecture au compartiment qui contient vos fichiers [!UICONTROL Data Transfer] et [!UICONTROL Match Table].

1. [Configurez le partage](https://support.google.com/dcm/partner/answer/6206106?hl=en) des données.

   Les [!DNL Google Campaign Manager] identifiants utilisateur partagés sont chiffrés afin de protéger la confidentialité. Encryption ajoute 2 colonnes à la fin de votre fichier de transfert de données, `PartnerId1` et `PartnerId2`. Ces colonnes contiennent des ID utilisateur codés spécifiques à chaque société qui reçoit ces fichiers.

   En tant que tiers autorisé, [!DNL Audience Manager] peut recevoir des données [!DNL Google Campaign Manager], mais ne peut pas décoder les ID. Cependant, du côté [!DNL Audience Manager], nous savons comment les identifiants codés correspondent à nos identifiants. Cela signifie que nous pouvons associer et synchroniser les utilisateurs avec confiance et précision.

   >[!NOTE]
   >Vous ne pouvez pas importer de fichiers [!DNL Google Campaign Manager] dans [!DNL Audience Manager] si vous partagez déjà des données avec 2 autres partenaires tiers.

1. Invitez [!DNL Audience Manager] à rejoindre le groupe.

   Après avoir créé un groupe et lui avoir donné accès à un regroupement de données, invitez [!DNL Audience Manager] à le rejoindre. Envoyez une invitation par courrier électronique à DFA-AAM@adobe.com. Veillez à inclure l’URL du fichier de données à l’étape 3. Nos équipes internes travailleront avec vous pour vérifier l&#39;accès après avoir accepté l&#39;invitation. 1. Configurez deux sources de données pour les données [!DNL Google Campaign Manager] dans l&#39;interface utilisateur [!DNL Audience Manager].

   Nommez les sources de données `Advertiser Analytics: DCM Platform` et `Advertiser Analytics: AAM+DCM Platform`. Dans le flux de travaux [Créer des sources de données](../../../features/manage-datasources.md#create-data-source), définissez le type d’ID sur `Cookie`. Partagez les ID des deux nouvelles sources de données avec nos équipes internes.

1. Vous pouvez facilement créer des caractéristiques à partir des fichiers [!DNL Google Campaign Manager] que vous importez dans [!DNL Audience Manager]. Voir [Fichiers journaux utilisables](../../../integration/media-data-integration/actionable-log-files.md) et demandez à votre [!DNL Audience Manager] consultant ou au service à la clientèle d&#39;activer la fonction pour vous.
