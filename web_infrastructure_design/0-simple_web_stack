## 1. Vue d'ensemble de l'architecture

**Infrastructure :**  
- **Nom de domaine :** `foobar.com` (avec un enregistrement DNS `www` pointant vers l’IP du serveur `8.8.8.8`)  
- **Serveur :**  
  - Serveur web unique (Nginx)  
  - Serveur d’application  
  - Base de code applicative (fichiers source)  
  - Base de données (MySQL)

Exemple de diagramme (texte) :  
```
Utilisateur
   |
   v
www.foobar.com (DNS → IP 8.8.8.8)
   |
   v
[Serveur : Nginx – Serveur web]
   |
   v
[Serveur d’application]
   |
   v
[Base de données : MySQL]
```

***

## 2. Explications des composants

### Qu’est-ce qu’un serveur ?  
Un serveur est un dispositif, une machine virtuelle ou un processus logiciel fournissant des ressources et services à d’autres programmes ou appareils, appelés clients.

### Rôle du nom de domaine  
Le nom de domaine fournit à l’utilisateur une adresse facile à retenir qui dirige vers l’IP du serveur.

### Quel type d’enregistrement DNS pour `www` dans `www.foobar.com` ?  
`www` est généralement un enregistrement A (adresse IPv4) ou CNAME (nom canonique) qui redirige vers l’IP serveur.

### Rôle du serveur web  
Le serveur web (Nginx) reçoit les requêtes HTTP, sert les fichiers statiques et transmet les requêtes dynamiques au serveur d’application.

### Rôle du serveur d’application  
Le serveur d’application exécute la logique métier, traite les entrées utilisateur, interagit avec la base de données, génère des pages web dynamiques.

### Rôle de la base de données  
La base de données (MySQL) stocke, organise et permet l’accès rapide aux données persistantes (utilisateurs, contenus, transactions).

### Quel protocole le serveur utilise-t-il pour communiquer avec l’utilisateur ?  
La communication s’effectue via le protocole HTTP, transporté sur TCP/IP.

***

## 3. Limitations de l’infrastructure

- **SPOF (Single Point of Failure) :**  
  La panne du serveur rend tout le site inaccessible.

- **Downtime lors de la maintenance :**  
  Mettre à jour ou redémarrer le serveur entraîne une interruption du service.

- **Limites de montée en charge :**  
  Un seul serveur peut être saturé par trop de trafic, ralentissant le service ou provoquant des pannes.

***

## 4. Acronymes clés

- **LAMP :** Linux, Apache, MySQL, PHP/Python/Perl (ici Nginx remplace Apache).  
- **SPOF :** Point unique de défaillance.  
- **QPS :** “Queries Per Second” – nombre de requêtes traitées par seconde.

***

## 5. Résumé

Cette infrastructure simple démontre comment un site web est généralement construit autour d’un unique serveur hébergeant toutes les couches (serveur web, application, base de données), ce qui limite la disponibilité et la scalabilité sans ressources supplémentaires.