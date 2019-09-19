---
description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de tests dans Audience Lab.
seo-description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de tests dans Audience Lab.
seo-title: Gestion des groupes de tests
solution: Audience Manager
title: Gestion des groupes de tests
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Gestion des groupes de tests {#manage-test-groups}

Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de tests dans [!UICONTROL Audience Lab].

## Création de groupes de tests de segments {#create-test-groups}

### Conditions préalables

<!-- create-test-group.xml -->

* Vous devez avoir au moins une caractéristique **de** conversion configurée. Vous pouvez configurer des caractéristiques de conversion dans le créateur [de](../../features/traits/create-onboarded-rule-based-traits.md)caractéristiques en sélectionnant **la conversion** comme type d’événement. Pour plus d'informations sur les caractéristiques de conversion et comment les configurer, nous avons préparé une [vidéo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) pour vous.

   >[!IMPORTANT]
   >
   >[Les caractéristiques](../../features/traits/about-folder-traits.md) des dossiers **ne sont pas prises en charge** par [!UICONTROL Audience Lab]. La définition du type [d’](../../features/traits/create-onboarded-rule-based-traits.md) événement d’une caractéristique de dossier sur la **conversion** [!UICONTROL Audience Lab] ne génère aucune donnée pour cette caractéristique de dossier spécifique.

* Pour les entreprises qui utilisent le contrôle [d'accès basé sur](../../features/administration/administration-overview.md)un rôle : Attribuez l’autorisation [!UICONTROL Audience Lab] [de caractères génériques à](../../features/administration/administration-overview.md#wild-card-permissions) **[!UICONTROL User Groups]** fournir l’accès. Cette autorisation permet à l’utilisateur de créer et d’afficher les résultats d’un test. Un utilisateur ne pourra utiliser que les segments d’une source de données pour laquelle il a **lu** et **mappé les privilèges de destination** . L’utilisateur ne pourra utiliser que les caractéristiques de conversion d’une source de données pour laquelle il dispose des autorisations de **"lecture"** . Un utilisateur ne pourra voir que les destinations auxquelles il a également accès. Ainsi, avant d’ajouter l’autorisation de [!DNL Audience Lab] caractère générique à un groupe, assurez-vous que le groupe a :
   * l'accès à la lecture des caractéristiques de conversion pertinentes;
   * l'accès à la lecture et à la cartographie des segments pertinents pour les tests;
   * accès aux destinations appropriées.

Pour créer une nouvelle [!UICONTROL Segment Test Group]:

1. Sélectionnez **[!UICONTROL Create New Test Group]** dans le [!UICONTROL Audience Lab] tableau de bord pour démarrer l’assistant.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Remplissez un **[!UICONTROL Test Group Name]** et un **[!UICONTROL Description]**.
   * Choisissez l’élément **[!UICONTROL Base Segment]** en naviguant dans le navigateur de fichiers ou en saisissant dans la barre de recherche, confirmez en appuyant sur **[!UICONTROL Choose Segment.]**
   * Vous pouvez enregistrer le groupe de tests en tant que brouillon et reprendre ultérieurement son travail.
   * Une alerte s’affiche au cas où le segment de base sélectionné serait déjà utilisé dans d’autres groupes de tests. L’utilisation du segment de base deux fois peut fausser les résultats de conversion pour les deux tests.

1. **[!UICONTROL Allocate Test Segments]**

   * Vous pouvez créer **jusqu’à 15 segments** de test et diviser le pourcentage de périphériques comme vous le souhaitez.
   * Vous pouvez modifier le nom des segments de test en cliquant dessus.
   * Les pourcentages sont automatiquement répartis uniformément entre 100 % lorsque de nouveaux segments de test sont alloués. Vous pouvez ensuite modifier manuellement les pourcentages. Cochez la case après avoir modifié les pourcentages et assurez-vous qu’ils atteignent 100 %, sinon vous ne pourrez pas passer à l’étape suivante.

1. **[!UICONTROL Set a Control Segment]**

   * Sélectionnez un segment de contrôle si vous souhaitez réserver une partie du segment à utiliser comme groupe de contrôle. Les groupes de contrôle vous permettent de voir l’impact des segments de test que vous avez créés par rapport à un test de référence.
   * Vous pouvez sélectionner un segment de test en tant que segment de contrôle dans la liste déroulante, ou choisir **[!UICONTROL None]** de ne pas le contrôler.
   * Cliquez **[!UICONTROL Next]** quand vous avez terminé.

1. **[!UICONTROL Select Conversion Traits]**

   * Ajoutez des caractéristiques de conversion en saisissant dans la fenêtre Caractéristiques de conversion. Il s’agit d’une étape **obligatoire** et vous ne pouvez pas passer à l’étape suivante à moins d’ajouter au moins une caractéristique de conversion.
   * Vous pouvez ajouter jusqu’à 5 caractéristiques de conversion si vous le souhaitez.
   * Une alerte s’affiche au cas où vous sélectionneriez une caractéristique de conversion déjà utilisée pour d’autres groupes de tests.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Entrez les destinations de votre choix dans le champ de recherche ou utilisez la flèche déroulante. [!UICONTROL Audience Lab] les segments de test peuvent être envoyés vers des URL, des cookies ou des destinations serveur à serveur.
   * Faites glisser des segments vers des destinations.
   * Après avoir déposé un segment dans une destination, renseignez le champ **[!UICONTROL Destination Mapping Value]** en aveugle.
   * Vous pouvez envoyer le même segment de test à plusieurs destinations et ajouter plusieurs segments de test à une seule destination.
   * Les destinations sont grisées si elles ne sont pas disponibles pour un certain segment de test en fonction des contrôles [d’exportation de](../../features/data-export-controls.md)données.
   * Les utilisateurs ne verront que les destinations auxquelles ils ont accès en fonction du groupe [d’utilisateurs](../../features/administration/administration-overview.md) RBAC auquel ils appartiennent.
   * Enfin, vous devez sélectionner une date de début pour votre groupe de tests. Cette date marque le début de la période pendant laquelle votre groupe de tests sera publié vers les destinations. Sélectionnez **Aucune date** de fin pour une comparaison indéfinie des segments de test.
   >[!NOTE]
   >
   >[!UICONTROL Profile Merge Rules] avec un profil authentifié sont uniquement pris en charge dans les destinations en temps réel. Si un segment de test avec une règle de fusion de profil de cette configuration est envoyé vers une destination serveur à serveur basée sur des fichiers, les audiences peuvent ne pas être renseignées.

   Cliquez sur **[!UICONTROL Next]** pour revoir et finaliser votre groupe de tests.

1. **[!UICONTROL Summary & Finalize]**

   * Passez en revue les informations que vous avez ajoutées lors des étapes précédentes et sélectionnez **[!UICONTROL Finalize Group]**.
   * N’oubliez pas qu’une fois que vous avez finalisé un groupe de test, il peut être dupliqué ou supprimé, mais pas modifié.
   >[!NOTE]
   >* Vous pouvez enregistrer les groupes de test à tout moment du processus de création et revenir à l’assistant ultérieurement. L’état du groupe de tests sera **[!UICONTROL Draft]** défini et le groupe de tests n’enverra aucune donnée vers les destinations tant que vous n’aurez pas terminé le groupe de tests de segments.
   >* Pour les tests préliminaires, vous pouvez revenir en arrière et modifier les groupes de tests en cliquant sur **[!UICONTROL Edit]** dans la carte du groupe de tests dans la vue principale [!UICONTROL Audience Lab] .


## Modifier les groupes de tests de segments {#edit-test-groups}

Dans [!UICONTROL Audience Lab], vous ne pouvez modifier que les groupes de tests préliminaires. Dans l’ [!UICONTROL Create Segment Test Group] assistant, vous pouvez enregistrer votre groupe de tests en tant que brouillon et reprendre ultérieurement son travail.

1. Accédez à la vue [!UICONTROL Audience Lab] principale.
1. Recherchez vos groupes de tests préliminaires et sélectionnez le **[!UICONTROL Edit]** contrôle dans la carte du groupe de tests.
1. Reprenez l’assistant [Créer un groupe](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) de test de segment et sélectionnez **[!UICONTROL Finalize Group]** lorsque vous avez terminé.

## Supprimer des groupes de test de segment {#delete-test-groups}

1. Accédez à la vue [!UICONTROL Audience Lab] principale.
1. Recherchez le groupe de tests à supprimer. Vous pouvez effectuer l’une des opérations suivantes :

   * appuyez sur la **[!UICONTROL Delete]** commande dans la carte du groupe de tests, ou
   * appuyez sur le titre du groupe de test dans la carte du groupe de test pour accéder à la vue Informations [du groupe de](../../features/audience-lab/audience-lab-information-view.md) test et appuyez sur la **[!UICONTROL Delete]** commande dans la barre de titre.

1. Pour les segments [de test](../../features/audience-lab/audience-lab.md#status)terminés, une alerte vous invitera à télécharger le fichier CSV afin d’enregistrer les rapports si vous le souhaitez.
