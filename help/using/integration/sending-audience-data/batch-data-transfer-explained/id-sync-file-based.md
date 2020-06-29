---
description: Décrit les champs obligatoires, la syntaxe et les conventions d’attribution de noms utilisées pour la synchronisation des identifiants basée sur des fichiers. Nommez et organisez le contenu de votre fichier selon ces spécifications.
seo-description: Décrit les champs obligatoires, la syntaxe et les conventions d’attribution de noms utilisées pour la synchronisation des identifiants basée sur des fichiers. Nommez et organisez le contenu de votre fichier selon ces spécifications.
seo-title: Exigences en matière de nom et de contenu pour les fichiers de synchronisation d’identifiants
solution: Audience Manager
title: Exigences en matière de nom et de contenu pour les fichiers de synchronisation d’identifiants
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 7%

---


# Exigences en matière de nom et de contenu pour les fichiers de synchronisation d’identifiants {#name-and-content-requirements-for-id-synchronization-files}

Décrit les champs obligatoires, la syntaxe et les conventions d’attribution de noms utilisées pour la synchronisation des identifiants basée sur des fichiers. Nommez et organisez le contenu de votre fichier selon ces spécifications.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italiques*, crochets `[ ]` `( )`, etc.) dans ce document, indiquez les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe du nom de fichier et exemples {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

Les noms de fichiers d’ID contiennent les éléments obligatoires et facultatifs suivants :

*`[adobe_id_]`* *`[c2c_id_]`*`MASTERDPID_DPID`*`[_DPID]`*`_TIMESTAMP.sync`*`[.SPLIT_NUMBER]`*`[.gz]`

<table id="table_727A465D7C38419CA0750EF32DEDA2FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> adobe_id</code> </p> </td> 
   <td colname="col2"> <p>Préfixe statique qui identifie le fichier comme fichier de synchronisation des identifiants. Utilisez ce préfixe lorsque vous faites correspondre des ID de périphérique à d’autres ID de périphérique ou de client (DPUUID).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Préfixe statique qui identifie le fichier comme fichier de synchronisation des identifiants pour les destinations basées sur les personnes. Utilisez ce préfixe lorsque vous faites correspondre des ID de client (DPUUID) à des adresses électroniques hachées pour les destinations basées sur les personnes.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> L’ID de fournisseur de données maître est l’ID parent des DPID dans le nom de fichier. En outre, le premier ID utilisateur du fichier de données correspond à l’ID maître. Les DPID suivants sont d’autres identifiants qui appartiennent au maître. La synchronisation fait correspondre les DPID du nom de fichier aux UUID du fichier. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>ID de fournisseur de données. Ces identifiants représentent des entités ou des sources de données associées au DPID maître. La synchronisation fait correspondre les DPID du nom de fichier aux UUID du fichier. </p> <p>Le nombre de DPID dans le nom de fichier doit correspondre au nombre d’UUID dans le fichier de données. Par exemple, supposons que votre nom de fichier contient un DPID maître et 3 DPID. Votre fichier de données doit inclure 4 colonnes correspondantes d’UUID, au format décrit dans la section de contenu de fichier ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Horodatage UNIX à 10 chiffres en secondes. L’horodatage permet de rendre chaque nom de fichier unique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Indique une synchronisation normale complète. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Entier. Utilisé lorsque vous séparez des fichiers volumineux en plusieurs fichiers plus petits. Cela permet d’améliorer les temps de traitement. Le numéro indique la partie du fichier d'origine que vous envoyez. Consultez les exemples de noms de fichier ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Indique que votre fichier est compressé avec la compression gzip facultative. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemples de noms de fichier

Les exemples suivants montrent les noms de fichiers correctement formatés. Vos noms de fichier peuvent ressembler.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Pour la dénomination des fichiers de synchronisation des identifiants (préfixe c2c) pour les destinations basées sur les personnes, voir [Workflow A - Personnalisation basée sur toutes les Activités en ligne combinées avec des données](../../../features/destinations/people-based-destinations-workflow-combined.md) hors ligne ou [Workflow B - Personnalisation basée sur des données](../../../features/destinations/people-based-destinations-workflow-offline.md)hors ligne uniquement.

## Syntaxe du contenu du fichier et exemples {#file-content-syntax}

Le contenu d’un fichier d’ID comprend les éléments suivants :

*`UUID`* `<tab>`*`UUID`* `<tab>`*`UUID`*`<tab>` *`UUID`*

Le fichier contient des ID d’utilisateur ([!DNL UUID]). Dans chaque ligne, séparez les ID par un onglet. L’exemple suivant montre un fichier d’ID correctement formaté. Votre contenu pourrait avoir l&#39;air similaire.

```
abc123 def456 ghi789 xyz987
```

## La synchronisation correspond aux DPUUID aux UUID {#sync-matches-dpuuids-uuids}

Un fichier de synchronisation des identifiants a pour but de synchroniser les [DPUUID](../../../reference/ids-in-aam.md) de vos propres sources de données avec [!DNL Audience Manager] des UUID. La synchronisation mappe les [!DNL DPUUID]s du maître [!DNL DPID] et des [!DNL DPID]s associés aux [!DNL Audience Manager] [!DNL UUID]s. L’emplacement des identifiants dans le nom et le corps du fichier détermine la manière dont ces identifiants sont mappés les uns aux autres. Par exemple, prenez les deux fichiers d’exemple suivants :

* **Fichier 1 :** `adobe_id_0_12345_1476312152.sync`

* **Fichier 2 :**  `adobe_id_12345_67890_1476312876.sync`

<br/>

Compte tenu du nom et du contenu de l’exemple, les identifiants correspondent comme suit :

**Fichier 1** ( [Télécharger un exemple de fichier](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = UUID d&#39;Adobe Audience Manager | DPID 12345 |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Étape 1 : le processus de synchronisation des identifiants synchronise les [!DNL DPUUID]s à partir de [!DNL DPID] 12345 avec les [!DNL Audience Manager] [!DNL UUID]s dans la colonne de gauche. Notez que le [!DNL DPID] &quot;0&quot; dans le nom de fichier représente [!DNL Audience Manager] [!DNL UUID]s.
<br/>

**Fichier 2** ( [Télécharger un exemple de fichier](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-Trj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Étape 2 : les [!DNL DPUUID]s de [!DNL DPID] 12345 ont été synchronisés à l&#39;étape 1 avec l&#39;Audience Manager [!DNL UUID]s. Cette synchronisation des identifiants permettra de synchroniser les [!DNL DPUUID]s de [!DNL DPID] 67890 avec les Audiences Manager [!DNL UUID]de l’étape 1.

<br/>

## Autres formats requis {#other-format-reqs}

Les ID utilisateur ne peuvent pas :

* Posséder des onglets dans l’identifiant lui-même. Les onglets ne sont utilisés que pour séparer les ID individuels dans le fichier de données.
* Contenir des informations d&#39;identification personnelle ([!UICONTROL PII]).
* Utilisez [!DNL URL] le codage. Transmettez uniquement des ID non codés.

Les lignes qui se terminent par des tabulations ou des espaces ne seront pas traitées ni réalisées. En règle générale, assurez-vous que la fin des lignes reste claire.