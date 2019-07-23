---
layout: default
title: Schema Definitions
nav_order: 4
description: "Dokumentace modulu Schema Definitions"
permalink: /docs/integracni-moduly/schema-definitions/
has_children: true
parent: Integrační moduly
---

# Schema Definitions

> Sada schémat datových struktur sloužící pro validaci při vstupu dat (v Input Gateway a Integration Engine) a pro výstupní formát dat (v Output Gateway). Zároveň v projektu udržujeme veškeré databázové migrace při úpravě datových vstupů či jejich transformací.

## Funkce

Schema Definitions je soubor definicí databázových schémat pro jednotlivé datové sady.


## 
Vstupní data
JSON, XML, CSV
Funkce
Validace oproti schématu pro každý definovaný endpoint
Monitoring počtu entit/řádků v payloadu příchozích dat
Výstup
Data jsou zapsána ve zprávě do Message Brokeru (AMQP 0-9-1)
Monitoring se provádí do InfluxDB
