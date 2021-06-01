---
description: Chaque fois qu’un fichier entrant de serveur à serveur est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s’il est configuré, au partenaire.
seo-description: Chaque fois qu’un fichier entrant de serveur à serveur est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s’il est configuré, au partenaire.
seo-title: Message d’exemple aux partenaires après le traitement entrant
solution: Audience Manager
title: Message d’exemple aux partenaires après le traitement entrant
uuid: 69e3a8b3-8465-4f4c-8005-8a9ff15ae19a
feature: Transferts des données entrantes
exl-id: acfc788f-63e6-445f-a086-0a2cc6c8865b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 3%

---

# Message d’exemple aux partenaires après le traitement entrant{#sample-message-to-partners-after-inbound-processing}

Chaque fois qu&#39;un fichier [!UICONTROL Server-to-Server] entrant est traité, un reçu est envoyé par email aux solutions partenaires et, s&#39;il est configuré, au partenaire.

<!-- r_inbound_message.xml -->

L’exemple suivant est un exemple de message électronique. Le tableau ci-dessous décrit les différentes lignes du message.

<table id="table_F579C2278A044213BFCEF97F3BEC2C0C"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>De : aam-noreply@adobe.com  </b> </p> <p> <b>Objet : Adobe Audience Manager Server-To-Server Processing Result :</b> </p> <p> <b>Cher partenaire Adobe : (ID:7)</b> <b></b> </p> <p> <b>Nous avons reçu votre diffusion de fichier de serveur à serveur Adobe Audience Manager.</b> </p> <p> <b>Nom du fichier :</b> <i></i> </p> <p> <b> s3n://&lt;&gt;nom_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806402.sync</b><i> </i></p> <p> <b> s3n://&lt;&gt;nom_compartiment&gt;</i>/2018-05-16/ftp_dpm_7_901_1368655202.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nom_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784804.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nom_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806403.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nom_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784802.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nom_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368784803.sync  </b><i> </i></p> <p> <b>s3n://&lt;&gt;nom_compartiment&gt;</i>/2018-05-17/ftp_dpm_7_901_1368806404.sync</b><i> </i></p> <p> <b>Enregistrements reçus : 40669900</b> </p> <p><b>Erreurs de format : 0</b> </p> <p> <b>ID AAM non valide : 112  </b> </p> <p> <b>Aucun identifiant d’AAM correspondant : 0  </b> </p> <p> <b>Aucune caractéristique réalisée : 26730823  </b> </p> <p> <b>Enregistrements traités : 40669900  </b> </p> <p> <b>Enregistrements stockés : 13938958  </b> </p> <p> <b>Nombre total d’appareils : 21  </b> </p> <p> <b>Signaux totaux : 918878926  </b> </p> <p> <b>Nombre total de signaux inutilisés : 660348376  </b> </p> <p> <b>Nombre total de caractéristiques réalisées : 258086908  </b> </p> <p> <b>Nombre total de caractéristiques supprimées : 0  </b> </p> <p> <b>Échec de la validation du nombre total de caractéristiques : 0  </b> </p> <p> <b>Nombre total d’utilisateurs qui ont des caractéristiques dont la validation a échoué : 0  </b> </p> <p> <b>Heure de début de la tâche : 2018-05-17 18:07:49  </b> </p> <p> <b>Heure de fin de la tâche : 2018-05-17 18:45:02</b> </p> </td> 
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
   <td colname="col2"> <p>Liste de tous les fichiers entrants reçus par l’Adobe pour ce partenaire qui ont été traités ensemble. Dans l’exemple de message électronique précédent, l’ID de partenaire est 7 et l’ID de propriétaire des données est 901. </p> <p>Le numéro de queue (1,2,3...) est le numéro partagé ajouté par le client ou par le distributeur entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements reçus </td> 
   <td colname="col2"> <p>Nombre total d'enregistrements Adobe reçus dans tous les fichiers. Dans la plupart des cas, il doit s’agir du nombre total de lignes dans les fichiers entrants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Erreurs de format </td> 
   <td colname="col2"> <p>Nombre de lignes ne correspondant pas au format attendu. Ces lignes n'étaient pas reconnaissables par le traitement entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID d’AAM non valide </td> 
   <td colname="col2"> <p>Nombre d’UUID d’Audience Manager qui ne correspondaient pas au format de 38 chiffres attendu. Ou les UUID d’Audience Manager envoyés dans le fichier ne sont pas des nombres. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aucun identifiant d’AAM correspondant </td> 
   <td colname="col2"> <p>Nombre total d’utilisateurs pour lesquels l’Audience Manager n’a pas trouvé d’UUID correspondant. Ces fichiers n’ont pas été synchronisés avec l’ID. Par conséquent, l’Audience Manager ne peut pas rechercher l’UUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aucune caractéristique réalisée </td> 
   <td colname="col2"> <p>Nombre d’enregistrements pour lesquels aucun des signaux sur la ligne ne correspond à une caractéristique d’Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements traités </td> 
   <td colname="col2"> <p>Nombre total d'enregistrements traités dans l'Audience Manager. Dans la plupart des cas, ce nombre doit être identique à "Enregistrements reçus". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Enregistrements stockés </td> 
   <td colname="col2"> <p>Nombre d’enregistrements entraînant le chargement de données dans le système = Enregistrements traités - Erreurs de format - Identifiants d’AAM non valides - Aucun identifiant AAM correspondant - Aucune caractéristique réalisée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de périphériques </td> 
   <td colname="col2"> <p>Nombre d’appareils pour lesquels des données ont été chargées dans le système. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Signaux totaux </td> 
   <td colname="col2"> <p> Nombre total de signaux pour tous les utilisateurs dans tous les fichiers entrants (nombre total de paires clé/valeur dans les enregistrements traités). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de signaux inutilisés </td> 
   <td colname="col2"> <p>Nombre total de signaux inutilisés pour tous les utilisateurs dans tous les fichiers entrants (paires clé/valeur qui n’ont pas été mappées aux caractéristiques d’Audience Manager). Dans la plupart des cas, cela signifie que les règles de l’Audience Manager ne sont pas définies pour le signal. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de caractéristiques réalisées </td> 
   <td colname="col2"> <p>Nombre de caractéristiques d’Audience Manager pour tous les utilisateurs sur tous les fichiers entrants en fonction des signaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total de caractéristiques supprimées </td> 
   <td colname="col2"> <p> Nombre total de caractéristiques supprimées pour tous les utilisateurs dans tous les fichiers entrants. Pour les synchronisations complètes, cela se produit si l’utilisateur avait la caractéristique lors d’une exécution précédente, mais pas lors de l’exécution actuelle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Validation des caractéristiques totales ayant échoué </td> 
   <td colname="col2"> <p>Représente le nombre de caractéristiques qui n’appartiennent pas à la source de données déclarée dans le nom de fichier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nombre total d’utilisateurs qui ont des caractéristiques dont la validation a échoué </td> 
   <td colname="col2"> <p>Nombre d’enregistrements dont les caractéristiques ont échoué lors de la validation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de début de la tâche </td> 
   <td colname="col2"> <p>Heure à laquelle la tâche entrante commence. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Heure de fin de la tâche </td> 
   <td colname="col2"> <p>Heure à laquelle la tâche entrante se termine. </p> </td> 
  </tr> 
 </tbody> 
</table>
