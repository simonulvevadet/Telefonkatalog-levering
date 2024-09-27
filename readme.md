# brukervegledning
1. Åpne terminal på din rasberry pi

2. finn og installer oppdateringer til allprogramvare som er installert

        a. sudo apt update (finner oppdatering)

        b. sudo apt upgrame (installerer oppdateringen)

3. sett opp firewall

        a. sudo apt install ufw (installerer UFW)

        b. sudo ufw enable (starter firewall ved startup)

        c. sudo ufw allow ssh (slipper ssh gjennom firewall)

        d. sjekk firewall status ved å skrive sudo ufw status

4. aktiver ssh

        a. sudo apt install openssh-server (installerer ssh server)

        b. sudo systemctl enable ssh (skrur på ssh ved startup)

5. finn ip

        a. skriv ip-a i terminalen

b. Hvis du har kablet nettverk, vil IP vises ved eth0: linje.

 Hvis du kun har trådløst, vil ipvises ved wlan0: linje.
 
 IP-adresse er vanligvis 10.2.3.x eller noe lignende (hvor x er etnummer mellom 2 og 254)

 6. installer git, python og mariadb

         a. sudo install python3-pip

         b. sudo apt install git

        c. sudo apt install mariadb-server

        d. sudo mysql_secure_installation

 7. lag ny database-bruker og sett riktige rettigheter

        a. Logg inn i mariadb med koden: sudo mariadb-u root

        b. lag ny bruker med koden: CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';

        c. gi bruker rettigheter med koden: GRANT ALL PRIVILEGES ON *.* TO 'username'@’localhost’IDENTIFIED BY 'password';

        d: oppdater rettigheter med koden: flush privileges;

 8. Installer annen programvare du ønsker. For eksempel VS Code, en annen nettleser,wireshark, nmap, etc
 
 a.  Hvis du får trøbbel med VS Code, last ned .deb for arm64 frahttps://code.visualstudio.com/docs/setup/linux Naviger til mappen du lastetned filen
  
        b.  Skriv sudo apt install ./code og trykk tab, så enter 

         9. skriv koden: sudo apt update  

