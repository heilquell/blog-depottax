---
title: 'CapTrader Steuererklärung Österreich'
date: 2026-10-19
lastmod: 2026-10-19
description: 'CapTrader führt keine österreichische KESt ab und stellt keine Steuerbescheinigung aus. Welche Unterlagen es gibt und was Du selbst erklären musst.'
keywords: ['CapTrader Steuererklärung', 'CapTrader Steuerbericht', 'CapTrader Steuer Österreich', 'CapTrader steuereinfach', 'CapTrader Quellensteuer', 'CapTrader Steuerbescheinigung', 'CapTrader E1kv']
tags: ['CapTrader', 'Steuererklärung', 'E1kv', 'Quellensteuer', 'Österreich', 'IBKR']
---

# CapTrader Steuererklärung Österreich

> **Stand:** 2026-10-19 · **Lesezeit:** ~8 Minuten · **Gilt für:** in Österreich unbeschränkt steuerpflichtige Privatpersonen mit einem CapTrader-Depot

Die meisten CapTrader-Kunden in Österreich suchen irgendwann nach dem **Steuerbericht** — jener Datei, die man dem Finanzamt hinlegt und die alles erklärt. Es gibt sie nicht. Es gibt einen Jahresdepotauszug, einen Dividendenbericht und, gegen Gebühr, eine Quellensteuerbescheinigung. Keines dieser Dokumente ist auf österreichisches Steuerrecht gemünzt, und eine Steuerbescheinigung stellt CapTrader ausdrücklich nicht aus.

Das ist kein Mangel des Brokers, sondern eine Folge der Konstruktion. Dieser Artikel erklärt die Konstruktion, sagt welche Unterlagen es tatsächlich gibt, und zeigt, was Du für die **Steuererklärung in Österreich** daraus machen musst.

## Die kurze Antwort

- **CapTrader ist nicht steuereinfach.** Es wird keine österreichische Kapitalertragsteuer einbehalten und nichts ans Finanzamt abgeführt.
- **Du erklärst selbst**, jedes Jahr, mit der Einkommensteuererklärung **E1 und der Beilage E1kv**.
- **Einen „Steuerbericht" im Sinn einer Steuerbescheinigung gibt es nicht** — nur Rohunterlagen.
- Die Steuerinfos auf der CapTrader-Website sind **für deutsche Kunden geschrieben**. Wer sie als Österreicher wörtlich nimmt, rechnet mit den falschen Sätzen.
- Für die Zahlen brauchst Du eine **FlexQuery**, nicht den Jahresdepotauszug als PDF.

## Warum das so ist: CapTrader ist ein Introducing Broker

CapTrader sitzt in Ratingen, hält aber selbst nichts. Auf der eigenen Website steht es deutlich:

> „CapTrader ist als Introducing Broker von Interactive Brokers tätig."
> „CapTrader führt keine Aufträge in Finanzinstrumenten aus, berät nicht zu Finanzinstrumenten und hält kein Kundenvermögen."

Und zur Verwahrung:

> „Da Ihr Depot bei Interactive Brokers Ltd. in Irland geführt wird, unterliegt es nicht dem deutschen Steuerrecht."

Dein Depot liegt also in Irland, auf derselben Infrastruktur wie ein IBKR-Direktkonto. CapTrader ist die deutschsprachige Oberfläche davor. Steuerlich heißt das: **was für IBKR gilt, gilt für CapTrader**, Zeile für Zeile. Dasselbe gilt für LYNX, Banx und Brokerport.

→ [IBKR direkt oder Reseller? Ein Trade-Kosten-Vergleich](/posts/broker-wechsel-trade-kosten/)
→ [LYNX Steuererklärung Österreich](/posts/lynx-steuererklaerung-oesterreich/)

## Ist CapTrader steuereinfach?

Nein. „Steuereinfach" heißt in Österreich, dass die depotführende Stelle die KESt einbehält und abführt, womit die Erträge endbesteuert sind. Das setzt eine **inländische** depotführende Stelle voraus (§ 95 EStG). Ein Depot in Irland ist keine.

CapTrader formuliert es selbst so:

> „CapTrader berechnet keine Kapitalertragssteuern und führt diese auch nicht ab."

Die Folge ist nicht, dass die Erträge steuerfrei wären — sie sind **noch nicht erklärt**. Dividenden, Zinsen, Kursgewinne, Optionsprämien: alles landet in Deiner Einkommensteuererklärung.

→ [„KESt-endbesteuert" — was das wirklich heißt](/posts/kest-endbesteuerung-ibkr/)

## Gibt es einen CapTrader-Steuerbericht?

Es gibt drei Unterlagen, und es ist wichtig zu wissen, was sie sind:

| Unterlage | Was drinsteht | Taugt als … |
|---|---|---|
| **Jahresdepotauszug** (Kontoverwaltung) | alle Transaktionen, Gewinne und Verluste, Gebühren, Dividenden | Rohmaterial, kein Ergebnis |
| **Dividendenbericht** (von IBKR, jährlich, unter „Performance & Berichte → Steuerdokumente") | Dividenden und die je Zahlung einbehaltene Quellensteuer | Beleg für KZ 998 |
| **Quellensteuerbescheinigung** (kostenpflichtig, Bearbeitung mindestens drei Wochen) | Nachweis über einbehaltene Steuern bei Kapitalmaßnahmen und Fondsausschüttungen | Einzelnachweis, wenn der Auszug nicht reicht |

Was es **nicht** gibt, sagt CapTrader selbst:

> „Eine Steuerbescheinigung gemäß dem deutschen Steuerrecht wird daher nicht ausgestellt."

Für Österreich steht dort gar nichts — die Steuerseiten von CapTrader erwähnen Österreich nicht ein einziges Mal. Sie erklären die deutsche Abgeltungsteuer, den Satz von 26,375 % auf deutsche Dividenden und die Verrechnung zum 31. Dezember. Nichts davon gilt für Dich.

> ⚠️ **Das ist die eigentliche Falle.** Nicht das fehlende Dokument, sondern die vorhandene Anleitung: Sie ist richtig — für deutsche Kunden. Wer als Österreicher danach vorgeht, nimmt die falschen Sätze, die falsche Verlustverrechnung und die falsche Kostenbasis.

## Warum der Jahresdepotauszug für die E1kv nicht reicht

Drei Gründe, und alle drei verändern die Steuerzahl:

1. **Die Kostenbasis.** In Österreich ist der **gleitende Durchschnittspreis** vorgeschrieben (§ 27a Abs 4 Z 3 EStG). Der Report rechnet FIFO. Wer mehrfach nachgekauft hat, bekommt eine andere Zahl.
2. **Die Spesen.** Anschaffungsnebenkosten dürfen bei Sondersatz-Einkünften **nicht** in die Kostenbasis (§ 27a Abs 4 Z 2 EStG) — in Deutschland schon. Ein nach deutscher Logik gerechneter Gewinn ist hier systematisch zu niedrig.
3. **Die Töpfe.** Welcher Ertrag in welche Kennzahl gehört, steht nirgends im Auszug. Nicht verbriefte Optionen und Futures fallen zum Beispiel nicht unter die 27,5 %, sondern unter den Tarif.

Deshalb brauchst Du statt des PDF eine **FlexQuery** mit den Feldern, die die Zuordnung überhaupt erst möglich machen. Sie funktioniert bei CapTrader identisch wie bei IBKR direkt.

→ [FlexQuery für die AT-Steuererklärung einrichten](/posts/ibkr-flexquery-einrichten/)
→ [KZ 863 vs KZ 994 — wo trage ich was ein?](/posts/kz-863-vs-kz-994/)
→ [Die drei Schichten der Optionen-Steuerfalle](/posts/optionen-steuerfalle-at-drei-schichten/)

## Quellensteuer bei CapTrader

Bei Dividenden wird sehr wohl etwas einbehalten — nur nicht von CapTrader, sondern im Quellenstaat. Österreich rechnet davon an, was das jeweilige Doppelbesteuerungsabkommen zulässt, in der Regel **15 %**. Was darüber hinausgeht, holst Du Dir im Quellenstaat zurück, nicht beim österreichischen Finanzamt.

Zwei Punkte, die speziell bei CapTrader auftauchen:

- **W-8BEN.** Ohne hinterlegtes Formular zieht die US-Seite 30 % statt 15 % ab. CapTrader fragt es bei der Kontoeröffnung ab; prüfen kannst Du es in der Kontoverwaltung unter den Steuerformularen.
- **Irische Zinsen.** Weil das Depot in Irland liegt, weist CapTrader darauf hin, dass auf irische Zinserträge Quellensteuer anfällt und Privatpersonen mit Wohnsitz in der EU eine Reduktion oder Rückforderung beantragen können.

→ [Quellensteuer bei IBKR: USA, Schweiz, UK](/posts/quellensteuer-ibkr-usa-schweiz-uk/)

## Was Du konkret tun musst

1. **FlexQuery einrichten** und die Rohdaten holen — nicht das Activity Statement als PDF.
2. **Erträge klassifizieren**: Dividenden, Zinsen, Aktiengewinne, verbriefte und nicht verbriefte Derivate, Fondserträge. Jede Gruppe hat ihre eigene Kennzahl und teils ihren eigenen Steuersatz.
3. **Von L1 auf E1 wechseln**, falls Du bisher die Arbeitnehmerveranlagung gemacht hast — die Beilage E1kv gibt es dort nicht. → [Der Erklärungswechsel in FinanzOnline](/posts/erklaerungswechsel-l1-auf-e1-finanzonline/)
4. **Kennzahlen von Hand eintragen.** Kein XML-Upload. → [Warum das „upload-fertige XML" gefährlicher ist, als es klingt](/posts/finanzonline-xml-upload-falle/)
5. **Belege behalten** — die Herleitung zählt, nicht die eingetragene Zahl.

Die Fristen sind Ende April, bei elektronischer Abgabe Ende Juni (§ 134 Abs 1 BAO). Für Arbeitnehmer wird die Erklärung ab **730 Euro** anderer Einkünfte zur Pflicht (§ 41 Abs 1 Z 1 EStG).

→ [Interactive Brokers Steuererklärung Österreich — der vollständige Überblick](/posts/interactive-brokers-steuererklaerung-oesterreich/)

## Wenn Du von oder zu CapTrader wechselst

Beim Wechsel zwischen Auslandsdepots ändert sich steuerlich wenig — beim Wechsel **aus dem Ausland auf eine österreichische Stelle** dagegen sehr viel: Du musst die Anschaffungskosten selbst melden, **innerhalb eines Monats**, nicht verlängerbar. Sonst gilt der Übertrag als Verkauf.

→ [Depot-Übertrag bei IBKR — muss ich das erklären?](/posts/depotuebertrag-ibkr-oesterreich/)
→ [Vom Erste-Bank-Depot zu IBKR](/posts/at-bank-zu-ibkr-depotuebertrag/)

---

> 🛠 **[DepotTax](https://depottax.at)** liest die CapTrader-FlexQuery genauso wie die von IBKR direkt und erzeugt daraus die E1kv-Kennzahlen, eine PDF-Beilage als Beleg und eine Excel-Auswertung je Trade — mit gleitendem Durchschnittspreis, getrennten § 27-Töpfen und Quellensteuer-Anrechnung bis zum DBA-Satz. Mehrere Konten nebeneinander, etwa das alte CapTrader-Depot neben einem neuen IBKR-Konto, werden zusammengerechnet.

Aktuell in geschlossener Beta. Wenn Du Interesse hast — melde Dich.

### Verwandte Guides

- [Interactive Brokers Steuererklärung Österreich](/posts/interactive-brokers-steuererklaerung-oesterreich/) — der Überblick über alle Ertragsarten, Kennzahlen und Fristen
- [IBKR direkt oder Reseller?](/posts/broker-wechsel-trade-kosten/) — was der Wechsel wirklich kostet, mit echten Zahlen
- [„KESt-endbesteuert" — was das wirklich heißt](/posts/kest-endbesteuerung-ibkr/) — warum bei keinem dieser Broker etwas abgegolten ist

### Quellen

- [CapTrader: Steuerinformationen für private Depots](https://www.captrader.com/steuern/steuerinformationen-fuer-private-depots/) — Jahresdepotauszug, Dividendenbericht, Quellensteuerbescheinigung, keine Steuerbescheinigung
- [CapTrader: Steuern](https://www.captrader.com/de/steuern/) — kein automatischer Steuerabzug, W-8BEN, irische Quellensteuer
- [CapTrader: Über uns](https://www.captrader.com/de/ueber-uns/) — Introducing Broker, kein Kundenvermögen
- [§ 95 EStG (RIS)](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10004570&Paragraf=95) — Abzugsverpflichteter
- [§ 27a EStG (RIS)](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10004570&Paragraf=27a) — gleitender Durchschnittspreis, Anschaffungsnebenkosten
- [§ 134 BAO (RIS)](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10003940&Paragraf=134) und [§ 41 EStG (RIS)](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10004570&Paragraf=41) — Fristen und Pflichtgrenze

*Dieser Artikel ist keine Steuerberatung, sondern eine Aufbereitung öffentlich zugänglicher Quellen, Stand 19.10.2026. Die zitierten CapTrader-Angaben können sich ändern — prüf sie vor dem Einreichen in der Kontoverwaltung nach.*
