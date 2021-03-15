# Projet inside

Un POC (prove of concept) pour vérifier si c'est possible de faire une recherche sur les pages et medias des pages inside de l'EPFL. Ce POC a été fait sur un NAS Synology qui contenait un conteneur avec la base de données elasticsearch et kibana et un autre conteneur avec un siteweb wordpress.

## read_and_write_pages_medias.js

Script qui permet de lire le contenu des pages et medias d'un siteweb wordpress depuis leurs URL et mettre le contenu dans elasticsearch.  
  
**Pour les medias :**  
  
Il cherche les données depuis l'URL de l'API REST et les encodent, en base64, pour ensuite les mettre dans elasticsearch. La conversion en base64 est nécessaire pour que si nous voulons faire une recherche full text, le contenu de cette media (Ex: fichier PDF) soit accessible.  
  
**Pour les pages :**  
  
Il cherche les données depuis l'URL de l'API REST et il enlève les balises HTML et les retours à ligne qui ne sont pas nécessaires et ensuite met tout dans elasticsearch.  

