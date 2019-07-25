---
layout: default
title: Technické zadání
nav_order: 1
description: "Funkční požadavky vývoje Datové platformy."
permalink: /docs/popis-reseni/technicke-zadani
parent: Popis řešení
---

# Technické zadání

## Funkční požadavky

### Integrace dat z externích systémů měst a městských společností

1. Systém bude zpracovávat real time data
    1. Vystavené push API
1. Systém bude umět oboustranně komunikovat s připojenými zařízeními
    1. Volání externího ovládacího API
    1. Napojení přes websocket (v prototypu nebude)
1. Systém bude zpracovávat statická data a data z API / DB
    1. Pull API
        1. JSON REST API
        1. Proprietární HTTP/S API
    1. Externí FTP úložiště
        1. Stahování dat v intervalu 1 min až 1 rok
    1. Nastavitelné konfigurací (definice CRON)
1. Systém bude zpracovávat ruční vstupy (mapové podklady, číselníky) - přímým nahráním do databáze
    1. Formát GeoJSON, JSON, CSV
1. Systém bude umožňovat automatické nahrávání do katalogu OD
    1. Týdenní, denní frekvence
1. Nad přijatými daty budou prováděny výpočty
    1. Geoprocessing, výpočet zpoždění, predikce, obohacení dat

### Úložiště dat 

1. V systému budou použity SQL a NoSQL databáze, účelem je otestovat možné varianty
1. Systém bude ukládat aktuální data (aktuální poloha, aktuální obsazenost)
1. Systém bude ukládat historická data (historie obsazenosti, historie polohy, historie stavu)

### Datová analýza 

1. Možnosti připojení nástrojů pro datovou analýzu (Grafana, PowerBI, R studio, ArcGIS Desktop, popř. jiné standardní nástroje)
1. Systém bude uchovávat přijatá raw data po různou dobu dle potřeb projektu

### Webové aplikace 

1. Webová aplikace interních dashboardů, dispečinku (operativního monitoringu) a administračního panelu DP, popř. využití webu Golemio pro veřejné dashboardy
    1. Zobrazení dashboardů pro veřejnost
    1. Zobrazení interních dashboardů
    1. Možnost ovládání připojených zařízení přes aplikaci dispečinku
1. Přístup skrze přihlašovací údaje k webové aplikaci určené k zobrazování specifických dashboardů
    1. Přihlašování a rozdělení přístupů k jednotlivým dashboardům dle rolí
    1. Rozdělení přístupů k jednotlivým datům na dashboardech (např. Dashboard lampy, některý uživatel vidí pouze lampy s parametrem “městská část: Praha 7”, některý uživatel všechny)
        1. Přístup na základě městské části
        1. Přístup na základě povolených ID jednotlivých záznamů
1. Aktualizace dat (nejmenší možná doba aktualizace) 
    1. Pro veřejné dashboardy od 30 min
    1. Interní dashboard od 1 min
    1. Dispečerský panel od 10s
1. Administrační API pro správu uživatelů a práv
    1. Správa uživatelů, uživatelský skupin, API přístupů

### Open API 

1. Implementace výstupní gateway pro zpřístupnění dat z DP pro třetí strany (mobilní vývojáři, externí systémy)
    1. Jednotné REST API
    1. Dokumentace výstupního API
1. Nastavení request limitů, role a oprávnění přístupu, logování přístupů
    1. Administrační panel s přehledem přístupů/využití
    1. Nastavitelné přístupy k jednotlivým API endpointům
    1. Logování všech přístupů a generování statistik
    1. Blokace dříve poskytnutého přístupu
    1. Bude možné určovat celkový rate limit pro uživatele
    1. Nastavení oprávnění přístupů bude možné jak za základě datové sady (endpoint) tak i podle atributů v datech
    1. Přístup k jednotlivým API endpointům
    1. Přístup na základě městské části
    1. Přístup na základě povolených ID jednotlivých záznamů
    1. Přístup s maximálním limitem (velikosti) dotazu
1. Automatické generování API klíčů
    1. Uživatelé musí mít možnost si sami vygenerovat svůj klíč, který bude mít výchozí hodnotu rate limitu
    1. Ověří se emailem - posílání verifikačního emailu pro aktivaci klíče

### Alerting

1. Kontrola dat
    1. V daném časovém úseku musí přijít dávka dat, jinak se odešle upozornění
    1. Periodické provolání externích zdrojů a validace schématu
    1. Ověřování hodnot vůči stanoveným pravidlům

## Nefunkční požadavky

1. Dispečink a dashboardy budou dostupné jako webová aplikace s řízením přístupů
1. Administrační panel bude dostupný jako webová aplikace s řízením přístupů
1. Jednotlivé moduly řešení budou horizontálně škálovatelné - vrstva pro integraci dat, vrstva pro výstupní rozhraní, databázová vrstva, napojení na senzory
1. Moduly umožní navýšení výkonu a počtu zpracovávaných požadavků/kapacity úložiště pomocí horizontálního škálování bez zásahu do zdrojových kódů řešení
1. Jednotlivé moduly/vrstvy budou jednotlivě nahraditelné - integrace dat, výstupní rozhraní, databázová vrstva, napojení na senzory (vstupní rozhraní)
1. Řešení bude využívat systému queue (fronty) pro zajištění perzistence a synchronizace přijímaných dat/zpráv
1. Celé řešení bude možné nasadit na virtualizované architektuře VMWare
1. Jednotlivé moduly budou k nasazení využívat technologii linuxových kontejnerů (Docker)
1. Zdrojový kód jednotlivých částí řešení bude udržován v git repozitáři, nebude obsahovat citlivá data a bude připraven k publikaci jako open-source
1. Zdrojové kódy budou pokryty jednotkovými testy, které se budou automaticky spouštět před nasazením nové verze
1. Modul výstupního rozhraní a integračního rozhraní s databázovou vrstvou bude možno plnohodnotně zprovoznit samostatně bez závislosti na ostatních modulech
1. Celé řešení bude monitorovatelné standardními monitoring nástroji
1. Předpokládaný objem dat je 1 TB za dobu 3 měsíců, řešení bude dimenzováno minimálně na tento objem
1. Systém bude dimenzován na vstup 200 datových zpráv za 1s
1. Řešení bude robustní k výpadku jakéhokoliv jednoho modulu (vrstvy) aplikace po omezený čas
1. Celé řešení bude nasazené v režimu vysoké dostupnosti, odolné vůči výpadku jakéhokoliv z virtuálních strojů (pro prototyp není vyžadováno):
1. Systém bude provádět automatické zálohy dat z datového úložiště a ostatních modulů 
1. Dostupnost služeb bude:
    * Výstupní API: 99,5
    * Databázová vrstva: 99,5
    * Dispečink: 99,5
    * Monitoring: 99,5
    * Alerting: 99,5
1. Součástí řešení je i návrh řešení Disaster recovery a kritických scénářů
1. Součástí prototypu je návrh automatického zálohování, export dat pro migraci dat
