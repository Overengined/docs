---
title: Come utilizzare MySQL e MariaDB
slug: come-utilizzare-mysql-e-mariadb
excerpt: Guida all'utilizzo dei tuoi database
section: Per iniziare
order: 02
---

Vuoi utilizzare MySQL o MariaDB? Scopri come creare e gestire i tuoi database con la massima semplicità!


## Introduzione

### Prerequisiti

- Un'istanza CloudDB attiva
- Aver consultato [la guida all’utilizzo di CloudDB](../iniziare-a-utilizzare-clouddb/)

### Cose un database MySQL?
MySQL è un modello di database relazionale sviluppato per ottimizzare le prestazioni in lettura.

Questo motore è open source e la sua casa madre è Oracle.


### Cose un database MariaDB?
MariaDB è un derivato (fork) del modello di database MySQL.

Questo motore è compatibile al 100% ed è stato progettato per essere più "libero" del suo fratello maggiore MySQL. Contrariamente alla versione di Oracle, tutti i bug e la roadmap sono pubblicamente accessibili. Inoltre, utilizza XtraDB in sostituzione del motore di storage InnoDB e ha introdotto ulteriori ottimizzazioni per garantire un aumento delle performance.


## Connettiti al database


> [!primary]
>
> Ricordiamo che questa offerta non dà accesso all’host ma ai database ospitati su di esso. È possibile utilizzare tutti i comandi SQL generici e i software come HeidiSQL o SQuirreL SQL sono totalmente compatibili.
> 



> [!primary]
>
> MariaDB è un derivato di MySQL, è quindi possibile utilizzare gli stessi comandi per entrambi i database.
> 

Per accedere al tuo database, sono necessarie queste informazioni:

- indirizzo della tua istanza
- porta
- nome utente
- password
- nome del database

Questi dati sono disponibili nella sezione Web del tuo [Spazio Cliente OVH](https://www.ovh.com/manager/web/){.external}.

Se necessario, consulta la guida: [Inziare a utilizzare CloudDB](../starting_with_clouddb/guide.it-it.md){.ref}


### Connessione da riga di comando

```bash
mysql --host=server --user=utente --port=porta --password=password nome_database
```


### Connessione con script PHP

```php
1. <?php
2. $db = new PDO('mysql:host=host;port=porta;dbname= nome_database', 'utente', 'password');
3. ?>
```


### Connessione da software (SQuirreL SQL)
- Avvia SQuirreL SQL, clicca su `Aliases`{.action} e poi su `+`{.action}


![launch SQuirreL SQL](images/1.PNG){.thumbnail}

- Completa i campi qui sotto e clicca su `OK`{.action} per confermare:
    - **Name**: scegli un nome
    - **Driver**: scegli "MySQL Driver"
    - **URL**: inserisci l’indirizzo del server e la porta in formato jdbc:mysql://server:porta
    - **User Name**: inserisci il nome utente
    - **Password**: inserisci la password


![config connection](images/2.PNG){.thumbnail}

- Clicca su `Connect`{.action} per confermare


![valid connection](images/3.PNG){.thumbnail}

A questo punto, sei connesso al tuo database:


![config connection](images/4.PNG){.thumbnail}


### Connessione con phpMyAdmin
*Presto disponibile in un’altra guida.*


## Esporta un database MySQL o MariaDB

### Esportare il tuo database da riga di comando

```bash
mysqldump --host=server --user=utente --port=porta --password=password nome_database > nome_database.sql
```


## Importa un database MySQL o MariaDB

### Importare il tuo database da riga di comando

```bash
cat nome_database.sql | mysql --host=server --user=utente --port=porta --password=password nome_database
```
