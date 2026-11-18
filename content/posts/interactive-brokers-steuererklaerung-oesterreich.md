---
title: 'Interactive Brokers in Österreich: Steuererklärung, E1kv und Tax Reports'
seotitle: 'Interactive Brokers Österreich: Steuererklärung und E1kv'
date: 2026-10-19
lastmod: 2026-11-18
description: 'Interactive Brokers in Österreich: Was Du selbst erklären musst, warum die Tax Reports von IBKR nicht reichen, welche Kennzahlen der E1kv betroffen sind und wie Du von der FlexQuery zur Steuererklärung kommst.'
keywords: ['Interactive Brokers Österreich', 'Interactive Brokers Steuererklärung Österreich', 'IBKR Tax Reporting Österreich', 'Interactive Brokers Tax Report', 'Interactive Brokers Österreich Steuer', 'IBKR Steuererklärung', 'Interactive Brokers Kapitalertragsteuer', 'IBKR E1kv', 'Interactive Brokers Steuererklärung Anleitung']
tags: ['Interactive Brokers', 'IBKR', 'Steuererklärung', 'E1kv', 'Österreich', 'Überblick']
---

# Interactive Brokers in Österreich: Steuererklärung, E1kv und Tax Reports

> **Stand:** 2026-11-18 · **Lesezeit:** ~10 Minuten · **Gilt für:** in Österreich unbeschränkt steuerpflichtige Privatpersonen mit einem Depot bei Interactive Brokers oder einem IBKR-Reseller

Wer als Österreicher bei **Interactive Brokers** handelt, bekommt am Jahresende keine Steuerbescheinigung, mit der das Finanzamt etwas anfangen kann, und es wurde auch keine Kapitalertragsteuer abgezogen. Die **Steuererklärung** für das IBKR-Depot machst Du selbst — vollständig, von Hand, in einem Formular, das Du in der Arbeitnehmerveranlagung nicht einmal zu sehen bekommst.

Diese Seite ist die Übersicht dazu: was erklärt werden muss, wo es hingehört, in welcher Reihenfolge Du vorgehst und welche fünf Fehler in der Praxis am teuersten sind. Für jeden Punkt steht darunter ein eigener Artikel mit den Details.

## Die kurze Antwort

- **Interactive Brokers zieht keine österreichische KESt ab.** Es gibt keine Endbesteuerung, nichts ist „automatisch erledigt".
- Du brauchst die **Einkommensteuererklärung E1 mit der Beilage E1kv**. In der Arbeitnehmerveranlagung (L1) existiert die Beilage nicht.
- **Frist:** Ende April des Folgejahres, bei elektronischer Übermittlung über FinanzOnline Ende Juni (§ 134 Abs 1 BAO).
- **Pflicht wird es** für Arbeitnehmer, wenn die anderen Einkünfte zusammen **730 Euro übersteigen** (§ 41 Abs 1 Z 1 EStG).
- Die Zahlen holst Du aus einer **FlexQuery**, nicht aus dem Activity Statement als PDF.

## Warum bei Interactive Brokers nichts abgezogen wird

Die Endbesteuerung mit 27,5 % ist in Österreich an die **inländische depotführende Stelle** gebunden. Interactive Brokers ist keine, also greift sie nicht — unabhängig davon, wie „ordentlich" der Broker sonst arbeitet. Was Du dort an Dividenden, Zinsen und Kursgewinnen erzielst, ist nicht steuerfrei und nicht abgegolten, sondern **noch nicht erklärt**.

Das gilt genauso für die Reseller, die auf der IBKR-Infrastruktur aufsitzen: **CapTrader, LYNX, Banx, Brokerport**. Dieselbe Abwicklung, dieselben Reports, dieselbe steuerliche Lage — ein Steuerbericht vom Reseller ersetzt die Erklärung nicht.

→ [„KESt-endbesteuert" — was das wirklich heißt und warum es bei IBKR nicht greift](/posts/kest-endbesteuerung-ibkr/)
→ [IBKR direkt oder Reseller? Ein Trade-Kosten-Vergleich](/posts/broker-wechsel-trade-kosten/)
→ [CapTrader Steuererklärung Österreich](/posts/captrader-steuererklaerung-oesterreich/)
→ [LYNX Steuererklärung Österreich](/posts/lynx-steuererklaerung-oesterreich/)

## Und die Tax Reports von Interactive Brokers?

Interactive Brokers stellt seine Steuerunterlagen im Client Portal unter **Performance & Reports → Tax Documents** bereit. Dort liegen die US-Formulare wie das 1099 und, je nach gewählter Jurisdiktion, sogenannte **Informational Tax Reports** für einzelne Länder, etwa für Deutschland ab dem Steuerjahr 2019. Den deutschen Bericht veröffentlicht IBKR laut eigener Angabe meist ab Ende des Sommers des Folgejahres, also erst nach der Frist für die elektronische Erklärung Ende Juni.

Für die österreichische Steuererklärung hilft das wenig:

- Ein Bericht, der die **Kennzahlen der Beilage E1kv** ausweist, ist uns dort nicht bekannt. Welche Jurisdiktionen Dein Konto anbietet, siehst Du über das Zahnrad neben „Jurisdictions".
- Der **deutsche Bericht** rechnet nach deutschen Regeln. Kostenbasis, Spesen und Verlustverrechnung weichen von den österreichischen ab, die Zahlen lassen sich nicht einfach übernehmen. → [Warum deutsche Steuerbescheinigungen in Österreich kaum taugen](/posts/deutsche-steuerbescheinigung-oesterreich-untauglich/)
- Die realisierten Gewinne im **Activity Statement** folgen der Lot-Zuordnung des Kontos, standardmäßig FIFO. Österreich verlangt den gleitenden Durchschnittspreis (siehe Fehler 2 weiter unten).

Brauchbar sind die Tax Documents trotzdem als Gegenprobe, etwa für die einbehaltene Quellensteuer je Land. Die Grundlage für die E1kv bleibt die FlexQuery.

## Was Du melden musst

Die Beilage E1kv ist **ein** Formular mit mehreren Kennzahlen. Die Zuordnung entscheidet über den Steuersatz, und sie ist nicht immer die, die der Buchungstext vermuten lässt:

| Was Du bei IBKR hast | Gehört in | Detail |
|---|---|---|
| Dividenden, Payment In Lieu, Anleihekupons | KZ 863 | [KZ 863 vs KZ 994](/posts/kz-863-vs-kz-994/) |
| Verzinsung des Cash-Bestands | KZ 861 **oder** 863 — eine echte Entscheidung | [KZ 863 vs KZ 994](/posts/kz-863-vs-kz-994/) |
| Realisierte Gewinne und Verluste aus Aktien | KZ 994 / 892 | [KZ 863 vs KZ 994](/posts/kz-863-vs-kz-994/) |
| Verbriefte Derivate, Zertifikate, Turbos | KZ 995 / 896 | [Gold- und Silber-ETC](/posts/gold-silber-etc-kz-995-oesterreich/) |
| Nicht verbriefte Optionen und Futures | **Tarif** statt 27,5 % | [Die drei Schichten der Optionen-Steuerfalle](/posts/optionen-steuerfalle-at-drei-schichten/) |
| Ausschüttungsgleiche Erträge thesaurierender Fonds | KZ 937 | [KZ 937 / OeKB](/posts/kz-937-oekb-ausschuettungsgleich/) |
| Ausländische Quellensteuer | KZ 998, nur bis zum DBA-Satz | [Quellensteuer USA, Schweiz, UK](/posts/quellensteuer-ibkr-usa-schweiz-uk/) |
| Spot-Forex-Gewinne | Graubereich § 27 oder § 31 | [Forex bei IBKR](/posts/forex-besteuerung-ibkr-oesterreich/) |

Der folgenschwerste Posten in dieser Tabelle ist die fünfte Zeile. Nicht verbriefte Optionen und Futures fallen nicht unter den Sondersatz, sondern unter den **Tarif** — bis zu 55 %. Dafür darfst Du in diesem Topf als einzigem Werbungskosten abziehen, also Datenfeed, Börsengebühren und Kommissionen.

→ [Werbungskosten bei Optionen](/posts/werbungskosten-optionen-z7-oesterreich/)
→ [IBKR-Aktien-Optionen: KZ 995 oder KZ 857?](/posts/ibkr-optionen-kz-995-oder-kz-857/)

## Der Weg in fünf Schritten

**1. FlexQuery einrichten.** Das PDF-Activity-Statement reicht nicht, weil es die Felder nicht enthält, die Du für die Zuordnung brauchst. Du brauchst eine Activity Flex Query mit den richtigen Sektionen — insbesondere mit **Executions**, sonst bleibt die Trades-Sektion leer.
→ [IBKR FlexQuery für die AT-Steuererklärung einrichten](/posts/ibkr-flexquery-einrichten/)

**2. Erträge klassifizieren.** Hier entsteht der größte Teil der Fehler. Ein „Dividend" kann eine Einlagenrückzahlung sein, ein ETC ist kein Fonds, und ein thesaurierender Fonds erzeugt auch ohne Ausschüttung steuerpflichtige Erträge.
→ [E1kv ausfüllen für IBKR-User](/posts/e1kv-ausfuellen-ibkr/)

**3. Von L1 auf E1 wechseln.** Die Beilage E1kv gibt es in der Arbeitnehmerveranlagung nicht. In FinanzOnline heißt der Vorgang Erklärungswechsel, und er ist kein Nebenschritt, sondern Voraussetzung.
→ [Von L1 auf E1: der Erklärungswechsel in FinanzOnline](/posts/erklaerungswechsel-l1-auf-e1-finanzonline/)

**4. Kennzahlen eintragen — von Hand.** Lass Dich nicht von „upload-fertigen XMLs" verleiten. Der Erklärungs-Upload in FinanzOnline reicht sofort die **komplette** Einkommensteuererklärung ein; alles, was im XML fehlt, gilt als leer, und die elektronische Berichtigung ist danach gesperrt.
→ [„Upload-fertiges FinanzOnline-XML" — warum das gefährlicher ist, als es klingt](/posts/finanzonline-xml-upload-falle/)

**5. Belege aufbewahren.** Nicht die eingetragene Zahl ist der Beleg, sondern die Herleitung: Trade-Liste, Durchschnittskosten je Position, Umrechnungskurse. Wenn eine Rückfrage kommt, kommt sie zu einer einzelnen Position.

## Die fünf Fehler, die am meisten kosten

**1. Die deutsche Steuerbescheinigung verwenden.** Wer neben IBKR ein Depot bei einem deutschen Broker hat, bekommt dort eine Bescheinigung, die für Österreich fast wertlos ist: andere Verrechnungsregeln, andere Kostenbasis, deutsche Abgeltungsteuer, die hier nur bis zum DBA-Satz anrechenbar ist.
→ [Die Steuerbescheinigung Deines deutschen Brokers](/posts/deutsche-steuerbescheinigung-oesterreich-untauglich/)

**2. FIFO rechnen.** In Österreich ist der **gleitende Durchschnittspreis** vorgeschrieben (§ 27a Abs 4 Z 3 EStG). Wer die FIFO-Zahlen aus dem IBKR-Report übernimmt, rechnet mit der falschen Kostenbasis — bei mehrfach nachgekauften Positionen weicht das Ergebnis deutlich ab.

**3. Spesen in die Kostenbasis nehmen.** Anschaffungsnebenkosten dürfen bei Kapitalvermögen im Sondersatz **nicht** angesetzt werden (§ 27a Abs 4 Z 2 EStG). Das ist einer der Punkte, an denen Österreich und Deutschland auseinandergehen — ein deutscher Rechenweg produziert hier systematisch falsche Zahlen.

**4. Quellensteuer in voller Höhe anrechnen.** Angerechnet wird nur, was das jeweilige Doppelbesteuerungsabkommen zulässt. Was der Quellenstaat darüber hinaus behalten hat, holst Du dort zurück — nicht beim österreichischen Finanzamt.
→ [Quellensteuer bei IBKR: USA, Schweiz, UK](/posts/quellensteuer-ibkr-usa-schweiz-uk/)

**5. Die Monatsfrist beim Depotübertrag verpassen.** Kommt ein Depot aus dem Ausland auf eine inländische Stelle, musst **Du** die Anschaffungskosten melden, innerhalb eines Monats, nicht verlängerbar. Sonst gilt der Übertrag als Verkauf. Das trifft gerade zwei größere Nutzergruppen.
→ [Scalable Capital ist jetzt steuereinfach — und der Wechsel ist meldepflichtig](/posts/scalable-capital-steuereinfach-oesterreich-meldepflicht/)
→ [Trading 212 zieht Österreicher nach Deutschland um](/posts/trading212-oesterreich-depotuebertrag-deutschland/)
→ [Depot-Übertrag bei IBKR — muss ich das erklären?](/posts/depotuebertrag-ibkr-oesterreich/)

## Fristen und Pflichtgrenzen

| | Regel | Fundstelle |
|---|---|---|
| Abgabefrist Papier | Ende April des Folgejahres | § 134 Abs 1 BAO |
| Abgabefrist elektronisch | Ende Juni des Folgejahres | § 134 Abs 1 BAO |
| Pflicht zur Veranlagung (Arbeitnehmer) | andere Einkünfte über **730 Euro** | § 41 Abs 1 Z 1 EStG |
| Meldung Anschaffungskosten bei Depotübertrag aus dem Ausland | **ein Monat**, nicht verlängerbar | § 27 Abs 6 Z 2 EStG |

Wer von einer Steuerberatung vertreten wird, fällt unter deren Quotenregelung und hat längere Fristen. Das ist eine Frage an die Kanzlei, nicht an FinanzOnline.

## Sonderfälle, die oft dazukommen

- **Ein FFB-Konto neben IBKR.** Inländische Stelle, also teils endbesteuert — die beiden Depots werden nicht gleich behandelt. → [FFB-Konto neben IBKR](/posts/ffb-konto-steuererklaerung-oesterreich/)
- **Ein Depot bei einer österreichischen Bank, das zu IBKR wandert.** Was Du dabei steuerlich verlierst, ist mehr als die KESt-Automatik. → [Vom Erste-Bank-Depot zu IBKR](/posts/at-bank-zu-ibkr-depotuebertrag/)
- **Gold- und Silber-ETC.** Keine Aktien, keine Fonds, sondern besicherte Schuldverschreibungen. → [KZ 995/896 statt 994/892](/posts/gold-silber-etc-kz-995-oesterreich/)

---

> 🛠 **[DepotTax](https://depottax.at)** liest Deine IBKR- oder CapTrader-FlexQuery und erzeugt die E1kv-Kennzahlen, eine PDF-Beilage als Beleg und eine Excel-Auswertung je Trade — mit gleitendem Durchschnittspreis, getrennten § 27-Töpfen und DBA-Cap je Quellenland.

DepotTax gibt es ab 99 € je Steuerjahr, zurückliegende Jahre ab 29 € — alle Tarife auf der [Preisseite](https://depottax.at/preise).

### Quellen

- [§ 134 BAO (RIS)](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10003940&Paragraf=134) — Abgabefristen
- [§ 41 EStG (RIS)](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10004570&Paragraf=41) — Pflichtveranlagung, 730-Euro-Grenze
- [§ 27a EStG (RIS)](https://www.ris.bka.gv.at/NormDokument.wxe?Abfrage=Bundesnormen&Gesetzesnummer=10004570&Paragraf=27a) — Sondersatz, gleitender Durchschnittspreis, Anschaffungsnebenkosten
- [Formulare des Bundesministeriums für Finanzen](https://service.bmf.gv.at/service/anwend/formulare)
- [Interactive Brokers: German tax report FAQ](https://www.interactivebrokers.com/support/faq/content/german-tax-report-faq-1152810164) — Tax Documents, Jurisdictions, Veröffentlichungszeitpunkt
- [Interactive Brokers: Tax Management Tools and Reporting](https://www.interactivebrokers.com/en/support/tax-management-and-reporting.php)

*Dieser Artikel ist keine Steuerberatung, sondern eine Aufbereitung öffentlich zugänglicher Quellen. Für Deinen konkreten Fall — besonders bei Optionen, Fonds ohne OeKB-Meldung und Depotüberträgen — klär die Zuordnung mit Deiner Steuerberatung ab.*
