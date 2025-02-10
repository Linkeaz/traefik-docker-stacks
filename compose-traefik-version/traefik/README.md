<p align="left">
    <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo-dark.png">
        <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo.png">
        <img alt="Traefik" title="Traefik" src="https://raw.githubusercontent.com/traefik/traefik/master/docs/content/assets/img/traefik.logo.png" width="250">
    </picture>
</p>

# Traefik

### Author : [Traefik Labs](https://github.com/traefik)

### Repository : [Traefik on GitHub](https://github.com/traefik/traefik)

A modern, cloud-native, and easy-to-use reverse proxy and load balancer.

## About

Traefik is an efficient and dynamic **reverse proxy** and **load balancer** designed for modern cloud-native applications. It integrates seamlessly with **Docker**, **Kubernetes**, **Consul**, and various other orchestrators, automatically detecting services and routing traffic without requiring extensive manual configuration.

## Features

- **Automatic service discovery**: Traefik dynamically updates routes as services start, stop, or scale.
- **Built-in Let's Encrypt SSL**: Automated HTTPS certificates and renewal.
- **Powerful middleware**: Includes authentication, rate limiting, and custom routing.
- **Observability**: Detailed metrics, logging, and tracing support.
- **Flexible deployment**: Works with Docker, Kubernetes, Swarm, Consul, and more.
- **Dashboard**: Intuitive web UI for monitoring and managing traffic routes.

## Containers

| Name    | Description                                | Port    |
| ------- | ------------------------------------------ | ------- |
| traefik | Reverse proxy and load balancer management | 80, 443 |

## Setting Up Authentication

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

For detailed setup instructions and advanced configurations, visit the official [Traefik Documentation](https://doc.traefik.io/traefik).

## Community & Support

- [Community Forum](https://community.traefik.io/)
- [Twitter](https://twitter.com/intent/follow?screen_name=traefik)
- [GitHub Issues](https://github.com/traefik/traefik/issues)
