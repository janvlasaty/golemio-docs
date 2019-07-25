---
layout: default
title: Architektura systému
nav_order: 2
description: "Architektura systému Datové platformy."
permalink: /docs/popis-reseni/architektura-systému
parent: Popis řešení
---

# Architektura systému

Datová platforma je realizována jako modulární systém obsahující jednotlivě funkční, jednotlivě nasaditelné a nahraditelné moduly. Jednotlivé moduly a vrstvy jsou navrženy s myšlenkou nahraditelnosti za jiné řešení, či již existující službu (např. poskytovanou jako SaaS) a s myšlenkou maximální flexibility a škálovatelnosti. 

Z důvodu nejasného rozvoje do budoucna (co se týče datových objemů, počtů poskytovatelů dat a jednotlivých use casů) je kladen velký důraz na škálovatelnost - např. vrstva pro příjem dat je navržena jako minimální (lightweight) bezstavová aplikace, kterou je možné v kombinaci s load balancerem nasadit v několika instancích pro rychlý příjem dat a zajištění zařazení požadavků do fronty pro postupné zpracování. Fronta je také integrální součástí systému a realizuje příjem, persistenci dat, distribuci a synchronizaci mezi jednotlivými výpočetními uzly. Systém je tak schopen reagovat i na velké špičky v datových tocích.

Maximum modulů je řešeno jako bezstavové aplikace, kde držitelem stavu je společný databázový cluster. Výpočetní uzly (jednotlivé instance realizující zpracování dat, transformace a výpočty dat) jsou také libovolně škálovatelné a navýšením počtu jejich instancí se urychlí proces zpracování a vyzvedávání dat z fronty.

Architektura systému kloubí výhody microservice-oriented architektury (flexibilita, samostatné škálování, nahraditelnost, rychlost roll outů nových aktualizací) s tradičním návrhem. To samozřejmě přináší nejen výhody, ale i několik úskalí, na které musel být brán při návrhu a realizaci (zejména z pohledu provozu a povyšování verzí se zpětně nekompatibilními úpravami), jelikož se nejedná čistě o úplně nezávislé microservices; popsáno níže. 

Celý systém je provozován na virtualizované infrastruktuře, jednotlivé aplikace v kontejnerizovaném prostředí (Docker). Nad kontejnery je vystavena orchestrační vrstva, která se stará o load balancing, clusterování, nasazování nových verzí (tzv. rolling update u jednotlivých služeb, kdy se nejprve spustí druhá instance v nové verzi, přesměruje se traffic a až následně se stará verze vypne, proto je dosažen zero-downtime deployment) apod. 

## Aplikace je rozdělena do jednotlivých samostatných modulů:

* Vstupní rozhraní (input gateway),
* Přístupová vrstva (ACL, permission proxy),
* Fronta (queue),
* Integrační vrstva (integration engine),
* Databázová vrstva,
* Výstupní rozhraní (output gateway),
* Administrační panel (admin panel),
* Dispečink a datová analýza (client panel),
* Správa časově řízených úkonů (CRON).

## Rámcové schéma architektury:

Následující schéma popisuje jednotlivé moduly řešení vč. způsobu napojení mezi nimi (druh připojení, rozhraní) a naznačení komunikace a závislostí. Každý modul obsahuje svůj název a název projektu projektu (repozitáře).

<img src="/golemio-docs/assets/images/schemas/Architecture_schema.svg" alt="Technologické Schéma architektury" class="img-highlighted"/>

# Technologické schéma

<img src="/golemio-docs/assets/images/schemas/Technology_schema.svg" alt="Technologické Schéma architektury" class="img-highlighted"/>

# Infrastrukturní schéma

<img src="/golemio-docs/assets/images/schemas/Infrastructure_schema.svg" alt="Technologické Schéma architektury" class="img-highlighted"/>