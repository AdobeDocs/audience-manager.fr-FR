---
description: Ce rapport renvoie un nombre de fréquence de toutes les informations inutilisées collectées sur votre inventaire et envoyé à Audience Manager.
seo-description: Ce rapport renvoie un nombre de fréquence de toutes les informations inutilisées collectées sur votre inventaire et envoyé à Audience Manager.
seo-title: Rapport Signaux inutilisés
solution: Audience Manager
title: Rapport Signaux inutilisés
uuid: 04334 a 5 c -3 e 21-44 db-b 971-0 b 4457685 e 9 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Unused Signals Report{#unused-signals-report}

Ce rapport renvoie un nombre de fréquence de toutes les informations inutilisées collectées sur votre inventaire et envoyé à Audience Manager.

<!-- 

c_unused_signals.xml

 -->

## Rapport Signaux inutilisés

A signal is information from your website passed in to [!DNL Audience Manager] in the form of [key-value pairs](../../reference/key-value-pairs-explained.md) (e.g., `color=blue, price>100, gender=female`, etc.).

Les signaux inutilisés consistent en données que vous collectez mais que vous n&#39;avez pas associées à une caractéristique. The [!UICONTROL Unused Signals] report shows data in a table by date, key, value, and frequency count. Any unmapped signal passed in to [!DNL Audience Manager] at least 100 times in a day qualifies for the [!UICONTROL Unused Signals] report.

Examinez ce rapport pour identifier les signaux orphelins qui peuvent être associés à des caractéristiques nouvelles ou existantes.

>[!NOTE]
>
>Spécifiez un nom de clé ou de valeur dans les champs de recherche pour limiter les résultats à des enregistrements spécifiques.

## Cas d’utilisation

<table id="table_E5EE0EC078E14EF4B197243488517A2D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exemples </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Vérifier l'uniformité des caractéristiques ou ajouter des valeurs associées à une clé unique</b> </p> </td> 
   <td colname="col2"> <p>Examinez le rapport pour tenir compte des variations de valeur différentes pour un signal particulier. </p> <p>For example, say you have a trait for the state "North Carolina" defined in a key-value pair as <code> c_state = North Carolina</code>. The report can help you find name variants and add those to the trait (e.g., <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Vous pouvez également remplacer les variantes de noms par le rapport et remplacer celles qui ont une valeur uniforme sur tous les sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Créer des caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Examinez le rapport pour voir quelles nouvelles valeurs sont transmises sur une clé particulière. Vous pouvez créer de nouvelles paires clé-valeur basées sur ces nouvelles valeurs. </p> <p> <p>Remarque : Vérifiez le rapport toutes les deux semaines pour les valeurs qui changent fréquemment (par exemple, affichages, campagnes, célébrités, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Rechercher des valeurs non mappées</b> </p> </td> 
   <td colname="col2"> <p>Examinez le rapport du numéro 1. The number 1 in an <span class="wintitle"> Unused Signals</span> report represents a null value. Ce n'est pas nécessairement mauvais. Cela signifie simplement qu'une clé particulière n'a pas de correspondance de valeur associée. Lorsque vous voyez un grand nombre de valeurs pour une variable importante, vérifiez auprès de l'équipe de votre site que toutes vos pages sont correctement balisées. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bonnes pratiques

Run and check the [!UICONTROL Unused Signals] report:

* Après avoir créé une caractéristique ou des règles de caractéristique de mise à jour. Cela garantit la configuration appropriée de vos caractéristiques et de vos règles. Le nombre 1 dans les résultats indique qu&#39;une nouvelle caractéristique peut ne pas être configurée correctement.
* « Bi-hebdomadaire ou mensuel ». Les révisions planifiées garantissent que les correspondances de caractéristiques sont à jour.

>[!NOTE]
>
>Lorsque vous recherchez des valeurs inutilisées dans le rapport, veuillez tenir compte des particularités suivantes. Il existe une différence d&#39;expression entre les deux exemples ci-dessous :

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Both examples show a trait which contains two key-value pairs v and a. The first expression translates into: the trait contains key v with the value 1 [!UICONTROL AND NOT] the key a with the value 23. The second expression contains key v with the value 1 [!UICONTROL AND] the key a with the value [!UICONTROL NOT EQUAL] 23.
* Considering the two different expressions above, let&#39;s say you search in the [!UICONTROL Unused Signals Report] for the values that get passed on key a with any value different than 23, you&#39;ll only obtain results in the first case because values for key were not sent AT ALL. Dans le deuxième cas, les valeurs différentes de 23 étaient envoyées de sorte que la clé a n&#39;était pas inutilisée.

## Création de caractéristiques en bloc

Contact your Partner Solutions representative if you need to bulk create a lot of traits based on data obtained from the [!UICONTROL Unused Signals] report.
