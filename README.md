## WORKSHOP 001: Automatisation de l'Infrastructure et Gestion de la Configuration

### Stack

- Ansible
- Terraform
- Linux
- Docker
- AWS

### Objectifs

#### 1. Création de l'infrastructure nécessaire à l'outil de configuration Ansible à l'aide de Terraform

##### Notions

- **Modules Terraform** : Comprendre l'utilisation des modules dans Terraform, créer du code réutilisable et évolutif, organiser l'infrastructure en tant que code.
- **Outputs** : Définir des outputs dans Terraform pour exposer des informations sur l'infrastructure, telles que des adresses IP ou des IDs de ressources, à utiliser dans d'autres configurations ou pour la documentation.
- **Variables et Précédence** : Gérer les variables d'entrée dans Terraform, comprendre l'ordre de priorité, et gérer les données sensibles de manière sécurisée.
- **Backend Local vs. Remote** : Comparer le stockage d'état local avec des backends distants comme S3, comprendre les avantages de l'utilisation de backends distants pour la collaboration et la gestion de l'état.
- **S3 Backend** : Configurer S3 en tant que backend distant pour stocker les fichiers d'état de Terraform, assurer la sécurité et la cohérence des données.
- **Provisioners** : Utiliser les provisioners pour exécuter des scripts sur des machines distantes ou locales dans le cadre du processus de déploiement de Terraform, comprendre les meilleures pratiques pour l'utilisation des provisioners.

#### 2. Configuration des serveurs avec Ansible

##### Notions

- **Inventaire Ansible** : Définir et gérer l'inventaire des hôtes que Ansible va gérer, comprendre les différents formats d'inventaire (INI, YAML).
- **Commandes Ad Hoc** : Exécuter des commandes ponctuelles sur des hôtes distants en utilisant les commandes ad hoc d'Ansible, utiles pour des tâches rapides et des tests.
- **Variables d'Inventaire** : Utiliser les variables d'inventaire pour gérer les détails de configuration spécifiques aux hôtes ou aux groupes d'hôtes, améliorer la flexibilité et la réutilisabilité des playbooks.
- **Ansible.cfg** : Personnaliser le comportement d'Ansible via le fichier de configuration ansible.cfg, définir des paramètres par défaut pour l'inventaire, les options SSH, etc.
- **Modules Intégrés** : Explorer les modules essentiels d'Ansible pour les tâches courantes, telles que la gestion des utilisateurs, les opérations sur les fichiers et le contrôle des services.
- **Playbook Ansible 001** : Écrire un playbook pour automatiser des tâches comme la création d'utilisateurs et de groupes, les permissions de fichiers, la configuration SSH, les liens symboliques et les paramètres d'interface réseau.
- **Playbook Ansible 002** : Créer un playbook pour installer et configurer un serveur web Nginx, gérer les dépendances basées sur les facts d'Ansible, utiliser les variables et le templating.
- **Handlers** : Implémenter des handlers pour déclencher des actions en fonction des résultats des tâches, garantir que des tâches comme le redémarrage des services ne se produisent que lorsque cela est nécessaire.
- **Rôles et Ansible Galaxy** : Structurer les playbooks en rôles pour la modularité et la réutilisabilité, utiliser Ansible Galaxy pour trouver et partager des rôles.

#### 3. Linux - Rappel Mémoire

##### Notions

- **SED** : Maîtriser l'éditeur de flux pour analyser et transformer du texte dans des fichiers ou des flux.
- **AWK** : Utiliser le langage de programmation AWK pour le balayage et le traitement de motifs.
- **Regex** : Appliquer des expressions régulières pour la recherche et la manipulation de texte avancées.
- **Processus de Boot** : Comprendre le processus de démarrage de Linux, du BIOS/UEFI à l'initialisation du système.
- **Processus de Login** : Analyser les étapes impliquées dans le processus de connexion Linux, de l'authentification de l'utilisateur à la configuration de la session.
- **Partitions** : Gérer les partitions de disque, comprendre la structure et l'utilisation des systèmes de fichiers.
- **Espace Utilisateur vs. Espace Noyau** : Différencier l'espace utilisateur de l'espace noyau et leur rôle dans le fonctionnement du système.
- **Interfaces Réseaux** : Configurer et gérer les interfaces réseaux sous Linux.
- **Conteneurs Bas Niveau** : Explorer les runtime de conteneurs comme runc, crio, containerd et dockerd.
- **Proxy Réseau** : Configurer et gérer les proxies réseau pour le forward et le reverse proxy.

#### 4. Docker

##### Notions

- **Architecture Réseau** : Comprendre l'architecture réseau de Docker, en se concentrant sur le réseau bridge pour la communication entre conteneurs.
- **Dockerfile** : Écrire des Dockerfiles pour créer des images SSH pour Ubuntu et CentOS, couvrir les meilleures pratiques pour la création et la gestion d'images.

#### 5. AWS

##### Notions

- **S3** : Utiliser Amazon S3 pour le stockage d'objets, comprendre la configuration des buckets, la gestion des données et la sécurité.
- **DynamoDB** : Gérer des bases de données NoSQL avec Amazon DynamoDB, comprendre la création de tables, les opérations sur les données et la mise à l'échelle.

### Structure du Workshop

1. **Introduction et Objectifs (30 mins)**
   - Présentation des objectifs et de l'agenda du workshop.
   - Brève introduction à chaque composant de la stack technologique.

2. **Création d'Infrastructure avec Terraform (2 heures)**
   - Cours : Introduction à Terraform et ses concepts de base.
   - Pratique : Création d'une infrastructure simple avec Terraform.
   - Exercice : Définir des variables, des outputs et utiliser des modules.

3. **Gestion de Configuration avec Ansible (2 heures)**
   - Cours : Introduction à Ansible, gestion des inventaires et commandes ad hoc.
   - Pratique : Écriture de playbooks de base pour la configuration des serveurs.
   - Exercice : Création de playbooks complexes et de rôles.

4. **Rappel Mémoire Linux (1.5 heures)**
   - Cours : Concepts et commandes essentiels de Linux.
   - Pratique : Utilisation de SED, AWK et regex à travers des exemples.
   - Exercice : Comprendre les processus de boot et de login, et gérer les interfaces réseau.

5. **Notions de Base Docker (1.5 heures)**
   - Cours : Architecture et configuration réseau de Docker.
   - Pratique : Écriture de Dockerfiles pour des images SSH.
   - Exercice : Création et exécution de conteneurs Docker.

6. **Services AWS (1 heure)**
   - Cours : Présentation d'AWS S3 et DynamoDB.
   - Pratique : Configuration de buckets S3 et de tables DynamoDB.
   - Exercice : Réalisation d'opérations sur les données et gestion des ressources.

7. **Q&A et Conclusion (30 mins)**
   - Session ouverte pour les questions et clarifications.
   - Récapitulatif des points clés et prochaines étapes.

### Ressources

- **Lecture Préparatoire** : Introduction à chaque composant de la stack technologique.
- **Matériel du Workshop** : Diapositives, exemples de code et fichiers de configuration.
- **Devoirs Post-Workshop** : Tâches pratiques pour renforcer l'apprentissage et encourager l'exploration continue.
