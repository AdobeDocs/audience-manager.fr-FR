---
description: Ce rapport renvoie un nombre de fréquences de toutes les informations inutilisées collectées dans votre inventaire et envoyées à l’Audience Manager.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Rapport Signaux inutilisés
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 8fd148df6c19a5d8331faf66c671f91686954a77
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 1%

---

# Rapport Signaux inutilisés{#unused-signals-report}

Ce rapport renvoie un nombre de fréquences de toutes les informations inutilisées collectées dans votre inventaire et envoyées à l’Audience Manager. Pour accéder à ce rapport, sélectionnez **Analytics > Rapports d’audience > Autres rapports > Signaux inutilisés**.

>[!NOTE]
>
>Si le message &quot;Vous n’avez pas accès aux rapports d’audience&quot; s’affiche, contactez votre consultant d’Audience Manager ou l’assistance clientèle pour qu’il mette le rapport à votre disposition.

![Capture d’écran du rapport Signaux inutilisés](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Présentation

Un signal est une information de votre site web transmise à [!DNL Audience Manager] sous la forme de [paires clé-valeur](../../reference/key-value-pairs-explained.md) (par exemple, `color=blue, price>100, gender=female`, etc.).

Les signaux inutilisés se composent de données que vous collectez mais qui n’ont pas été mappées à une caractéristique. Le rapport [!UICONTROL Unused Signals] présente les données d’un tableau par date, clé, valeur et nombre de fréquence. Tout signal non mappé transmis à [!DNL Audience Manager] au moins 100 fois par jour est admissible pour le rapport [!UICONTROL Unused Signals]. Les signaux inutilisés sont stockés pendant 45 jours, puis ignorés.

Consultez ce rapport pour identifier les signaux orphelins qui peuvent être mappés à des caractéristiques nouvelles ou existantes.

>[!NOTE]
>
>Indiquez un nom de clé ou de valeur dans les champs de recherche pour limiter les résultats à des enregistrements spécifiques.

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
   <td colname="col1"> <p><b> Garantir l’unité des caractéristiques ou Ajouter des valeurs associées à une clé unique</b> </p> </td> 
   <td colname="col2"> <p>Consultez le rapport afin de tenir compte de différentes variations de valeur pour un signal particulier. </p> <p>Par exemple, supposons que vous ayez une caractéristique pour l’état "Caroline du Nord" définie dans une paire clé-valeur comme <code> c_state = North Carolina</code>. Le rapport peut vous aider à trouver des variantes de nom et à les ajouter à la caractéristique (par exemple, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Vous pouvez également repérer les variantes de nom avec le rapport et les remplacer par une valeur uniforme sur tous les sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Créer de nouvelles caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Consultez le rapport pour savoir quelles nouvelles valeurs sont transmises sur une clé spécifique. Vous pouvez créer de nouvelles paires clé-valeur en fonction de ces nouvelles valeurs. </p> <p> <p>Remarque : Consultez le rapport toutes les deux semaines pour connaître les valeurs qui changent fréquemment (par exemple, les programmes, les campagnes, les célébrités, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Rechercher des valeurs non mappées</b> </p> </td> 
   <td colname="col2"> <p>Examinez le rapport pour le numéro 1. Le nombre 1 dans un rapport <span class="wintitle"> Signaux inutilisés</span> représente une valeur nulle. Ce n'est pas nécessairement mauvais. Cela signifie simplement qu’une clé spécifique n’a pas de mappage de valeur associé. Lorsque vous voyez de nombreuses valeurs pour une variable importante, vérifiez auprès de l’équipe de votre site que toutes vos pages sont correctement balisées. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bonnes pratiques

Exécutez et vérifiez le rapport [!UICONTROL Unused Signals] :

* Après avoir créé une caractéristique ou mis à jour des règles de caractéristique, Cela permet de vous assurer que vos caractéristiques et vos règles sont correctement configurées. Le nombre 1 dans les résultats indique qu’une nouvelle caractéristique peut ne pas être configurée correctement.
* Bi-hebdomadaire ou mensuel. Les révisions planifiées permettent de s’assurer que les mappages de caractéristiques sont à jour.

>[!NOTE]
>
>Lors de la recherche de valeurs inutilisées dans le rapport, veuillez tenir compte des points suivants. Il existe une différence d’expression entre les deux exemples ci-dessous :

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Les deux exemples présentent une caractéristique qui contient deux paires clé-valeur v et a. La première expression se traduit par : la caractéristique contient la clé v avec la valeur 1 [!UICONTROL AND NOT] la clé a avec la valeur 23. La seconde expression contient la clé v avec la valeur 1 [!UICONTROL AND] la clé a avec la valeur [!UICONTROL NOT EQUAL] 23.
* En tenant compte des deux expressions différentes ci-dessus, supposons que vous recherchiez dans le [!UICONTROL Unused Signals Report] les valeurs transmises à la clé a avec une valeur différente de 23, vous obtiendrez uniquement des résultats dans le premier cas, car les valeurs de la clé n’ont pas été envoyées À TOUS. Dans le deuxième cas, des valeurs différentes de 23 ont été envoyées, de sorte que la clé a n’est pas inutilisée.

## Création de caractéristiques en bloc

Contactez votre représentant Partenaires en solutions si vous devez créer en masse de nombreuses caractéristiques en fonction des données obtenues à partir du rapport [!UICONTROL Unused Signals].
