Pour voir la documentation des etapes se placer dans les dossiers

﻿# tp-docker-final
# TP Final Docker Avancé : Volumes, Secrets, Réseaux et Compose

## Durée : 5 heures

## Objectifs du TP
- Comprendre et utiliser les volumes Docker
- Gérer les secrets dans Docker
- Configurer et utiliser les réseaux Docker
- Maîtriser le merge de fichiers Docker Compose

## Prérequis
- Docker installé sur la machine
- Connaissances de base de Docker et Docker Compose

## Structure du TP
1. Volumes Docker (1h)
2. Secrets Docker (1h)
3. Réseaux Docker (1h)
4. Merge de fichiers Docker Compose (1h)
5. Projet final (1h)

---

## 1. Volumes Docker (1h)

### 1.1 Introduction aux volumes (15 min)
- Explication des types de volumes : volumes nommés, bind mounts, tmpfs
- Cas d'utilisation pour chaque type de volume
- Avantages et inconvénients des différentes approches

### 1.2 Exercice : Bind mounts (25 min)
1. Créez un fichier HTML simple sur votre machine hôte
2. Lancez un conteneur Nginx en montant ce fichier dans le conteneur
3. Modifiez le fichier sur l'hôte et observez les changements en temps réel
4. Explorez les options de montage (read-only, selinux, etc.)

### 1.3 Exercice : Volumes tmpfs (20 min)
1. Lancez un conteneur avec un volume tmpfs
2. Écrivez des données dans ce volume
3. Vérifiez la persistance des données après redémarrage du conteneur
4. Comparez les performances avec un volume standard

### 1.4 Défi : Sauvegarde et restauration de volumes (20 min)
1. Créez un script bash pour sauvegarder le contenu d'un volume dans un fichier tar.gz
2. Créez un second script pour restaurer un volume à partir d'une sauvegarde
3. Testez le processus de sauvegarde et restauration avec des données réelles

### 1.5 Discussion et bonnes pratiques (10 min)
- Quand utiliser chaque type de volume ?
- Sécurité des volumes et des données
- Gestion des volumes dans un environnement de production

---

## 2. Secrets Docker (1h)

### 2.1 Introduction aux secrets (10 min)
- Explication de l'utilité des secrets et de leur fonctionnement dans Docker

### 2.2 Exercice : Création et utilisation de secrets (20 min)
1. Créez un secret contenant un mot de passe pour une base de données
2. Lancez un conteneur PostgreSQL en utilisant ce secret
3. Vérifiez que le secret est correctement utilisé

### 2.3 Exercice : Secrets dans Docker Compose (20 min)
1. Créez un fichier Docker Compose utilisant le secret précédent
2. Ajoutez un service web qui se connecte à la base de données en utilisant le secret

### 2.4 Défi : Rotation des secrets (10 min)
Implémentez une méthode pour mettre à jour un secret sans interruption de service

---

## 3. Réseaux Docker (1h)

### 3.1 Introduction aux réseaux Docker (10 min)
- Explication des types de réseaux : bridge, host, overlay, macvlan

### 3.2 Exercice : Réseau bridge personnalisé (20 min)
1. Créez un réseau bridge personnalisé
2. Lancez deux conteneurs sur ce réseau
3. Testez la communication entre ces conteneurs

### 3.3 Exercice : Réseau overlay (si possible avec Docker Swarm) (20 min)
1. Initialisez un swarm Docker
2. Créez un réseau overlay
3. Déployez un service utilisant ce réseau

### 3.4 Défi : Isolation réseau (10 min)
Configurez un environnement avec trois réseaux isolés et démontrez l'isolation

---

## 4. Merge de fichiers Docker Compose (1h)

### 4.1 Introduction au merge de fichiers Compose (10 min)
- Explication de l'utilité et des cas d'usage

### 4.2 Exercice : Merge simple (20 min)
1. Créez un fichier `docker-compose.yml` de base
2. Créez un fichier `docker-compose.override.yml`
3. Combinez ces fichiers et observez le résultat

### 4.3 Exercice : Merge pour différents environnements (20 min)
1. Créez des fichiers pour les environnements dev, test et prod
2. Utilisez le merge pour déployer dans chaque environnement

### 4.4 Défi : Merge complexe (10 min)
Créez une structure de fichiers Compose permettant de gérer plusieurs services avec des configurations spécifiques par environnement

---

## 5. Projet final (1h)

### Objectif
Créer une application multi-conteneurs utilisant tous les concepts vus précédemment.

### Description du projet
Développez une application web avec :
- Un frontend (Nginx)
- Un backend (Node.js)
- Une base de données (PostgreSQL)
- Un cache (Redis)

### Exigences
1. Utilisez des volumes pour la persistance des données
2. Implémentez des secrets pour les mots de passe
3. Configurez des réseaux isolés pour la sécurité
4. Utilisez le merge de fichiers Compose pour gérer les environnements dev et prod

### Étapes suggérées
1. Créez les Dockerfiles nécessaires
2. Configurez les volumes et les secrets
3. Mettez en place la structure réseau
4. Créez les fichiers Docker Compose et implémentez le merge
5. Testez le déploiement en dev et en prod

### Bonus
- Ajoutez un service de monitoring (par exemple, Prometheus + Grafana)


