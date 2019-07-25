---
layout: default
title: HW požadavky
nav_order: 3
description: "HW požadavky Datové platformy Golemio."
permalink: /docs/hw-pozadavky
---

# HW požadavky pro instalaci

> Řešení tvoří soubor aplikačních a databázových modulů, které jsou připraveny jako hotové Docker kontejnery. Pro orchestraci je zvolen Docker Swarm.

## HW požadavky pro instalaci

Všechny moduly platformy lze provozovat na localhostu ve specifikaci: 4 jádra CPU, 8 GB RAM, 100GB HDD.

### Hello world specifikace serverů:

| Název serveru | CPU | RAM | Disk | OS |
|:-|:-|:-|:-|:-|
| All in one | >= 6 jader | >= 8 GB | 200 GB | Debian |

### Vývojová specifikace serverů:

| Název serveru | CPU | RAM | Disk | OS |
|:-|:-|:-|:-|:-|
| Frontend server     | >= 1 jader | >= 1 GB |  64 GB | Debian |
| Backend aplikace    | >= 2 jádra | >= 4 GB | 128 GB | Debian |
| Databázový server   | >= 2 jádra | >= 4 GB | 200 GB | Debian |
| Monitorovací server | >= 2 jádra | >= 4 GB | 128 GB | Debian |

### Produkční specifikace serverů:

| Název serveru | CPU | RAM | Disk | OS |
|:-|:-|:-|:-|:-|
| Frontend server     | >= 2 jader | >= 2 GB |    64 GB | Debian |
| Backend aplikace    | >= 4 jader | >= 8 GB |   128 GB | Debian |
| Databázový server   | >= 4 jader | >= 8 GB | 1 024 GB | Debian |
| Monitorovací server | >= 2 jádra | >= 8 GB |   128 GB | Debian |
