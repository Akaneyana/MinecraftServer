# Installasjon Av Minecraft Server med Hjelp av Ubuntu

I denne brukerveiledningen skal du lære hvordan man setter opp en Minecraft-server ved hjelp av en Ubuntu-enhet. 
Denne veiledningen gjelder for **Minecraft Java Edition** og beskriver hvordan man lager en server i Java-versjonen av Minecraft.

---

## Før du starter

Det kan være lurt å oppdatere Ubuntu-systemet ditt før du begynner. Bruk følgende kommandoer for å oppdatere systemet

**Oppdater systemet:**
```bash
sudo apt update && sudo apt upgrade
```

**Finn IP-adressen til systemet:**
```bash
ipa
```

## Installasjon av Java og Oppsett av Filstruktur

Java er hovedkomponenten i en Minecraft-server. Installer Java og organiser serverfilene dine som beskrevet nedenfor.

Installer Java Kjør denne kommandoen for å installere Java:
```bash
sudo apt-get install openjdk-21-jdk
```

### Guide for å lagre din server

Finn et fornuftig sted å lagre serveren din

Bruk følgende kommandoer for å navigere og organisere filene dine
- **Se alle filer i en mappe:**  
```bash
dir
```
Dette viser alle filer og mapper i gjeldende katalog.

- **Gå inn i en spesifikk mappe:**  
```bash
cd «mappenavn»
```
Bytter til mappen med navnet «mappenavn».


- **Opprett en ny mappe:**  
```bash
mkdir «mappenavn»
```
Lager en ny mappe med navnet «mappenavn».


## Oppsett av Minecraft Server

I dette eksempelet skal vi laste ned versjon **1.21.3** av Minecraft. 
Hvis du skal laste ned eldre eller nyere versjoner av Minecraft, må du justere koden i noen tilfeller.

### Last ned Minecraft 1.21.3-versjonen
Bruk følgende kommando for å laste ned serverfilen:
```bash
wget https://piston-data.mojang.com/v1/objects/45810d238246d90e811d896f87b14695b7fb6839/server.jar
```

Start Minecraft Servern med:
```bash
java -Xmx1024M -Xms1024M -jar server.jar nogui
```

## eula.txt

Når du startet serveren, fikk du sannsynligvis en feilmelding som lignet på:  
*"Gi tilgang til eula.txt for å kjøre serveren."*

Grunnen til at vi starter serveren før vi endrer noe i `eula.txt`, 
er at dette oppretter alle filene vi trenger for å hoste serveren.

### Åpne `eula.txt`
Bruk følgende kommando for å åpne filen:
```bash
nano eula.txt
```
<br>

**Endre `eula=false` til `eula=true`:**

Bytt ut linjen som sier:
```plaintext
eula=false
```
med:
```plaintext
eula=true
```

## Start serveren på nytt

Etter at du har endret `eula.txt`, start serveren på nytt ved å bruke følgende kommando:
```bash
java -Xmx1024M -Xms1024M -jar server.jar nogui
```
Når serveren er startet, kan du skrive kommandoen **`help`** for å få en liste over tilgjengelige Minecraft-kommandoer


## Koble til serveren

For å koble til Minecraft-serveren din, følg disse trinnene:

1. **Sørg for at du har Minecraft Java installert** på systemet ditt.

2. **Åpne Minecraft og gå til "Multiplayer"**:
   - Klikk på **"Multiplayer"**-knappen i Minecraft-menyen.

3. **Legg til serveren**:
   - Klikk på **"Add Server"**-knappen.

4. **Fyll ut serverinformasjonen**:
   - **Server Name:** Du kan velge et valgfritt navn for serveren.
   - **Server Address:** Skriv inn IP-adressen til Ubuntu-systemet ditt (den du fant tidligere).

5. **Koble til serveren**:
   Når du har fylt ut informasjonen, kan du nå koble til serveren ved å klikke på **"Join Server"**.
