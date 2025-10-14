---
description: Cette procédure vous guide tout au long des étapes nécessaires pour créer, modifier ou supprimer un groupe de test dans Audience Lab
seo-description: This procedure walks you through the steps needed to create, edit, or delete a test group in Audience Lab
seo-title: Manage Test Groups
solution: Audience Manager
title: Gérer les groupes de tests
uuid: 2fadddeb-7574-4853-8c52-c58456582c62
feature: Audience Lab
exl-id: 1d07c8f1-34dc-4339-bd5d-87042a22f7e9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 0%

---

# Gérer les groupes de tests {#manage-test-groups}

Cette procédure décrit les étapes nécessaires à la création, la modification ou la suppression d’un groupe de test dans [!UICONTROL Audience Lab].

## Créer des groupes de test de segment {#create-test-groups}

### Conditions préalables

<!-- create-test-group.xml -->

* Vous devez avoir au moins une caractéristique **conversion** configurée. Vous pouvez configurer les caractéristiques de conversion dans le [créateur de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md) en sélectionnant **conversion** comme type d’événement. Pour plus d’informations sur les caractéristiques de conversion et sur la manière de les configurer, nous avons préparé une [vidéo](https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html) à votre intention.

  >[!IMPORTANT]
  >
  >[Les caractéristiques de dossier](../../features/traits/about-folder-traits.md) ne sont **pas prises en charge** par [!UICONTROL Audience Lab]. La définition du [Type d’événement](../../features/traits/create-onboarded-rule-based-traits.md) d’une caractéristique de dossier sur **conversion** ne génère aucune donnée en [!UICONTROL Audience Lab] pour cette caractéristique de dossier spécifique.

* Pour les sociétés qui utilisent [contrôle d’accès en fonction du rôle](../../features/administration/administration-overview.md) : attribuez l’autorisation [!UICONTROL Audience Lab] [caractère générique](../../features/administration/administration-overview.md#wild-card-permissions) à **[!UICONTROL User Groups]** pour fournir l’accès. Cette autorisation permet à l’utilisateur de créer et d’afficher les résultats d’un test. Un utilisateur ne pourra utiliser les segments d’une source de données que pour lesquels il dispose de privilèges **lecture** et **mappage à la destination**. L’utilisateur ne pourra utiliser les caractéristiques de conversion que d’une source de données pour laquelle il dispose **’autorisations de lecture** Un utilisateur ne pourra également voir que les destinations auxquelles il a accès. Ainsi, avant d’ajouter l’autorisation de caractère générique [!DNL Audience Lab] à un groupe, assurez-vous que le groupe dispose des éléments suivants :
   * l’accès aux caractéristiques de conversion pertinentes ;
   * accès à la lecture et au mappage des segments pertinents pour les tests ;
   * l&#39;accès aux destinations pertinentes.

Pour créer un [!UICONTROL Segment Test Group] :

1. Sélectionnez **[!UICONTROL Create New Test Group]** dans le tableau de bord [!UICONTROL Audience Lab] pour démarrer l’assistant.
1. **[!UICONTROL Basic Info & Choose Segment]**

   * Remplissez un **[!UICONTROL Test Group Name]** et un **[!UICONTROL Description]**.
   * Sélectionnez le **[!UICONTROL Base Segment]** en accédant à l’explorateur de fichiers ou en saisissant dans la barre de recherche, puis confirmez en appuyant sur **[!UICONTROL Choose Segment.]**
   * Vous pouvez enregistrer le groupe de test en tant que brouillon et reprendre à travailler dessus ultérieurement.
   * Une alerte s’affiche si le segment de base que vous avez sélectionné est déjà utilisé dans d’autres groupes de test. L’utilisation répétée du segment de base peut fausser les résultats de conversion pour les deux tests.

1. **[!UICONTROL Allocate Test Segments]**

   * Vous pouvez créer **jusqu’à 15 segments de test** et diviser le pourcentage d’appareils selon vos besoins.
   * Vous pouvez modifier le nom des segments de test en cliquant dessus.
   * Les pourcentages sont automatiquement divisés de manière égale à 100 % lorsque de nouveaux segments de test sont alloués. Vous pouvez ensuite modifier manuellement les pourcentages. Cochez la case après avoir modifié les pourcentages et assurez-vous qu’ils s’additionnent à 100 %. Sinon, vous ne pourrez pas passer à l’étape suivante.

1. **[!UICONTROL Set a Control Segment]**

   * Sélectionnez un segment témoin si vous souhaitez réserver une certaine partie du segment à utiliser comme population témoin. Les populations témoins vous permettent de voir l’impact des segments de test que vous avez créés par rapport à un banc d’essai.
   * Vous pouvez sélectionner un segment de test comme segment de contrôle dans la liste déroulante ou choisir **[!UICONTROL None]** pour aucun contrôle.
   * Cliquez sur **[!UICONTROL Next]** lorsque vous avez terminé.

1. **[!UICONTROL Select Conversion Traits]**

   * Ajoutez des caractéristiques de conversion en les saisissant dans la fenêtre caractéristique de conversion. Il s’agit d’une étape **obligatoire** et vous ne pouvez pas passer à l’étape suivante à moins d’ajouter au moins une caractéristique de conversion.
   * Vous pouvez ajouter jusqu’à 5 caractéristiques de conversion si vous le souhaitez.
   * Une alerte s’affiche si vous sélectionnez une caractéristique de conversion déjà utilisée pour d’autres groupes de test.
   * Notez qu’Audience Manager ne prend pas en charge l’utilisation de [caractéristiques de dossier](/help/using/features/traits/about-folder-traits.md) comme caractéristiques de conversion. La sélection d’une caractéristique de dossier comme caractéristique de conversion entraîne l’affichage de 0 rapport d’agrégats et de tendances dans le test.

1. **[!UICONTROL Choose Destinations & Dates]**

   * Saisissez les destinations souhaitées dans le champ de recherche ou utilisez la flèche déroulante. [!UICONTROL Audience Lab] segments de test peuvent être envoyés vers des destinations d’URL, de cookie ou de serveur à serveur.
   * Faites glisser et déposez des segments vers les destinations.
   * Après avoir déposé un segment dans une destination , remplissez le **[!UICONTROL Destination Mapping Value]** à l’aveugle.
   * Vous pouvez envoyer le même segment de test à plusieurs destinations et vous pouvez ajouter plusieurs segments de test à une seule destination.
   * Les destinations sont grisées si elles ne sont pas disponibles pour un certain segment de test en fonction des [&#x200B; Contrôles d’exportation de données &#x200B;](../../features/data-export-controls.md).
   * Les utilisateurs verront uniquement les destinations auxquelles ils ont accès en fonction du [Groupe d’utilisateurs RBAC](../../features/administration/administration-overview.md) auquel ils appartiennent.
   * Enfin, vous devez sélectionner une date de début pour votre groupe de test. Cette date marque le début de la période au cours de laquelle votre groupe de test sera publié vers les destinations. Sélectionnez **Aucune date de fin** pour une comparaison indéfinie des segments de test.

   >[!NOTE]
   >
   >Les [!UICONTROL Profile Merge Rules] avec un profil authentifié ne sont pris en charge que dans les destinations en temps réel. Si un segment de test avec une règle de fusion de profil de cette configuration est envoyé à une destination serveur à serveur basée sur des fichiers, les audiences peuvent ne pas être renseignées.

   Cliquez sur **[!UICONTROL Next]** pour examiner et finaliser votre groupe de test.

1. **[!UICONTROL Summary & Finalize]**

   * Passez en revue les informations que vous avez ajoutées lors des étapes précédentes et sélectionnez **[!UICONTROL Finalize Group]**.
   * N’oubliez pas qu’une fois que vous avez finalisé un groupe de test, il peut être dupliqué ou supprimé, mais pas modifié.

   >[!NOTE]
   >* Vous pouvez enregistrer les groupes de test à tout moment du processus de création et revenir à l’assistant ultérieurement. Le statut du groupe de test est **[!UICONTROL Draft]** et le groupe de test n’envoie aucune donnée aux destinations tant que vous n’avez pas finalisé le groupe de test de segment.
   >* Pour les brouillons de tests, vous pouvez revenir en arrière et modifier les groupes de tests en cliquant sur **[!UICONTROL Edit]** dans la vignette de groupe de tests de la vue principale de l’[!UICONTROL Audience Lab].

## Modifier les groupes de test de segment {#edit-test-groups}

Dans [!UICONTROL Audience Lab], vous ne pouvez modifier que les brouillons de groupes de test. Dans l’assistant de [!UICONTROL Create Segment Test Group], vous pouvez enregistrer votre groupe de test en tant que brouillon et reprendre à travailler dessus ultérieurement.

1. Accédez à la vue principale [!UICONTROL Audience Lab].
1. Recherchez vos brouillons de groupes de test et sélectionnez le contrôle de **[!UICONTROL Edit]** dans la vignette de groupe de test.
1. Reprenez l’assistant [Créer un groupe de test de segment](../../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) et sélectionnez **[!UICONTROL Finalize Group]** lorsque vous avez terminé.

## Supprimer les groupes de test de segment {#delete-test-groups}

1. Accédez à la vue principale [!UICONTROL Audience Lab].
1. Recherchez le groupe de test à supprimer. Vous pouvez effectuer l’une des opérations suivantes :

   * appuyez sur la commande **[!UICONTROL Delete]** dans la carte groupe de test, ou
   * appuyez sur le titre du groupe de test dans la carte groupe de test pour accéder à la vue [Informations sur le groupe de test](../../features/audience-lab/audience-lab-information-view.md) et appuyez sur la commande **[!UICONTROL Delete]** dans la barre de titre.

1. Pour les [segments de test terminés](../../features/audience-lab/audience-lab.md#status), une alerte vous invitera à télécharger le fichier CSV pour enregistrer les rapports si vous le souhaitez.
