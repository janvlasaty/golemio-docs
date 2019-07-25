---
layout: default
title: Integrace datové sady
nav_order: 1
description: "Tutorialy - Schema Definitions - Integrace datové sady"
permalink: /docs/tutorialy/schema-definitions/integrace-datove-sady
parent: Schema Definitions [návody]
grand_parent: Tutorialy
---

# Schema Definitions - Integrace datové sady

1. vytvořit nový soubor v `schema-definitions/src/`
1. vytvořit v tomto souboru všechna potřebná schémata, dodržet jmenné konvence v  `schema-definitions/CONTRIBUTING.md`
1. vytvořit nové migrační skripty dle `schema-definitions/docs/migrations.md`
1. přidat `export` do `schema-definitions/src/index.ts`
1. publikovat změny
1. globální použití Merge Request
1. lokální použití `npm pack` (popsáno v `schema-definitions/README.md`)