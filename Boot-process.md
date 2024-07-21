

<img src="images/diagram.png" alt="Diagram" width="400"/>


Le processus de boot sous Linux se compose de plusieurs étapes distinctes qui permettent au système d'exploitation de passer de l'état de mise sous tension à un système pleinement opérationnel. Voici une vue d'ensemble des principales étapes du processus de boot :

1. **BIOS/UEFI** :
   - **BIOS (Basic Input/Output System)** ou **UEFI (Unified Extensible Firmware Interface)** est le premier code exécuté lorsque l'ordinateur est allumé.
   - Le BIOS/UEFI initialise le matériel, effectue des tests matériels de base (POST - Power-On Self Test), et recherche un périphérique de démarrage (disque dur, SSD, clé USB, etc.) contenant un chargeur de démarrage.

2. **MBR/GPT** :
   - Le BIOS/UEFI lit le **MBR (Master Boot Record)** ou la **GPT (GUID Partition Table)** du périphérique de démarrage.
   - Le MBR, qui est situé dans le premier secteur du disque, contient un petit code exécutable appelé **bootloader** et la table de partitions du disque.
   - La GPT est une version plus moderne de la table de partitions, utilisée surtout avec UEFI.

3. **Bootloader** :
   - Le **bootloader** (par exemple, GRUB - GRand Unified Bootloader) est chargé par le BIOS/UEFI.
   - Le bootloader permet de sélectionner le système d'exploitation à démarrer (en cas de multiboot) et charge le noyau Linux en mémoire.
   - Il peut également passer des paramètres au noyau Linux.

4. **Noyau Linux** :
   - Le bootloader charge le **noyau Linux** en mémoire et lui passe le contrôle.
   - Le noyau initialise les composants matériels (processeur, mémoire, périphériques) et monte le système de fichiers root (root filesystem).
   - Il exécute ensuite le processus init ou systemd.

5. **Init/Systemd** :
   - **Init** (ou **systemd** sur les systèmes modernes) est le premier processus utilisateur exécuté par le noyau Linux. Il a l'ID de processus 1 (PID 1).
   - **Systemd** est un système d'initialisation et un gestionnaire de services qui gère les services de démarrage et les dépendances, offre une meilleure parallélisation des tâches de démarrage et réduit le temps de démarrage.

6. **Runlevel/Target** :
   - **Init** utilise des runlevels (niveaux de fonctionnement) pour définir l'état du système et les services à démarrer.
   - **Systemd** utilise des cibles (targets) qui sont des points de synchronisation pour l'initialisation du système.
   - Les runlevels traditionnels vont de 0 à 6, chaque niveau ayant un but spécifique (par exemple, 3 pour multi-utilisateur sans interface graphique, 5 pour multi-utilisateur avec interface graphique, 0 pour arrêt, 6 pour redémarrage).
   - Les cibles de systemd sont plus flexibles et permettent une gestion plus fine des états et des services (par exemple, multi-user.target, graphical.target).

7. **Services et Daemons** :
   - À ce stade, les services et démons (daemons) configurés pour démarrer au boot sont lancés. Cela inclut des services tels que le réseau, les journaux système, les interfaces utilisateur graphiques, etc.
   - Ces services sont définis dans des fichiers de configuration et sont gérés par init scripts ou unit files (dans le cas de systemd).

8. **Login Prompt** :
   - Une fois que tous les services nécessaires sont démarrés, le système présente une invite de connexion (login prompt).
   - Cela peut être une invite de connexion en mode texte (TTY) ou un gestionnaire de connexion graphique (comme GDM, LightDM) si le système est configuré pour démarrer en mode graphique.

9. **Session Utilisateur** :
   - Après la connexion, une session utilisateur est lancée. En mode graphique, cela inclut le gestionnaire de fenêtres et le bureau.
   - Les scripts de démarrage utilisateur (comme .bashrc, .profile pour bash) sont exécutés.

Chaque étape du processus de boot est essentielle pour s'assurer que le système d'exploitation Linux démarre correctement et est prêt à être utilisé.
