---
layout: default
title: Integrační moduly 
nav_order: 10
description: "Integrační moduly Datové platformy."
has_children: true
permalink: /docs/integracni-moduly/
---

# Integrační moduly

> Skupina modulů pro autorizaci přístupů, přijímání, zpracování, odesílání dat, časově řízené úlohy, export dat do jiných systému atd.

<img src="/golemio-docs/assets/images/logos/DP_icon_permission_proxy.svg" alt="Schéma architektury" style="height: 60px; 
margin-top: 1rem;
margin-bottom: -1rem;"/>

## Permission proxy

Modul pro řešení přístupových práv a ACL. Zkontroluje API klíč/přístupové údaje, provádí autentizaci a autorizaci a povoluje přístup k jednotlivým endpointům. Ukládá statistiky o využití. Navrženo jako “proxy” z důvodu požadavků na funkcionalitu přidělování práv: např. na základě API klíče povolovat přístup pouze k některým datům v DB (tedy na úrovni řádků) nebo přidání nějakých parametrů (např. limit) do požadavků.

<img src="/golemio-docs/assets/images/logos/DP_icon_input_gateway.svg" alt="Schéma architektury" style="height: 60px; 
margin-top: 1rem;
margin-bottom: -1rem;"/>

## Input Gateway

Bezstavový server, vstupní RESTful API nadefinované dle popisu Apiary, testované přes Dredd nebo Postman API testy. Vstupní API přijímá push požadavky (POST) s daty ke zpracování, data zvaliduje a pošle do Message Queue ke zpracování.
Node.js, Express, Typescript, Mongoose pro validaci, amqplib pro připojení k RabbitMQ, Docker

<img src="/golemio-docs/assets/images/logos/DP_icon_message_broker.svg" alt="Schéma architektury" style="height: 60px; 
margin-top: 1rem;
margin-bottom: -1rem;"/>

## Message Broker

Message Broker je modul pro předávání zpráv ve frontovém systému. Pro různé datové sady definujeme různě komplexní workflow a právě Message Broker slouží pro příjem dat/úkolů přes Exchange servery, které odešlou zprávy do specifických front. V současnosti využíváme platformu RabbitMQ. 

<img src="/golemio-docs/assets/images/logos/DP_icon_integration_engine.svg" alt="Schéma architektury" style="height: 60px; 
margin-top: 1rem;
margin-bottom: -1rem;"/>

## Integration Engine

Integrační komponenta pro příjem, transformaci, agregaci, obohacení a ukládání dat do DB. Celkově processing dat. Komunikace (požadavky, data,..) probíhá přes Message Queue případně RESTful API (zatím není implementováno), synchronizace přes Message Queue. Hlavní komponenty jsou Workery, které provádí nadefinované operace s daty. Aplikace nemusí data jen přijímat, ale na podnět (z MQ) si data stáhne a zpracuje (polling).
Node.js, Typescript, Mongoose pro připojení k DB, amqplib pro připojení k RabbitMQ, Docker.

## Schema Definitions

Samostatný modul kde budeme ukládat schémata jednotlivých datových sad, jejich popis a metadata. Ostatní moduly toto používají např. pro validaci dle daného schématu, nebo schéma pro uložení do DB.

## Exporting Module

Periodické generování CSV, GeoJSON popř. dalších souborů z naměřených hodnot senzorů, aktualizace seznamů entit, mapových podkladů apod. Ukládání do lokálního úložiště, statický URL link pro uveřejnění datové sady na opendatovém katalogu (v současnosti na CKAN na opendata.praha.eu).

## Cron

Cron generuje v dané časy zprávu bez obsahu do fronty, slouží jako trigger pro spouštění některých úkonů systému (aktualizace dat, spouštění výpočtů apod.).
