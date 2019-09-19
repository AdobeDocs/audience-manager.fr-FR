---
description: Champs, syntaxe et règles obligatoires à respecter lors du formatage d’un fichier de données de caractéristiques entrant.
seo-description: Champs, syntaxe et règles obligatoires à respecter lors du formatage d’un fichier de données de caractéristiques entrant.
seo-title: Syntaxe du contenu du fichier de données entrant, caractères, variables et exemples non valides
solution: Audience Manager
title: Syntaxe du contenu du fichier de données entrant, caractères, variables et exemples non valides
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
translation-type: tm+mt
source-git-commit: 5a822460f93bb7295edafff03104ae7626b69a51

---


#  Contenu du fichier de données entrantes : Syntaxe, Caractères non valides, Variables et exemples{#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Champs, syntaxe et règles obligatoires à respecter lors du formatage d’un fichier de données de caractéristiques entrant.

## Syntaxe du contenu du fichier {#file-content-syntax}

Les champs du fichier de données entrant doivent apparaître dans l’ordre indiqué ci-dessous. Dans cet exemple, les `<` symboles `>` ont été ajoutés afin de séparer visuellement chaque élément. Vous n’avez pas besoin de les inclure dans votre fichier de données.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Pour consulter d’autres formats de contenu de fichier acceptés, voir Intégrations [de partenaires](/help/using/integration/sending-audience-data/custom-partner-integrations.md)personnalisés.

>[!NOTE]
>
>Nous avons une limite de 200 lignes que nous pouvons traiter pour chaque ID utilisateur envoyé dans le fichier de données entrant. Par exemple, si vous envoyez 300 lignes pour un ID utilisateur, les 200 premières lignes sont conservées et les 100 lignes supplémentaires sont ignorées. Dans l’exemple ci-dessous, vous êtes bien, car vous envoyez 3 lignes chacune pour l’ID utilisateur 1 et l’ID utilisateur 2. Nous n’imposons pas de limite au nombre de caractéristiques ou de paires clé-valeur que vous incluez dans une ligne.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Définition des variables de fichier {#file-variables-defined}

Le tableau répertorie et définit les variables utilisées dans un fichier de données entrant correctement formaté. Le format *italique* indique un espace réservé variable.

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
   <td colname="col2"> <p>Un ID utilisateur peut être : </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">ID utilisateur unique attribué par <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> UUID Audience Manager </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">ID utilisateur unique affecté dans votre système de gestion de la relation client ( <a href="../../../reference/ids-in-aam.md"> DPUUID, dans Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">ID de périphérique mobile Android ou iOS dans son formulaire d’origine, non modifié, tel qu’il est révélé par le système d’exploitation mobile. </li> 
     </ul> </p> <p>Pour les ID mobiles : </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Format IDFA : Les identifiants doivent être en majuscules et non pas hachés. Par exemple, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Format Android : Les ID doivent être en minuscules et non en hachage. Par exemple, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TABULATION </code> </p> </td> 
   <td colname="col2"> <p>Séparez l’ID utilisateur et les ID de caractéristiques à l’aide d’un délimiteur de tabulation unique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ID de <i>caractéristique </i></code> </p> </td> 
   <td colname="col2"> <p>ID de <span class="keyword"> caractéristique d’Audience Manager </span> . Nous vous demandons d’inclure <i>uniquement des caractéristiques</i> intégrées dans les fichiers de données entrants. Nous ne traitons aucun autre type de caractéristique dans le transfert de données entrant. </p> <p> <p>Remarque :  L’ID de caractéristique peut être trouvé en utilisant la méthode GET qui renvoie des détails sur toutes vos caractéristiques. Pour plus d’informations, voir Méthodes de l’API <a href="../../../api/rest-api-main/api-traits.md"> de caractéristiques </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatage des ID de caractéristiques {#formatting-trait-ids}

Le tableau suivant décrit les préfixes qui identifient les noms ou les ID de caractéristiques dans un fichier de données entrant. Voir les [exemples de fichiers](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) pour en savoir plus.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Préfixe </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p>Le <code> préfixe d_sid </code> indique à notre système que l’ID est un <span class="keyword"> identifiant </span> de caractéristique d’Audience Manager. Il s’agit du même ID que celui qui est affiché dans l’interface utilisateur. Vous pouvez également renvoyer des ID de caractéristiques à l’aide de la méthode <code> GET de l’API </code> . Voir Méthodes de l’API <a href="../../../api/rest-api-main/api-traits.md"> de caractéristiques </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Les données avec le préfixe <code> d_unsid </code> enlèvent les utilisateurs de cette caractéristique. Le <code> préfixe d_unsid </code> est ignoré dans un <code> </code> fichier de remplacement. </p> <p>Le <code> _unsid= </code> indique à notre système que l’ID est un <span class="keyword"> identifiant </span> de caractéristique d’Audience Manager. Il s’agit du même ID que celui qui est affiché dans l’interface utilisateur. Vous pouvez également renvoyer des ID de caractéristiques à l’aide de la méthode <code> GET de l’API </code> . Voir Méthodes de l’API <a href="../../../api/rest-api-main/api-traits.md"> de caractéristiques </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Les règles de caractéristiques vous </a> permettent de définir des critères pour la qualification des caractéristiques. Si vous mettez en forme une règle de caractéristiques sous la forme <code> ic == ID de caractéristique </code>, vous pouvez envoyer des caractéristiques dans une simple liste au format virgule. </p> <p>Supposons, par exemple, que vous créiez les 3 règles de caractéristiques suivantes : </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Ces caractéristiques sont associées à la <code> clé </code> ic. Vous pouvez ainsi créer une liste de caractéristiques plus simple dans le fichier de données. Et vous n’avez pas besoin d’inclure le <code> préfixe </code> ic. Par conséquent, le contenu de votre fichier de données peut se présenter comme suit : </p> <p>
     <code> 
                       
      ID <i>utilisateur</i>&lt;TAB&gt; 123 456 789 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paires clé-valeur </p> </td> 
   <td colname="col2"> <p>Les données de caractéristiques peuvent être formatées sous forme de paires clé-valeur à l’aide de chaînes alphanumériques. Il existe plusieurs méthodes de formatage des paires clé-valeur, comme illustré ci-dessous : </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = valeur </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "genre"=m </code> , <code> modèle = "pick up pick up pick" </code> , <code> produit = tablette </code> sont tous des exemples de paires clé-valeur correctement formatées. </p> </td> 
  </tr>
 </tbody>
</table>

## Caractères non valides dans les ID de caractéristiques, les ID utilisateur et les paires clé-valeur {#invalid-chars}

### ID de caractéristiques

Les identifiants de caractéristiques sont constitués uniquement de caractères numériques. Nous vous demandons d’inclure *uniquement des caractéristiques* intégrées dans les fichiers de données entrants. Nous ne traitons aucun autre type de caractéristique dans le transfert de données entrant.

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
   <td colname="col2"> <p><i>N'utilisez pas</i> de deux-points codés ( <code> %3A </code>) ni de deux-points non codés ( : ) dans les DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de périphérique mobile iOS (IDFA) ou Android </p> </td> 
   <td colname="col2"> <p>Les ID de périphérique mobile doivent être strictement formatés, comme illustré ici : </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Format IDFA : Les identifiants doivent être en majuscules et non pas hachés. Par exemple, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Format Android : Les ID doivent être en minuscules et non en hachage. Par exemple, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Paires clé-valeur

Des noms de valeur mal formatés dans une paire clé-valeur posent également problème. Suivez les règles suivantes lorsque vous créez ou nommez la valeur dans une paire clé-valeur :

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caractère </th> 
   <th colname="col2" class="entry"> Condition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Caractère de devis (") </p> </td> 
   <td colname="col2"> <p>Vous pouvez utiliser le caractère de guillemet dans la clé et dans la partie valeur de la paire clé-valeur, comme suit : </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caractère tiret (-) </p> </td> 
   <td colname="col2"> <p>Nous ignorons les signes de tirets au début des clés. Par exemple, <code> -product = camera </code> est interprété comme <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TABULATION </code> </p> </td> 
   <td colname="col2"> <p><i>N’utilisez pas</i> l’ <code> onglet </code> au lieu de valeurs vides dans les paires clé-valeur. Utilisez uniquement <code> TAB </code> pour séparer les variables dans le fichier de données entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>N’utilisez pas les nouveaux caractères de ligne ou de tabulation ( <code> \n, \t </code>) dans les clés ou dans les valeurs. </p> </td> 
  </tr>
 </tbody>
</table>

## Exemples de fichiers de données {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Format du fichier de données </th> 
   <th colname="col2" class="entry"> Description et exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Avec <code> _sid </code> ou <code> _unsid </code> </p> </td> 
   <td colname="col2"> <p>Ce fichier de données montre un utilisateur qualifié pour les caractéristiques 24, 26, 27 et a été supprimé des caractéristiques 28 et 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d sid=26,d_sid=27,d_unsid=28,d_unsid=29 </code> </p> <p>Remarque :  <p>Au lieu d’utiliser d_unsid, vous pouvez également supprimer des caractéristiques des profils utilisateur en utilisant la syntaxe suivante : </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;;nbsp;29: 1 </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avec <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Ces caractéristiques ont été ajoutées à une règle de caractéristiques avec le <code> préfixe </code> ic. Vous pouvez ainsi les ajouter au fichier de données en les séparant par des virgules, comme indiqué. Un onglet sépare l’UUID et les ID de caractéristique. Le <code> préfixe ic </code> n’est pas obligatoire dans le fichier. </p> <p><b>ID numériques</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30 626 </code> </p> <p><b>ID de chaîne</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avec des paires clé-valeur </p> </td> 
   <td colname="col2"> Ces données de fichier utilisent des paires clé-valeur pour transmettre les données à <span class="keyword"> Audience Manager </span>. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;"gender"="femelle","luxe_shopper"="yes"" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Téléchargez](assets/ftp_dpm_1234_1445374061.overwrite) le fichier de données d’exemple si vous avez besoin d’exemples supplémentaires. Le fichier de téléchargement a une extension de `.overwrite` fichier. Vous pouvez l’ouvrir dans un éditeur de texte simple.

## Exemple de matrice {#examples-matrix}

Le graphique ci-dessous présente des exemples de la manière appropriée de formater vos fichiers entrants, selon le [type d’ID](../../../reference/ids-in-aam.md) et la méthode d’ajout de caractéristiques aux profils.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’ID / Opération </th> 
   <th colname="col2" class="entry"> Utiliser d_sid pour ajouter des caractéristiques à un profil utilisateur </th> 
   <th colname="col3" class="entry"> Utiliser d_unsid pour supprimer des caractéristiques d’un profil utilisateur </th> 
   <th colname="col4" class="entry"> Envoyer des paires clé-valeur pour ajouter des caractéristiques à un profil utilisateur </th> 
   <th colname="col5" class="entry"> Utilisation du préfixe ic pour ajouter des caractéristiques à un profil utilisateur </th> 
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
   <td colname="col1"> <p>Identifiant Google Advertising pour périphériques Android </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Exemple 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Exemple 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Exemple 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Exemple 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA pour les périphériques iOS </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Exemple 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Exemple 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Exemple 10 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Exemple 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Votre propre ID CRM (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Exemple 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Exemple 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Exemple 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Exemple 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Example 1 {#example-1}

Utilisez les ID de caractéristique pour envoyer des informations de qualification de caractéristiques pour les UUID d’Audience Manager.

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Example 2 {#example-2}

Utilisez les ID de caractéristique pour envoyer des informations de disqualification pour les UUID d’Audience Manager.

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

Envoyez des paires clé-valeur pour ajouter des informations de qualification de caractéristiques pour les UUID d’Audience Manager.

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

ou

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 4 {#example-4}

Utilisez le préfixe ic pour envoyer des informations de qualification de caractéristiques pour les UUID d’Audience Manager.

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

ou

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Example 5 {#example-5}

Utilisez les ID de caractéristique pour envoyer des informations de qualification de caractéristique pour les périphériques Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 6 {#example-6}

Utilisez les ID de caractéristique pour envoyer des informations sur la disqualification des caractéristiques pour les périphériques Android.

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

Envoyez des paires clé-valeur pour ajouter des informations de qualification des caractéristiques pour les périphériques Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 8 {#example-8}

Utilisez le préfixe ic pour envoyer des informations de qualification des caractéristiques pour les périphériques Android.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Example 9 {#example-9}

Utilisez les ID de caractéristiques pour envoyer des informations de qualification de caractéristiques pour les périphériques iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 10 {#example-10}

Utilisez les ID de caractéristique pour envoyer des informations sur la disqualification des caractéristiques pour les périphériques iOS.

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

Envoyez des paires clé-valeur pour ajouter des informations de qualification des caractéristiques pour les périphériques iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Example 12 {#example-12}

Utilisez le préfixe ic pour envoyer des informations de qualification des caractéristiques pour les périphériques iOS.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Example 13 {#example-13}

Utilisez des ID de caractéristique pour envoyer des informations de qualification de caractéristique pour les DPUUID.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Example 14 {#example-14}

Utilisez les ID de caractéristique pour envoyer des informations sur la disqualification des caractéristiques pour les DPUUID.

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

Envoyez des paires clé-valeur pour ajouter des informations de qualification des caractéristiques pour les DPUUID.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Example 16 {#example-16}

Utilisez le préfixe ic pour envoyer des informations de qualification des caractéristiques pour les DPUUID.

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORE_LIKE_This]
>
>* [Générateur de caractéristiques](../../../features/traits/about-trait-builder.md)

