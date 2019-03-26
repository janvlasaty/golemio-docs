---
layout: default
title: Úvod
nav_order: 1
description: "Dokumentace Datové platformy."
permalink: /
---

# Golemio - dokumentace Datové platformy

## Účel platformy

**Datová platforma je soubor SW nástrojů pro integraci, ukládání a vizualizaci dat z městského prostředí, zejména pak v oblasti Smart City dat.**

<img src="/golemio-docs/assets/images/schemas/DP_schema_simple.png" alt="Schéma architektury" style="margin-botom: 1rem;"/>

### Co umí platforma zpracovat?

* Metrická data (meteosenzory, detektory průjezdů aut / cyklistů)
* Polohová data (polohy vozidel, kolony / nehody)
* Mapové podklady (hranice území, vyznačené oblasti, trasy linek)
* Číselníky a katalogy

### Možnosti výstupů

* Mapové vizualizace, včetně analytických nástrojů
* Realtime i pravidelné reporty, včetně interaktivních aplikací
* Alerting měřených hodnot

### Popis funkcí

Datová platforma zajišťuje **integraci dat**...

Znamená to možnost volat API rozhraní externích systémů (zpravidla dodavatelů technologických řešení měření ovzduší, detektorů průjezdů apod.) skrze standardní rozhraní (REST API, SOAP, RSS, WebSocket, FTP soubory aj.) s různým typem zabezpečení (API klíč, OAuth, JWT aj.). Extrakci dat z externích systémů zajišťuje modul #Integration Engine.
Data lze získávat také ze systémů, které aktivně posílají data na definovaný endpoint na straně platformy (REST API, WebSocket aj.) opět s různým typem zabezpečení spojení. Pasivní příjem dat zajišťují moduly #Permission Proxy a #Input Gateway.
Pro data, která vznikají či se aktualizují nepravidelně (číselníky, mapové podklady) platforma umožňuje i ruční vstup.

Datová platforma zajišťuje **ukládání dat**...

Pro data využíváme dvou databází - PostgreSQL a MongoDB a volíme vhodnější typ vždy specificky pro strukturu integrovaných dat (ve smyslu relační / dokumentové data). Více v #Databázový modul.
Než se příchozí data uloží však často dochází k transformacím, obohacování dat, popř. vytvoření dalších derivátů dat. Specifické worflow je možné impementovat v modulech #Integration Engine a #Message Broker.
Na ukládání dat navazuje i přístup k archivaci a retenci datových záznamů, které je řízen časově skrze #Cron Module a rozšiřuje v podstatě workflow o další procesy.

Datová platforma zajišťuje **vizualizaci dat**...

Vizualizací rozumíme nejen zobrazování dat v grafech. K výstupům přistupujeme z mnoha hledisek. Prvním je samozřejmě služba městu a městským částem k lepšímu rozhodování a plánování. Proto je v platformě pro každý typ dat zvolen vhodný nástroj dle samotné povahy dat, ale i z hlediska potřeb klienta - míra interaktivity výstupu, dostupnost analytický nástrojů, tvorba pohledů, exportu dat apod.

Senzorická data zpravidla zobrazujeme pomocí nástroje Grafana a PowerBI. Mapové podklady pak pomocí ArcGIS, popř. webových aplikací na míru (React+Redux, Mapbox, Deck.gl). Pro ad-hoc analýzu a vytvoření modelů pak volíme specialozované nástroje (RStudio aj.)

Do této části patří i klientské aplikace vyvinuté pro práci s platformou. První je klientský panel, který pro klienty slouží jako rozcestník mezi jednotlivými výstupy z datových sad - modul #Client Panel. Druhou aplikací je pak správa API klíčů pro přístup k datům pro vývojáře a externí systémy - #Client API Management.

## Moduly platformy

Jednotlivé moduly platformy zajišťují vždy jednu z funkcí a jsou navrženy tak, aby bylo možné je nahradit jinými komponentami, popř. SaaS.

### Schéma modulů

<img src="/golemio-docs/assets/images/schemas/DP_schema_general.png" alt="Schéma architektury" style="margin-botom: 1rem;"/>

#### Integrační moduly platformy

* Permission Proxy
* Input Gateway
* Output Gateway
* Message Broker
* Integration Engine

#### Databázové moduly platformy

* MongoDB
* PostgreSQL
* Archivace a retence
* Pomocné databáze, logování, monitoring

#### Vizualizační moduly platformy

* Grafana
* PowerBI
* ArcGIS
* Mapové aplikace

#### Klientské aplikace platformy

* Client Panel
* Client API Management

## Tvůrce Datové platformy

<img src="/golemio-docs/assets/images/logos/OICT_logo_grey.svg" alt="Logo OICT" style="margin-botom: 1rem; min-width:200px; width: 30%;"/>
