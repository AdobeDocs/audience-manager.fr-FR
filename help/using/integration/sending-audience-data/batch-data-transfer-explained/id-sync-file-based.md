---
description: Décrit les champs obligatoires, la syntaxe et les conventions de nommage utilisés pour la synchronisation des identifiants basée sur des fichiers. Nommez et organisez le contenu de votre fichier en fonction de ces spécifications.
seo-description: Describes the required fields, syntax, and naming conventions used for file-based ID synchronization. Name and organize your file contents according to these specifications.
seo-title: Name and Content Requirements for ID Synchronization Files
solution: Audience Manager
title: Nom et contenu requis pour les fichiers de synchronisation des identifiants
uuid: bfe42af9-9149-4da3-830e-f227c4e610c2
feature: Inbound Data Transfers
exl-id: e6b3a438-f843-4a24-89fd-03ef77d7cf04
TQID: https://experienceleague.adobe.com/yJ5QIV70F6YyRqA0LxqxQaHMoWwe7pLJ8V17MvyEK70
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
  - id: c814092e-2730-45e8-a12d-e084529f52cb
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 782
ht-degree: 2%

---

# Nom et contenu requis pour les fichiers de synchronisation des identifiants {#name-and-content-requirements-for-id-synchronization-files}

Décrit les champs obligatoires, la syntaxe et les conventions de nommage utilisés pour la synchronisation des identifiants basée sur des fichiers. Nommez et organisez le contenu de votre fichier en fonction de ces spécifications.

>[!NOTE]
>
>Les styles de texte (`monospaced text`, *italique*, crochets `[ ]` `( )`, etc.) de ce document indiquent les éléments de code et les options. Pour plus d’informations, voir les [conventions de style relatives aux éléments de code et de texte](../../../reference/code-style-elements.md).

## Syntaxe et exemples du nom de fichier {#file-name-syntax}

<!-- c_file_based_id_sync.xml -->

Les noms de fichier d’ID contiennent les éléments obligatoires et facultatifs suivants :

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
   <td colname="col2"> <p>Préfixe statique qui identifie le fichier en tant que fichier de synchronisation des identifiants. Utilisez ce préfixe lors de la mise en correspondance des ID d’appareil avec d’autres ID d’appareil ou ID de client (DPUUID).  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> c2c_id</code> </p> </td> 
   <td colname="col2"> <p>Préfixe statique qui identifie le fichier en tant que fichier de synchronisation des identifiants pour les destinations basées sur les personnes. Utilisez ce préfixe lors de la mise en correspondance des ID de client (DPUUID) avec des adresses e-mail hachées pour les destinations basées sur les personnes.  </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>MASTERDPID</i></code> </td> 
   <td colname="col2"> <p>L’ID du fournisseur de données principal est l’ID parent des DPID dans le nom du fichier. En outre, le premier identifiant utilisateur dans le fichier de données correspond à l’identifiant principal. Les DPID suivants sont d’autres identifiants appartenant au maître. La synchronisation mappe les DPID dans le nom de fichier avec les UUID dans le fichier .</p> <p>Ce DPID ne doit contenir que des identifiants d’appareil, tels que l’UUID AAM, GAID, IDFA, etc. Il ne peut pas contenir DPUUID. Cela peut entraîner une synchronisation incorrecte.</p>  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DPID</i></code> </p> </td> 
   <td colname="col2"> <p>Identifiants du fournisseur de données. Ces identifiants représentent des entités ou des sources de données associées au DPID principal. La synchronisation mappe les DPID dans le nom de fichier avec les UUID dans le fichier . </p> <p>Le nombre de DPID dans le nom de fichier doit correspondre au nombre d’UUID dans le fichier de données. Supposons, par exemple, que votre nom de fichier contienne un DPID principal et 3 DPID. Votre fichier de données doit inclure 4 colonnes correspondantes d’UUID, formatées comme décrit dans la section contenu du fichier ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><code><i>timestamp</i></code> </td> 
   <td colname="col2"> <p>Horodatage UNIX à 10 chiffres, exprimé en secondes. L’horodatage permet de rendre chaque nom de fichier unique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .sync</code> </p> </td> 
   <td colname="col2"> <p>Indique une synchronisation normale et complète. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>.SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Nombre entier. Utilisé lorsque vous divisez des fichiers volumineux en plusieurs fichiers plus petits. Cela permet d’améliorer les temps de traitement. Le nombre indique la partie du fichier original que vous envoyez. Consultez les exemples de noms de fichier ci-dessous. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Indique que votre fichier est compressé à l’aide d’une compression gzip facultative. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exemples de noms de fichier

Les exemples suivants affichent les noms de fichiers correctement formatés. Vos noms de fichier peuvent ressembler.

<ul class="simplelist"> 
 <li> <code> adobe_id_111_222_333_444_1454442149.sync</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.1.gz</code> </li> 
 <li> <code> adobe_id_123_898_456_1454442149.sync.2.gz</code> </li> 
 <li> <code>c2c_id_123_898_1454442149.sync.gz</code> </li> 
</ul>

>[!NOTE]
> Pour connaître les noms des fichiers de synchronisation des identifiants (préfixe c2c) pour les destinations basées sur les personnes, voir [Workflow A - Personalization basé sur toutes les activités en ligne combinées aux données hors ligne](../../../features/destinations/people-based-destinations-workflow-combined.md) ou [Workflow B - Personalization basé sur les données hors ligne uniquement](../../../features/destinations/people-based-destinations-workflow-offline.md).

## Syntaxe et exemples du contenu du fichier {#file-content-syntax}

Le contenu d’un fichier d’ID comprend les éléments suivants :

*`UUID`* `<tab>`*`UUID`*`<tab>`*`UUID`*`<tab>`*`UUID`*

Le fichier contient des ID utilisateur ([!DNL UUID]). Dans chaque ligne, séparez les identifiants par un onglet. L’exemple suivant illustre un fichier d’ID correctement formaté. Votre contenu pourrait ressembler à ceci.

```
abc123 def456 ghi789 xyz987
```

### Considérations relatives au contenu des fichiers {#considerations}

Lors de la création de vos fichiers entrants, assurez-vous que la première colonne n’est renseignée qu’avec des identifiants d’appareil, tels que [!DNL AAM UUID], [!DNL GAID], [!DNL IDFA], etc. Voir [Index des identifiants dans Audience Manager](../../../reference/ids-in-aam.md) pour une explication détaillée des identifiants pris en charge par Audience Manager.

>[!IMPORTANT]
>
>N&#39;utilisez pas [DPUUIDs](../../../reference/ids-in-aam.md) sur la première colonne. Cela peut entraîner une synchronisation incorrecte.

## La synchronisation fait correspondre les DPUUID aux UUID {#sync-matches-dpuuids-uuids}

L’objectif d’un fichier de synchronisation des identifiants est de synchroniser les [DPUUID](../../../reference/ids-in-aam.md) de vos propres sources de données avec les UUID [!DNL Audience Manager]. La synchronisation mappe les [!DNL DPUUID] du [!DNL DPID] maître et ses [!DNL DPID] associés aux [!DNL Audience Manager] [!DNL UUID]. L’emplacement des identifiants dans le nom et le corps du fichier détermine la manière dont ces identifiants sont mappés les uns aux autres. Par exemple, prenez les deux fichiers d’exemple présentés ici :

* **Fichier 1:** `adobe_id_0_12345_1476312152.sync`

* **Fichier 2:** `adobe_id_12345_67890_1476312876.sync`

<br/>

Compte tenu du nom et du contenu de l’exemple, les identifiants sont mappés comme suit :

**Fichier 1** ( [Télécharger l’exemple de fichier](assets/adobe_id_0_12345_1476312152.sync))

| DPID 0 = UUID ADOBE AUDIENCE MANAGER | 12345 DPID |
|---|---|
| 68079982765673198504052656074456196039 | XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 |
| 67412682083411995725538770443620307584 | XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 |
| 89159024796760343733111707646026765593 | XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM |
| 66552757407517449462805881945288602094 | XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M |
| 66184778222667870903738139438735041506 | XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw |

Étape 1 : le processus de synchronisation des identifiants synchronise les [!DNL DPUUID] de [!DNL DPID] 12345 avec les [!DNL Audience Manager] [!DNL UUID] dans la colonne de gauche. Notez que le [!DNL DPID] « 0 » dans le nom du fichier représente [!DNL Audience Manager] [!DNL UUID].
<br/>

**Fichier 2** ( [Télécharger l’exemple de fichier](assets/adobe_id_12345_67890_1477846458.sync))

| [!DNL DPID] 12345 | [!DNL DPID] 67890 |
|---|---|
| XYZ3017D_2kzkTOXkFYIAgwbajoqWRcqkXl-TTrj6E4njaMR38 | 4598060374 |
| XYZ3017BBR4DAFJWfM6D4Gb4lN_T5jk_f7rdEcqNs9wfnA7h70 | 4581274262 |
| XYZ3017PryPID8tzfhkEE-gE034LI-53Jde0utCYcIwd0A2OlM | 4392434426 |
| XYZ3017QvBddD-bLJS28DPxiqUfmIBxE3_55bvQJMLwregJU2M | 2351382994 |
| XYZ3017q9r60kuHPOca_Ek-btCN2iu1HyVaUe0rd412TzbyCMw | 4601584763 |

Étape 2 : les [!DNL DPUUID] de [!DNL DPID] 12345 ont été synchronisés à l’étape 1 avec les [!DNL UUID] Audience Manager. Cette synchronisation des identifiants synchronise les [!DNL DPUUID] de [!DNL DPID] 67890 avec les [!DNL UUID] d’Audience Manager de l’étape 1.

<br/>

## Autres exigences en matière de format {#other-format-reqs}

Les ID d’utilisateur ne peuvent pas :

* comporter des onglets dans l’ID lui-même ; Les onglets ne sont utilisés que pour séparer les identifiants individuels dans le fichier de données.
* Contiennent des informations d’identification personnelle ([!UICONTROL PII]).
* Utilisez l’encodage [!DNL URL]. Transmettez uniquement les identifiants non codés.

Les lignes qui se terminent par des tabulations ou des espaces ne sont pas traitées ni réalisées. En règle générale, veillez à ce que la fin des lignes soit dégagée.
