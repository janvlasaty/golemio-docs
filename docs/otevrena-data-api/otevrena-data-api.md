---
layout: default
title: Otevřená data & API
nav_order: 6
description: "Informace k publikovaným otevřeným datům a veřejnému API."
# has_children: true
permalink: /docs/otevrena-data-api/
---

# Otevřená data & API

> V rámci projektu poskytuje široké veřejnosti data k dalšímu použití jako tzv. Open Data. Data jsou povahou realtime data, statistická data, popř. číselníky, katalogy a mapová data.

## Možnosti přístupu

- Opendata katalog Hlavního města Prahy ([opendata.praha.eu](http://opendata.praha.eu){:target="_blank"})
    - Exporty dat s meta informacemi o struktuře, povaze, zdroji, četnosti aktualizace, kontaktní osobě atd.
    - Stálé URL pro datové sady
    - Katalogizace v rámci NKOD ([data.gov.cz](//data.gov.cz){:target="_blank"})
- Public API - Realtime přístup do Datové platformy Golemio
    - REST API zdokumentované na [outputgateway.docs.apiary.io](//outputgateway.docs.apiary.io){:target="_blank"}
    - Přístup zabezpečený pomocí `api-key`, nebo `JWT`


## Publikovaná data v katalogu OD

Operátor ICT provozuje pro HMP katalog otevřených dat, na data, která zvěřejňuje z projektu Golemio se lze dostat na [opendata.praha.eu/dataset?organization=operatorict](http://opendata.praha.eu/dataset?organization=operatorict).

## Přístup k veřejnému API

### API URL

> https://api.golemio.cz/<ROUTES>

#### Zabezpečení

Využíváme JWT token popř. vygenerování API klíče.

### Registrace uživatele

Na stránce [api.golemio.cz/api-keys](//api.golemio.cz/api-keys){:target="_blank"} si lze po bezplatné registraci a ověření přes váš email vygenerovat `api-key` pro přístup k API.

### Přístup bez registrace

Registrace je bezplatná, stejně tak i využítí open dat z Datové platformy, nicméně i pro neregistrované máme možnost data otestovat a sice přes dočasný API klíč.

```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImFkbWluQG9wZXJhdG9yaWN0LmN6IiwiaWQiOjIsIm5hbWUiOm51bGwsInN1cm5hbWUiOm51bGwsImlhdCI6MTU2MzM3MTk3NiwiZXhwIjoxMTU2MzM3MTk3NiwiaXNzIjoiZ29sZW1pbyIsImp0aSI6IjkzMzEzOWQ2LTk4YmEtNDcyMC05YWY2LWY3ZTM4Y2M2MTlhZiJ9.NAuRt-y5JLlbJSmEgfVuxdErVTneTZ9ngMgIxsBJW9Q
```
**POZOR** - tento klíč má omezený `rate-limit` a může být kdykoliv revalidován! Použití je doporučeno výhradně pro testovací účely.

<!-- ## Dokumentace datových sad

Pro úplnost zde uvádíme i některé z datových sad, u kterých je vhodné rozšířit dokumentaci nad rámec dokumentace v API Blueprint. Kliknutím na příslušnou podkategorii přejděte na detailní popis. -->