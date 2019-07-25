---
description: Décrit les champs obligatoires, la syntaxe et les conventions d'attribution de noms utilisées pour la synchronisation des identifiants basés sur les fichiers. Nommez et organisez le contenu de votre fichier conformément à ces spécifications.
seo-description: Décrit les champs obligatoires, la syntaxe et les conventions d'attribution de noms utilisées pour la synchronisation des identifiants basés sur les fichiers. Nommez et organisez le contenu de votre fichier conformément à ces spécifications.
seo-title: Exigences en matière de nom et de contenu pour les fichiers de synchronisation d’identifiants
solution: Audience Manager
title: Exigences en matière de nom et de contenu pour les fichiers de synchronisation d’identifiants
uuid: bfe 42 af 9-9149-4 da 3-830 e-f 227 c 4 e 610 c 2
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Exigences en matière de nom et de contenu pour les fichiers de synchronisation d’identifiants {#name-and-content-requirements-for-id-synchronization-files}

Décrit les champs obligatoires, la syntaxe et les conventions d'attribution de noms utilisées pour la synchronisation des identifiants basés sur les fichiers. Nommez et organisez le contenu de votre fichier conformément à ces spécifications.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document indique les éléments et options du code. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## File Name Syntax and Examples {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

Les noms des fichiers d'ID contiennent les éléments obligatoires et facultatifs suivants :

`adobe_id_`*`MASTERDPID_DPID[_DPID_DPID`*`]_`*`TIMESTAMP`*`.sync[.`*`SPLIT_NUMBER`*`][.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_ id</code> </p> </td> 
   <td colname="col2"> <p>Préfixe statique qui identifie le fichier comme un fichier d'ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> L'ID du fournisseur de données maître est l'identifiant parent des DPIDS dans le fichier - name. En outre, le premier utilisateur - id dans le fichier de données correspond à l'ID maître. Les DPIDS suivants sont d'autres identifiants qui appartiennent au gabarit. La synchronisation associe les DPIDS du fichier - nom aux UUID du fichier. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>ID du fournisseur de données. Ces identifiants représentent les entités ou les sources de données associées au DPID maître. La synchronisation associe les DPIDS du fichier - nom aux UUID du fichier. </p> <p>Le nombre de DPIDS dans le fichier doit correspondre au nombre d'UUID dans le fichier de données. Par exemple, supposons que votre fichier comporte un fichier DPID maître et 3 DPIDS. Votre fichier de données doit inclure 4 colonnes correspondantes d'UUID, formatées comme décrit dans la section du contenu du fichier ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Horodatage UNIX à 10 chiffres, en secondes. L'horodatage permet de rendre chaque fichier unique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> . sync</code> </p> </td> 
   <td colname="col2"> <p>Indique une synchronisation normale et complète. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>. SPLIT_ NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous scindez des fichiers volumineux en plusieurs fichiers plus petits. Cela contribue à améliorer les temps de traitement. Le nombre indique la partie du fichier d'origine dans lequel vous envoyez le fichier. Voir le fichier - exemples de nom ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Indique que votre fichier est compressé avec une compression gzip facultative. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Fichier - nom exemples

Les exemples suivants montrent les noms de fichiers correctement formatés. Vos noms de fichier peuvent être similaires.

<ul class="simplelist"> 
 <li> <code> adobe_ id_ 111_ 222_ 333_ 444_ 1454442149. sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
</ul>

## File Content Syntax and Examples {#file-content-syntax}

Le contenu d'un fichier d'ID inclut les éléments suivants :

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

The file contains user IDs ([!DNL UUID]). Dans chaque ligne, séparez les identifiants par un onglet. L'exemple suivant illustre un fichier d'ID correctement formaté. Votre contenu peut ressembler à celui-ci.

```
abc123 def456 ghi789 xyz987
```

## Synchronization Matches DPUUIDs to UUIDs {#sync-matches-dpuuids-uuids}

The purpose of an ID sync file is to sync the [DPUUIDs](../../../reference/ids-in-aam.md) from your own Data Sources with [!DNL Audience Manager] UUIDs. Synchronization maps the [!DNL DPUUID]s from the master [!DNL DPID] and its related [!DNL DPID]s to the [!DNL Audience Manager] [!DNL UUID]s. Where you put the IDs in the file name and body determines how these identifiers are mapped to each other. Par exemple, prenons les deux exemples de fichiers présentés ici :

* **Fichier 1 :**`adobe_id_0_12345_1476312152.sync`

* **Fichier 2 :**`adobe_id_12345_67890_1476312876.sync`

<br/>

À partir de l'exemple de nom et du contenu, les identifiants correspondent comme suit :

**Fichier 1** ( [Télécharger un exemple de fichier](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = UUID Adobe Audience Manager | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 |
| 67412682083411995725538770443620307584 | XYZ 3017 BBR 4 dafjwfm 6 D 4 Gb 4 ln_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 |
| 89159024796760343733111707646026765593 | XYZ 3017 prypid 8 tzfhkee-gE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm |
| 66552757407517449462805881945288602094 | XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 M |
| 66184778222667870903738139438735041506 | XYZ 3017 q 9 r 60 kuhpoca_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw |

Step 1: the ID sync process will sync the [!DNL DPUUID]s from [!DNL DPID] 12345 with the [!DNL Audience Manager] [!DNL UUID]s in the left column. Note that the [!DNL DPID] "0" in the file name represents [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**Fichier 2** ( [Télécharger un exemple de fichier](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ 3017 D_ 2 kzktoxkfyiagwbajoqwrcqkxl-ttrj 6 E 4 njamr 38 | 4598060374 |
| XYZ 3017 BBR 4 dafjwfm 6 D 4 Gb 4 ln_ T 5 jk_ f 7 rdecqns 9 wfna 7 h 70 | 4581274262 |
| XYZ 3017 prypid 8 tzfhkee-gE 034 LI -53 Jde 0 utcyciwd 0 A 2 olm | 4392434426 |
| XYZ 3017 qvbddd-bljs 28 dpxiqufmibxe 3_ 55 bvqjmlwregju 2 M | 2351382994 |
| XYZ 3017 q 9 r 60 kuhpoca_ Ek-btcn 2 iu 1 hyvaue 0 rd 412 tzbycmw | 4601584763 |

Step 2: the [!DNL DPUUID]s from [!DNL DPID] 12345 have been synced in step 1 with the Audience Manager [!DNL UUID]s. What this ID sync will do is sync the [!DNL DPUUID]s from [!DNL DPID] 67890 with the Audience Manager [!DNL UUID]s from step 1.

<br/>

## Other Format Requirements {#other-format-reqs}

Utilisateur - les identifiants ne peuvent pas :

* Comporte des onglets dans l'ID lui-même. Les onglets ne sont utilisés que pour séparer des ID individuels dans le fichier de données.
* Contain personally identifiable information ([!UICONTROL PII]).
* Use [!DNL URL] encoding. Transmettez uniquement les ID non codés.

Les lignes qui se terminent par des tabulations ou des espaces ne seront ni traitées, ni converties. En règle générale, veillez à effacer la fin des lignes.