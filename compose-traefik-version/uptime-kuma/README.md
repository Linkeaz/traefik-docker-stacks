<p align="center">
    <img src="https://raw.githubusercontent.com/louislam/uptime-kuma/master/public/icon.svg" width="150" alt="Uptime Kuma Logo" />
</p>

# Uptime Kuma

### Author: [Louis Lam](https://github.com/louislam)
### Repository: [Uptime Kuma on GitHub](https://github.com/louislam/uptime-kuma)

An open-source alternative to "Uptime Robot" for monitoring service availability.

## About

Uptime Kuma is a simple, self-hosted uptime monitor that helps track the status of your servers and services. It features a modern web interface and provides advanced notifications.

## Features

- **Server and service monitoring** via HTTP(s), TCP, Ping, DNS, and more.
- **Customizable notifications** with Telegram, Discord, Email, Slack, and other services.
- **Modern and interactive dashboard**.
- **Log storage and failure history**.
- **Support for Let's Encrypt SSL certificates with Traefik**.

## Containers

| Name        | Description                                  | Ports  |
|------------|--------------------------------------------|--------|
| uptime-kuma | Web interface for service monitoring      | 3001   |

## IP Filtering Configuration (Optional)

Traefik allows enabling IP filtering to restrict access to Uptime Kuma.
To activate it, add the allowed IP addresses in the `.env` file under the `ALLOWED_IPS` variable.

Example configuration in `.env`:
```ini
ALLOWED_IPS=192.168.1.1,192.168.1.2
```

If you do not wish to enable this restriction, you can comment out or remove these lines in `docker-compose.yml`:
```yaml
- "traefik.http.routers.uptime-kuma.middlewares=uptime-kuma-ipwhitelist"
- "traefik.http.middlewares.uptime-kuma-ipwhitelist.ipwhitelist.sourcerange=${ALLOWED_IPS}"
```

## Resource Configuration (Optional)

Resource limits for the Uptime Kuma container can be set in the `.env` file:
```ini
UPTIME_KUMA_MEMORY_LIMIT=256M
UPTIME_KUMA_MEMORY_RESERVATION=128M
UPTIME_KUMA_CPU_LIMIT=0.3
```
These values help limit RAM and CPU usage to ensure optimal performance without overloading the server.

## Documentation

For more information on installation and advanced configurations, refer to the [Official Uptime Kuma Documentation](https://github.com/louislam/uptime-kuma/wiki).

## Community & Support

- [GitHub Issues](https://github.com/louislam/uptime-kuma/issues)
