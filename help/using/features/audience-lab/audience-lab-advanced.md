---
description: Cet article décrit deux fonctions qui offrent des fonctionnalités avancées pour le modèle d'allocation des Duplicata du laboratoire d'Audiences et le délai d'attente des segments.
seo-description: Cet article décrit deux fonctions qui offrent des fonctionnalités avancées pour le modèle d'allocation des Duplicata du laboratoire d'Audiences et le délai d'attente des segments.
seo-title: Fonctionnalités avancées d'Audience Lab
solution: Audience Manager
title: Fonctionnalités avancées d'Audience Lab
uuid: 0f57d634-caa0-40da-81a2-c23fbd299bfd
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---


# [!DNL Audience Lab] Fonctionnalités avancées {#audience-lab-advanced-functionality}

Cet article décrit deux fonctionnalités avancées pour [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] et [!DNL Segment Holdout].

## Modèle d’allocation de Duplicata {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

Dans [!DNL Audience Lab], la [!DNL Allocation Template] représente les différentes sélections que vous effectuez lors de la création d’un groupe de tests :

* la répartition des dispositifs entre les segments d&#39;essai ;
* la mise en correspondance des segments de test avec les destinations ;
* Les caractéristiques de conversion que vous utilisez pour un groupe de tests ;
* Plage de dates au cours de laquelle le groupe de tests publie vers les destinations sélectionnées.

En dupliquant un modèle d’attribution, vous pouvez réutiliser la même distribution de segments et de destinations de test pour un segment de base différent, dans un nouveau groupe de test. Un exemple de modèle d’allocation est illustré ci-dessous. L’image est prise à partir de l’ [!UICONTROL Summary & Finalize] étape du processus de **création d’un groupe** de tests.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Utilisation du modèle d’allocation de Duplicata

Créez un groupe de tests initial, puis choisissez **[!UICONTROL Duplicate Allocation Template]** de réutiliser les mêmes paramètres pour plusieurs groupes de tests. Par exemple, vous pouvez utiliser cette fonctionnalité si vous exécutez un test dans lequel vous souhaitez déterminer l’efficacité de plusieurs destinations pour plusieurs segments.

1. Dans la vue principale du laboratoire d&#39;Audiences, recherchez le groupe de tests dont vous souhaitez reproduire le modèle d&#39;allocation dans un nouveau groupe de tests. Dans la liste déroulante, sélectionnez **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. Dans l’ [!UICONTROL Create Test Group] assistant, vous pouvez spécifier un segment de base et renommer vos segments de test, si vous le souhaitez.
3. Vous *ne pouvez pas* modifier :

   * la répartition des dispositifs entre les segments d&#39;essai ;
   * la ou les caractéristiques de conversion ;
   * Mappage des segments de test vers les destinations. Vous pouvez uniquement renseigner la clé de mappage pour les destinations qui en ont besoin.
   * Période au cours de laquelle votre groupe de test publiera vers les destinations sélectionnées.

4. Passez en revue les informations que vous avez ajoutées lors des étapes précédentes et sélectionnez **[!UICONTROL Finalize Group]**.

## Extraction de segment de test {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] est une fonctionnalité avancée, activée sur demande du client. Veuillez contacter [!DNL Customer Care] ou [!DNL Adobe Consulting] activer cette fonction.

Utilisez cette fonction pour empêcher une partie de l’audience d’être incluse dans le test. Le pourcentage que vous sélectionnez n’est pas pris en compte dans le test. Ainsi, vous pouvez mesurer et comparer le nombre de conversions à partir d’audiences ciblées (activées sur les destinations) et non ciblées (groupe d’exclusion).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Utilisation de l&#39;exclusion de segment de test

1. Créez un groupe de tests à l’aide de l’ [!UICONTROL Create Test Group] assistant.
1. Dans l’ **[!UICONTROL Allocate Test Segment]** étape, vous pouvez sélectionner une partie de l’audience à exclure du test.

   ![Article Liste](assets/test-segment-holdout.png)

1. Utilisez le curseur pour régler le nombre de périphériques que vous souhaitez tenir hors test. Notez comment Test Segment 1 et Test Segment 2 ne représentent désormais que 70 % du total des périphériques.

   ![](assets/test-segment-holdout-selected.png)

1. Passez en revue les autres étapes du **[!UICONTROL Create Test Group]** processus et sélectionnez **[!UICONTROL Finalize Group]** lorsque votre sélection vous convient. Vous disposez maintenant d’un groupe de test dont une partie de l’audience est exclue du test.
