---
layout: default
title: Input Gateway 
nav_order: 2
description: "Modul Input Gateway"
permalink: /docs/integracni-moduly/input-gateway/
has_children: true
parent: Integrační moduly
---

# Input Gateway

> Rozhraní pro pasivní příjem dat určené pro zpracování informace v reálném čase. Modul vstupní data validuje a následně předává do Message Brokeru k transformaci / uložení do databáze.

## Popis

Input Gateway je REST API - Node.js aplikace postavená na frameworku Express.js s připojením do Message Brokeru (RabbitMQ, AMQP 0-9-1). Využívá se pro integraci dat ze systémů, které umožňují posílat do Datové platformy data aktivně na stanovený endpoint (URL) - tzv. PUSH metoda. Tato metoda je vhodná pro data, kde chceme minimalizovat zpoždění přenosu informace - např. jde o aktuální polohy vozidel autobusů, obsazení konkrétního parkovacího místa, obousměrná komunikace s IoT zařízeními apod. Přijatá data na jednotlivých endpointech se zároveň validují vůči očekáváné struktuře (schématu) dat a následně vloží k dalšímu zpracování do Message Brokeru.

## Podporovaný formát vstupních dat

- JSON,
- XML, 
- CSV

## Funkce

- Validace dat oproti schématu pro každý definovaný endpoint
- Monitoring počtu entit/řádků v payloadu příchozích dat

## Výstup

- Data jsou zapsána ve zprávě do Message Brokeru (protokol AMQP v0-9-1)
- Monitoring se provádí do InfluxDB
