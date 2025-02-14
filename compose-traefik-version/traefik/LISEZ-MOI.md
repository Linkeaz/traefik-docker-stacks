<p align="center">
    <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo-dark.png">
        <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo.png">
        <img alt="Traefik" title="Traefik" src="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo.png" width="250">
    </picture>
</p>

# Traefik

### Auteur : [Traefik Labs](https://github.com/traefik)
### Dépôt : [Traefik sur GitHub](https://github.com/traefik/traefik)

Un proxy inverse moderne, cloud-native et facile à utiliser.

## À propos

Traefik est un **proxy inverse** et un **équilibreur de charge** dynamique conçu pour les applications cloud-native modernes. Il s'intègre parfaitement avec **Docker**, **Kubernetes**, **Consul**, et divers autres orchestrateurs, détectant automatiquement les services et routant le trafic sans nécessiter une configuration manuelle étendue.

## Fonctionnalités

- **Découverte automatique des services** : mise à jour dynamique des routes lorsque des services démarrent, s'arrêtent ou évoluent.
- **SSL Let's Encrypt intégré** : génération et renouvellement automatique des certificats HTTPS.
- **Middleware puissant** : authentification, limitation de débit, et routage personnalisé.
- **Observabilité** : métriques détaillées, journalisation et support du tracing.
- **Déploiement flexible** : compatible avec Docker, Kubernetes, Swarm, Consul, et plus encore.
- **Tableau de bord** : interface web intuitive pour surveiller et gérer les routes de trafic.

## Conteneurs

| Nom    | Description                                | Ports  |
| ------- | ------------------------------------------ | ------- |
| traefik | Gestion du proxy inverse et de l'équilibrage de charge | 80, 443 |

## Configuration du filtrage IP (optionnel)

Traefik permet d'activer un filtrage d'IP pour restreindre l'accès à certains utilisateurs.
Pour l'activer, ajoutez les adresses IP autorisées dans le fichier `.env` sous la variable `ALLOWED_IPS`.

Exemple de configuration dans `.env`:
```ini
ALLOWED_IPS=192.168.1.1,192.168.1.2
```

Si vous ne souhaitez pas activer cette restriction, vous pouvez commenter ou supprimer ces lignes dans le `docker-compose.yml` :
```yaml
- "traefik.http.routers.traefik-secure.middlewares=traefik-ipwhitelist"
- "traefik.http.middlewares.traefik-ipwhitelist.ipwhitelist.sourcerange=${ALLOWED_IPS}"
```

## Configuration de l'authentification

Pour sécuriser le tableau de bord Traefik avec une authentification de base, suivez ces étapes :

### Installer `htpasswd` :
```bash
sudo apt update
sudo apt install apache2-utils
```

### Générer un utilisateur et un mot de passe pour le tableau de bord :
```bash
echo $(htpasswd -nb user password) | sed -e s/\$/\$\$/g
```
Remplacez `user` et `password` par vos identifiants souhaités.

### Modifier le fichier `.env` et ajouter :
```env
TRAEFIK_DASHBOARD_CREDENTIALS=user:password
```

## Configuration des ressources (optionnel)

Les limites de ressources pour le conteneur Traefik peuvent être définies dans le fichier `.env` :
```ini
TRAEFIK_MEMORY_LIMIT=512M
TRAEFIK_MEMORY_RESERVATION=256M
TRAEFIK_CPU_LIMIT=1.0
```
Ces valeurs permettent de limiter l'utilisation de la RAM et du CPU pour garantir un fonctionnement optimal sans surcharger le serveur.
## Documentation

Pour des instructions détaillées sur l'installation et les configurations avancées, consultez la [Documentation officielle de Traefik](https://doc.traefik.io/traefik).

## Communauté & Support

- [Forum communautaire](https://community.traefik.io/)
- [Twitter](https://twitter.com/intent/follow?screen_name=traefik)
- [Issues GitHub](https://github.com/traefik/traefik/issues)
