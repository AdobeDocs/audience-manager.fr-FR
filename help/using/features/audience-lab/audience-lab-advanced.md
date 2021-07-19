---
description: Cet article décrit deux fonctionnalités qui fournissent des fonctionnalités avancées pour le modèle d’attribution en double d’Audience Lab et l’exclusion de segments.
seo-description: Cet article décrit deux fonctionnalités qui fournissent des fonctionnalités avancées pour le modèle d’attribution en double d’Audience Lab et l’exclusion de segments.
seo-title: Fonctionnalités avancées d’Audience Lab
solution: Audience Manager
title: Fonctionnalités avancées d’Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: 'Audience Lab '
exl-id: 40b2c8c2-63c0-485d-8217-beab34d7a7f1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# [!DNL Audience Lab] Fonctionnalité avancée {#audience-lab-advanced-functionality}

Cet article décrit deux fonctionnalités avancées de [!DNL Audience Lab] : [!DNL Duplicate Allocation Template] et [!DNL Segment Holdout].

## Dupliquer le modèle d’attribution {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

Dans [!DNL Audience Lab], [!DNL Allocation Template] représente les différentes sélections que vous effectuez lors de la création d’un groupe de test :

* la répartition des appareils entre les segments de test ;
* le mappage des segments de test aux destinations ;
* la ou les caractéristiques de conversion que vous utilisez pour un groupe de test ;
* La période au cours de laquelle le groupe de test publie sur les destinations sélectionnées.

En dupliquant un modèle d’attribution, vous pouvez réutiliser la même distribution de segments et de destinations de test pour un segment de base différent, dans un nouveau groupe de test. Un exemple de modèle d&#39;attribution est illustré ci-dessous. L’image est extraite de l’étape [!UICONTROL Summary & Finalize] du workflow **Créer un groupe de test**.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Utilisation d’un modèle d’attribution en double

Créez un groupe de test initial, puis sélectionnez **[!UICONTROL Duplicate Allocation Template]** pour réutiliser les mêmes paramètres sur plusieurs groupes de test. Vous pouvez, par exemple, utiliser cette fonction si vous exécutez un test pour déterminer l’efficacité de plusieurs destinations pour plusieurs segments.

1. Dans la vue principale d’Audience Lab, recherchez le groupe de test dont vous souhaitez reproduire le modèle d’attribution dans un nouveau groupe de test. Dans la liste déroulante, sélectionnez **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. Dans l’assistant [!UICONTROL Create Test Group], vous pouvez spécifier un segment de base et renommer vos segments de test, si vous le souhaitez.
3. Vous *ne pouvez pas* modifier :

   * la répartition des appareils entre les segments de test ;
   * la ou les caractéristiques de conversion ;
   * Mappage des segments de test aux destinations. Vous pouvez uniquement remplir la clé de mappage pour les destinations qui en requièrent une.
   * La période au cours de laquelle votre groupe de test publiera vers les destinations sélectionnées.

4. Vérifiez les informations que vous avez ajoutées aux étapes précédentes et sélectionnez **[!UICONTROL Finalize Group]**.

## Extraction de segment test {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] est une fonctionnalité avancée, activée sur demande du client. Veuillez contacter [!DNL Customer Care] ou [!DNL Adobe Consulting] pour activer cette fonctionnalité.

Utilisez cette fonction pour empêcher une partie de l’audience d’être incluse dans le test. Le pourcentage sélectionné est exclu du test. Vous pouvez ainsi mesurer et comparer le nombre de conversions à partir des audiences ciblées (activées sur les destinations) et non ciblées (groupe d’exclusion).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Utilisation de l’exclusion de segment test

1. Créez un groupe de test à l’aide de l’assistant [!UICONTROL Create Test Group].
1. À l’étape **[!UICONTROL Allocate Test Segment]**, vous pouvez sélectionner une partie de l’audience à exclure du test.

   ![Élément de liste](assets/test-segment-holdout.png)

1. Utilisez le curseur pour ajuster le nombre d’appareils que vous souhaitez retirer du test. Notez que les segments 1 et 2 de test ne représentent désormais que 70 % du total des appareils.

   ![](assets/test-segment-holdout-selected.png)

1. Suivez les autres étapes du workflow **[!UICONTROL Create Test Group]** et sélectionnez **[!UICONTROL Finalize Group]** lorsque vous êtes satisfait de votre sélection. Vous disposez maintenant d’un groupe de test avec une partie de l’audience refusée du test.
