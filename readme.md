# brukervegledning

installere os på rpi

# Guide: Installere et OS på Raspberry Pi

Denne guiden beskriver hvordan du installerer Raspberry Pi OS (tidligere kjent som Raspbian) på en Raspberry Pi.

## Steg 1: Hva du trenger
- Ha en razberry pi

## Steg 2: Last ned Raspberry Pi OS

Gå til den offisielle nettsiden for å laste ned operativsystemet:
[Raspberry Pi OS Nedlastinger](https://www.raspberrypi.org/software/operating-systems/)

Du har flere alternativer:
- **Raspberry Pi OS with desktop**: Full versjon med skrivebordsmiljø (anbefalt).
- **Raspberry Pi OS Lite**: For bruk uten skrivebordsmiljø (hodetelefon-modus).
- **Raspberry Pi OS with desktop and recommended software**: Inkluderer ekstra programvare for læring og programmering.

Velg den versjonen som passer deg best.

## Steg 3: Last ned Raspberry Pi Imager

For å installere operativsystemet på SD-kortet, må du bruke et verktøy som heter Raspberry Pi Imager:
[Raspberry Pi Imager](https://www.raspberrypi.org/software/)

1. Gå til nettsiden og last ned verktøyet for ditt operativsystem (Windows, macOS, eller Linux).
2. Følg instruksjonene for å installere programvaren.

## Steg 4: Klargjør microSD-kortet

1. Sett microSD-kortet inn i datamaskinens SD-kortleser (bruk en adapter om nødvendig).
2. Åpne Raspberry Pi Imager.
3. Velg `Choose OS`, og velg deretter Raspberry Pi OS.
4. Velg `Choose SD Card`, og velg SD-kortet du vil installere operativsystemet på.
5. Klikk på `Write` for å starte skriveprosessen.

> **Merk:** Denne prosessen vil formatere SD-kortet og slette alle data som allerede er der.

## Steg 5: Start opp Raspberry Pi

Når prosessen er ferdig:

1. Fjern SD-kortet fra datamaskinen og sett det inn i Raspberry Pi.
2. Koble til tastatur, mus og skjerm til Raspberry Pi.
3. Koble til strømforsyningen. Raspberry Pi vil starte automatisk.

## Steg 6: Første gangs oppsett

Når Raspberry Pi starter for første gang:

1. Velg språk og tidssone.
2. Koble til Wi-Fi eller Ethernet for å gi Pi internettilgang.
3. Hvis det er tilgjengelige oppdateringer, vil Raspberry Pi OS be deg om å installere disse.
4. Velg et nytt passord for brukerkontoen `pi`.

## Steg 7: Valgfritt - Aktiver SSH og sett opp statisk IP

1. Gå til `Preferences` > `Raspberry Pi Configuration`.
2. Under `Interfaces`, slå på SSH for å få fjernstyring over nettverk.
3. Under `Network`, kan du konfigurere en statisk IP-adresse (dette kan også gjøres via router).

## Steg 8: Ferdig

Nå er Raspberry Pi ferdig installert med operativsystemet og klar til bruk. Du kan begynne å utforske mulighetene, fra programmering til å sette opp Raspberry Pi som en server.





installering av programmer etc
1. Åpne terminal på din rasberry pi

2. finn og installer oppdateringer til allprogramvare som er installert

        a. sudo apt update (finner oppdatering)

        b. sudo apt upgrame (installerer oppdateringen)

3. sett opp firewall

        a. sudo apt install ufw (installerer UFW)

        b. sudo ufw enable (starter firewall ved startup)

        c. sudo ufw allow ssh (slipper ssh gjennom firewall)

        d. sjekk firewall status ved å skrive sudo ufw status

4. 
- aktiver ssh

        a. sudo apt install openssh-server (installerer ssh server)

        b. sudo systemctl enable ssh (skrur på ssh ved startup)

5. 
- finn ip

        a. skriv ip-a i terminalen

b:

- Hvis du har kablet nettverk, vil IP vises ved eth0: linje.

 - Hvis du kun har trådløst, vil ipvises ved wlan0: linje.
 
 - IP-adresse er vanligvis 10.2.3.x eller noe lignende (hvor x er etnummer mellom 2 og 254)

 6. installer git, python og mariadb

         a. sudo install python3-pip

         b. sudo apt install git

        c. sudo apt install mariadb-server

        d. sudo mysql_secure_installation

 7.
 - lag ny database-bruker og sett riktige rettigheter

        a. Logg inn i mariadb med koden: sudo mariadb-u root

        b. lag ny bruker med koden: CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';

        c. gi bruker rettigheter med koden: GRANT ALL PRIVILEGES ON *.* TO 'username'@’localhost’IDENTIFIED BY 'password';

        d: oppdater rettigheter med koden: flush privileges;

 8. 
 - Installer annen programvare du ønsker. For eksempel VS Code, en annen nettleser,wireshark, nmap, etc
 
 a. 
 - Hvis du får trøbbel med VS Code, last ned .deb for arm64 fra https://code.visualstudio.com/docs/setup/linux Naviger til mappen du lastetned filen
  
        b.  Skriv sudo apt install ./code og trykk tab, så enter 

         9. skriv koden: sudo apt update  

