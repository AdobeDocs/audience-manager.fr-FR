---
description: Cet article décrit deux fonctionnalités qui offrent des fonctionnalités avancées pour le modèle d'allocation dupliquée Audience Lab et le segment Holdout.
seo-description: Cet article décrit deux fonctionnalités qui offrent des fonctionnalités avancées pour le modèle d'allocation dupliquée Audience Lab et le segment Holdout.
seo-title: Fonctionnalité d'Audience Lab Advanced
solution: Audience Manager
title: Fonctionnalité d'Audience Lab Advanced
uuid: 0 f 57 d 634-caa 0-40 da -81 a 2-c 23 fbd 299 bfd 299
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# [!DNL Audience Lab] Fonctionnalité avancée {#audience-lab-advanced-functionality}

This article describes two features which provide advanced functionality for [!DNL Audience Lab]: [!DNL Duplicate Allocation Template] and [!DNL Segment Holdout].

## Duplicate Allocation Template {#duplicate-allocation-template}

<!-- 
<p>The <b>Allocation Template</b> represents how you split a test group into test segments and the way the test segments are mapped to destinations. </p>
 -->

In [!DNL Audience Lab], the [!DNL Allocation Template] represents the various selections you make when creating a test group:

* Répartition des périphériques entre les segments de test ;
* Mappage des segments de test aux destinations ;
* Caractéristiques de conversion que vous utilisez pour un groupe de test ;
* période dans laquelle le groupe de test est publié dans les destinations sélectionnées.

En dupliquant un modèle d&#39;allocation, vous pouvez réutiliser la même répartition des segments de test et des destinations pour un autre segment de base, dans un nouveau groupe de test. Voici un exemple de modèle d&#39;allocation illustré ci-dessous. The image is taken from the [!UICONTROL Summary & Finalize] step in the **Create Test Group** workflow.

![](assets/allocation_template_3.png)

<!--
With the option to duplicate allocation templates, you can increase your productivity when running multivariate tests as part of multivariate campaigns.
-->

### Utilisation du modèle d&#39;allocation en double

Create an initial test group, then select **[!UICONTROL Duplicate Allocation Template]** to reuse the same settings across multiple test groups. Vous pouvez, par exemple, utiliser cette fonctionnalité si vous exécutez un test où vous souhaitez déterminer l&#39;efficacité de plusieurs destinations pour plusieurs segments.

1. Dans la vue principale Audience Lab, recherchez le groupe de test dont vous souhaitez reproduire le modèle d&#39;allocation dans un nouveau groupe de test. In the drop-down box, select **[!UICONTROL Duplicate Allocation Template]**.

   ![](assets/duplicate-allocation-template.png)

2. In the [!UICONTROL Create Test Group] wizard, you can specify a base segment and rename your test segments, if you wish.
3. You *cannot* modify:

   * Répartition des périphériques entre les segments de test ;
   * Caractéristique (s) de conversion ;
   * Mappage des segments de test aux destinations. Vous pouvez uniquement remplir la clé de mappage pour les destinations qui en requièrent un.
   * période dans laquelle votre groupe de test sera publié sur vos destinations sélectionnées.

4. Review the information you added in the previous steps and select **[!UICONTROL Finalize Group]**.

## Test Segment Holdout {#test-segment-holdout}

>[!NOTE]
>
>[!UICONTROL Test Segment Holdout] est une fonctionnalité avancée activée sur demande client. Please contact [!DNL Customer Care] or [!DNL Adobe Consulting] to activate this feature.

Utilisez cette fonctionnalité pour empêcher l&#39;inclusion du public dans le test. Le pourcentage que vous sélectionnez est abandonné du test. Vous pouvez ainsi mesurer et comparer le nombre de conversions depuis les audiences ciblées (activé sur les destinations) et les audiences non ciblées (groupe de groupe).

<!--
<p>Note that this option is different to the control segment because it subtracts the percentage ................. You can withhold an audience group and still use a control segment. </p>
-->

### Utilisation du segment de test Holdout

1. Create a new test group by using the [!UICONTROL Create Test Group] wizard.
1. In the **[!UICONTROL Allocate Test Segment]** step, you can select a part of the audience to be withheld from testing.

   ![Elément de liste](assets/test-segment-holdout.png)

1. Utilisez le curseur pour ajuster le nombre d&#39;appareils que vous souhaitez empêcher de tester. Notez comment le segment Test 1 et le segment test 2 ne réalisent désormais que 70 % des périphériques totaux.

   ![](assets/test-segment-holdout-selected.png)

1. Go through the rest of the steps in the **[!UICONTROL Create Test Group]** workflow and select **[!UICONTROL Finalize Group]** when you&#39;re satisfied with your selection. Vous disposez maintenant d&#39;un groupe de test avec une partie de l&#39;audience conservée du test.
