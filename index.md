---
layout: default
title: Úvod
nav_order: 1
description: "Dokumentace Datové platformy."
permalink: /
---

# Obecná dokumentace Datové platformy

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

## Komu platforma slouží?

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

## Moduly platformy

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
