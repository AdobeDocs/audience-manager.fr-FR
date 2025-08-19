---
description: Champs obligatoires, syntaxe et règles à suivre lors du formatage d’un fichier de données de caractéristiques entrant.
solution: Audience Manager
title: Contenu du fichier de données entrant - Syntaxe, caractères non valides, variables et exemples
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
source-git-commit: dbb557928a296d3dd5f0646644e2ca0cdc11dfdc
workflow-type: tm+mt
source-wordcount: '1210'
ht-degree: 3%

---

# Contenu du fichier de données entrant : syntaxe, caractères non valides, variables et exemples {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Champs obligatoires, syntaxe et règles à suivre lors du formatage d’un fichier de données de caractéristiques entrant.

## Syntaxe du contenu du fichier {#file-content-syntax}

Les champs du fichier de données entrant doivent apparaître dans l’ordre indiqué ci-dessous. Dans cet exemple, les symboles `<` `>` ont été ajoutés pour aider à séparer visuellement chaque élément. Vous n’avez pas besoin de les inclure dans votre fichier de données.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Pour les autres formats de contenu de fichier acceptés, voir [Intégrations de partenaires personnalisées](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Nous avons une limite de 200 lignes que nous pouvons traiter pour chaque ID utilisateur envoyé dans le fichier de données entrant. Par exemple, si vous envoyez 300 lignes pour un identifiant utilisateur, les 200 premières lignes sont conservées et les 100 lignes supplémentaires sont ignorées. Dans l’exemple ci-dessous, tout va bien, car vous envoyez 3 lignes chacune pour les ID d’utilisateur 1 et 2. Nous n’imposons pas de limite au nombre de caractéristiques ou de paires clé-valeur que vous incluez dans une ligne.
>
>```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Variables de fichier définies {#file-variables-defined}

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
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Un identifiant utilisateur peut être : </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">ID d’utilisateur unique attribué par <span class="keyword"> </span> Audience Manager ( <a href="../../../reference/ids-in-aam.md"> UUID Audience Manager </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Un identifiant utilisateur unique attribué dans votre système CRM ( <a href="../../../reference/ids-in-aam.md"> DPUUID, dans Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Identifiant d’appareil mobile Android ou iOS dans sa forme d’origine non modifiée, tel qu’exposé par le système d’exploitation mobile. </li> 
     </ul> </p> <p>Pour les identifiants mobiles : </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">Format IDFA : les identifiants doivent être en majuscules et non hachés. Par exemple, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Format Android : les identifiants doivent être en minuscules et non hachés. Par exemple, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Séparez les ID d’utilisateur et de caractéristique par un seul délimiteur de tabulation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>L’identifiant <span class="keyword"> de caractéristique de </span> Audience Manager. Nous vous demandons d’inclure <i>uniquement les caractéristiques intégrées</i> dans les fichiers de données entrants. Nous ne traitons aucun autre type de caractéristique lors du transfert de données entrantes. </p> <p> <p>Remarque : l’ID de caractéristique se trouve à l’aide de la méthode GET qui renvoie des détails sur toutes vos caractéristiques. Pour plus d’informations, voir Méthodes de l’API Trait <a href="../../../api/rest-api-main/api-traits.md"> </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formatage des [!UICONTROL Trait IDs] {#formatting-trait-ids}

Le tableau suivant décrit les préfixes qui identifient les noms ou identifiants [!UICONTROL trait] dans un fichier de données entrant. Voir [exemples de fichiers](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) pour obtenir des exemples.

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
   <td colname="col2"> <p>Le préfixe <code> d_sid </code> indique à notre système que l’identifiant est un identifiant de caractéristique <span class="keyword"> Audience Manager </span>. Il s’agit du même identifiant que celui affiché dans l’interface utilisateur d’. Vous pouvez également renvoyer des identifiants de caractéristique avec la méthode <code> GET </code> de l’API. Voir Méthodes d’API de caractéristique <a href="../../../api/rest-api-main/api-traits.md"> </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Les données dotées du préfixe <code> d_unsid </code> suppriment les utilisateurs de cette caractéristique. Le préfixe <code> d_unsid </code> est ignoré dans un fichier <code> overwrite </code>. </p> <p>Le préfixe <code> d_unsid= </code> indique à notre système que l’identifiant est un identifiant de caractéristique <span class="keyword"> Audience Manager </span>. Il s’agit du même identifiant que celui affiché dans l’interface utilisateur d’. Vous pouvez également renvoyer des identifiants de caractéristique avec la méthode <code> GET </code> de l’API. Voir Méthodes d’API de caractéristique <a href="../../../api/rest-api-main/api-traits.md"> </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> règles de caractéristique vous </a> de définir des critères pour la qualification de la caractéristique. Si vous formatez une règle de caractéristique en tant que <code> ic == trait ID </code>, vous pouvez envoyer des caractéristiques dans une simple liste formatée par des virgules. </p> <p>Supposons, par exemple, que vous créiez ces 3 règles de caractéristique : </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Ces caractéristiques sont associées à la clé <code> ic </code>. Vous pouvez ainsi créer une liste de caractéristiques plus simple dans le fichier de données. De plus, il n’est pas nécessaire d’inclure le préfixe <code> ic </code> . Par conséquent, le contenu de votre fichier de données peut ressembler à ceci : </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Paires clé-valeur </p> </td> 
   <td colname="col2"> <p>Les données de caractéristiques peuvent être formatées en tant que paires clé-valeur à l’aide de chaînes alphanumériques. Il existe plusieurs manières de formater des paires clé-valeur, comme illustré ci-dessous : </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> , <code> "gender"=m </code> , <code> model = "pickup truck" </code> , <code> product = tablet </code> sont tous des exemples de paires clé-valeur correctement formatées. </p> </td> 
  </tr>
 </tbody>
</table>

## Caractères non valides dans les paires [!UICONTROL Trait IDs], [!UICONTROL User IDs] et clé-valeur {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] se composent uniquement de caractères numériques. Nous vous demandons d’inclure *uniquement[!UICONTROL onboarded traits]* dans les fichiers de données entrants. Nous ne traitons aucun autre type de [!UICONTROL trait] lors du transfert de données entrantes.

### [!UICONTROL User IDs]

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
   <td colname="col2"> <p><i>N’utilisez pas </i> signe deux-points codé ( <code> %3A </code>) ou non codé ( : ) dans les DPUUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant de l’appareil Mobile iOS (IDFA) ou Android </p> </td> 
   <td colname="col2"> <p>Les identifiants d’appareil mobile doivent être strictement formatés comme illustré ici : </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">Format IDFA : les identifiants doivent être en majuscules et non hachés. Par exemple, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Format Android : les identifiants doivent être en minuscules et non hachés. Par exemple, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Paires Clé-Valeur

Des noms de valeurs mal formatés dans une paire clé-valeur entraînent également des problèmes. Suivez ces règles lors de la création ou de l’attribution d’un nom à la valeur dans une paire clé-valeur :

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Caractère </th> 
   <th colname="col2" class="entry"> Condition </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Guillemet ( ») </p> </td> 
   <td colname="col2"> <p>Vous pouvez utiliser le guillemet dans la clé et dans la partie valeur de la paire clé-valeur, comme suit : </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Tiret (-) </p> </td> 
   <td colname="col2"> <p>Nous ignorons les tirets au début des clés. Par exemple, <code> -product = camera </code> est interprété comme <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Ne pas utiliser</i> utilisez <code> TAB </code> au lieu de valeurs vides dans les paires clé-valeur. N’utilisez <code> TAB </code> que pour séparer les variables dans le fichier de données entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>N’utilisez pas les nouveaux caractères de ligne ou de tabulation ( <code> \n, \t </code>) dans les clés ou les valeurs. </p> </td> 
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
   <td colname="col1"> <p>Avec <code> d_sid </code> ou <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Ce fichier de données montre un utilisateur qualifié pour les caractéristiques 24, 26, 27 et a été supprimé des caractéristiques 28 et 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Remarque :  <p>Au lieu d_unsid, vous pouvez également supprimer des caractéristiques des profils utilisateur à l’aide de la syntaxe suivante : </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avec <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Ces caractéristiques ont été ajoutées à une règle de caractéristique avec le préfixe <code> ic </code>. Vous pouvez donc les ajouter au fichier de données en les séparant par des virgules, comme illustré ci-dessous. Un onglet sépare l’UUID et les identifiants de caractéristique. Le préfixe <code> ic </code> n’est pas requis dans le fichier . </p> <p><b>Identifiants numériques</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>ID de chaîne</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Avec des paires clé-valeur </p> </td> 
   <td colname="col2"> Ces données de fichier utilisent des paires clé-valeur pour transmettre des données à <span class="keyword">’</span> Audience Manager. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Télécharger](assets/ftp_dpm_1234_1445374061.overwrite) l’exemple de fichier de données si vous avez besoin d’exemples supplémentaires. Le fichier de téléchargement a une extension de fichier `.overwrite`. Vous pouvez l’ouvrir à l’aide d’un simple éditeur de texte.

## Matrice des exemples {#examples-matrix}

Le graphique ci-dessous présente des exemples de mise en forme correcte de vos fichiers entrants, en fonction du [type d’ID](../../../reference/ids-in-aam.md) et de la méthode par laquelle vous souhaitez ajouter des [!UICONTROL traits] aux profils.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type d’identifiant/opération </th> 
   <th colname="col2" class="entry"> Utilisez d_sid pour ajouter des caractéristiques à un profil utilisateur </th> 
   <th colname="col3" class="entry"> Utilisez d_unsid pour supprimer des caractéristiques d’un profil utilisateur </th> 
   <th colname="col4" class="entry"> Envoi de paires clé-valeur pour ajouter des caractéristiques à un profil utilisateur </th> 
   <th colname="col5" class="entry"> Utiliser le préfixe ic pour ajouter des caractéristiques à un profil utilisateur </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>UUID AUDIENCE MANAGER </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Exemple 1 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Exemple 2 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Exemple 3 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Exemple 4 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Advertising ID pour les appareils Android </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Exemple 5 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Exemple 6 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Exemple 7 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Exemple 8 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA pour les appareils iOS </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Exemple 9 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Exemple 10 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Exemple 11 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Exemple 12 </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Votre propre identifiant CRM (DPUUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Exemple 13 </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Exemple 14 </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Exemple 15 </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Exemple 16 </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemple 1 {#example-1}

Utilisez [!UICONTROL trait IDs] pour envoyer des informations de qualification de [!UICONTROL trait] pour [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Exemple 2 {#example-2}

Utilisez [!UICONTROL trait IDs] pour envoyer [!UICONTROL trait] informations de disqualification pour [!DNL Audience Manager] [!DNL UUIDs].

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

### Exemple 3 {#example-3}

Envoyez des paires clé-valeur pour ajouter des informations de qualification [!UICONTROL trait] pour [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

ou

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Exemple 4 {#example-4}

Utilisez le préfixe `ic` pour envoyer [!UICONTROL trait] informations de qualification pour [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

ou

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Exemple 5 {#example-5}

Utilisez [!UICONTROL trait IDs] pour envoyer des informations de qualification de [!UICONTROL trait] pour les appareils [!DNL Android].

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Exemple 6 {#example-6}

Utilisez [!UICONTROL trait IDs] pour envoyer des informations de disqualification de [!UICONTROL trait] pour les appareils [!DNL Android].

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

### Exemple 7 {#example-7}

Envoyez des paires clé-valeur pour ajouter des informations de qualification [!UICONTROL trait] pour les appareils [!DNL Android].

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Exemple 8 {#example-8}

Utilisez le préfixe `ic` pour envoyer des informations de qualification de [!UICONTROL trait] pour les appareils [!DNL Android].

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

ou

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Exemple 9 {#example-9}

Utilisez [!UICONTROL trait IDs] pour envoyer des informations de qualification de [!UICONTROL trait] pour les appareils [!DNL iOS].

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Exemple 10 {#example-10}

Utilisez [!UICONTROL trait IDs] pour envoyer des informations de disqualification de [!UICONTROL trait] pour les appareils [!DNL iOS].

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

### Exemple 11 {#example-11}

Envoyez des paires clé-valeur pour ajouter des informations de qualification [!UICONTROL trait] pour les appareils [!DNL iOS].

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Exemple 12 {#example-12}

Utilisez le préfixe `ic` pour envoyer des informations de qualification de [!UICONTROL trait] pour les appareils [!DNL iOS].

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

ou

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Exemple 13 {#example-13}

Utilisez [!UICONTROL trait IDs] pour envoyer des informations de qualification de [!UICONTROL trait] pour [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Exemple 14 {#example-14}

Utilisez [!UICONTROL trait IDs] pour envoyer des informations de disqualification de [!UICONTROL trait] pour [!DNL DPUUIDs].

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

### Exemple 15 {#example-15}

Envoyez des paires clé-valeur pour ajouter des informations de qualification [!UICONTROL trait] pour les [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Exemple 16 {#example-16}

Utilisez le préfixe `ic` pour envoyer des informations de qualification de [!UICONTROL trait] pour [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

ou

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Créateur de caractéristiques](../../../features/traits/about-trait-builder.md)
