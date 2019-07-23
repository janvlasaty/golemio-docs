---
layout: default
title: Public API
nav_order: 6
description: "Informace k Public API."
has_children: true
permalink: /docs/public-api/
---

# Public API

> V rámci projektu poskytuje široké veřejnosti data k dalšímu použití jako tzv. Open Data. Data jsou povahou realtime data, statistická data, popř. číselníky, katalogy a mapová data.

## Možnosti přístupu

- Opendata katalog Hlavního města Prahy ([opendata.praha.eu](//opendata.praha.eu){:target="_blank"})
    - Exporty dat s meta informacemi o struktuře, povaze, zdroji, četnosti aktualizace, kontaktní osobě atd.
    - Stálé URL pro datové sady
    - Katalogizace v rámci NKOD ([data.gov.cz](//data.gov.cz){:target="_blank"})
- Public API - Realtime přístup do Datové platformy Golemio
    - REST API zdokumentované na [outputgateway.docs.apiary.io](//outputgateway.docs.apiary.io){:target="_blank"}
    - Přístup zabezpečený pomocí `api-key`, nebo `JWT`
    - Doku

## Přístup k Public API

Na stránce [api.golemio.cz/api-keys](//api.golemio.cz/api-keys){:target="_blank"} si lze po bezplatné registraci a ověření přes váš email vygenerovat `api-key` pro přístup k API.

Pro demonstrační účely lze použít i dočasný `api-key`: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFkbWluQG9wZXJhdG9yaWN0LmN6IiwiaWQiOjIsIm5hbWUiOm51bGwsInN1cm5hbWUiOm51bGwsImlhdCI6MTU2MzM3MTk3NiwiZXhwIjoxMTU2MzM3MTk3NiwiaXNzIjoiZ29sZW1pbyIsImp0aSI6IjkzMzEzOWQ2LTk4YmEtNDcyMC05YWY2LWY3ZTM4Y2M2MTlhZiJ9.NAuRt-y5JLlbJSmEgfVuxdErVTneTZ9ngMgIxsBJW9Q`.
**POZOR** - tento klíč má omezený `rate-limit` a může být kdykoliv revalidován!

## Dokumentace datových sad

Pro úplnost zde uvádíme i některé z datových sad, u kterých je vhodné rozšířit dokumentaci nad rámec dokumentace v API Blueprint. Kliknutím na příslušnou podkategorii přejděte na detailní popis.