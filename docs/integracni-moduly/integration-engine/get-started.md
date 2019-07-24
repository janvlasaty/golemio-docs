---
layout: default
title: Get Started
nav_order: 1
description: "Integration Engine - Get Started"
permalink: /docs/integracni-moduly/integration-engine/get-started
parent: Integration Engine
grand_parent: Integrační moduly
---

# Get started

Aplikační modul pro zpracování příchozích dat na Input Gateway, stahování dat z externích API, realizaci transformačního workflow, obohacování, spojování a agregaci dat a ukládání dat do DB. 
Integration Engine je node.js aplikace. Vytváří v Message Brokeru workflow zpracování dat. Pro každou datovou sadu existuje zpravidla několik workerů - transformačních skriptů, které atomicky provádí jednu činnost v procesu: přijmutí (stažení dat) -> transformace -> obohacení/agregace -> uložení.
Vstupní data
JSON, XML z Input Gateway ve frontě v Message Brokeru
Časově řízené inicializační povely z CRON Modulu
Funkce
Transformace vstupního formátu dat
Obohacování dat o další atributy
Stahování dat z externích zdrojů (HTTP, FTP) ve formátu dat JSON, XML, CSV

Výstup

