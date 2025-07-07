# SCHEMA

Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi [Dipartimenti] (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più [ Corsi di Laurea ] (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi [Corsi] (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi [Insegnanti];
- ogni Corso prevede più appelli d'[Esame];
- ogni [Studente] è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il [voto] ottenuto, anche se non sufficiente. Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.

## Tables

### dipartimenti
- id PK
- nome
- descrizione
- presidente
- posizione

### corsi_laurea
- id PK
- id_dipartimento FK
- nome
- descrizione
- dfu_totali

### corsi
- id PK
- id_corso_laurea FK
- nome
- descrizione
- cfu

### studenti
- id PK
- nome
- cognome
- id_corso_laurea FK
- codice_fiscale
- indirizzo
- telefono

### esami
- id PK
- id_corso FK
- sessione
- data_appello

### [pivot] esami_studenti
- id_esame
- id_studente

### insegnanti
- id PK
- nome
- cognome
- titolo
- ruolo

### [pivot] corsi_insegnanti
- id_corso
- id_insegnante


