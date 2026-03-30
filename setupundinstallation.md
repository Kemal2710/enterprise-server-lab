# Installation Guide

## System Update
```bash
sudo apt update && sudo apt upgrade -y
```

---

## Benutzer erstellen
```bash
sudo adduser admin
sudo usermod -aG sudo admin
su - admin
```

---

## Firewall (UFW)
```bash
sudo apt install ufw -y
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 22/tcp
sudo ufw enable
sudo ufw status
```

---

## SSH
```bash
sudo apt install openssh-server -y
sudo systemctl enable ssh
sudo systemctl start ssh
```

---

## Projektstruktur
```bash
mkdir -p ~/server/{docker,configs,data,logs}
```

---

## Docker
```bash
sudo apt install docker.io -y
sudo systemctl enable docker
sudo systemctl start docker
docker run hello-world
sudo usermod -aG docker $USER
```

---

## Netzwerk
```bash
docker network create mynet
```

---

## Website

```bash
mkdir -p ~/server/website
nano ~/server/website/index.html
```

HTML Inhalt:
```html
<h1>Delamain Server läuft</h1>
<p>Mein erstes sicheres System</p>
```

Container starten:
```bash
docker run -d \
--name website \
--network mynet \
-p 8080:80 \
-v ~/server/website:/usr/share/nginx/html \
nginx
```

---

## App

```bash
mkdir -p ~/server/apps/app1
nano ~/server/apps/app1/index.html
```

HTML Inhalt:
```html
<h1>App1 läuft</h1>
<p>Interner Dienst</p>
```

Container starten:
```bash
docker run -d \
--name app1 \
--network mynet \
-p 8081:80 \
-v ~/server/apps/app1:/usr/share/nginx/html \
nginx
```

---

## Reverse Proxy

```bash
mkdir -p ~/server/proxy
nano ~/server/proxy/nginx.conf
```

Config:
```nginx
events {}

http {
    server {
        listen 80;

        location / {
            proxy_pass http://website;
        }

        location /app/ {
            proxy_pass http://app1/;
        }
    }
}
```

Container starten:
```bash
docker run -d \
--name proxy \
--network mynet \
-p 80:80 \
-v ~/server/proxy/nginx.conf:/etc/nginx/nginx.conf \
nginx
```

---

## Portainer (UI)

```bash
docker volume create portainer_data
```

```bash
docker run -d \
--name portainer \
--network mynet \
-p 9000:9000 \
-v /var/run/docker.sock:/var/run/docker.sock \
-v portainer_data:/data \
portainer/portainer-ce
```

---

## Monitoring

```bash
sudo apt install htop -y
htop
```

---

## Fail2Ban

```bash
sudo apt install fail2ban -y
sudo systemctl enable fail2ban
sudo systemctl start fail2ban
```

Config erstellen:

```bash
sudo nano /etc/fail2ban/jail.local
```

Inhalt:
```ini
[DEFAULT]
bantime = 600
findtime = 600
maxretry = 5

[sshd]
enabled = true
```

Neustarten:
```bash
sudo systemctl restart fail2ban
sudo fail2ban-client status
```

---

## Logs & Analyse

```bash
journalctl -u ssh
docker logs website
ss -tuln
```

---

# Skills

## Systemadministration
- Linux Server Setup
- Benutzerverwaltung
- Systemprozesse verstehen

## Netzwerke
- Ports und Verbindungen
- TCP/UDP Grundlagen
- Client-Server Kommunikation

## Docker
- Container erstellen und verwalten
- Netzwerke nutzen (mynet)
- Volumes verstehen

## Web
- NGINX konfigurieren
- Reverse Proxy einrichten
- Routing verstehen

## Sicherheit
- Firewall konfigurieren (UFW)
- SSH absichern
- Brute-Force Schutz mit Fail2Ban
- Log-Analyse

## Monitoring
- Systemüberwachung mit htop
- Docker Logs analysieren
