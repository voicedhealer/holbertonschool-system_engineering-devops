# Infrastructure web sécurisée et monitorée – Conception et explications

## Vue d'ensemble de l'infrastructure

Une infrastructure distribuée sur trois serveurs pour héberger www.foobar.com doit garantir la sécurité, le chiffrement du trafic et un système de supervision.  
Composants ajoutés :
- 3 firewalls  
- 1 certificat SSL pour servir www.foobar.com en HTTPS  
- 3 clients de monitoring (collecteurs de données pour SumoLogic ou équivalent)

***

## Rôle et justification de chaque élément

- **Firewalls :**  
  Protègent chaque serveur contre les intrusions, filtrent le trafic non désiré, sécurisent accès et données. Chaque serveur a son propre pare-feu pour compartimenter la sécurité.

- **Certificat SSL :**  
  Garantit le chiffrement des échanges entre le site et ses visiteurs. HTTPS protège contre les interceptions et altérations du trafic, préserve confidentialité et intégrité.

- **Clients de monitoring :**  
  Recueillent en temps réel des métriques (CPU, trafic, logs, erreurs…) et transmettent les données à une plateforme de supervision (SumoLogic…). Permettent le suivi de la santé et des performances du système.

***

## Explications techniques

- **Pourquoi le trafic est servi en HTTPS ?**  
  Pour sécuriser les échanges, protéger les données utilisateurs et vérifier l’authenticité du serveur.

- **À quoi servent les firewalls ?**  
  À filtrer le trafic entrant/sortant, bloquer les attaques, limiter les accès aux seuls services nécessaires.

- **Pourquoi utiliser du monitoring ?**  
  Pour détecter rapidement les incidents, prévenir les défaillances et suivre la charge système (QPS, erreurs, disponibilité…).

- **Comment les outils de monitoring collectent-ils les données ?**  
  Par des agents installés sur chaque serveur qui agrègent et envoient les métriques à une plateforme centralisée.

- **Surveiller le QPS du serveur web :**  
  Configurer un agent/collecteur pour suivre le nombre de requêtes par seconde, observer les pics de trafic, anticiper les besoins en scalabilité.

***

## Problèmes potentiels dans cette architecture

- **Terminer le SSL au niveau du load-balancer :**  
  Si le chiffrement s’arrête au load-balancer (et non en bout de chaîne), le trafic entre le load-balancer et les serveurs backend n’est pas chiffré, exposant une faille de sécurité.

- **Un seul serveur MySQL acceptant les écritures :**  
  Risque de SPOF ; si ce serveur lâche, les données sont inaccessibles ou non modifiables, ce qui bloque l’application.

- **Tous les serveurs identiques en composants :**  
  Cela complique la gestion (synchronisation, cohérence de données…), multiplie les points de défaillance et peut rendre la montée en charge plus complexe.

***

## Résumé

Cette infrastructure vise une sécurité renforcée (firewall, HTTPS), la surveillance active (monitoring), mais doit résoudre les risques liés à la centralisation des bases de données, au chiffrement partiel, et à la gestion multi-composants identiques.
