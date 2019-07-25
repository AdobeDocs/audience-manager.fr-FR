---
description: Champs obligatoires, syntaxe et règles à suivre lors du formatage d'un fichier de données de caractéristiques entrantes.
seo-description: Champs obligatoires, syntaxe et règles à suivre lors du formatage d'un fichier de données de caractéristiques entrantes.
seo-title: Syntaxe du contenu du fichier de données entrantes, caractères, variables et exemples non valides
solution: Audience Manager
title: Syntaxe du contenu du fichier de données entrantes, caractères, variables et exemples non valides
uuid: 88699 b 29-1502-4183-a 9 a 4-be 70692 a 02 bb
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


# Inbound Data File Contents: Syntax, Invalid Characters, Variables, and Examples{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Champs obligatoires, syntaxe et règles à suivre lors du formatage d'un fichier de données de caractéristiques entrantes.

## File Content Syntax {#file-content-syntax}

Les champs du fichier de données entrantes doivent figurer dans l'ordre indiqué ci-dessous. In this example, the `<` `>` symbols have been added to help separate each element visually. Vous n'avez pas besoin de les inclure dans votre fichier de données.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

For other accepted file content formats, see [Custom Partner Integrations](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Nous sommes limités à 200 lignes pour chaque utilisateur - ID envoyé dans le fichier de données entrantes. Par exemple, si vous envoyez 300 lignes à un utilisateur - id, les 200 premières lignes sont conservées et les 100 lignes supplémentaires sont ignorées. Dans l'exemple ci-dessous, vous êtes bon car vous envoyez 3 lignes chacune pour user - id 1 et user - id 2. Nous n'imposons pas de limite quant au nombre de caractéristiques ou de paires clé-valeur que vous incluez dans une ligne.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## File Variables Defined {#file-variables-defined}

Le tableau répertorie et définit les variables utilisées dans un fichier de données entrantes correctement formaté. Le format *italique* indique un espace réservé variable.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>Identifiant utilisateur </i> </code> </p> </td> 
   <td colname="col2"> <p>Un utilisateur - l'ID peut être : </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">A unique user ID assigned by <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UUID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">A unique user ID assigned in your CRM system ( <a href="../../../reference/ids-in-aam.md"> DPUUID, in Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">ID de périphérique Android ou ios mobile dans le formulaire d'origine non modifié tel qu'il est exposé par le système d'exploitation mobile. </li> 
     </ul> </p> <p>Pour les ID mobiles : </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Format IDFA : Les ID doivent être supérieurs à la casse et non hachés. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Format Android : Les ID doivent être en minuscules et ne pas être hachés. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Séparez l'utilisateur - ID et ID de caractéristique par un seul délimiteur de tabulation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>identifiant de caractéristique </i></code> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> Audience Manager </span> trait ID. We ask that you include <i>only onboarded traits</i> in inbound data files. Nous ne traitons aucun autre type de caractéristique dans le transfert des données entrantes. </p> <p> <p>Remarque : L'ID de caractéristique est accessible à l'aide de la méthode GET qui renvoie des détails sur toutes vos caractéristiques. For more information, see <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatting Trait IDs {#formatting-trait-ids}

Le tableau suivant décrit les préfixes qui identifient les noms ou les ID des caractéristiques dans un fichier de données entrant. See the [sample files](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) for examples.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Préfixe </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_ sid = </code> </p> </td> 
   <td colname="col2"> <p>The <code> d_sid </code> prefix tells our system that the ID is an <span class="keyword"> Audience Manager </span> trait ID. Il s'agit du même ID affiché dans l'interface utilisateur. You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_ unsid = </code> </p> </td> 
   <td colname="col2"> <p>Data prefixed with <code> d_unsid </code> removes users from that trait. The <code> d_unsid </code> prefix is ignored in an <code> overwrite </code> file. </p> <p>The <code> d_unsid= </code> prefix tells our system that the ID is an <span class="keyword"> Audience Manager </span> trait ID. Il s'agit du même ID affiché dans l'interface utilisateur. You can also return trait IDs with the API <code> GET </code> method. See <a href="../../../api/rest-api-main/api-traits.md"> Trait API Methods </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic = </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Les règles de caractéristique </a> vous permettent de définir des critères pour la qualification des caractéristiques. If you format a trait rule as <code> ic == trait ID </code>, you can send in traits in a simple comma formatted list. </p> <p>Par exemple, imaginons que vous créiez ces trois règles de caractéristiques : </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic = = « 123 » </code> </li>
      <li> <code> ic = = « 456 » </code> </li>
      <li> <code> ic = = « 789 » </code> </li>
     </ul> </p> <p>These traits are associated with the <code> ic </code> key. Vous pouvez ainsi créer une liste de caractéristiques plus simple dans le fichier de données. And, you do not need to include the <code> ic </code> prefix. Par conséquent, le contenu de votre fichier de données peut ressembler à ceci : </p> <p>
     <code><i>user - id</i> &lt; TAB &gt; 123,456,789 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paires clé-valeur </p> </td> 
   <td colname="col2"> <p>Les données de caractéristiques peuvent être formatées en tant que paires clé-valeur à l'aide de chaînes alphanumériques. Il existe plusieurs manières de formater des paires clé-valeur, comme illustré ci-dessous : </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> « key » = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = « value » </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> « key » = « value » </code> </li> 
     </ul><code> « age » = « 32 » </code> , <code> « sexe » = m </code> , <code> modèle = « pick pickup truck » </code> , <code> product = tablet </code> sont tous des exemples de paires clé-valeur correctement formatées. </p> </td> 
  </tr>
 </tbody>
</table>

## Invalid Characters in Trait IDs, User IDs and Key-Value Pairs {#invalid-chars}

### ID de caractéristique

Les ID de caractéristique se composent uniquement de caractères numériques. We ask that you include *only onboarded traits* in inbound data files. Nous ne traitons aucun autre type de caractéristique dans le transfert des données entrantes.

### Identifiants d’utilisateurs

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’ID </th> 
   <th colname="col2" class="entry"> Condition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>N'utilisez pas</i> deux points codés ( <code> % 3 A </code>) ou deux-points non codés (: ) dans les dpuuid. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile ios (IDFA) ou ID de périphérique Android </p> </td> 
   <td colname="col2"> <p>Les ID des appareils mobiles doivent être mis en forme de manière strictement formatée, comme indiqué ici : </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Format IDFA : Les ID doivent être supérieurs à la casse et non hachés. For example, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Format Android : Les ID doivent être en minuscules et ne pas être hachés. For example, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Paires clé-valeur

Les noms de valeurs mal formatés dans une paire clé-valeur provoquent également des problèmes. Suivez ces règles lorsque vous créez ou nommez la valeur d'une paire clé-valeur :

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caractère </th> 
   <th colname="col2" class="entry"> Condition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractère guillemet ( ») </p> </td> 
   <td colname="col2"> <p>Vous pouvez utiliser le caractère guillemet-apostrophe dans la clé et dans la partie valeur de la paire clé-valeur, comme suit : </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_ city = « New York », d_ city = « San Francisco » </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> « d_ city » = « New York », « d_ city » = « San Francisco » </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractère tiret (-) </p> </td> 
   <td colname="col2"> <p>Nous ignorons les signes de tiret au début des clés. For example, <code> -product = camera </code> is interpreted as <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>N</i> 'utilisez <code> pas l'onglet TAB </code> au lieu de valeurs vides dans des paires clé-valeur. Only use <code> TAB </code> to separate variables in the inbound data file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \ n,\ t </code> </p> </td> 
   <td colname="col2"> <p>Do not use the new line or tab characters ( <code> \n, \t </code>) in keys or in values. </p> </td> 
  </tr>
 </tbody>
</table>

## Data File Examples {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Format du fichier de données </th> 
   <th colname="col2" class="entry"> Description et exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>With <code> d_sid </code> or <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Ce fichier de données affiche un utilisateur qualifié pour les caractéristiques 24, 26, 27 et a été supprimé de la caractéristique 28 et 29. </p> <p> 
     <code>59767559181262060060278870901087098252 &amp; amp ; nbsp ; &amp; amp ; nbsp ; d_ sid = 24, d_ sid = 26, d_ sid = 27, d_ unsid = 28, d_ unsid = 29 </code>
  </p> <p>Remarque :  <p>Au lieu d'utiliser d_ unsid, vous pouvez également supprimer des caractéristiques des profils utilisateur en utilisant la syntaxe suivante : </p> <p> 
      <code>59767559181262060060278870901087098252 &amp; amp ; nbsp ; 28:0, &amp; amp ; nbsp ; 29:0 </code>
  </p> <p> 
      <code>59767559181262060060278870901087098252 &amp; amp ; nbsp ; 28:-1, &amp; amp ; nbsp ; 29:-1 </code>
  </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>With <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>These traits have been added to a trait rule with the <code> ic </code> prefix. Vous pouvez donc les ajouter au fichier de données en les séparant par des virgules. Un onglet sépare l'UUID et les ID de caractéristique. The <code> ic </code> prefix is not required in the file. </p> <p><b>ID numériques</b> </p> <p> 
     <code>Dbwfoc 3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp ; nbsp ; &amp; amp ; nbsp ; 3060850354,5033850352,30626 </code>
  </p> <p><b>ID de chaîne</b> </p> <p> 
     <code>Dbwfoc 3 dhfmncfbh 2 M 4 F 9 zkjexmnnrdh 2 pxvni 1 &amp; amp ; nbsp ; &amp; amp ; nbsp ; ic = 52, ic = 55 </code>
  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avec paires clé-valeur </p> </td> 
   <td colname="col2"> This file data uses key-value pairs to pass in data to <span class="keyword"> Audience Manager </span>. <p> 
     <code>59767559181262060060278870901087098252 &amp; amp ; nbsp ; « gender » = » femme », « luxury_ shopper » = » yes » </code>
  </p> </td> 
  </tr> 
 </tbody> 
</table>

[Téléchargez](assets/ftp_dpm_1234_1445374061.overwrite) le fichier de données d'exemple si vous avez besoin d'exemples supplémentaires. The download file has a `.overwrite` file extension. Vous pouvez l'ouvrir à l'aide d'un simple éditeur de texte.

## Examples Matrix {#examples-matrix}

The chart below shows examples of the correct way to format your Inbound files, depending on the [type of IDs](../../../reference/ids-in-aam.md) and the method by which you want to add traits to profiles.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d'ID/Opération </th> 
   <th colname="col2" class="entry"> Utiliser d_ sid pour ajouter des caractéristiques à un profil utilisateur </th> 
   <th colname="col3" class="entry"> Utiliser d_ unsid pour supprimer des caractéristiques d'un profil utilisateur </th> 
   <th colname="col4" class="entry"> Envoi de paires clé-valeur pour ajouter des caractéristiques à un profil utilisateur </th> 
   <th colname="col5" class="entry"> Utiliser le préfixe ic pour ajouter des caractéristiques à un profil utilisateur </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID Audience Manager </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Exemple 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Exemple 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Exemple 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Exemple 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de publicité Google pour appareils Android </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Exemple 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Exemple 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Exemple 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Exemple 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA pour les périphériques ios </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Exemple 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Exemple 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Exemple 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Exemple 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Votre propre ID de gestion de la relation client (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Exemple 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Exemple 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Exemple 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Exemple 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example-1}

Utilisez les ID de caractéristique pour envoyer des informations de qualification des caractéristiques pour les UUID d'Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

Utilisez des ID de caractéristique pour envoyer des informations de disqualification de caractéristique pour les UUID d'Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

ou

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

ou

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 3 {#example-3}

Envoyez des paires clé-valeur pour ajouter des informations de qualification des caractéristiques pour les UUID d'Audience Manager.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

ou

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

Utilisez le préfixe ic pour envoyer des informations de qualification des caractéristiques pour les UUID d'Audience Manager.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

ou

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

Utilisez des ID de caractéristique pour envoyer des informations de qualification de caractéristique pour les périphériques Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

Utilisez des ID de caractéristique pour envoyer des informations de disqualification de caractéristique pour les périphériques Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 7 {#example-7}

Envoyez des paires clé-valeur pour ajouter des informations de qualification de caractéristique pour les périphériques Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

Utilisez le préfixe ic pour envoyer des informations de qualification de caractéristique pour les périphériques Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

Utilisez des ID de caractéristique pour envoyer des informations de qualification de caractéristique pour les appareils ios.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

Utilisez des ID de caractéristique pour envoyer des informations de disqualification de caractéristique pour les périphériques ios.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Example 11 {#example-11}

Envoyez des paires clé-valeur pour ajouter des informations de qualification de caractéristique pour les périphériques ios.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

Utilisez le préfixe ic pour envoyer des informations de qualification de caractéristique pour les périphériques ios.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

Utilisez les ID de caractéristique pour envoyer des informations de qualification de caractéristique pour les dpuuid.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

Utilisez des ID de caractéristique pour envoyer des informations de disqualification de caractéristique pour les dpuuid.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Example 15 {#example-15}

Envoyez des paires clé-valeur pour ajouter des informations de qualification de caractéristique pour les dpuuid.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

Utilisez le préfixe ic pour envoyer des informations de qualification de caractéristique pour les dpuuid.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_ LIKE_ THIS]
>
>* [Générateur de caractéristiques](../../../features/traits/about-trait-builder.md)

