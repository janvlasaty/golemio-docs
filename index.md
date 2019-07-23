---
layout: default
title: Úvod
nav_order: 1
description: "Dokumentace Datové platformy."
permalink: /
---

# Golemio - dokumentace Datové platformy

> Datová platforma je soubor SW nástrojů pro integraci, ukládání a vizualizaci dat z městského prostředí, zejména pak v oblasti Smart City dat.

## Základní funkční schéma

<img src="/golemio-docs/assets/images/schemas/GolemioAim.svg" alt="Základní funkční schéma" class="img-highlighted"/>

## Co umí platforma zpracovat?

* Dopravní data:
    * polohy vozů MHD, realtime výpočet zpoždění
    * jízdní řády,
    * detektory průjezdů aut,
    * data o aktuální dopravní situaci (kongesce, nehody, výluky)
    * realtime parkovací situace (P+R, on-street v zonách placeného stání, komerční parkoviště, stání pro ZTP řidiče)
* Ovzduší
    * meteostanice na území Prahy
    * Smart City prvky se senzory městského prostředí
    * 
* Pohyb
    * sčítače průchodů chodců
    * cyklosčítače (detektory průjezdů, mobilní cyklonavigace)
* BI analýzy
    * analýza dopadu Airbnb, popř. jiných platforem
    * zpracování mapových podkladů (zóny placeného stání, katalogy služeb)
    * potenciál zelených střech v Praze
    * analýza chování uživatelů karty Lítačka
* IoT zařízení (skrze API dodavatele)
    * senzory zaplněnosti odpadových nádob
    * chytré osvětlení
    * kvalita prostředí v budovách
    * energetický monitoring budov
    * E-Health projekt

## Výstupy dat

* Klient - **Magistrát a městské části**
    * Analytické webové aplikace na míru
    * Tvorba veřejných výstupů dat
    * BI reporting, interaktivní analýzy a podklady pro rozhodování
    * Monitoring a alerting na základě realtime dat
* Klient - **Městské společnosti**
    * BI reporting, tvorba analýz a podkladů
    * Realizace integrační mezivrtstvy mezi různými IT systémy
* Klient - **Veřejnost**
    * Veřejné webové aplikace
    * Opendata
    * Public API pro integraci do aplikací třetích stran

## Popis funkcí

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

Jednotlivé moduly platformy zajišťují vždy jednu z funkcí a jsou navrženy tak, aby bylo možné je nahradit jinými komponentami.

### Schéma modulů

<img src="/golemio-docs/assets/images/schemas/DP_schema_general.svg" alt="Schéma architektury" class="img-highlighted"/>

#### Integrační moduly platformy

* Input Gateway
* Output Gateway
* Schema Definitions
* Integration Engine
* Message Broker
* Permission Proxy

#### Databázové moduly platformy

* MongoDB
* PostgreSQL
* Archivace a retence
* Pomocné databáze, logování, monitoring

#### Vizualizační moduly platformy

* Grafana
* PowerBI Online
* ArcGIS Online

#### Klientské aplikace platformy

* Client Panel
* Client API Management
* Admin Permission Proxy Management

## Tvůrce Datové platformy

<img src="/golemio-docs/assets/images/logos/OICT_logo_grey.png" alt="Logo OICT" style="margin-botom: 1rem; min-width:200px; width: 30%;"/>
