# Enterprise Server Lab

## Projektbeschreibung
Dieses Projekt dokumentiert den Aufbau eines sicheren, containerisierten Serversystems auf Basis von Ubuntu. Ziel ist es, eine realistische Unternehmensumgebung zu simulieren und praktische Kenntnisse in Systemadministration, Netzwerken und IT-Sicherheit zu erlangen.

---

## Ziele
- Aufbau eines Linux-Servers
- Nutzung von Docker zur Containerisierung
- Einrichtung eines Reverse Proxys
- Implementierung von Sicherheitsmechanismen
- Systemüberwachung und Analyse

---

## Technologien
- Ubuntu Server
- Docker
- NGINX
- Portainer
- Fail2Ban

---

## Architektur

Der Server besteht aus mehreren Docker-Containern:

- Website (Port 8080)
- App (Port 8081)
- Reverse Proxy (Port 80)
- Portainer UI (Port 9000)

Routing über Reverse Proxy:

- `/` → Website
- `/app/` → App

---

## Sicherheit
- Firewall (UFW)
- SSH abgesichert
- Fail2Ban (Schutz vor Brute-Force-Angriffen)

---

## Monitoring
- Portainer (Container UI)
- htop (Systemmonitoring)
- Log-Analyse (journalctl, docker logs)

---

## Aktueller Stand
- Server läuft stabil
- Container aktiv
- Reverse Proxy funktioniert
- Sicherheitsmaßnahmen implementiert

---

## Nächste Schritte
- Datenbank integrieren
- Lokale KI hinzufügen
- Monitoring erweitern
- Automatisierung (CI/CD)

---

## Autor
Kemal
