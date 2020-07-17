---
description: Dans le créateur de destinations, la section Configuration contient les champs Domaine du cookie et Publier les données vers. Vous pouvez ainsi créer des règles pour déterminer si une destination définit un cookie ou renvoie un cookie. Domaine des cookies et données de publication Pour travailler indépendamment les uns des autres et sont facultatifs. Vous pouvez créer une destination de cookie sans les utiliser.
seo-description: Dans le créateur de destinations, la section Configuration contient les champs Domaine du cookie et Publier les données vers. Vous pouvez ainsi créer des règles pour déterminer si une destination définit un cookie ou renvoie un cookie. Domaine des cookies et données de publication Pour travailler indépendamment les uns des autres et sont facultatifs. Vous pouvez créer une destination de cookie sans les utiliser.
seo-title: Paramètres facultatifs pour les destinations de cookie
solution: Audience Manager
title: Paramètres facultatifs pour les destinations de cookie
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 7%

---


# Paramètres facultatifs pour les destinations de cookie {#optional-settings-cookies}

Dans [!UICONTROL Destination Builder], [!UICONTROL Configuration section] contient les [!UICONTROL Cookie Domain] champs et [!UICONTROL Publish Data To] . Vous pouvez ainsi créer des règles pour déterminer si une destination définit un cookie ou renvoie un cookie. [!UICONTROL Cookie Domain] et [!UICONTROL Publish Data To] travaillent indépendamment les uns des autres et sont facultatifs. Vous pouvez créer une destination de cookie sans les utiliser.

## Domaine du cookie : Syntaxe et exemples {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domaine du cookie </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Syntaxe</b> </p> </td> 
   <td colname="col2"> <p>Le champ Domaine <span class="wintitle"> du</span> cookie accepte une chaîne de texte simple qui vous permet de définir des cookies sur un domaine spécifié ou sur tous les domaines. Lors de l’utilisation de cette fonctionnalité : </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Définissez un seul domaine pour chaque destination de cookie. N’entrez pas plusieurs domaines dans le champ Domaine <span class="wintitle"> du</span> cookie. Créez plutôt une autre <span class="wintitle"> destination</span> . </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">N’utilisez pas de caractères génériques. </li> 
     </ul> </p> <p> Laissez le champ Domaine <span class="wintitle"> du</span> cookie vide pour définir un cookie sur tous les domaines. Il s’agit du paramètre par défaut. </p> <p>Pour définir des cookies sur un domaine et sous-domaines spécifiques : </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Entrez le nom du domaine dans le champ Domaine <span class="wintitle"> du</span> cookie. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Début le nom de domaine avec un point. Par exemple, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">The <code> https://www</code> prefix is not required. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exemple</b> </p> </td> 
   <td colname="col2"> <p>En guise d'exemple, supposons que nous ayons un site fictif appelé sports.com. Sports.com a des domaines pour le golf, le baseball et le football. Pour définir un cookie dans tous les domaines sportifs, saisissez-le dans la zone Domaine <span class="wintitle"> du</span> cookie, comme indiqué ci-dessous : </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Cela indique à <span class="keyword"> l’Audience Manager</span> de définir un cookie dans tout domaine qui contient le modèle <code><i>something</i></code>.sports.com. Pour obtenir un ensemble d’exemples plus complexe, voir ci-dessous. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemples de domaines de cookies complexes

Ces exemples vous montrent si [!DNL Audience Manager] vous allez définir un cookie en fonction de la configuration de l’ [!UICONTROL Cookie Domain] option.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Site Web </th> 
   <th colname="col2" class="entry">Domaine du cookie : .sports.com <p>Jeu de cookies </p> </th> 
   <th colname="col3" class="entry">Domaine du cookie : .golf.sports.com <p>Jeu de cookies </p> </th> 
   <th colname="col4" class="entry">Domaine du cookie : Vierge <p>Jeu de cookies </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Oui </td> 
   <td colname="col3"> Non </td> 
   <td colname="col4"> Oui </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Oui </td> 
   <td colname="col3"> Oui </td> 
   <td colname="col4"> Oui </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Oui </td> 
   <td colname="col3"> Non </td> 
   <td colname="col4"> Oui </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> Non </td> 
   <td colname="col3"> Non </td> 
   <td colname="col4"> Oui </td> 
  </tr> 
 </tbody> 
</table>

## Publier les données vers {#publish-data-to}

Les [!UICONTROL Publish Data To] paramètres renvoient un cookie si le domaine répond aux critères définis par les options sélectionnées. Les options incluent :

* **[!UICONTROL All of our domains]**: (Valeur par défaut) Renvoie une valeur [!DNL cookie] pour tout domaine.
* **[!UICONTROL Only the selected domains]**: Renvoie un cookie uniquement pour les domaines sélectionnés dans la liste de domaines.
* **[!UICONTROL All of our domains except the selected domains]**: Empêche les domaines sélectionnés de recevoir un [!DNL cookie]message. Tous les autres domaines peuvent recevoir un [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Créer une destination de cookie](../../features/destinations/create-cookie-destination.md)