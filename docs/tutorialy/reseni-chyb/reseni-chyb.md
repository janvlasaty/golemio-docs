---
layout: default
title: Řešení chyb
permalink: /docs/tutorialy/reseni-chyb
nav_order: 2
parent: Tutorialy
---

# Případy a řešení chyb jednotlivých modulů

## Co když se nepodaří uložit data do databáze? (poslat ack? Poslat message znovu? Kumulovat v rabbitovi?)

Odložil bych to do dead queue ktera bude specialne pro uložení dat. Až to opravíme, tak to z ní doimportujeme.

## Co když proces umře v některém z mezikroků? (příjem dat-transformace-dopočty hodnot-etc-uložení do db-send ack)

Tak se nepošle ACK a další worker to zkusí udělat znovu. Případně pak odloží do monitorované deadqueue.

## Jak budou řešeny Dead Queues?

Každý datový projekt by si měl založit i vlastní queues, které nebude vybírat, ale budou jen poslouchat na DLX(dead-letter exchange) https://www.rabbitmq.com/dlx.html