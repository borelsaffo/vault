## C'est quoi vault 
### Vault
      Un serveur Vault (ou HashiCorp Vault) est un outil open source conçu pour la gestion centralisée et sécurisée des secrets, tels que : 
       - les mots de passe, 
       - les clés d'API,
       - les certificats et autres informations sensibles.
       
       Vault permet de stocker, d'accéder et de distribuer ces secrets de manière sécurisée dans un environnement informatique.

    Vault fournit un coffre-fort dans lequel les secrets sont stockés de manière chiffrée. Il offre des fonctionnalités avancées telles que : 
    - l'audit des accès, 
    - la génération de mots de passe aléatoires, 
    - la rotation automatique des clés, et la prise en charge de plusieurs méthodes d'authentification pour contrôler l'accès aux secrets.

    L'utilisation de Vault permet de : 
    - centraliser la gestion des secrets, 
    - de limiter l'accès aux informations sensibles,
    - d'appliquer des politiques de sécurité granulaires et de faciliter l'intégration des secrets dans les applications, les infrastructures et les processus automatisés.

 Vault est une solution de gestion des secrets qui aide à sécuriser les informations sensibles utilisées dans un environnement informatique en offrant une couche de protection et de contrôle d'accès supplémentaire.

###  Installation 
    - wget https://releases.hashicorp.com/vault/1.8.4/vault_1.8.4_linux_amd64.zip
    - unzip vault_<version>_linux_amd64.zip
    - sudo mv vault /usr/local/bin/
    - vault --version


- creer le fichier de conf de vault
- indiquer a vault ou trouver sa conf 'dossier dans lequel il ya le fichier de conf) : vault server -config=/home/ubuntu/vault/
- export VAULT_ADDR=https://127.0.0.1:8200  si TLS activé dans le fichier de configuration de vaul
- si  TLS non activé : export VAULT_ADDR=http://127.0.0.1:8200

### Configuration de Vault
La configuration de vault passe par plusieurs étapes : 

        - Initialisation de Vault : La première étape consiste à initialiser Vault et à générer les clés de chiffrement nécessaires.
        Pour cela, exécutez la commande suivante : vault operator init
        Cette commande générera un jeu de clés maître et des clés d'urgence.

        - Démarrez le serveur Vault : Une fois Vault initialisé, vous pouvez démarrer le serveur Vault en utilisant la commande 
        suivante : vault server -config=/path/to/config/file
        Par défaut vault écoute sur le port 8200

        - Configuration de l'authentification : Vous devez configurer les méthodes d'authentification pour permettre aux
        utilisateurs ou aux applications de s'authentifier auprès de Vault. Vault prend en charge différentes méthodes d'authentification, telles que :
                . la méthode d'authentification basée sur les jetons (token-based authentication),
                . l'authentification par approbation (approvale-based authentication), 
                . l'authentification par certificat (certificate-based authentication), 

        - Configuration du stockage : Vous devez également configurer le backend de stockage pour Vault. 
        Vault peut être configuré pour stocker ses données dans différents backends, tels que : 
                . le stockage local, 
                . le stockage cloud, 
                . les bases de données, 

        - Politiques et secrets : Une fois Vault configuré, vous pouvez définir des politiques d'accès et commencer à stocker des
        secrets dans Vault. Les politiques définissent les autorisations d'accès aux secrets en fonction des rôles et des chemins d'accès. 
        pouvez également utiliser l'API de Vault pour gérer les secrets et effectuer des opérations telles que ;:
                . la création, 
                . la récupération,
                . la mise à jour 
                . et la suppression de secrets.
        Dans ce repertoire vous avez quelques exemple de fichier de configuration de vault.
###
###
###
###
###
