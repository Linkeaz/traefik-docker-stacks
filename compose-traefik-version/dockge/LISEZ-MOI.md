<p align="center">
    <img src="https://raw.githubusercontent.com/louislam/dockge/master/frontend/public/icon.svg" width="100" alt="Dockge Logo" />
</p>

# Dockge

### Auteur : [Louis Lam](https://github.com/louislam)

### Dépôt : [Dockge sur GitHub](https://github.com/louislam/dockge/tree/master)

Un gestionnaire élégant, intuitif et réactif pour les piles Docker Compose.

## À propos

Dockge est un outil léger et efficace conçu pour gérer les stacks **Docker Compose** via une interface utilisateur simple et intuitive. Il permet d'administrer facilement plusieurs services en conteneur tout en offrant une gestion optimisée et fluide.

## Fonctionnalités

- **Gestion simplifiée** des stacks Docker Compose.
- **Interface utilisateur intuitive** pour administrer les conteneurs.
- **Léger et réactif** pour un usage efficace.
- **Compatibilité complète avec Docker Compose**.

## Conteneurs

| Nom    | Description                                     | Port |
| ------ | ----------------------------------------------- | ---- |
| dockge | Interface web pour la gestion des stacks Docker | 5001 |

## Configuration du filtrage IP (optionnel)

Traefik permet d'activer un filtrage d'IP pour restreindre l'accès à certains utilisateurs.
Pour l'activer, ajoutez les adresses IP autorisées dans le fichier .env sous la variable ALLOWED_IPS.

Exemple de configuration dans `.env`:

```ini
ALLOWED_IPS=192.168.1.1,192.168.1.2
```

Si vous ne souhaitez pas activer cette restriction, vous pouvez commenter ou supprimer ces lignes dans le `docker-compose.yml` :

```yaml
- "traefik.http.routers.dockge.middlewares=dockge-ipwhitelist"
- "traefik.http.middlewares.dockge-ipwhitelist.ipwhitelist.sourcerange=${ALLOWED_IPS}"
```

## Documentation

Pour plus d'informations sur l'installation et l'utilisation, consultez la [Documentation officielle de Dockge](https://github.com/louislam/dockge/tree/master).

## Communauté & Support

- [Dépôt GitHub](https://github.com/louislam/dockge)
- [Issues GitHub](https://github.com/louislam/dockge/issues)

