---
layout: default
title: Integrace datové sady
nav_order: 1
description: "Tutorialy - Output Gateway - Integrace datové sady"
permalink: /docs/tutorialy/output-gateway/integrace-datove-sady
parent: Output Gateway [návody]
grand_parent: Tutorialy
---

# Output Gateway - Integrace datové sady

1. import datasetu z projektu `schema-definitions` (v `App.ts`)
1. přidat data v `RouterBuilder`; přidat datové definice do `array` načítaných dat v metodě `LoadData()` (tento krok automaticky vytvoří všechny potřebné výchozí `routes` (tj. `<API>/<ROUTE>/` and `<API>/<ROUTE>/{id}`, případně `<API>/<ROUTE>/history`)
1. vytvořit API Blueprint dokumentaci (v `output-gateway/docs/apiary_docs.apib`), včetně MSON specifikací datových struktur
1. vytvořit nová testovací data (`mongo dump`, pomocí mongodump tool) a přidat je do `output-gateway/db/example/mongo_data/dataplatform`
1. vytvořit Dredd hooks pro testy (typicky přidáním existujícího ID z odpovědi API do testu API metody pro detail entity `<API>/<ROUTE>/{id}`)

Aktuální podrobnější návod pro integraci datové sady v tomto projektu najdete na [gitlab.com/operator-ict/golemio/output-gateway/blob/master/docs/new_dataset_integration.md](//gitlab.com/operator-ict/golemio/output-gateway/blob/master/docs/new_dataset_integration.md).