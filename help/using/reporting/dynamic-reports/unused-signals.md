---
description: Ce rapport renvoie un nombre de fréquence de toutes les informations inutilisées collectées sur votre stock et envoyées à Audience Manager.
seo-description: Ce rapport renvoie un nombre de fréquence de toutes les informations inutilisées collectées sur votre stock et envoyées à Audience Manager.
seo-title: Rapport Signaux inutilisés
solution: Audience Manager
title: Rapport Signaux inutilisés
uuid: 04334a5c-3e21-44db-b971-0b4457685e9a
translation-type: tm+mt
source-git-commit: dcc44161df89b44ca1a234070c4afbb0210dc723

---


# Rapport Signaux inutilisés{#unused-signals-report}

Ce rapport renvoie un nombre de fréquence de toutes les informations inutilisées collectées sur votre stock et envoyées à Audience Manager. Pour accéder à ce rapport, sélectionnez **Analytics > Rapports d’audience > Autres rapports > Signaux** inutilisés.

>[!NOTE]
>
>Si le message &quot;Vous n’avez pas accès aux rapports Audience&quot; s’affiche, contactez votre conseiller Audience Manager ou le service à la clientèle pour que le rapport vous soit fourni.

![Capture d&#39;écran du rapport Signaux inutilisés](/help/using/reporting/dynamic-reports/assets/unused-signals.png)

## Aperçu

Un signal est une information de votre site Web transmise à [!DNL Audience Manager] sous la forme de paires [valeur-](../../reference/key-value-pairs-explained.md) clé (ex. `color=blue, price>100, gender=female`, etc.).

Les signaux inutilisés sont constitués de données que vous collectez mais que vous n’avez pas mappées à une caractéristique. Le [!UICONTROL Unused Signals] rapport affiche les données dans un tableau par date, clé, valeur et nombre de fréquences. Tout signal non mappé transmis [!DNL Audience Manager] au moins 100 fois par jour est admissible pour le [!UICONTROL Unused Signals] rapport.

Consultez ce rapport pour identifier les signaux orphelins qui peuvent être mappés à des caractéristiques nouvelles ou existantes.

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
   <td colname="col1"> <p><b>Vérifier l’uniformité des caractéristiques ou ajouter des valeurs associées à une clé unique</b> </p> </td> 
   <td colname="col2"> <p>Consultez le rapport pour tenir compte des différentes variations de valeur pour un signal particulier. </p> <p>Par exemple, supposons que vous ayez une caractéristique pour l’état "Caroline du Nord" définie dans une paire clé-valeur comme <code> c_state = North Carolina</code>. Le rapport peut vous aider à trouver des variantes de nom et à les ajouter à la caractéristique (par exemple, <code> c_state = North Carolina, NC, N.C., NCarolina</code>). Vous pouvez également repérer les variantes de nom avec le rapport et les remplacer par une valeur uniforme sur tous les sites. </p> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Créer de nouvelles caractéristiques</b> </p> </td> 
   <td colname="col2"> <p>Consultez le rapport pour savoir quelles nouvelles valeurs sont transmises sur une clé particulière. Vous pouvez créer de nouvelles paires clé-valeur en fonction de ces nouvelles valeurs. </p> <p> <p>Remarque :  Consultez le rapport toutes les deux semaines pour connaître les valeurs qui changent fréquemment (par exemple, les émissions, les campagnes, les célébrités, etc.). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Rechercher des valeurs non mappées</b> </p> </td> 
   <td colname="col2"> <p>Vérifiez le numéro 1 du rapport. Le nombre 1 dans un rapport Signaux <span class="wintitle"></span> inutilisés représente une valeur nulle. Ce n'est pas nécessairement mauvais. Cela signifie simplement qu’une clé spécifique n’est pas associée à un mappage de valeurs. Lorsque vous voyez un grand nombre de valeurs pour une variable importante, vérifiez auprès de votre équipe de site que toutes vos pages sont correctement balisées. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bonnes pratiques

Exécutez et vérifiez le [!UICONTROL Unused Signals] rapport :

* Une fois que vous avez créé une caractéristique ou mis à jour les règles de caractéristiques. Cela permet de s’assurer que vos caractéristiques et règles sont correctement configurées. Le nombre 1 dans les résultats indique qu’une nouvelle caractéristique peut ne pas être correctement configurée.
* Bi-hebdomadaire ou mensuel. Les révisions planifiées permettent de s’assurer que les mappages de caractéristiques sont à jour.

>[!NOTE]
>
>Lors de la recherche de valeurs inutilisées dans le rapport, tenez compte des points suivants. Il existe une différence d’expression entre les deux exemples suivants :

* T(v=1 [!UICONTROL AND NOT] (a=23))
* T(v=1 [!UICONTROL AND] (a!=23))
* Les deux exemples présentent un trait qui contient deux paires clé-valeur v et a. La première expression se traduit par : la caractéristique contient la clé v avec la valeur 1 [!UICONTROL AND NOT] la clé a avec la valeur 23. La deuxième expression contient la clé v avec la valeur 1 [!UICONTROL AND] la clé a avec la valeur [!UICONTROL NOT EQUAL] 23.
* Compte tenu des deux expressions différentes ci-dessus, supposons que vous recherchiez dans la [!UICONTROL Unused Signals Report] section les valeurs qui sont transmises à la clé a avec une valeur différente de 23, vous obtiendrez uniquement des résultats dans le premier cas, car les valeurs de clé n’ont pas été envoyées À TOUT. Dans le deuxième cas, des valeurs différentes de 23 ont été envoyées, de sorte que la clé a n’est pas inutilisée.

## Création de caractéristiques en bloc

Contactez votre représentant Solutions partenaires si vous devez créer en bloc de nombreuses caractéristiques en fonction des données obtenues à partir du [!UICONTROL Unused Signals] rapport.
