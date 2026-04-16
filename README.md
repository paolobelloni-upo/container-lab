# container-lab

Questo laboratorio sara' svolto esclusivamente su Google Cloud Shell.
Non è necessario installare nulla sul PC!

Strumenti utilizzati:
- git
- Docker
 
## Accesso all’ambiente di laboratorio

### 1. Google Cloud Shell
Accedere da browser a:
https://shell.cloud.google.com

Dopo il login con account Google, si apre automaticamente:
- una shell Linux
- con git e docker già installati

Non è necessario installare nulla sul proprio PC.

### 2. Entrare nell’ambiente Docker

Docker è già disponibile nella shell.

Verifiche iniziali:

~$ docker --version  
~$ git --version

## Obiettivi
- Capire i comandi base di Docker
- Creare e avviare container manualmente
- Comprendere networking Docker di base

## Esercizio 1

~$ docker run hello-world  

## Preparazione Esercizio 2 ed Esercizio 3

Clonare il repository GitHub corrente su Cloud shell. Attraverso questa operazione saranno scaricate 2 cartelle contenenti i file degli Esercizi 1 e 2.

~$ git clone https://github.com/paolobelloni-upo/container-lab.git

## Esercizio 2

~$ cd container-lab/LISTA

Il programma python (list.py) in questa cartella fa la lista dei file e delle cartelle presenti nella directory corrente.

### Creare immagine

~$ docker build -t imamgine-lista .

NOTA: il punto alla fine della riga fa parte del comando!

#### SPIEGAZIONE
docker build: avvia la costruzione di una immagine Docker

-t immagine-lista: assegna un nome (tag) all’immagine costruita

. : indica il contesto di build, cioè la directory corrente (Docker cerca qui il Dockerfile)

Al termine, l’immagine è salvata localmente.
Verificare la presenza dell’immagine con il comando:

~$ docker images
#################################################################################
### Avvio del container

~$ docker run -it stampa-lista

#### SPIEGAZIONE
docker run: crea e avvia un container

-i: 
mantiene aperto lo standard input

-t: alloca un terminale (TTY)

stampa-lista: nome dell’immagine da usare

Il container viene eseguito in primo piano

Per uscire dal container: exit

Al termine, verificare la lista dei container in esecuzione con il comando:

~$ docker ps
oppure
~$ docker ps -a 
per vedere i container sia in esecuzione che terminati.
