---
layout: default
title: Integrační moduly 
nav_order: 10
description: "Integrační moduly Datové platformy."
has_children: true
permalink: /docs/integracni-moduly/
---

# Integrační moduly

Skupina modulů pro zpracování dat.

<img src="/golemio-docs/assets/images/logos/DP_icon_permission_proxy.svg" alt="Schéma architektury" style="height: 60px; 
margin-top: 1rem;
margin-bottom: -1rem;"/>

## Permission proxy

Permission proxy je REST API, které volání klienta na definované endpointy (URL) přesměrovává na cílové adresy (TARGET URL a ENDPOINT) aplikačních serverů. Slouží pro příjem a výdej dat. Zároveň umožňuje na úrovni uživatele, role a specifického přístupu k dané cílové adrese (scope) limitovat dané volání na základě parametrů dotazu (např. dle počtu záznamů, id datové entity, městské části, IP adresy klienta apod.)

[Dokumentace modulu na permission-proxy.github.io](#)

<img src="/golemio-docs/assets/images/logos/DP_icon_input_gateway.svg" alt="Schéma architektury" style="height: 60px; 
margin-top: 1rem;
margin-bottom: -1rem;"/>

## Input Gateway

Input Gateway je REST API, které je určeno pro pasivní příjem dat. Jde o případ integrace dat ze systémů, které umožňují posílat do Datové platformy data aktivně na stanovený endpoint (URL) - tzv. PUSH metoda. Jde o princip, který je vhodný pro data, kde chceme minimalizovat zpoždění přenosu informace - např. jde o aktuální polohy vozidel autobusů, obsazení parkovacího místa ZTP apod.
Přijatá data na jednotlivých endpointech se zároveň validují vůči očekávánému formátu (schématu) dat a následně vloží k dalšímu zpracování do Message Brokeru.

[Dokumentace modulu na input-gateway.github.io](#)

<img src="/golemio-docs/assets/images/logos/DP_icon_message_broker.svg" alt="Schéma architektury" style="height: 60px; 
margin-top: 1rem;
margin-bottom: -1rem;"/>

## Message Broker

Message Broker je modul pro předávání zpráv ve frontovém systému. Datová platforma příchozí data nejen ukládá, ale může je i transformovat do jiné struktury, obohocovat o další atributy, případně data propojovat atp. Pro různé datové sady jde o různě komplexní workflow a právě Message Broker pomocí specifických front (Queues) je vhodným nástrojem pro systém managementu úloh v každém workflow zpracování dat.

[Dokumentace modulu na message-broker.github.io](#)

<img src="/golemio-docs/assets/images/logos/DP_icon_integration_engine.svg" alt="Schéma architektury" style="height: 60px; 
margin-top: 1rem;
margin-bottom: -1rem;"/>

## Integration Engine

Integration Engine...

[Dokumentace modulu na integration-engine.github.io](#)
