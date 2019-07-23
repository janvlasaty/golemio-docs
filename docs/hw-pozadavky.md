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

Doporučená, otestovaná, vývojová specifikace serverů:

| Název serveru | CPU | RAM | Disk | OS |
|:-|:-|:-|
| Backend aplikace | > 4 jádra | > 8 GB  | > 100GB | Debian
| Databázový server | > 4 jádra | > 16 GB  | > 500GB | Debian
| Monitorovací server | > 2 jádra | > 4 GB  | > 100GB | Debian