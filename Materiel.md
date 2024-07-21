### Matériel du Workshop

#### Création d'Infrastructure avec Terraform

- **Introduction à Terraform**
  - Concepts de base de Terraform.
  - Modules Terraform.
  - Variables et Précédence.
  - Backend Local vs. Remote.
  - Provisioners.

- **Création d'une Infrastructure Simple**

  ```hcl
  # main.tf
  provider "aws" {
    region = "us-west-2"
  }

  resource "aws_instance" "example" {
    ami           = "ami-0c55b159cbfafe1f0"
    instance_type = "t2.micro"

    tags = {
      Name = "Terraform Example"
    }
  }
  ```

- **Exercice Pratique : Variables et Outputs**

  ```hcl
  # variables.tf
  variable "instance_type" {
    description = "Type d'instance EC2"
    default     = "t2.micro"
  }

  # outputs.tf
  output "instance_id" {
    value = aws_instance.example.id
  }
  ```

#### Gestion de Configuration avec Ansible

- **Introduction à Ansible**
  - Concepts de base d'Ansible.
  - Inventaire Ansible.
  - Commandes Ad Hoc.
  - Configuration ansible.cfg.
  - Modules Intégrés.

- **Playbook Ansible 001**

  ```yaml
  # playbook001.yml
  - name: Configuration de base des serveurs
    hosts: all
    tasks:
      - name: Créer un utilisateur
        user:
          name: john
          state: present
          groups: sudo

      - name: Configurer les permissions des fichiers
        file:
          path: /etc/example.conf
          owner: root
          group: root
          mode: '0644'
  ```

- **Playbook Ansible 002**

  ```yaml
  # playbook002.yml
  - name: Installation et configuration d'un serveur web Nginx
    hosts: all
    tasks:
      - name: Installer Nginx
        apt:
          name: nginx
          state: present
          update_cache: yes

      - name: Démarrer le service Nginx
        service:
          name: nginx
          state: started
          enabled: yes

      - name: Déployer la configuration Nginx
        template:
          src: templates/nginx.conf.j2
          dest: /etc/nginx/nginx.conf
        notify:
          - Redémarrer Nginx

    handlers:
      - name: Redémarrer Nginx
        service:
          name: nginx
          state: restarted
  ```

#### Rappel Mémoire Linux

- **Concepts Essentiels de Linux**
  - Introduction à SED et AWK.
  - Expressions Régulières.
  - Processus de Boot et de Login.
  - Gestion des Partitions.
  - Espace Utilisateur vs. Espace Noyau.
  - Configuration des Interfaces Réseaux.

- **Utilisation de SED**

  ```bash
  # Remplacer toutes les occurrences de 'foo' par 'bar' dans un fichier
  sed 's/foo/bar/g' fichier.txt
  ```

- **Utilisation de AWK**

  ```bash
  # Imprimer la première et la troisième colonne d'un fichier
  awk '{print $1, $3}' fichier.txt
  ```

#### Notions de Base Docker

- **Architecture et Configuration Réseau de Docker**
  - Introduction à Docker.
  - Réseau Bridge.
  - Écriture de Dockerfiles.

- **Dockerfile pour Ubuntu avec SSH**

  ```dockerfile
  # Dockerfile
  FROM ubuntu:20.04

  RUN apt-get update && apt-get install -y openssh-server
  RUN mkdir /var/run/sshd
  RUN echo 'root:password' | chpasswd

  EXPOSE 22
  CMD ["/usr/sbin/sshd", "-D"]
  ```

#### Services AWS

- **Présentation d'AWS S3 et DynamoDB**
  - Introduction à Amazon S3.
  - Introduction à DynamoDB.

- **Configuration d'un Bucket S3**

  ```bash
  # Créer un bucket S3
  aws s3 mb s3://my-bucket-name
  ```

- **Création d'une Table DynamoDB**

  ```bash
  # Créer une table DynamoDB
  aws dynamodb create-table --table-name MaTable \
      --attribute-definitions AttributeName=Id,AttributeType=S \
      --key-schema AttributeName=Id,KeyType=HASH \
      --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5
  ```

