# Différence entre serveur d'application et serveur web

## Définitions générales

- **Serveur Web** :  
  Logiciel ou appareil physique qui permet d’accéder à des sites web via Internet ou un réseau local (intranet). Il répond aux demandes des visiteurs avec du contenu statique comme des pages HTML, images, fichiers CSS ou JavaScript.

- **Serveur d’application** :  
  Logiciel plus complexe qui exécute la logique métier, traite les données, communique avec la base de données et génère du contenu dynamique adapté à chaque utilisateur.

***

## Différences clés
```
 ----------------------------------------------------------------------------------------------------------------------------
| Aspect                   | Serveur Web                                  | Serveur d’application                            |
|--------------------------|----------------------------------------------|--------------------------------------------------|
| **Contenu servi**        | Contenu statique (pages, images, scripts)    | Contenu dynamique généré à la demande            |
| **Protocole principal**  | HTTP (plus accès parfois FTP, SMTP)          | Plusieurs protocoles, y compris HTTP, RPC.       | 
| **Fonction principale**  | Distribution rapide des fichiers statiques   | Exécution de la logique métier et des calculs.   |
| **Ressources utilisées** | Généralement faible                          | Plus élevée en raison du traitement dynamique.   |
| **Multithreading**       | Souvent non utilisé                          | Utilisé pour gérer plusieurs requêtes simultanées|
 ----------------------------------------------------------------------------------------------------------------------------
```
***

## Collaboration entre les deux serveurs

- Le serveur web reçoit la requête HTTP initiale.  
- Si la requête porte sur un fichier statique, il le sert directement.  
- Pour du contenu dynamique, il transfère la demande au serveur d’application qui traite la logique, interagit avec la base de données puis retourne la réponse au serveur web.  
- Le serveur web envoie finalement la réponse au client.

***

## Conclusion

Le serveur web est optimisé pour servir rapidement du contenu statique tandis que le serveur d’application est conçu pour traiter les demandes complexes et produire des données dynamiques. Ensemble, ils composent l’architecture web moderne pour combiner rapidité et dynamisme.