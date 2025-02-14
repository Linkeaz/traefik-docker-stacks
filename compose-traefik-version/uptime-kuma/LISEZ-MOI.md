<p align="center">
    <img src="https://raw.githubusercontent.com/louislam/uptime-kuma/master/public/icon.svg" width="150" alt="Uptime Kuma Logo" />
</p>

# Uptime Kuma

### Auteur : [Louis Lam](https://github.com/louislam)
### Dépôt : [Uptime Kuma sur GitHub](https://github.com/louislam/uptime-kuma)

Une alternative open-source à "Uptime Robot" pour surveiller la disponibilité des services.

## À propos

Uptime Kuma est un moniteur de disponibilité simple et auto-hébergé permettant de suivre l'état de vos serveurs et services. Il dispose d'une interface web moderne et propose des notifications avancées.

## Fonctionnalités

- **Surveillance de serveurs et services** via HTTP(s), TCP, Ping, DNS, et plus encore.
- **Notifications personnalisables** avec Telegram, Discord, Email, Slack, et d'autres services.
- **Tableau de bord moderne et interactif**.
- **Stockage des journaux et historique des défaillances**.
- **Support des certificats SSL Let's Encrypt avec Traefik**.

## Conteneurs

| Nom          | Description                                     | Ports  |
|-------------|------------------------------------------------|--------|
| uptime-kuma | Interface web pour la surveillance des services | 3001   |

## Configuration du filtrage IP (optionnel)

Traefik permet d'activer un filtrage d'IP pour restreindre l'accès à Uptime Kuma.
Pour l'activer, ajoutez les adresses IP autorisées dans le fichier `.env` sous la variable `ALLOWED_IPS`.

Exemple de configuration dans `.env` :
```ini
ALLOWED_IPS=192.168.1.1,192.168.1.2
```

Si vous ne souhaitez pas activer cette restriction, vous pouvez commenter ou supprimer ces lignes dans `docker-compose.yml` :
```yaml
- "traefik.http.routers.uptime-kuma.middlewares=uptime-kuma-ipwhitelist"
- "traefik.http.middlewares.uptime-kuma-ipwhitelist.ipwhitelist.sourcerange=${ALLOWED_IPS}"
```

## Configuration des ressources (optionnel)

Les limites de ressources pour le conteneur Uptime Kuma peuvent être définies dans le fichier `.env` :
```ini
UPTIME_KUMA_MEMORY_LIMIT=256M
UPTIME_KUMA_MEMORY_RESERVATION=128M
UPTIME_KUMA_CPU_LIMIT=0.3
```
Ces valeurs permettent de limiter l'utilisation de la RAM et du CPU pour garantir un fonctionnement optimal sans surcharger le serveur.

## Documentation

Pour plus d'informations sur l'installation et les configurations avancées, consultez la [Documentation officielle de Uptime Kuma](https://github.com/louislam/uptime-kuma/wiki).

## Communauté & Support

- [Issues GitHub](https://github.com/louislam/uptime-kuma/issues)
