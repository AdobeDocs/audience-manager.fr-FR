---
description: Lorsqu'un fichier serveur à serveur entrant est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s'il est configuré, au partenaire.
seo-description: Lorsqu'un fichier serveur à serveur entrant est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s'il est configuré, au partenaire.
seo-title: Exemple de message aux partenaires après le traitement entrant
solution: Audience Manager
title: Exemple de message aux partenaires après le traitement entrant
uuid: 69 e 3 a 8 b 3-8465-4 f 4 c -8005-8 a 9 ff 15 ae 19 a
translation-type: tm+mt
source-git-commit: 3fb90da3be8f50fe670c1193600f5e3a027be52c

---


# Sample Message to Partners after Inbound Processing{#sample-message-to-partners-after-inbound-processing}

Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner.

<!-- r_inbound_message.xml -->

L&#39;exemple suivant illustre un exemple de courrier électronique. Le tableau ci-dessous décrit les différentes lignes du message.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>De : aam-noreply@adobe.com </b> </p> <p> <b>Objet : Résultat de traitement serveur/à serveur d'Adobe Audience Manager :</b> </p> <p> <b>Cher partenaire Adobe : (ID : 7)</b><b></b> </p> <p> <b>Nous avons reçu votre livraison de fichiers serveur à serveur Adobe Audience Manager</b> </p> <p> <b>Fichier - name :</b><i></i> </p> <p> <b> s 3 n:// &lt;<i>nom_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806402. sync</b> </p> <p> <b> s 3 n:// &lt;<i>nom_ bucket &gt;</i>/2018-05-16/ftp_ dpm_ 7_ 901_ 1368655202. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nom_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784804. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nom_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806403. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nom_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784802. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nom_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368784803. sync </b> </p> <p> <b>s 3 n:// &lt;<i>nom_ bucket &gt;</i>/2018-05-17/ftp_ dpm_ 7_ 901_ 1368806404. sync</b> </p> <p> <b>Enregistrements reçus : 40669900</b> </p> <p><b>Erreurs de format : 0</b> </p> <p> <b>ID AAM non valide : 112 </b> </p> <p> <b>Aucun ID AAM correspondant : 0 </b> </p> <p> <b>Aucune caractéristique réalisée : 26730823 </b> </p> <p> <b>Enregistrements traités : 40669900 </b> </p> <p> <b>Enregistrements stockés : 13938958 </b> </p> <p> <b>Nombre total de périphériques : 21 </b> </p> <p> <b>Total des signaux : 918878926 </b> </p> <p> <b>Total des signaux inutilisés : 660348376 </b> </p> <p> <b>Caractéristiques générées totales : 258086908 </b> </p> <p> <b>Total supprimé des caractéristiques : 0 </b> </p> <p> <b>Echec de la validation des caractéristiques : 0 </b> </p> <p> <b>Nombre total d'utilisateurs dont la validation a échoué : 0 </b> </p> <p> <b>Heure de début de la tâche : 2018-05-17 18:07:49 </b> </p> <p> <b>Heure de fin de tâche : 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Le tableau suivant contient des lignes correspondant aux lignes du message électronique reçu.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ligne </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Fichier - nom </td> 
   <td colname="col2"> <p>liste de tous les fichiers entrants reçus par Adobe pour ce partenaire qui ont été traités ensemble. Dans l'exemple de message électronique précédent, l'ID du partenaire est 7 et l'ID de propriétaire de données est 901. </p> <p>Le numéro de fin (1,2,3…) est le numéro de division ajouté par le client ou par le grossiste entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements reçus </td> 
   <td colname="col2"> <p>Nombre total d'enregistrements reçus par Adobe dans tous les fichiers. Dans la plupart des cas, il doit s'agir du nombre total de lignes dans les fichiers entrants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreurs de format </td> 
   <td colname="col2"> <p>Nombre de lignes qui ne correspondaient pas au format attendu. Ces lignes n'étaient pas reconnaissables par la tâche intégrée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID AAM non valide </td> 
   <td colname="col2"> <p>Nombre d'UUID d'Audience Manager qui ne correspondaient pas au format attendu à 38 chiffres. Les UUID d'Audience Manager envoyés dans le fichier ne sont pas des nombres. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aucun ID AAM correspondant </td> 
   <td colname="col2"> <p>Nombre total d'utilisateurs pour lesquels Audience Manager n'a pas trouvé d'identifiant UUID correspondant. Ces fichiers n'ont pas été synchronisés. Audience Manager ne peut donc pas rechercher l'UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aucune caractéristique réalisée </td> 
   <td colname="col2"> <p>Nombre d'enregistrements où aucun des signaux de la ligne ne correspond à une caractéristique Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements traités </td> 
   <td colname="col2"> <p>Nombre total d'enregistrements traités par Audience Manager. Dans la plupart des cas, ce nombre doit être identique à « Enregistrements reçus.  » » </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements stockés </td> 
   <td colname="col2"> <p>Nombre d'enregistrements qui génèrent des données à charger dans le système = Enregistrements traités - Erreurs de format - ID AAM non valide - Aucun identifiant AAM correspondant - Aucune caractéristique réalisée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de périphériques </td> 
   <td colname="col2"> <p>Nombre de périphériques pour lesquels les données ont été chargées dans le système. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total des signaux </td> 
   <td colname="col2"> <p> Nombre total de signaux pour tous les utilisateurs dans tous les fichiers entrants (nombre total de paires clé/valeur dans les enregistrements traités). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total des signaux inutilisés </td> 
   <td colname="col2"> <p>Nombre total de signaux inutilisés pour tous les utilisateurs dans tous les fichiers entrants (paires clé/valeur qui ne correspondaient pas aux caractéristiques Audience Manager). Dans la plupart des cas, cela signifie qu'Audience Manager n'a pas de règles définies pour le signal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Caractéristiques générées totales </td> 
   <td colname="col2"> <p>nombre de caractéristiques Audience Manager pour tous les utilisateurs pour tous les fichiers entrants en fonction des signaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de caractéristiques supprimées </td> 
   <td colname="col2"> <p> Nombre total de caractéristiques supprimées pour tous les utilisateurs dans tous les fichiers entrants. Pour une synchronisation complète, cela se produit si l'utilisateur avait la caractéristique lors d'une exécution précédente mais pas dans l'exécution actuelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Echec de la validation des caractéristiques </td> 
   <td colname="col2"> <p>Représente le nombre de caractéristiques qui n'appartiennent pas à la source de données déclarée dans le fichier - nom. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total d'utilisateurs dont la validation a échoué </td> 
   <td colname="col2"> <p>nombre d'enregistrements dont la validation a échoué. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de début de la tâche </td> 
   <td colname="col2"> <p>Heure de début du travail entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin de tâche </td> 
   <td colname="col2"> <p>Heure à laquelle la tâche entrant se termine. </p> </td> 
  </tr> 
 </tbody> 
</table>