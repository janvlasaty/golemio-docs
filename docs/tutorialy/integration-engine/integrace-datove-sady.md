---
layout: default
title: Návody
nav_order: 1
description: "Schema Definitions - Návody"
permalink: /docs/integracni-moduly/schema-definitions/navody
parent: Schema Definitions
grand_parent: Integrační moduly
---

# Integration Engine - Integrace datové sady

1. vytvoření nové složky v `input-gateway/src/resources`
1. v této složce vytvoření nového souboru `Router` a `Controller`
1. import datasetu z projektu `schema-definitions` (`Controller`)
1. `app.use(<Router>)` v souboru `App.ts`
1. vytvoření API Blueprint documentatace (`input-gateway/docs/apiary_docs.apib`), včetně  MSON specifikace datové struktury
1. vytvoření testů (`input-gateway/test/resources`)