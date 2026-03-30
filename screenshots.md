## Screenshots

### Container Management (Portainer)


<img width="1810" height="985" alt="Bildschirmfoto vom 2026-03-30 23-56-20" src="https://github.com/user-attachments/assets/f49be3ab-b26f-4b13-8d0b-44383feba27e" />


Übersicht über die Docker-Umgebung mit laufenden Containern, Ressourcenverbrauch und Systemstatus.  
Die Oberfläche ermöglicht eine einfache Verwaltung sowie Monitoring in Echtzeit.

---

### Docker Container Übersicht

<img width="1810" height="985" alt="Bildschirmfoto vom 2026-03-30 23-56-36" src="https://github.com/user-attachments/assets/7a423bbd-dc62-412e-ac0c-d1f2b05fb0f0" />


Liste aller Container mit Status, Ports und IP-Adressen.  
Die zentralen Services (Website, App, Reverse Proxy, Portainer) sind hier sichtbar.

---

### Container Logs

<img width="1810" height="985" alt="Bildschirmfoto vom 2026-03-30 23-57-12" src="https://github.com/user-attachments/assets/2338cf56-dc1e-43d7-ad27-251748401f2c" />


Einblick in die Logs eines Containers zur Analyse von Systemverhalten und Fehlern.  
Logs sind essenziell für Debugging und Monitoring.

---

### Website

<img width="1810" height="985" alt="Bildschirmfoto vom 2026-03-30 23-59-08" src="https://github.com/user-attachments/assets/87ca21c8-bfe2-4d50-b4f6-0134834130d5" />


Die Hauptseite des Servers, ausgeliefert über einen Docker-Container.  
Zeigt die erfolgreiche Bereitstellung eines Webservers.

---

### App (über Reverse Proxy)

<img width="1810" height="985" alt="Bildschirmfoto vom 2026-03-30 23-59-25" src="https://github.com/user-attachments/assets/7fba6347-af19-4c99-9146-f4ba2f4051e0" />


Interner Service, erreichbar über den Reverse Proxy unter `/app`.  
Demonstriert Routing und Service-Trennung innerhalb der Architektur.

---

### Fail2Ban Schutz

<img width="918" height="251" alt="Bildschirmfoto vom 2026-03-31 00-02-11" src="https://github.com/user-attachments/assets/27d102ae-9100-4800-8d45-a276e6672b6c" />


Anzeige aktiver Sicherheitsmaßnahmen.  
Nach mehreren fehlgeschlagenen Login-Versuchen wird die angreifende IP automatisch blockiert.

---

### Angriffserkennung (SSH Logs)

<img width="1721" height="752" alt="Bildschirmfoto vom 2026-03-31 00-08-03" src="https://github.com/user-attachments/assets/c10480b3-2404-443a-9112-9375e53c1f9b" />


Darstellung mehrerer fehlgeschlagener Login-Versuche (Brute-Force-Angriff).  
Das System erkennt diese und reagiert mit automatischen Schutzmechanismen.

---

### Docker CLI Übersicht

<img width="1775" height="160" alt="Bildschirmfoto vom 2026-03-31 00-10-59" src="https://github.com/user-attachments/assets/869a184b-c900-461e-9317-a9add53917bf" />


Terminal-basierte Übersicht aller laufenden Container.  
Wird von Administratoren zur direkten Systemkontrolle genutzt.
