---
title: 'Wo Deine Depotdaten liegen — wie DepotTax technisch läuft'
seotitle: 'DepotTax: Server, Login, Datenschutz'
date: 2026-11-06
lastmod: 2026-11-06
description: 'Server in Frankfurt, Login ohne Passwort, getrennte Datenräume je Kunde, verschlüsselter Broker-Token, nichts an FinanzOnline: wie DepotTax mit Deinen Depotdaten umgeht und womit es läuft.'
keywords: ['DepotTax Datenschutz', 'DepotTax Server', 'IBKR FlexQuery Token sicher', 'Depotdaten Datenschutz Österreich', 'Steuertool Datenschutz', 'Hostinger Frankfurt']
tags: ['DepotTax', 'Datenschutz', 'Technik']
---

# Wo Deine Depotdaten liegen — wie DepotTax technisch läuft

> **Stand:** 2026-11-06 · **Lesezeit:** ~5 Minuten

Wer einem Steuertool seine Depotdaten gibt, gibt ziemlich viel her: jeden Kauf, jeden Verkauf, jede Dividende, oft über Jahre. Die Frage „Wo liegt das eigentlich, und wer kommt da ran?" ist deshalb berechtigt. Diese Seite beantwortet sie ohne Marketingsprache — was DepotTax tut, was es bewusst nicht tut, und womit es läuft.

Verbindlich ist die [Datenschutzerklärung](https://depottax.at/datenschutz). Hier steht dasselbe in Alltagssprache, dazu ein paar technische Hintergründe.

## 1. Der Server steht in Frankfurt

DepotTax läuft auf einem eigenen virtuellen Server bei **Hostinger**, Rechenzentrum **Frankfurt am Main**. Deine Steuer- und Trade-Daten liegen damit in der EU, und gerechnet wird auf genau diesem Server — es gibt keine Rechenstrecke irgendwo anders und keine Kopie bei einem Analysedienst.

Rund um den Server sind drei weitere Dienste beteiligt — jeder nur mit dem, was er für seine Aufgabe braucht:

| Dienst | Wofür | Was er bekommt |
|---|---|---|
| **Hostinger** | Server und Mailversand (office@depottax.at) | den Server selbst; Mails wie Login-Links und Laufhinweise |
| **Google** | Anmeldung mit dem Google-Konto | Deine E-Mail-Adresse und eine anonyme Kennung |
| **Cloudflare** | DNS, Auslieferung, Besucherstatistik | Verbindungsdaten; die Statistik ist cookiefrei und anonym |
| **Stripe** | Rechnung und Zahlung, wenn Du ein Steuerjahr kaufst | Name, Anschrift, gekaufte Jahre, Zahlungsdaten — **keine** Steuer- oder Trade-Daten |

Dieser Blog hier ist übrigens eine statische Seite auf GitHub Pages. Er kennt keine Kundendaten und hat auch keinen Zugang dazu.

## 2. Anmelden ohne Passwort

Bei DepotTax gibt es **kein Passwort**. Du meldest Dich entweder mit Deinem Google-Konto an oder lässt Dir einen Login-Link per Mail schicken, der 15 Minuten gilt.

Das ist keine Bequemlichkeit, sondern Absicht: Ein Passwort, das nicht existiert, kann nicht in einem Datenleck auftauchen, nicht erraten und nicht auf einer anderen Seite wiederverwendet werden. Die Sicherheit Deines Zugangs hängt damit an Deinem Mail- bzw. Google-Konto — das Du ohnehin schützen solltest, am besten mit zweitem Faktor.

## 3. Jeder Kunde hat einen eigenen Datenraum

In der Datenbank liegen die Daten aller Kunden, aber jede Zeile gehört genau einem Datenraum. Die Trennung prüft nicht nur die App, sondern die **Datenbank selbst** bei jeder Abfrage (PostgreSQL „Row-Level Security"). Selbst wenn in der App einmal eine Abfrage falsch formuliert wäre, gibt die Datenbank nur Zeilen des angemeldeten Kunden heraus.

Leben zwei Personen in einem Haushalt, etwa ein Ehepaar, können beide Steuersubjekte in einem gemeinsamen Datenraum liegen — getrennte Beilagen, getrennte Töpfe, aber eine gemeinsame Sicht.

## 4. Der Broker-Zugang kann nur lesen

Bei Interactive Brokers, CapTrader und den anderen IB-basierten Brokern holt DepotTax die Daten über die **FlexQuery** ab. Dafür trägst Du eine Query-ID und einen Token ein (auf der deutschen IB-Seite „Prüfcode").

- Der Token öffnet **nur den Abruf Deiner Flex-Berichte**. Handeln, Geld bewegen oder Einstellungen ändern kann man damit nicht — auch DepotTax nicht.
- Er liegt **AES-256-GCM-verschlüsselt** in der Datenbank. Ein Datenbank-Abzug allein reicht nicht, um ihn zu lesen.
- Du kannst ihn bei IB jederzeit neu erzeugen; der alte ist dann wertlos.

Wer keinen Token hinterlegen will, lädt die Dateien einfach selbst hoch. Hochgeladene Dateien werden nach dem Import gelöscht, nur die eingelesenen Buchungen bleiben.

## 5. Was DepotTax bewusst nicht tut

- **Nichts an FinanzOnline.** DepotTax rechnet die Kennzahlen für die Beilage E1kv aus, die Abgabe bleibt Dein Schritt. Warum ein „Upload-Knopf" hier eine Falle wäre, steht in [diesem Artikel](/posts/finanzonline-xml-upload-falle/).
- **Keine Werbe-Cookies, kein Tracking über Seiten hinweg.** Die Besucherstatistik zählt anonym, wie oft Seiten aufgerufen werden — nicht, wer.
- **Keine Kartendaten.** Beim Kauf gibst Du Karten- oder Kontodaten direkt bei Stripe ein; DepotTax sieht sie nie.
- **Keine Weitergabe** zu Werbe- oder Profiling-Zwecken.

## 6. Zwei Türen, die nur Du öffnest

Nach außen gehen Deine Auswertungen nur auf zwei Wegen, und beide sind ab Werk zu:

- **Freigabe-Link für die Kanzlei:** zeitlich begrenzt, nur lesend, jederzeit widerrufbar. Gedacht für Deinen Steuerberater.
- **KI-Schnittstelle (MCP):** Mit einem Token aus den Einstellungen kann ein KI-Assistent wie Claude Deine Auswertungen abfragen — nur lesend, ebenfalls jederzeit widerrufbar. Die abgefragten Daten gehen dann an den Anbieter des Assistenten; diese Entscheidung triffst Du.

## 7. Sicherungen

Die Datenbank wird täglich gesichert, die Sicherungen bleiben 14 Tage liegen. Zusätzlich sichert der Hoster den ganzen Server als Abbild. Ein verlorener Datenstand bei den Trades wäre ohnehin nachholbar — die FlexQuery liefert die Buchungen jederzeit neu.

Löschen kannst Du alles mit einer formlosen Nachricht an office@depottax.at. Ausgenommen sind nur Rechnungen, die wir sieben Jahre aufbewahren müssen.

## 8. Womit es läuft

Für die, die es genau wissen wollen:

- **Linux-Server** mit **Docker**; jeder Teil (Web-App, Datenbank, nächtlicher Abruf, Sicherung) in einem eigenen Container
- **Python** mit **Flask** für die Web-App, die Steuerlogik ebenfalls in Python
- **PostgreSQL** als Datenbank, mit Row-Level Security je Kunde
- **Traefik** als Eingangstor mit automatischen TLS-Zertifikaten — Verbindungen laufen nur verschlüsselt
- Der nächtliche Abruf holt neue Broker-Daten automatisch, rechnet die Steuer neu und schreibt Berichte und Formulare

Die Steuerregeln selbst — gleitender Durchschnittspreis, getrennte Töpfe, Fremdwährungsumrechnung, Meldefonds — sind der eigentliche Kern. Darum geht es in den [anderen Guides](/posts/).

<div style="border:1px solid #ccc; border-radius:6px; padding:12px 16px; margin:28px 0;">
<strong>Werbung:</strong> DepotTax läuft auf einem Server von Hostinger. Wenn Du selbst eine Website, einen Server oder ein Mailpostfach brauchst: Meldest Du Dich über
<a href="https://www.hostinger.com/de?REFERRALCODE=ODPMILOSIEUC" rel="sponsored nofollow noopener" target="_blank">diesen Partnerlink</a>
bei Hostinger an, erhält DepotTax dafür eine Provision. Mit DepotTax selbst hat das nichts zu tun — die Empfehlung ist freiwillig, und ob Du ihr folgst, ändert nichts an Deinem Zugang.
</div>

---

### Verwandte Guides

- [FinanzOnline-XML-Upload: die Falle beim „fertigen" XML](/posts/finanzonline-xml-upload-falle/)
- [Alle Guides](/posts/)

---

*Dieser Artikel beschreibt den technischen Stand bei Erscheinen. Verbindlich für die Verarbeitung Deiner Daten ist die [Datenschutzerklärung](https://depottax.at/datenschutz).*
