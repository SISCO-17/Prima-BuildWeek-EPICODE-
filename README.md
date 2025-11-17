# Prima-BuildWeek-EPICODE-
Progettazione di un'infrastruttura di rete sicura 'Defense in Depth' per un'azienda multilivello (Theta Co.). Include segmentazione VLAN, configurazione Firewall/IDS (pfSense, Suricata) e sviluppo di tool Python per il security testing.
# 🛡️ Secure Network Infrastructure Design - Theta Company (Build Week 1)

Questo repository ospita il progetto realizzato durante la prima Build Week del corso **Cybersecurity Specialist** di Epicode. Il progetto consisteva nella progettazione, messa in sicurezza e testing di un'infrastruttura di rete aziendale completa per la "Theta Company".

## 🎯 Obiettivo del Progetto
Progettare un'architettura di rete resiliente per un edificio di 6 piani (120 host), applicando il principio della **Defense in Depth**. L'obiettivo era garantire la segregazione dei dati sensibili, proteggere la proprietà intellettuale e assicurare la continuità operativa tramite un monitoraggio proattivo.

## 🏗️ Architettura e Topologia
La rete è stata progettata con una topologia a **Stella Estesa**, segmentata logicamente tramite VLAN per isolare i dipartimenti in base alla criticità dei dati:

* **Perimetro:** Firewall pfSense con configurazione "Deny All" di default.
* **DMZ (Demilitarized Zone):** Isolamento del Web Server pubblico (DVWA) con ispezione del traffico dedicata.
* **LAN Interna:** Segregazione dei dipartimenti critici:
    * *Amministrazione/Finanza* (Dati sensibili)
    * *R&D* (Proprietà Intellettuale)
    * *IT & Management*
* **Monitoraggio:** Implementazione di 3 nodi **IDS/IPS (Suricata)** per l'analisi del traffico est-ovest e nord-sud.

## 🛠 Tech Stack & Tools
* **Network Design:** Cisco Packet Tracer / VirtualBox Lab
* **Security Appliance:** pfSense (Firewall & Routing), Suricata (IDS/IPS)
* **Virtualization:** Kali Linux (Attacker), Metasploitable 2 (Target/Web Server)
* **Development:** Python 3 (Custom Security Tools)

## 💻 Tool Python Sviluppati (Custom Scripting)
Come parte del mandato, sono stati sviluppati internamente dei tool per la verifica della postura di sicurezza:

### 1. Port Scanner (`PortScanner.py`)
Scanner di rete TCP personalizzato per verificare l'efficacia delle regole di firewalling.
* *Funzione:* Scansiona range di porte su target specifici.
* *Risultato:* Ha permesso di individuare porte non standard aperte (es. 44444) sul target.

### 2. HTTP Verb Analyzer (`VerbiHTTP.py`)
Tool per l'analisi dei metodi HTTP supportati dal Web Server.
* *Funzione:* Invia richieste (OPTIONS, PUT, DELETE) per verificare configurazioni insicure.
* *Risultato:* Identificazione di metodi pericolosi abilitati su percorsi critici della DVWA.

### 3. Socket Listener (`Mysocket.py`)
Semplice server TCP implementato per testare la connettività e l'intercettazione di socket di rete grezzi.

## 📄 Documentazione
Nella repository sono inclusi i documenti ufficiali di progetto:
* `ReportFinale.pdf`: Dettagli tecnici, analisi dei rischi e configurazioni.
* `Preventivo.pdf`: Analisi dei costi hardware/software e manodopera.
* `Presentazione.pdf`: Overview esecutiva del progetto.

## 👥 Il Team
* [Tuo Nome]
* [Nome Collega 1]
* [Nome Collega 2]  
