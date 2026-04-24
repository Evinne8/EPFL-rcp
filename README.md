# EPFL-rcp (Open WebUI + SearXNG + Entra ID)

> L'application étant actuellement en phase de test, le processus de configuration n'est pas encore totalement optimisé

Ce dépôt contient la configuration nécessaire pour déployer une instance locale d'Open WebUI couplée à SearXNG pour la recherche web, et sécurisée via Microsoft Entra ID (SSO).

## Prérequis
* Docker et Docker Compose installés.
* Une inscription d'application configurée dans Microsoft Entra ID.

---

## Étape 1 : Déploiement initial

1. Clonez ce dépôt sur votre machine.
2. Créez un fichier `.env` en copiant le modèle fourni et en remplaçant les valeurs :
    ```bash
   cp .env.example .env
   ```

3. Lancez les conteneurs :
    ```Bash
    docker compose up -d
    ```

## Étape 2 : Création du compte Administrateur
Important : Dans Open WebUI, le tout premier compte créé via le formulaire d'inscription classique devient automatiquement l'Administrateur du système.

- Accédez à votre instance (ex: http://localhost:3000).
- Ignorez le bouton de connexion Microsoft pour le moment.
- Créez un compte avec un nom, une adresse email et un mot de passe.
- Cliquez sur Sign Up (S'inscrire).
- Ce compte a désormais les droits d'administration. Vous pouvez l'utiliser pour gérer les modèles (Ollama, API), les rôles des utilisateurs et les outils.

## Étape 3 : Création d'un compte Utilisateur
Dans Open WebUI chaque utilisateur doit être validé par l'administrateur pour accéder à l'interface.

Retourner sur la page de login et cliquer sur le bouton "Se connecter avec Microsoft" !

Maintenant retourner sur votre compte administrateur, cliquez sur votre profil en bas à gauche, puis sur  "Admin Panel" et changer le rôle de votre nouvel utilisateur de "Pending" à "User".

Voilà, maintenant vous pouvez vous connecter avec votre EntraID.

## Étape 4 : Utilisation de SearXNG (Recherche Web)
Sur votre compte Admin, cliquer sur votre profil (en bas à gauche), puis sur "Admin Panel, puis sur "Settings" et accéder à l'onglet "Web Search" et configurer comme cela :
    <img width="1329" height="228" alt="image" src="https://github.com/user-attachments/assets/26f15216-a774-46bd-ab9d-f612403a88d4" />
