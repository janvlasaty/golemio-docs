---
layout: default
title: HW požadavky
nav_order: 2
description: "HW požadavky Datové platformy Golemio."
permalink: /docs/hw-pozadavky
---

# HW požadavky pro instalaci

> Řešení tvoří soubor aplikačních a databázových modulů, které jsou připraveny jako hotové Docker kontejnery. Pro orchestraci je zvolen Docker Swarm.

## HW požadavky pro instalaci

Všechny moduly platformy lze provozovat na localhostu ve specifikaci: 4 jádra CPU, 8 GB RAM, 100GB HDD.

Doporučená, otestovaná, vývojová specifikace:

- VPS (4 jádra CPU, 8 GB RAM, 100GB HDD, Debian)
    - Beckend aplikační server
- VPS (4 jádra CPU, 8 GB RAM, 100GB HDD, Debian)
    - Databázový server
- VPS (4 jádra CPU, 8 GB RAM, 100GB HDD, Debian)
    - Monitorovací server