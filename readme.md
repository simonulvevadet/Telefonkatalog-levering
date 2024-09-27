# Brukerveiledning

## Installere OS på Raspberry Pi

### Guide: Installere et OS på Raspberry Pi

Denne guiden beskriver hvordan du installerer Raspberry Pi OS (tidligere kjent som Raspbian) på en Raspberry Pi.

---

### Steg 1: Hva du trenger

- Ha en Raspberry Pi

---

### Steg 2: Last ned Raspberry Pi OS

Gå til den offisielle nettsiden for å laste ned operativsystemet:  
[Raspberry Pi OS Nedlastinger](https://www.raspberrypi.org/software/operating-systems/)

Du har flere alternativer:

- **Raspberry Pi OS with desktop**: Full versjon med skrivebordsmiljø (anbefalt).
- **Raspberry Pi OS Lite**: For bruk uten skrivebordsmiljø (hodetelefon-modus).
- **Raspberry Pi OS with desktop and recommended software**: Inkluderer ekstra programvare for læring og programmering.

Velg den versjonen som passer deg best.

---

### Steg 3: Last ned Raspberry Pi Imager

For å installere operativsystemet på SD-kortet, må du bruke et verktøy som heter Raspberry Pi Imager:  
[Raspberry Pi Imager](https://www.raspberrypi.org/software/)

1. Gå til nettsiden og last ned verktøyet for ditt operativsystem (Windows, macOS, eller Linux).
2. Følg instruksjonene for å installere programvaren.

---

### Steg 4: Klargjør microSD-kortet

1. Sett microSD-kortet inn i datamaskinens SD-kortleser (bruk en adapter om nødvendig).
2. Åpne Raspberry Pi Imager.
3. Velg `Choose OS`, og velg deretter Raspberry Pi OS.
4. Velg `Choose SD Card`, og velg SD-kortet du vil installere operativsystemet på.
5. Klikk på `Write` for å starte skriveprosessen.

> **Merk:** Denne prosessen vil formatere SD-kortet og slette alle data som allerede er der.

---

### Steg 5: Start opp Raspberry Pi

Når prosessen er ferdig:

1. Fjern SD-kortet fra datamaskinen og sett det inn i Raspberry Pi.
2. Koble til tastatur, mus og skjerm til Raspberry Pi.
3. Koble til strømforsyningen. Raspberry Pi vil starte automatisk.

---

### Steg 6: Første gangs oppsett

Når Raspberry Pi starter for første gang:

1. Velg språk og tidssone.
2. Koble til Wi-Fi eller Ethernet for å gi Pi internettilgang.
3. Hvis det er tilgjengelige oppdateringer, vil Raspberry Pi OS be deg om å installere disse.
4. Velg et nytt passord for brukerkontoen `pi`.

---

### Steg 7: Valgfritt - Aktiver SSH og sett opp statisk IP

1. Gå til `Preferences` > `Raspberry Pi Configuration`.
2. Under `Interfaces`, slå på SSH for å få fjernstyring over nettverk.
3. Under `Network`, kan du konfigurere en statisk IP-adresse (dette kan også gjøres via router).

---

### Steg 8: Ferdig

Nå er Raspberry Pi ferdig installert med operativsystemet og klar til bruk. Du kan begynne å utforske mulighetene, fra programmering til å sette opp Raspberry Pi som en server.

---

## Installering av programmer

### Steg 1: Åpne terminal

På din Raspberry Pi, åpne terminal.

---

### Steg 2: Installer oppdateringer

Sørg for at all programvare er oppdatert:

```bash
sudo apt update  # Finner oppdateringer
sudo apt upgrade # Installerer oppdateringer
```

---

### Steg 3: Sett opp firewall

1. Installer UFW (Uncomplicated Firewall):

   ```bash
   sudo apt install ufw
   sudo ufw enable  # Starter firewall ved startup
   sudo ufw allow ssh  # Tillater SSH gjennom firewall
   ```

2. Sjekk statusen til firewallen:

   ```bash
   sudo ufw status
   ```

---

### Steg 4: Aktiver SSH

For å aktivere SSH:

```bash
sudo apt install openssh-server  # Installerer SSH-server
sudo systemctl enable ssh        # Skrur på SSH ved oppstart
```

---

### Steg 5: Finn IP-adresse

Skriv følgende kommando for å finne IP-adressen din:

```bash
ip a
```

- Hvis du har kablet nettverk, vises IP-adressen ved **eth0**-linjen.
- Hvis du bruker trådløst nettverk, vises IP-adressen ved **wlan0**-linjen.

> **Merk:** IP-adresser vil vanligvis være på formen `10.2.3.x` eller lignende, hvor `x` er et nummer mellom 2 og 254.

---

### Steg 6: Installer Git, Python og MariaDB

```bash
sudo apt install python3-pip git mariadb-server
sudo mysql_secure_installation  # Sikrer MariaDB
```

---

### Steg 7: Lag ny database-bruker og sett riktige rettigheter

1. Logg inn i MariaDB:

   ```bash
   sudo mariadb -u root
   ```

2. Lag en ny bruker:

   ```sql
   CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
   ```

3. Gi brukeren rettigheter:

   ```sql
   GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'password';
   ```

4. Oppdater rettigheter:

   ```sql
   FLUSH PRIVILEGES;
   ```

---

### Steg 8: Installer annen programvare

Installer annen programvare du trenger, for eksempel:

- **VS Code**: Last ned `.deb` for ARM64 fra [VS Code Linux Setup](https://code.visualstudio.com/docs/setup/linux).

Naviger til mappen der du lastet ned filen, og installer:

```bash
sudo apt install ./code*.deb
```

### Steg 9: Sjekk for oppdateringer

Sørg for at systemet er oppdatert:

```bash
sudo apt update
```
