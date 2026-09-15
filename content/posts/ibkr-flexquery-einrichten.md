---
title: 'IBKR FlexQuery für die AT-Steuererklärung einrichten — Schritt für Schritt'
date: 2026-05-31
lastmod: 2026-09-15
description: 'Wie Du in Interactive Brokers eine Activity Flex Query erstellst, die alle für die österreichische E1kv nötigen Daten enthält — Trades, Dividenden, Quellensteuer, Cash Transactions. Mit der Section-Checkliste, den leicht übersehenen Detailoptionen und den exakten Formatwerten.'
keywords: ['IBKR FlexQuery', 'IBKR FlexQuery erstellen', 'Activity Flex Query', 'IBKR Steuer Österreich', 'Interactive Brokers Steuererklärung', 'IBKR XML Export', 'FlexQuery Executions', 'Flex Web Service Token']
tags: ['FlexQuery', 'IBKR', 'Steuererklärung', 'Österreich']
---

# IBKR FlexQuery für die AT-Steuererklärung einrichten

> **Stand:** 2026-09-15 · **Lesezeit:** ~9 Minuten · **Gilt für:** AT-Privatpersonen, IBKR Client Portal 2026

Für die österreichische Steuererklärung („E1kv ohne KESt-Abzug") brauchst Du aus Interactive Brokers **alle** Trades, Dividenden, Quellensteuer-Abzüge und Cash-Bewegungen eines Kalenderjahres — in einem Format, das maschinenlesbar ist. Das **Activity Statement** im PDF reicht dafür nicht. Du brauchst eine **Activity Flex Query** als XML.

Diese Anleitung zeigt, **welche Sections Du anhakst**, welche **Detailoptionen** innerhalb der Sections leicht übersehen werden — und mit welchen **Formatwerten** die XML später sauber einlesbar ist.

> 💡 **Quick-Win:** Wenn Du den Export samt KZ-Zuordnung automatisieren willst — am Ende des Artikels gibt es einen Link zu einem [Tool](#tool), das die FlexQuery direkt einliest und die E1kv-Beilage erzeugt.

## Inhaltsverzeichnis

1. Warum FlexQuery (und nicht das normale Activity Statement)?
2. Wo findest Du FlexQueries im IBKR Client Portal?
3. Die Sections
4. Die Detailoptionen, die fast alle übersehen
5. Allgemeine Konfiguration: Formatwerte
6. Zeitraum, Speichern, Download
7. Häufige Fehler
8. Tool spart Dir die FlexQuery-Auswertung

---

## 1. Warum FlexQuery — reicht das Activity Statement nicht?

Kurze Antwort: **Nein, für die E1kv nicht.**

| Format | Was Du bekommst | Steuer-tauglich? |
|--------|----------------|------------------|
| **Activity Statement (PDF)** | Hübsche Übersicht, aber Spalten-Aggregation, keine Roh-Trades | ❌ — keine maschinelle Avg-Cost-Berechnung möglich |
| **Activity Statement (CSV)** | Trades je Zeile, aber CSV-Struktur ist instabil und mischt Sections | ❌ — Header ändern sich, FX-Kurse fehlen oft |
| **Activity Flex Query (XML)** | Ein Block pro Section, stabile Tags, FX-Kurse zum Buchungstag | ✅ — die einzige zuverlässige Quelle |
| **Tax Forms (1099 / 1042-S)** | US-Steuerunterlagen | ❌ — irrelevant für AT, gilt nur für US-Resident-Steuer |

Die FlexQuery ist also nicht „die luxuriöse Variante", sondern für AT-Steuerzwecke **die einzige korrekte**.

---

## 2. Wo findest Du FlexQueries im IBKR Client Portal?

1. Login im Client Portal (https://www.interactivebrokers.com → „Login" oben rechts).
2. Menü **Berichte / Reports** → **Flex Queries**.
3. Du landest auf einer Seite mit zwei Bereichen:
   - **Activity Flex Query** ← das willst Du
   - **Trade Confirmation Flex Query** ← brauchst Du **nicht**
4. Unter „Activity Flex Query" auf **+** (Neu / Create) klicken.

> 🇬🇧🇩🇪 Die Oberfläche gibt es auf Englisch und Deutsch. Die Section-Namen bleiben meist englisch, die allgemeinen Einstellungen sind teilweise übersetzt — unten stehen deshalb beide Bezeichnungen. Menüpfade können je nach Portal-Version leicht abweichen.

---

## 3. Die Sections

Im Create-Dialog gibst Du der Query zuerst einen **Namen** (z.B. `AT_Steuer`). Dann aktivierst Du die Sections. Innerhalb jeder Section: **alle Felder auswählen.**

### ✅ Unverzichtbar

| Section | Warum Du das brauchst |
|---------|----------------------|
| **Trades** | Jeder Aktien-/Options-/Forex-Trade. Basis für die Avg-Cost-Berechnung der realisierten Gewinne. **Detailoption „Executions" anhaken — siehe Abschnitt 4.** |
| **Cash Transactions** | Dividenden, Payment In Lieu, Quellensteuer, Broker-Zinsen, Gebühren. Basis für KZ 863 und die anrechenbare Quellensteuer (KZ 998). |
| **Open Positions** | Wertpapierbestand zum Stichtag — Basis für offene Positionen und den Einstand von Altbeständen. |
| **Statement of Funds** | Cash-Flow-Bewegungen je Währung. Cross-Check, ob die Summen zusammenpassen. |
| **Conversion Rates** | EUR-Wechselkurse zum Buchungstag. Ohne sie lassen sich USD-Beträge nicht korrekt in EUR umrechnen. |
| **Corporate Actions** | Splits, Spin-Offs, Ticker-Wechsel. Sonst zerschießt Dir ein Aktiensplit die Avg-Cost-Berechnung. |
| **Transfers** | Überträge von/zu anderen Brokern — die Anschaffungskosten müssen mitwandern. |

### 🔲 Stark empfohlen

| Section | Wofür |
|---------|-------|
| **Prior Period Positions** | Bestände zum Vortag — für den Übergang zwischen Abrufzeiträumen. |
| **FX Positions** | Fremdwährungsguthaben und -salden. |
| **Change in NAV** · **Equity Summary in Base** | Verlauf des Depotwerts — Grundlage für Rendite- und Portfolio-Auswertungen. |
| **Change in Dividend Accruals** · **Open Dividend Accruals** | Dividenden-Abgrenzung zum Stichtag — relevant für die korrekte Periodenzuordnung zum 31.12. |
| **Interest Accruals** · **Tier Interest Details** | Zinsabgrenzung und Zinsstaffel. |
| **Sales Tax** | Transaktions- und Umsatzsteuern auf Gebühren. |
| **Option EAE** (Exercise / Assignment / Expiration) | Unverzichtbar, sobald Du Optionen handelst — sonst fehlen Andienungen und Ausübungen. |
| **MTM Performance Summary in Base** · **Realized & Unrealized Performance Summary** | IBKRs eigene Performance-Zahlen — praktisch als Gegenprobe zur eigenen Rechnung. |
| **Account Information** | Stammdaten: Kontotyp, Basiswährung. |

Je vollständiger die Query, desto besser lassen sich die Zahlen gegenprüfen. Eine fehlende empfohlene Section macht die Steuerberechnung nicht falsch, aber einzelne Auswertungen bleiben leer.

---

## 4. Die Detailoptionen, die fast alle übersehen

Beim Bearbeiten einer Section gibt es **Detailoptionen** — sie sind leicht zu übersehen, und genau hier scheitern die meisten Einrichtungen.

| Section | Anhaken |
|---------|---------|
| **Trades** | ☑ **Executions** *und* ☑ **Closed Lots** |
| **Open Positions** | ☑ **Summary** *und* ☑ **Lot** |
| **Realized & Unrealized Performance Summary** | ☑ **Detail** |

> ⚠️ **„Executions" ist die wichtigste Option des ganzen Setups.** Ohne sie liefert IBKR die Section „Trades" **leer** — Bestände und Kontobewegungen kommen an, aber **kein einziger Kauf oder Verkauf**. Das fällt nicht sofort auf, weil die XML trotzdem gültig ist und die Section-Überschrift vorhanden ist. In der XML erkennst Du den Unterschied an Zeilen wie `<Trade … levelOfDetail="EXECUTION">` — fehlen sie, fehlt die Option.

Die **Lot-Ebene** bei Open Positions liefert je Steuer-Lot das Anschaffungsdatum und die Kostenbasis. Erst damit kann ein Tool bei einem schon länger laufenden Konto den Einstand der Altbestände korrekt ansetzen.

---

## 5. Allgemeine Konfiguration: Formatwerte

Am Ende des Dialogs, vor der Zustellung, steht ein Block mit allgemeinen Einstellungen. **Diese Werte exakt so setzen** — abweichende Datums- und Zeitformate machen die XML für viele Tools unlesbar.

| Einstellung (DE / EN) | Wert |
|-----------------------|------|
| Datumsformat / Date Format | `yyyy-MM-dd` |
| Zeitformat / Time Format | `HH:mm:ss` |
| Datum/Uhrzeit-Trennzeichen / Date/Time Separator | **Leerzeichen** |
| Gewinn und Verlust / Profit and Loss | Basiswährung |
| Include Offsetting Trade/Cancel Pairs | **Nein / No** |
| Wechselkurse miteinbeziehen / Include Currency Rates | **Ja / Yes** — nötig für die EUR-Umrechnung |
| Prüfpfadfelder einbeziehen / Include Audit Trail Fields | Nein / No |
| Konto-Pseudonym anstelle der Konto-ID / Display Account Alias | **Nein / No** — sonst kommen Konten verschlüsselt |
| Aufschlüsselung nach Tagen / Breakout by Day | **Nein / No** — sonst kommen Buchungen mehrfach |
| Zahlenformat / Number Format | ohne Tausendertrenner |

Mit diesen Werten sieht ein Zeitstempel in der XML so aus: `2025-05-15 20:59:59`.

> ⚠️ **Achtung Zeitzone:** IBKR liefert Zeitstempel in New Yorker Zeit, teils mit Suffix wie `EDT` oder `EST`. New York liegt in der Regel sechs Stunden hinter Wien. Kritisch ist der Jahreswechsel: Ein Trade am **31. Dezember um 20:00 New Yorker Zeit** ist in Wien bereits der **1. Jänner**. Ein Tool muss das bewusst behandeln, sonst landet ein Trade im falschen Steuerjahr.

---

## 6. Zeitraum, Speichern, Download

### Format
- **XML** wählen. **Nicht CSV.**

### Zeitraum
Eine einzelne Abfrage deckt **höchstens ein Jahr** ab. Daraus ergeben sich zwei typische Setups:

- **Für den laufenden automatischen Abruf:** „Letzte n Kalendertage" mit z.B. **14 Tagen**. Ein Tool, das den Datenbestand fortlaufend sammelt, braucht nicht bei jedem Abruf die volle Historie.
- **Für vergangene Jahre:** je Jahr eine eigene Abfrage mit **Custom Date Range**, z.B. `2025-01-01` bis `2025-12-31`, einmalig ausführen und die XML herunterladen. Für drei vergangene Jahre also drei Dateien.

### Speichern und ausführen
1. **Speichern / Save**. In der Liste steht nun die **Query ID** (eine Zahl) — die brauchst Du für die Automatisierung.
2. Neben dem Namen auf das **Play-Icon** (▶) klicken, Zeitraum bestätigen, **Run**.
3. Die erste Generierung dauert je nach Kontovolumen 30 Sekunden bis einige Minuten.
4. **Download** — die XML liegt auf Deinem Rechner.

### Automatisierung über den Flex Web Service
Statt jedes Mal manuell herunterzuladen, kannst Du die Daten automatisch abrufen lassen:

1. Im selben Bereich **Flex Web Service** öffnen und aktivieren.
2. Einen **Token** generieren — auf der deutschsprachigen IB-Seite heißt er **„Prüfcode"**. Er erlaubt nur den lesenden Abruf von Berichten.
3. **Query ID** und **Token** im Tool hinterlegen.

> ℹ️ Tokens haben ein **Ablaufdatum**. Läuft er ab, im selben Bereich einfach einen neuen erzeugen und im Tool aktualisieren.

---

## 7. Häufige Fehler

### „Die Section Trades ist leer — aber Bestände und Kontobewegungen sind da"
Detailoption **Executions** nicht angehakt. Die Section existiert in der XML, enthält aber keine `<Trade>`-Zeilen. Query bearbeiten, bei Trades **Executions** anhaken, speichern — beim nächsten Abruf kommen die Trades des abgefragten Zeitraums nach.

### „Bei meiner FlexQuery fehlen die Quellensteuer-Buchungen"
Section **Cash Transactions** vergessen. Die Section Trades enthält keine Dividenden und keine Quellensteuer — das sind technisch keine Trades.

### „USD-Beträge sind ohne EUR-Umrechnung"
Section **Conversion Rates** fehlt oder **Wechselkurse miteinbeziehen** steht auf Nein.

### „Mein Tool kann die Datums- oder Uhrzeitfelder nicht lesen"
Datums-/Zeitformat oder Trennzeichen abweichend gesetzt. Zurück auf `yyyy-MM-dd`, `HH:mm:ss` und **Leerzeichen** als Trennzeichen.

### „Mein Avg-Cost stimmt nicht — IBKR sagt was anderes"
Das ist **normal und erwartet**. IBKR rechnet je nach Konto-Einstellung mit anderen Lot-Methoden. AT verlangt den **gleitenden Durchschnittspreis (§ 27a Abs 4 Z 1 EStG)**. Das Steuer-Tool muss ihn selbst aus den Roh-Trades nachrechnen — die IBKR-PnL-Spalte ist für die AT-Steuererklärung **nicht** maßgeblich.

### „Corporate Action hat mein Avg-Cost zerstört"
Section **Corporate Actions** war nicht angehakt. Ohne sie sieht ein Tool die Stückzahlanpassung bei einem Split nicht und rechnet die Kostenbasis falsch.

### „Ich habe von einem anderen Broker zu IBKR übertragen — die Kostenbasis ist 0"
Section **Transfers** anhaken. Aber: Bei Überträgen **vor** dem ersten IBKR-Trade muss die historische Basis aus dem alten Broker-Statement nachgewiesen werden — keine FlexQuery kann Daten liefern, die der Broker nicht hat.

### „Meine Historie reicht nur ein paar Wochen zurück"
Die automatische Abfrage hat einen kurzen Zeitraum. Für vergangene Jahre je Jahr eine **Custom Date Range** exportieren und die Dateien einmalig einspielen.

---

## 8. <a id="tool"></a>Tool spart Dir die FlexQuery-Auswertung

Wenn Du die XML nicht selbst auswerten willst:

> 🛠 **[DepotTax](https://depottax.at)** liest Deine Activity Flex Query ein und erzeugt die E1kv-Kennzahlen — mit AT-konformem gleitendem Durchschnittspreis, getrennten Steuertöpfen und Herleitung bis auf die einzelne Transaktion. Du kannst die XML hochladen oder über den **Flex Web Service Token** automatisch abrufen lassen. Die App prüft außerdem, ob Deine Bestände zu den importierten Trades passen, und warnt, wenn etwas fehlt.

Aktuell in geschlossener Beta. Melde Dich, falls Du dabei sein willst.

### Verwandte Guides

- [E1kv ausfüllen für IBKR-User (Österreich 2026)](/posts/e1kv-ausfuellen-ibkr/) — der nächste Schritt nach dem FlexQuery-Setup
- [KZ 863 vs KZ 994 — wo trage ich was ein?](/posts/kz-863-vs-kz-994/) — Zuordnungstabelle pro Buchungstyp
- [Depotübertrag bei IBKR — muss ich das erklären?](/posts/depotuebertrag-ibkr-oesterreich/)

### Quellen

- IBKR Knowledge Base: „Activity Flex Query — Sections Reference"
- IBKR Help Center: „Flex Web Service Configuration"
- EStG § 27a Abs 4 Z 1 (gleitender Durchschnittspreis)

---

*Dieser Artikel ist keine Steuerberatung, sondern eine technische Anleitung. Menübezeichnungen im IBKR-Portal können sich ändern.*
