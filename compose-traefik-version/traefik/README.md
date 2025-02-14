<p align="center">
    <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo-dark.png">
        <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo.png">
        <img alt="Traefik" title="Traefik" src="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo.png" width="250">
    </picture>
</p>

# Traefik

### Author: [Traefik Labs](https://github.com/traefik)
### Repository: [Traefik on GitHub](https://github.com/traefik/traefik)

A modern, cloud-native, and easy-to-use reverse proxy.

## About

Traefik is a **reverse proxy** and **load balancer** designed for modern cloud-native applications. It integrates seamlessly with **Docker**, **Kubernetes**, **Consul**, and other orchestrators, automatically detecting services and routing traffic without extensive manual configuration.

## Features

- **Automatic service discovery**: Dynamically updates routes when services start, stop, or change.
- **Built-in Let's Encrypt SSL**: Automatically generates and renews HTTPS certificates.
- **Powerful middleware**: Authentication, rate limiting, and custom routing.
- **Observability**: Detailed metrics, logging, and tracing support.
- **Flexible deployment**: Works with Docker, Kubernetes, Swarm, Consul, and more.
- **Dashboard**: Intuitive web interface for monitoring and managing traffic routes.

## Containers

| Name    | Description                               | Ports  |
| ------- | ----------------------------------------- | ------ |
| traefik | Reverse proxy and load balancing manager | 80, 443 |

## IP Filtering Configuration (Optional)

Traefik allows enabling IP filtering to restrict access to specific users.
To enable it, add the authorized IP addresses in the `.env` file under the variable `ALLOWED_IPS`.

Example configuration in `.env`:
```ini
ALLOWED_IPS=192.168.1.1,192.168.1.2
```

If you do not want to enable this restriction, you can comment out or remove these lines in `docker-compose.yml`:
```yaml
- "traefik.http.routers.traefik-secure.middlewares=traefik-ipwhitelist"
- "traefik.http.middlewares.traefik-ipwhitelist.ipwhitelist.sourcerange=${ALLOWED_IPS}"
```

## Authentication Configuration

To secure the Traefik dashboard with basic authentication, follow these steps:

### Install `htpasswd`:
```bash
sudo apt update
sudo apt install apache2-utils
```

### Generate a user and password for the dashboard:
```bash
echo $(htpasswd -nb user password) | sed -e s/\$/\$\$/g
```
Replace `user` and `password` with your desired credentials.

### Modify the `.env` file and add:
```env
TRAEFIK_DASHBOARD_CREDENTIALS=user:password
```

## Documentation

For detailed installation instructions and advanced configurations, check the [Official Traefik Documentation](https://doc.traefik.io/traefik).

## Community & Support

- [Community Forum](https://community.traefik.io/)
- [Twitter](https://twitter.com/intent/follow?screen_name=traefik)
- [GitHub Issues](https://github.com/traefik/traefik/issues)

