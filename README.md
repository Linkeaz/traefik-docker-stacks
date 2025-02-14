# 📌 Traefik and Docker Stacks

[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

![Linux Compatible](https://img.shields.io/badge/Linux-Compatible-green?logo=linux)
![Ubuntu 22.04+](https://img.shields.io/badge/Ubuntu-22.04%2B-orange?logo=ubuntu)
![Debian 11+](https://img.shields.io/badge/Debian-11%2B-blue?logo=debian)
![Docker](https://img.shields.io/badge/Docker-Compose-informational?logo=docker)
![Traefik Prêt](https://img.shields.io/badge/Traefik-Ready-blueviolet?logo=traefikproxy)

This collection of **Docker Compose** stacks enables easy self-hosting using **Traefik** as the main reverse proxy. It automatically manages SSL certificates and secure routing.

#### ➡ **Read the French version/Lire la version française:** [LISEZ-MOI.md](LISEZ-MOI.md)
---

## 📂 Project Structure

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
LISEZ-MOI.md (French version)
README.md (this file)
```

Each Docker service is organized in its own subdirectory with its respective `docker-compose.yml` file.

---

## 💡 Project Overview

This project offers a collection of ready-to-use Docker Compose stacks, centered around **Traefik** as a reverse proxy. It simplifies self-hosting by ensuring **secure routing** and **automated SSL certificate management** via Let's Encrypt.

### 🔹 Key Features:
- **Traefik** as a reverse proxy to centralize and secure service access.
- **Simplified SSL certificate management** with Let's Encrypt.
- **Dockge** for graphical management of Docker stacks.
- **Modular organization** allowing easy integration of new services.

---

## 🔧 Available Stacks

### 🏗 **Traefik** (Secure Reverse Proxy)
- Smart routing for HTTP/HTTPS requests.
- Automated SSL certificate management.
- Service security with middlewares (authentication, IP filtering, etc.).

### 📊 **Dockge** (Container Management Interface)
- Simplified web interface for managing services.
- Quick access to logs and Docker configurations.
- Easy integration with Traefik.

### 🔄 **Other Modular Services**
The project is designed to be **scalable**, allowing additional services to be integrated into Traefik with custom configurations.

---

## ⚙️ Configuration and Customization

Each stack offers different configuration methods depending on usage:

- **Via `.env` files**: Some services use environment variables stored in a `.env` file.
- **Via `docker-compose.yml`**: Main configurations are directly within this file.
- **Customization during installation**: Some parameters must be manually set during initial setup.

### Configuration Examples
- **Secure Access**: Add authentication or restrict access via Traefik middlewares.
- **SSL Certificates**: Let's Encrypt automatically generates certificates; ensure your DNS is correctly set up before deployment.

---

## 📖 Useful Resources

- [Traefik Documentation](https://doc.traefik.io/traefik/)
- [Docker Docs](https://docs.docker.com/)
- [Let’s Encrypt](https://letsencrypt.org/docs/)

---

## 📜 License & Attribution

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

This project is licensed under the [Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

### 🔹 Rights and Obligations:
- ✅ You may **use, modify, and redistribute** this guide and its configurations.
- ✅ You must **credit the author** by citing **[Slym B.](https://github.com/slym-b)**.
- ❌ You **may not remove attribution**.

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

---

