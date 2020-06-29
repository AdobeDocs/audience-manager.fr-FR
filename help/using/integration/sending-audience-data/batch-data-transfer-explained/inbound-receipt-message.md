---
description: Chaque fois qu'un fichier de serveur à serveur entrant est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s'il est configuré, au partenaire.
seo-description: Chaque fois qu'un fichier de serveur à serveur entrant est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s'il est configuré, au partenaire.
seo-title: Exemple de message aux partenaires après le traitement entrant
solution: Audience Manager
title: Exemple de message aux partenaires après le traitement entrant
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 0%

---


# Exemple de message aux partenaires après le traitement entrant{#sample-message-to-partners-after-inbound-processing}

Chaque fois qu&#39;un [!UICONTROL Server-to-Server] fichier entrant est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s&#39;il est configuré, au partenaire.

<!-- r_inbound_message.xml -->

L’exemple suivant illustre un exemple de message électronique. Le tableau ci-dessous décrit les différentes lignes du message.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>De : aam-noreply@adobe.com </b> </p> <p> <b>Objet : Résultat de traitement Adobe Audience Manager serveur à serveur :</b> </p> <p> <b>Cher partenaire Adobe : (ID:7)</b> <b></b> </p> <p> <b>Nous avons reçu votre diffusion de fichiers Adobe Audience Manager serveur à serveur</b> </p> <p> <b>Nom du fichier :</b> <i></i> </p> <p> <b> s3 n://&lt;nom_<i>du_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b> </p> <p> <b> s3 n://&lt;nom_<i>du_compartiment&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync </b> </p> <p> <b>s3 n://&lt;nom_<i>du_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync </b> </p> <p> <b>s3 n://&lt;nom_<i>du_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync </b> </p> <p> <b>s3 n://&lt;nom_<i>du_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync </b> </p> <p> <b>s3 n://&lt;nom_<i>du_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync </b> </p> <p> <b>s3 n://&lt;nom_<i>du_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b> </p> <p> <b>Enregistrements reçus : 40669900</b> </p> <p><b>Erreurs de format : 0</b> </p> <p> <b>ID AAM non valide : 112 </b> </p> <p> <b>Aucun ID AAM correspondant : 0 </b> </p> <p> <b>Aucune caractéristique réalisée : 26730823 </b> </p> <p> <b>Enregistrements traités : 40669900 </b> </p> <p> <b>Enregistrements stockés : 13938958 </b> </p> <p> <b>Nombre total de périphériques : 21 </b> </p> <p> <b>Signaux totaux : 918878926 </b> </p> <p> <b>Total des signaux inutilisés : 660348376 </b> </p> <p> <b>Nombre total de caractéristiques réalisées : 258086908 </b> </p> <p> <b>Nombre total de caractères retirés : 0 </b> </p> <p> <b>Échec de la validation du nombre total de caractéristiques : 0 </b> </p> <p> <b>Nombre total d’utilisateurs présentant des caractéristiques dont la validation a échoué : 0 </b> </p> <p> <b>début de la tâche : 2018-05-17 18:07:49 </b> </p> <p> <b>Heure de fin de la tâche : 2018-05-17 18:45:02</b> </p> </td> 
  </tr> 
 </tbody> 
</table>

Le tableau suivant contient les lignes correspondant aux lignes du message électronique reçu.

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ligne </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nom du fichier </td> 
   <td colname="col2"> <p>Liste de tous les fichiers entrants reçus par Adobe pour ce partenaire qui ont été traités ensemble. Dans l’exemple de message électronique précédent, l’ID de partenaire est 7 et l’ID de propriétaire des données est 901. </p> <p>Le numéro de queue (1,2,3...) est le numéro fractionné ajouté soit par le client, soit par le distributeur entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements reçus </td> 
   <td colname="col2"> <p>Nombre total d’enregistrements reçus par Adobe dans tous les fichiers. Dans la plupart des cas, il doit s’agir du nombre total de lignes dans les fichiers entrants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreurs de format </td> 
   <td colname="col2"> <p>Nombre de lignes ne correspondant pas au format attendu. Ces lignes n'étaient pas reconnaissables par le travail entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID AAM non valide </td> 
   <td colname="col2"> <p>Nombre d’UUID d’Audience Manager qui ne correspondaient pas au format de 38 chiffres attendu. Ou les UUID d'Audience Manager envoyés dans le fichier ne sont pas des nombres. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aucun ID AAM correspondant </td> 
   <td colname="col2"> <p>Nombre total d’utilisateurs pour lesquels l’Audience Manager n’a pas trouvé d’UUID correspondant. Ces fichiers n’ont pas été synchronisés, l’Audience Manager ne peut donc pas rechercher l’UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aucun trait n'a été trouvé </td> 
   <td colname="col2"> <p>Nombre d'enregistrements dans lesquels aucun des signaux sur la ligne ne correspond à une caractéristique d'Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements traités </td> 
   <td colname="col2"> <p>Nombre total d'enregistrements Audience Manager traités. Dans la plupart des cas, ce nombre doit être identique à celui des "Enregistrements reçus". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements stockés </td> 
   <td colname="col2"> <p>Nombre d'enregistrements ayant abouti au chargement des données dans le système = Enregistrements traités - Erreurs de format - ID AAM non valides - Aucun ID AAM correspondant - Aucune caractéristique réalisée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de périphériques </td> 
   <td colname="col2"> <p>Nombre de périphériques pour lesquels des données ont été chargées dans le système. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Signaux totaux </td> 
   <td colname="col2"> <p> Nombre total de signaux pour tous les utilisateurs dans tous les fichiers entrants (nombre total de paires clé/valeur dans les enregistrements traités). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total des signaux inutilisés </td> 
   <td colname="col2"> <p>Nombre total de signaux inutilisés pour tous les utilisateurs dans tous les fichiers entrants (paires clé/valeur qui n’ont pas été mappées à des caractéristiques d’Audience Manager). Dans la plupart des cas, cela signifie que l'Audience Manager n'a pas de règles définies pour le signal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de caractéristiques réalisées </td> 
   <td colname="col2"> <p>Nombre de caractéristiques d’Audience Manager pour tous les utilisateurs dans tous les fichiers entrants en fonction des signaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de caractères retirés </td> 
   <td colname="col2"> <p> Nombre total de caractéristiques supprimées pour tous les utilisateurs dans tous les fichiers entrants. Pour les synchronisations complètes, cela se produit si l’utilisateur avait la caractéristique lors d’une exécution précédente mais pas lors de l’exécution en cours. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Échec de la validation des caractéristiques totales </td> 
   <td colname="col2"> <p>Représente le nombre de caractéristiques qui n’appartiennent pas à la source de données déclarée dans le nom de fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total d’utilisateurs présentant des caractéristiques dont la validation a échoué </td> 
   <td colname="col2"> <p>Nombre d’enregistrements dont les caractéristiques n’ont pas été validées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> début de la tâche </td> 
   <td colname="col2"> <p>Heure de début de la tâche entrante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin de la tâche </td> 
   <td colname="col2"> <p>Heure de fin de la tâche entrante. </p> </td> 
  </tr> 
 </tbody> 
</table>