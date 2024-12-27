# Martian's Hands-on AppSec Training Resources




# Self-Hosted Mini AppSec Range (Docker)

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
