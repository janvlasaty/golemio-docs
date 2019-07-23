---
layout: default
title: HW požadavky
nav_order: 2
description: "HW požadavky Datové platformy Golemio."
permalink: /docs/hw-pozadavky
---

# FAQ

> Zde je soubor nejčastějších dotazů k Datové platformě, pokud tento článek nezodpoví na vaše otázky, napište ná na [golemio@operatorict.cz](mailto:golemio@operatorict.cz)

## Plní vaše řešení funkci IoT platformy ve smyslu sběru dat ze SigFox, Lora a dalších sítí?

Nikoliv. V Praze jsme se dosud setkávali v projektech vždy s dodavateli poskytující standardní REST API skrze HTTP, není ani na pořadu dne ji využívat. Nicméně díky modularní architektuře platformy je možné kdykoliv předřadit existující řešení poskytující funkci IoT platformy pro komunikaci na odpovídajících IoT sítích.

## Kdy bude celá Datová platforma Open Source?

Začali jsme publikovat zdrojové kódy v polovině roku 2019 postupně po jednotlivých modulech. V dalším průběhu roku 2019 je v plánu zveřejnit kompletní soubor modulů platformy.

## Je připraven software k použití i pro nasazení v jiných městech?

První fází je zveřejnit moduly tak, jak byly navrženy a jsou používány v Praze, v druhé fázi (rok 2020) se nebráníme snahám zobecnit řešení a umožnit jednoduše nasadit software i pro jiná města. Nemělo by to být těžké, s tímto cílem jsme řešení od počátku navrhovali.

## Je to zadarmo?

Publikovali jsme kódy pod licencí MIT, odpověď tedy zní ano, kódy můžete vzít a používat i pro komerční účely zadarmo v rámci podmínek této volné licence. Chcete-li si přečíst o tom, co MIT obnáší, doporučujeme článek na [choosealicense.com/licenses/mit/](//choosealicense.com/licenses/mit/).

## Funguje to někde?

Ano, samozřejmě, jde o řešení, které aktuálně používá Praha pro integraci městských dat.