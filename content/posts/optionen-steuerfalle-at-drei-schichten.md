---
title: 'Die drei Schichten der österreichischen Optionen-Steuerfalle: DAC, Tarif, kein Verlustvortrag'
date: 2026-06-23
lastmod: 2026-06-23
description: 'Wer in Österreich als Privatperson echte Optionen oder Futures über einen Auslandsbroker handelt, fällt in eine dreifache Steuerfalle: keine inländische KESt-Abfuhr, voller progressiver Tarif statt 27,5 %, kein Verlustvortrag über das Jahresende hinaus. Welche Ausweg-Strategien praktikabel bleiben — und welche nur theoretisch klingen.'
keywords: ['Optionen Steuer Österreich', 'Futures Steuer AT', 'unverbriefte Derivate', '§ 27a Abs 2 Z 7 EStG', 'Tarifbesteuerung Derivate', 'kein Verlustvortrag Kapitalvermögen', 'Auslandsbroker KESt', 'DAC Amtshilfe', 'steuerlicher Vertreter Inland', 'verbriefte Zertifikate Alternative']
tags: ['Optionen', 'Futures', 'Auslandsbroker', '§ 27a EStG', 'KZ 857', 'Verlustvortrag', 'Österreich']
---

# Die drei Schichten der österreichischen Optionen-Steuerfalle

> **Stand:** 2026-06-23 · **Lesezeit:** ~6 Minuten · **Gilt für:** AT-Privatpersonen, die bei Interactive Brokers, CapTrader, LYNX, BANX oder ähnlichen Auslandsbrokern echte (= unverbriefte) Optionen oder Futures handeln

Wer als österreichische Privatperson aktiv mit Optionen oder Futures bei einem Auslandsbroker handelt, steht steuerlich in einer Konstellation, die im EU-Vergleich praktisch konkurrenzlos ungünstig ist. Drei Schichten greifen ineinander — und jede einzelne wäre für sich schon problematisch. Zusammen ergeben sie eine **strukturelle Hürde**, die selbst gut gerechnete Trading-Strategien wirtschaftlich entwertet.

Dieser Beitrag bündelt, was wir aus tausenden Mandantenfällen und der eigenen Tool-Entwicklung [depottax.at](https://depottax.at) für die Erfassung dieser Fälle gelernt haben.

## Schicht 1 — Keine automatische KESt-Abfuhr durch den Broker

### Das Problem
Auslandsbroker führen für AT-Kunden **keine Kapitalertragsteuer** direkt ab. Das ist nicht ein Versäumnis der Broker, sondern eine Konsequenz der österreichischen Rechtslage.

### Die Ursache
Das österreichische Gesetz verlangt für einen freiwilligen KESt-Einbehalt durch einen ausländischen Broker einen **inländischen steuerlichen Vertreter mit voller Haftung** (§ 95 Abs 2 Z 2 EStG iVm § 27a Abs 5 EStG). Das ist organisatorisch teuer, haftungsrechtlich riskant und wird von praktisch keinem großen Auslandsbroker übernommen.

### Der europarechtliche Widerspruch
Durch die EU-Amtshilferichtlinien — insbesondere **2011/16/EU (DAC)** in den aktualisierten Fassungen — besteht zwischen den EU-Mitgliedstaaten längst ein lückenloser automatischer Informationsaustausch über Kapitalerträge. Eine Vertreterpflicht im Inland ist europarechtlich als **Beschränkung des freien Dienstleistungsverkehrs** (Art 56 AEUV) hochgradig umstritten und in der Literatur als unionsrechtswidrig diskutiert. Bisher wurde sie aber nicht endgültig vor dem EuGH oder VfGH zu Fall gebracht.

### Was das praktisch heißt
Der Steuerpflichtige muss die Kapitalerträge selbst in die Einkommensteuer-Erklärung (Beilage E1kv) einbringen, die richtige Klassifizierung pro Topf finden, die Verluste fristgerecht ausgleichen — alles in Eigenverantwortung. **Tools wie [depottax.at](https://depottax.at) automatisieren genau diesen Schritt** für die häufigen Auslandsbroker-Konstellationen.

## Schicht 2 — Tarifbesteuerung bis 55 % statt 27,5 %

Hier liegt der finanziell größte Hebel der Steuerfalle.

### Die Rechtslage
Seit der Gesetzesreparatur durch das ÖkoStRefG 2022 (in Kraft seit **März 2022**) gilt für unverbriefte Auslands-Derivate eindeutig: **§ 27a Abs 2 Z 7 EStG**. Diese Norm schließt unverbriefte Derivate ausdrücklich vom 27,5-%-Sondersteuersatz aus und ordnet sie dem **regulären progressiven Einkommensteuertarif** zu.

Konkret bedeutet das:

| Tarifstufe | Steuersatz | Wirkt ab Gesamteinkommen |
|---|---:|---|
| Stufe 1 | 0 % | bis 13.308 € |
| Stufe 2 | 20 % | über 13.308 € |
| Stufe 3 | 30 % | über 21.617 € |
| Stufe 4 | 40 % | über 35.836 € |
| Stufe 5 | 48 % | über 69.166 € |
| Stufe 6 | 50 % | über 103.072 € |
| Stufe 7 | **55 %** | über 1.000.000 € |

(Werte für 2026 — Anpassung an Inflation laut Bundesgesetz.)

Ein Trader mit gutem Hauptberuf rutscht bei realisierten Options-Gewinnen schnell in die 48-%-Stufe. Im Vergleich zu den 27,5 % bei verbrieften Produkten zahlt er also **rund 75 % mehr Steuer** auf jeden Gewinn-Euro.

### Was zur Optionen-Klassifizierung zählt
- **Z7-Topf** (Tarif): Single-Stock-Optionen, Index-Optionen, Futures, Forwards, CFDs, FOPs — typische IBKR/CapTrader/LYNX-Produkte
- **27,5-%-Topf** (Sondersatz): verbriefte Zertifikate, Optionsscheine („Warrants"), strukturierte Produkte mit Wertpapier-Charakter

Die Abgrenzung „verbrieft vs. unverbrieft" ist scharf: entscheidend ist, ob ein Wertpapierkennnummer-tragendes Wertpapier gehandelt wird. Echte börsengehandelte Optionen (z. B. an der CBOE) sind zwar an einer Börse, aber **keine Wertpapiere** im Sinne des § 1 KMG — sie sind „nicht verbrieft" und damit Z7-Tarif.

## Schicht 3 — Kein Verlustvortrag über das Jahresende hinaus

Die wahrscheinlich härteste Schicht — und EU-weit isoliert.

### Die Norm
**§ 27 Abs 8 Z 4 EStG** verbietet im Privatvermögen den Vortrag von realisierten Kapitalverlusten in das Folgejahr. Verluste eines Kalenderjahrs sind **am 31. Dezember verloren**, wenn nicht innerhalb desselben Jahres ausreichend Gewinne aus demselben Topf zum Verrechnen vorhanden waren.

### Der EU-Vergleich
| Land | Kapitalverlust-Vortrag |
|---|---|
| **Deutschland** | unbeschränkt (§ 20 Abs 6 EStG) |
| **Frankreich** | 10 Jahre |
| **Italien** | 4 Jahre |
| **Spanien** | 4 Jahre |
| **Portugal** | 5 Jahre |
| **Polen** | 5 Jahre |
| **Tschechien** | 5 Jahre |
| **Dänemark** | 5 Jahre |
| **Finnland** | 5 Jahre |
| **Österreich** | **0 Jahre** |

Österreich ist innerhalb der EU damit der einzige Mitgliedstaat, der einen vollständigen Ausschluss des Verlustvortrags im Privatvermögen kennt. Die verfassungsrechtliche Vereinbarkeit mit dem **Leistungsfähigkeits- und Gleichheitsgrundsatz** ist von mehreren österreichischen Steuerrechtlern bestritten, aber bisher nicht höchstgerichtlich gekippt.

### Was das praktisch heißt
Eine schlechte Marktphase mit hohen realisierten Verlusten — wie sie aktive Optionshändler in einem schwachen Jahr typischerweise erleben — kann nicht mit den Gewinnen der Folgejahre verrechnet werden. Wer in einem Jahr 50.000 € Verlust und im Folgejahr 50.000 € Gewinn realisiert, zahlt im Folgejahr **die volle Tarifsteuer auf 50.000 €**, obwohl er wirtschaftlich bei null steht.

## Strategische Alternativen — was nicht funktioniert

### Trading-GmbH gründen
Die Idee klingt verlockend: Verluste können unbegrenzt vorgetragen werden, der Körperschaftsteuersatz liegt bei flachen 23 %.

**Warum es für die meisten Privattrader nicht passt:**
- Bei Entnahme aus der GmbH fällt **27,5 % KESt** auf die Dividende an → Gesamtsteuerbelastung ca. **44,3 %** (1 − (1 − 0,23) × (1 − 0,275))
- Laufende Steuerberatungskosten von typischerweise **3.000 - 6.000 € pro Jahr**
- Buchführungspflicht, doppelte Buchhaltung, Bilanzierungspflicht
- Bei Auflösung evtl. Liquidationssteuer, Sperrfristen

Eine Trading-GmbH lohnt sich erst ab einem **konstant hohen sechsstelligen jährlichen Trading-Gewinn**, und nur wenn das Kapital langfristig in der Gesellschaft bleiben kann.

### Gewerbliche Einstufung im Privatbereich
Theoretisch könnte das Finanzamt Trading-Aktivität als **gewerblich** einstufen — mit dem Vorteil eines Verlustvortrags und voller WK-Abzugsfähigkeit. In der Praxis lehnt das Finanzamt dies bei reiner Vermögensverwaltung **konsequent ab**. Die Voraussetzungen (Marktteilnahme, Fremd-Klienten, gewerbliche Organisation) sind für einen Privatanleger praktisch unerreichbar.

### Wohnsitz-Verlagerung
Ein Wegzug ist juristisch möglich, wirtschaftlich aber massiv: **Wegzugsbesteuerung** auf alle stillen Reserven, Anti-Treaty-Shopping-Regeln, doppelte Wohnsitzfiktion bei AT-Immobilien. Für die meisten keine reale Option.

## Was pragmatisch bleibt

Wenn die Systemebene nicht änderbar ist, kommen für AT-Privatanleger im Wesentlichen zwei pragmatische Wege in Frage:

### Weg A — Wechsel auf verbriefte Produkte
**Hebel-Zertifikate, Optionsscheine, Knock-out-Produkte** bei einem AT-Broker (z. B. flatex AT, Hello bank!) sind als Wertpapiere klassifiziert. Damit:
- 27,5 % Sondersteuersatz
- Automatische KESt-Abfuhr durch den AT-Broker (Endbesteuerung möglich)
- Verluste im 27,5-%-Topf mit anderen 27,5-%-Gewinnen verrechenbar
- Keine eigene Steuererklärungs-Pflicht für diese Erträge

**Nachteil:** Produktauswahl deutlich enger, Emittentenrisiko, oft schlechtere Preisstellung als echte Optionen. Für reine Hebel-Strategien funktioniert es; für komplexere Optionsstrategien (Spreads, Iron Condors etc.) fehlen die Bausteine.

### Weg B — Umschichten in steuereinfache Anlageformen
**Aktien, ETFs, klassische Investmentfonds** über einen AT-Broker. Steuerlich denkbar einfach: 27,5 % KESt, automatisch abgeführt, Verlustverrechnung innerhalb des Topfs möglich, kein Z7-Tarif. Für Buy-and-Hold-Strategien oder taktische Allokation oft die wirtschaftlich rationale Wahl, auch wenn sie die Trading-Identität fundamental verändert.

## Was die Mischung schwierig macht

Wer **gleichzeitig** Optionen, Aktien und Anleihen über einen Auslandsbroker hält, muss zumindest drei Töpfe sauber führen:

1. **27,5-%-Topf** (Aktien-Realgewinne, Dividenden, Zinsen, verbriefte Derivate)
2. **Z7-Tarif-Topf** (Optionen, Futures, CFDs)
3. **Quellensteuer-Block** (ausländische QSt, anrechenbar bis DBA-Höchstsatz)

Plus Sonderfälle wie ausschüttungsgleiche Erträge bei thesaurierenden Fonds (KZ 937 jahresweise, AW-Korrektur), Bond-Stückzinsen, Forex-Speku, Andienungen aus Stillhalter-Strategien. Jeder dieser Posten hat seine eigene KZ-Logik in der E1kv-Beilage.

**Hier setzt unser Tool an:** [depottax.at](https://depottax.at) liest Trade-Daten direkt aus dem Broker-FlexQuery, klassifiziert pro Position in den richtigen Topf, rechnet sauber AVG-Cost (AT-Pflichtmethode nach § 27a Abs 4 Z 1 EStG) und liefert eine E1kv-fertige PDF/Excel-Aufstellung — inklusive Audit-Spalten für die BP-Prüfung. Der manuelle Aufwand sinkt von Tagen auf Minuten.

## Fazit

Die österreichische Rechtslage für unverbriefte Auslands-Derivate im Privatvermögen ist EU-weit beispiellos ungünstig. Sie ergibt sich nicht aus einer einzigen Regel, sondern aus **drei verstärkenden Schichten** — DAC-Vertreterpflicht, Z7-Tarif, kein Verlustvortrag.

Pragmatisch bleiben drei Wege:

1. **System akzeptieren und korrekt deklarieren** (mit Tool-Unterstützung den manuellen Aufwand minimieren)
2. **Auf verbriefte Produkte umsteigen** (engere Produktwelt, dafür steuerlich gleich wie Aktien)
3. **Klassische Anlageformen wählen** (höchste steuerliche Effizienz, aber andere Strategie)

Die strategischen Alternativen Trading-GmbH und gewerbliche Einstufung sind in der Privatanleger-Realität meist Theorie.

Wer im System bleibt, sollte zumindest die korrekte Klassifizierung sicherstellen — falsche Topf-Zuordnungen führen Jahre später zu schmerzhaften BP-Korrekturen, oft mit Säumniszuschlägen. Genau dafür existiert [depottax.at](https://depottax.at).

---

*Disclaimer: Dieser Beitrag ist eine allgemeine Information zur aktuellen Rechtslage und ersetzt keine individuelle Steuerberatung. Konkrete Sachverhalte sollten mit einem österreichischen Steuerberater geklärt werden.*
