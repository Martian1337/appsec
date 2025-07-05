
#  AppSec Mini-Range

A plug-and-play application security mini-range built with Docker Compose, designed for learning, teaching, and testing common web and API vulnerabilities.

## What's Included

This environment includes the following intentionally vulnerable applications and services:

| Service        | Description                                                  | Port(s)                  |
|----------------|--------------------------------------------------------------|--------------------------|
| WebGoat        | Classic OWASP insecure Java app                              | 8080, 9090               |
| Juice Shop     | Modern insecure web app with rich OWASP coverage             | 8087                     |
| crAPI          | "Completely Ridiculous API" for API security hands-on labs  | Multiple (8082–8084, 8888, 8443) |
| PostgreSQL     | Backend DB for crAPI                                         | Internal                 |
| MongoDB        | NoSQL DB used by crAPI                                       | Internal                 |
| MailHog        | Email testing interface for crAPI mail features             | 8025                     |

The steps below also include Docker and Docker Compose installation.

## 🛠️ Usage

### Step1. Clone repo and Install docker
```bash
sudo apt install git && git clone https://github.com/martian1337/appsec/minirange.git && cd minirange && sudo apt-get update -y && sudo apt-get install ca-certificates curl lsb-release gnupg && sudo install -m 0755 -d /etc/apt/keyrings && sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc && sudo chmod a+r /etc/apt/keyrings/docker.asc && echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null && sudo apt-get update && sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y && sudo usermod -aG docker $USER && newgrp docker && sudo systemctl enable --now docker 
```
### Step 2. Start the environment

```bash
docker compose pull && docker compose up -d
```
---

Access the applications via your browser:

* WebGoat: [http://localhost:8080](http://localhost:8080)
* Juice Shop: [http://localhost:8087](http://localhost:8087)
* crAPI Web: [http://localhost:8888](http://localhost:8888)
* MailHog: [http://localhost:8025](http://localhost:8025)

