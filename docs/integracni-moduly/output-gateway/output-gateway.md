---
layout: default
title: Output Gateway 
nav_order: 3
description: "Dokumentace modulu Output Gateway"
permalink: /docs/integracni-moduly/output-gateway/
# has_children: true
parent: Integrační moduly
---

# Output Gateway

> Rozhraní pro výstup dat integrovaných datových sad. Provádí dotazy do databází s možností parametrizace dotazů, cachuje výsledky dotazů.

## Popis

Output Gateway je REST API - Node.js aplikace postavená na frameworku Express.js s připojením do databází. Nabízí možnost parametrizace dotazů (počet záznamů, časové období, GPS lokace s perimetrem apod.)

## Funkce

- Výstup dat z databází a parametrizace dotazů dle API volání
- Cachování výstupů