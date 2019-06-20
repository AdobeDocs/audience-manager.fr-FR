---
description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de test dans Audience Lab
seo-description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de test dans Audience Lab
seo-title: Gestion des groupes de test
solution: Audience Manager
title: Gestion des groupes de test
uuid: 2 fadddeb -7574-4853-8 c 52-c 58456582 c 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Test Groups {#manage-test-groups}

This procedure walks you through the steps needed to create, edit, or delete a test group in [!UICONTROL Audience Lab].

## Create Segment Test Groups {#create-test-groups}

### Conditions préalables

<!-- create-test-group.xml -->

* You need to have at least one **conversion trait** set up. You can set up conversion traits in the [Trait Builder](../../features/traits/create-onboarded-rule-based-traits.md), by selecting **conversion** as the event type. For more information on what conversion traits are and how to set them up, we prepared a [video](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) for you.

   >[!IMPORTANT]
   >
   >[Les caractéristiques](../../features/traits/about-folder-traits.md) de dossier **ne sont pas prises en charge** par [!UICONTROL Audience Lab]. Setting the [Event Type](../../features/traits/create-onboarded-rule-based-traits.md) of a folder trait to **conversion** will not generate any data in [!UICONTROL Audience Lab] for that specific folder trait.

* For companies using [Role-Based Access Control](../../features/administration/administration-overview.md): Assign the [!UICONTROL Audience Lab] [wildcard permission](../../features/administration/administration-overview.md#wild-card-permissions) to **[!UICONTROL User Groups]** to provide access. Cette autorisation permet à l&#39;utilisateur de créer et d&#39;afficher les résultats d&#39;un test. A user will only be able to use segments from a data source they have **read** and **map to destination** privileges for. The user will only be able to use conversion traits from a data source for which they have **&quot;read&quot;** permissions. Un utilisateur peut uniquement visualiser les destinations auxquelles ils ont accès. So, before adding the [!DNL Audience Lab] wildcard permission to a group, make sure the group has:
   * accès pour lire les caractéristiques de conversion appropriées ;
   * accès pour lire et mapper les segments pertinents pour les tests ;
   * accès aux destinations pertinentes.

To create a new [!UICONTROL Segment Test Group]:

1. Select **[!UICONTROL Create New Test Group]** in the [!UICONTROL Audience Lab] dashboard to start the wizard.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Fill in a **[!UICONTROL Test Group Name]** and a **[!UICONTROL Description]**.
   * Choose the **[!UICONTROL Base Segment]** either by navigating in the file browser or by typing in the search bar, confirm by pressing **[!UICONTROL Choose Segment.]**
   * Vous pouvez enregistrer le groupe de test en tant que brouillon et reprendre le travail dessus ultérieurement.
   * Une alerte s&#39;affiche si le segment de base que vous avez sélectionné est déjà utilisé dans d&#39;autres groupes de test. L&#39;utilisation simultanée du segment de base peut distordre les résultats de conversion pour les deux tests.

1. **[!UICONTROL Allocate Test Segments]**

   * You can create **up to 15 test segments** and divide the percentage of devices as you wish.
   * Vous pouvez modifier le nom des segments de test en cliquant dessus.
   * Les pourcentages se divisent automatiquement à 100 % lorsque de nouveaux segments de test sont alloués. Vous pouvez ensuite modifier manuellement les pourcentages. Cochez la case après avoir modifié les pourcentages et veillez à ajouter jusqu&#39;à 100 % ; sinon, vous ne pourrez pas passer à l&#39;étape suivante.

1. **[!UICONTROL Set a Control Segment]**

   * Sélectionnez un segment de contrôle si vous souhaitez ajouter une partie spécifique du segment à utiliser comme groupe de contrôle. Les groupes de contrôle vous permettent de voir l&#39;impact des segments de test que vous avez créés par rapport à un test de performance.
   * You can select a test segment as control segment in the drop-down list, or you can choose **[!UICONTROL None]** for no control.
   * Click **[!UICONTROL Next]** when you&#39;re done.

1. **[!UICONTROL Select Conversion Traits]**

   * Ajoutez des caractéristiques de conversion en saisissant dans la fenêtre de caractéristique de conversion. This is a **mandatory** step and you cannot proceed to the next step unless you add at least one conversion trait.
   * Vous pouvez ajouter jusqu&#39;à 5 caractéristiques de conversion si vous le souhaitez.
   * Une alerte s&#39;affiche si vous sélectionnez une caractéristique de conversion déjà utilisée pour d&#39;autres groupes de test.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Tapez les destinations souhaitées dans le champ de recherche ou utilisez la flèche déroulante. [!UICONTROL Audience Lab] les segments de test peuvent être envoyés à des destinations URL, cookie ou serveur à serveur.
   * Faites glisser les segments vers les destinations.
   * After dropping a segment in a destination, fill in the **[!UICONTROL Destination Mapping Value]** in the blind.
   * Vous pouvez envoyer le même segment de test à plusieurs destinations et ajouter plusieurs segments de test à une destination unique.
   * Destinations are grayed out if they are not available for a certain test segment based on [Data Export Controls](../../features/data-export-controls.md).
   * Users will only see the destinations they have access to based on the [RBAC User Group](../../features/administration/administration-overview.md) they belong to.
   * Enfin, vous devez sélectionner une date de début pour votre groupe de test. Cette date marque le début de la période dans laquelle votre groupe de tests sera publié sur les destinations. Select **No End Date** for an indefinite comparison of the test segments.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] avec un profil authentifié ne sont pris en charge que dans les destinations en temps réel. Si un segment de test avec une règle de fusion de profil de cette configuration est envoyé à une destination de serveur à serveur basée sur des fichiers, il se peut que les audiences ne remplissent pas.

   Click **[!UICONTROL Next]** to review and finalize your test group.

1. **[!UICONTROL Summary & Finalize]**

   * Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.
   * Rappelez-vous qu&#39;une fois que vous avez finalisé un groupe de test, il peut être dupliqué ou supprimé, mais pas modifié.
   >[!NOTE]
   >* Vous pouvez enregistrer les groupes de tests à tout moment dans le processus de création et revenir à l&#39;assistant ultérieurement. The test group status will be **[!UICONTROL Draft]** and the test group will not send any data to destinations until you finalize the segment test group.
   >* For draft tests, you can go back and edit the test groups by clicking **[!UICONTROL Edit]** in the test group card in the main [!UICONTROL Audience Lab] view.


## Edit Segment Test Groups {#edit-test-groups}

In [!UICONTROL Audience Lab], you are only able to edit draft test groups. In the [!UICONTROL Create Segment Test Group] wizard, you can save your test group as a draft and resume working on it later.

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Search for your draft test groups and select the **[!UICONTROL Edit]** control in the test group card.
1. Resume the [Create Segment Test Group](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) wizard and select **[!UICONTROL Finalize Group]** when you&#39;re done.

## Delete Segment Test Groups {#delete-test-groups}

1. Navigate to the [!UICONTROL Audience Lab] main view.
1. Recherchez le groupe de test que vous souhaitez supprimer. Vous pouvez effectuer l&#39;une des opérations suivantes :

   * press the **[!UICONTROL Delete]** control in the test group card, or
   * press the test group title in the test group card to go to the [Test Group Information](../../features/audience-lab/audience-lab-information-view.md) view and press the **[!UICONTROL Delete]** control in the title bar.

1. For [completed test segments](../../features/audience-lab/audience-lab.md#status), an alert will prompt you to download the CSV file to save the reporting if you wish.
