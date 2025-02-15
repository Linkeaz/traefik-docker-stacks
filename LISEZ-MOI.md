# 📌 Traefik et Docker Stacks

[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

![Ubuntu 22.04+](https://img.shields.io/badge/Ubuntu-22.04%2B-orange?logo=ubuntu)
![Debian 11+](https://img.shields.io/badge/Debian-11%2B-blue?logo=debian)
![Docker](https://img.shields.io/badge/Docker-Compose-informational?logo=docker)
![Traefik Prêt](https://img.shields.io/badge/Traefik-Ready-blueviolet?logo=traefikproxy)


Cette collection de stacks **Docker Compose** permet d'auto-héberger facilement vos services avec **Traefik** comme reverse proxy principal. Il gère automatiquement les certificats SSL et le routage sécurisé.

#### ➡ **Lire la version anglaise/Read the english version :** [README.md](README.md)
---

## 📂 Structure du projet

```
compose-traefik-version/
│── dockge/
│   ├── .env.example
│   ├── LISEZ-MOI.md
│   ├── README.md
│   ├── docker-compose.yml
│── traefik/
│   ├── .env.example
│   ├── LISEZ-MOI.md
│   ├── README.md
│   ├── docker-compose.yml
│── .../
CODE_OF_CONDUCT.md
LICENSE
LISEZ-MOI.md (ce fichier)
README.md (version anglaise)
```

Chaque service Docker est organisé dans un sous-dossier dédié avec son propre `docker-compose.yml`.

---

## 💡 Présentation du projet

Ce projet propose une collection de stacks Docker Compose prêtes à l'emploi, centrées autour de **Traefik** en tant que reverse proxy. Il simplifie l'auto-hébergement de services web en assurant un **routage sécurisé** et une **gestion automatisée des certificats SSL** via Let's Encrypt.

### 🔹 Points clés :
- **Traefik** comme proxy inverse pour centraliser et sécuriser l’accès aux services.
- **Gestion simplifiée des certificats SSL** avec Let's Encrypt.
- **Dockge** pour une gestion graphique des stacks Docker.
- **Organisation modulaire** permettant d'ajouter facilement de nouveaux services.

---

## 🔧 Stacks disponibles

### 🏗 **Traefik** (reverse proxy sécurisé)
- Routage intelligent des requêtes HTTP/HTTPS
- Gestion automatique des certificats SSL
- Sécurisation des services avec des middlewares (authentification, filtrage IP...)

### 📊 **Dockge** (interface de gestion des containers)
- Interface web simplifiée pour gérer les services
- Accès rapide aux logs et configurations Docker
- Intégration facile avec Traefik

### 🔄 **Autres services modulaires**
Le projet est conçu pour être **évolutif** : vous pouvez ajouter d'autres services et les intégrer à Traefik avec des configurations personnalisées.

---

## ⚙️ Configuration et Personnalisation

Chaque stack dispose de différentes méthodes de configuration selon son usage :

- **Via des fichiers `.env`** : Certains services utilisent des variables d'environnement stockées dans un `.env`.
- **Via `docker-compose.yml`** : Les configurations principales se trouvent directement dans ce fichier.
- **Personnalisation à l'installation** : D'autres paramètres doivent être définis manuellement au premier lancement.

### Exemples de configurations
- **Accès sécurisé** : Ajouter une authentification ou limiter les accès IP via les middlewares Traefik.
- **Certificats SSL** : Let's Encrypt génère automatiquement des certificats, assurez-vous que votre DNS est correctement configuré avant le premier lancement.

---

## 📖 Ressources utiles

- [Documentation Traefik](https://doc.traefik.io/traefik/)
- [Docker Docs](https://docs.docker.com/)
- [Let’s Encrypt](https://letsencrypt.org/docs/)

---

## 📜 Licence & Attribution

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

Ce projet est sous licence [Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

### 🔹 Droits et obligations :
- ✅ Vous pouvez **utiliser, modifier et redistribuer** ce guide et ses configurations.
- ✅ Vous devez **mentionner l’auteur** en citant **[Slym B.](https://github.com/slymb)**.
- ❌ Vous ne pouvez **pas supprimer l’attribution**.

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

---
