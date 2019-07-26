---
layout: default
title: Integrace datové sady
nav_order: 1
description: "Tutorialy - Input Gateway - Integrace datové sady"
permalink: /docs/tutorialy/input-gateway/integrace-datove-sady
parent: Input Gateway [návody]
grand_parent: Tutorialy
---

# Input Gateway - Integrace datové sady

1. vytvoření nové složky v `input-gateway/src/resources`
1. v této složce vytvoření nového souboru `Router` a `Controller`
1. import datasetu z projektu `schema-definitions` (`Controller`)
1. `app.use(<Router>)` v souboru `App.ts`
1. vytvoření API Blueprint documentatace (`input-gateway/docs/apiary_docs.apib`), včetně  MSON specifikace datové struktury
1. vytvoření testů (`input-gateway/test/resources`)

Aktuální podrobnější návod pro integraci datové sady v tomto projektu najdete na [gitlab.com/operator-ict/golemio/input-gateway/blob/master/docs/new_dataset_integration.md](//gitlab.com/operator-ict/golemio/input-gateway/blob/master/docs/new_dataset_integration.md).