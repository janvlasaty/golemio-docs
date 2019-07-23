---
layout: default
title: Návody
nav_order: 1
description: "Input Gateway - Návody"
permalink: /docs/integracni-moduly/input-gateway/navody
parent: Input Gateway
grand_parent: Integrační moduly
---

# Návody

Návod jak tento modul nainstalovat, nakonfigurovat a spustit včetně ukázkových dat lze v [README daného projektu na Gitlabu](#).

## Integrace nové datové sady

### 1. Analýza datové sady
- proces získání dat (PULL, PUSH)
- typ a velikost dat
- formát uložení a cílová DB (mongo, postgresql)

### 2. Vytvoření schémat pro dataset (Schema Definitions)
- git repo: https://gitlab.oict.cz/data-platform/schema-definitions
- vytvoření schémat podle povahy dat (input nebo datasource schéma, output schéma, history schéma, atd.)
- vytvoření migrace DB (nové tabulky, indexy)

### 3. Input Gateway
- git repo: https://gitlab.oict.cz/data-platform/input-gateway
- tento krok pouze pokud jsou data posílána aktivně ze zdroje (PUSH)
- vytvoření endpointu pro příjem dat
- validace příchozích dat
- odeslání dat do fronty
- dokumentace (apiary)

### 4. Integration Engine
- git repo: https://gitlab.oict.cz/data-platform/integration-engine
- vytvoření transformace dat, např. `modules/NewDataset/NewDatasetTransformation.ts`
- vytvoření workera, např. `modules/NewDataset/NewDatasetWorker.ts`
- přidání záznamu do `queueDefinitions.ts`
- nadefinování datového zdroje ve workeru, pouze pokud je data nutné aktivně stahovat (PULL)
- nadefinování modelu ve workeru
- samotná implementace metod pro zpracování zpráv z front, celá logika
- napsání testů
- dokumentace (`docs/datasets.md`)

### 5. Definice cron tasku
- git repo: https://gitlab.oict.cz/data-platform/cron-tasks
- pouze pokud je data nutné aktivně stahovat (PULL)
- definovat periodicitu a frontu pro odesílání zpráv z cronu
- odeslat definici na DevOps

### 6. Output Gateway
- git repo: https://gitlab.oict.cz/data-platform/output-gateway
- vytvoření rout pro dataset
- definice všech filtru, limitů, atd. podle povahy dat
- definice obohacení (linkování) dat, podle povahy dat
- dokumentace (apiary)
