---
description: Ce rapport renvoie un décompte de fréquence de toutes les informations inutilisées collectées sur votre inventaire et envoyées à Audience Manager.
seo-description: This report returns a frequency count of all the unused information collected on your inventory and sent to Audience Manager.
seo-title: Unused Signals Report
solution: Audience Manager
title: Rapport Signaux inutilisés
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
feature: Overlap Reports
exl-id: ab5cb5ad-4305-4463-8f56-237b5a2f1f9e
source-git-commit: 9c980b8fd5c3cb6ba7b3031726da726ee5caeec6
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 1%

---

# Rapport Signaux inutilisés{#unused-signals-report}

Ce rapport renvoie un décompte de fréquence de toutes les informations inutilisées collectées sur votre inventaire et envoyées à Audience Manager. Pour accéder à ce rapport, accédez à **Analytics > Rapports d’audience > Autres rapports > Signaux inutilisés**.

>[!NOTE]
>
>Si le message « Vous n’avez pas accès aux rapports d’audience » s’affiche, contactez votre consultant Audience Manager ou l’assistance clientèle pour configurer le rapport.

![Capture d&#39;écran du rapport Signaux inutilisés](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Présentation

Un signal est une information de votre site Web transmise à [!DNL Audience Manager] sous la forme de [paires clé-valeur](../../reference/key-value-pairs-explained.md) (par exemple, `color=blue, price>100, gender=female`, etc.).

Les signaux inutilisés sont constitués des données que vous collectez, mais qui n’ont pas été mappées à une caractéristique. Le rapport [!UICONTROL Unused Signals] affiche les données d’un tableau par date, clé, valeur et nombre de fréquences. Tout signal non mappé transmis à [!DNL Audience Manager] au moins 100 fois par jour est éligible au rapport [!UICONTROL Unused Signals].

Les signaux non utilisés sont stockés pendant 45 jours, puis éliminés. Le rapport Signaux inutilisés affiche les données des 10 derniers jours.

Consultez ce rapport pour identifier les signaux orphelins qui peuvent être associés à des caractéristiques nouvelles ou existantes.

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
   <td colname="col1"> <p><b>Uniformisation des caractéristiques ou ajout de valeurs associées à une seule clé</b> </p> </td> 
   <td colname="col2"> <p>Examinez le rapport pour tenir compte des variations de valeur différentes pour un signal particulier. </p> <p>Supposons, par exemple, que vous ayez une caractéristique pour l’état « Caroline du Nord » défini dans une paire clé-valeur comme <code> c_state = North Carolina</code>. Le rapport peut vous aider à trouver des variantes de nom et à les ajouter à la caractéristique (par exemple, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Vous pouvez également repérer les variantes de nom avec le rapport et les remplacer par une valeur uniforme sur tous les sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Créer de nouvelles caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Consultez le rapport pour voir quelles nouvelles valeurs sont transmises sur une clé particulière. Vous pouvez créer de nouvelles paires clé-valeur en fonction de ces nouvelles valeurs. </p> <p> <p>Remarque : recherchez dans le rapport bimensuel les valeurs qui changent fréquemment (par exemple, émissions, campagnes, célébrités, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Rechercher les valeurs non mappées</b> </p> </td> 
   <td colname="col2"> <p>Examinez le rapport pour le numéro 1. Le nombre 1 dans un rapport <span class="wintitle"> Signaux inutilisés</span> représente une valeur nulle. Ce n'est pas nécessairement mauvais. Cela signifie simplement qu’une clé particulière n’est pas associée à un mappage de valeurs. Lorsque vous voyez beaucoup de valeurs 1 pour une variable importante, contactez l’équipe de votre site pour vous assurer que toutes vos pages sont correctement balisées. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bonnes pratiques

Exécutez et vérifiez le rapport [!UICONTROL Unused Signals] :

* Après avoir créé une caractéristique ou mis à jour les règles de caractéristique. Cela permet de s’assurer que vos caractéristiques et règles sont correctement configurées. Le nombre 1 dans les résultats indique qu’une nouvelle caractéristique peut ne pas être configurée correctement.
* Bi-hebdomadaire ou mensuel. Les révisions planifiées permettent de s’assurer que les mappages des caractéristiques sont à jour.

>[!NOTE]
>
>Lors de la recherche de valeurs inutilisées dans le rapport, veuillez tenir compte de la particularité suivante. Il existe une différence d’expression entre les deux exemples ci-dessous :

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a !=23))
* Les deux exemples montrent une caractéristique qui contient deux paires clé-valeur v et a. La première expression se traduit par : la caractéristique contient la clé v avec la valeur 1 [!UICONTROL AND NOT] la clé a avec la valeur 23. La deuxième expression contient la clé v de valeur 1 [!UICONTROL AND] la clé a de valeur [!UICONTROL NOT EQUAL] 23.
* Compte tenu des deux expressions différentes ci-dessus, supposons que vous recherchiez dans le [!UICONTROL Unused Signals Report] les valeurs qui sont transmises sur la clé a avec n’importe quelle valeur différente de 23, vous n’obtiendrez de résultats que dans le premier cas, car les valeurs de la clé n’ont pas été envoyées du TOUT. Dans le deuxième cas, des valeurs différentes de 23 ont été envoyées, de sorte que la clé a n’est pas inutilisée.

## Création de caractéristiques en bloc

Contactez votre représentant Partner Solutions si vous devez créer en bloc de nombreuses caractéristiques en fonction des données obtenues à partir du rapport [!UICONTROL Unused Signals].
