---
title: 'IBKR-Aktien-Optionen: KZ 995 mit 27,5 % oder KZ 857 mit Tarif? Was die Literatur tatsächlich sagt'
date: 2026-06-16
lastmod: 2026-06-16
description: 'Börsennotierte Aktien-Optionen bei IBKR, CapTrader, LYNX, BANX — viele Berater tragen sie ins KZ 995 (27,5 %). Die herrschende Lehre und der VwGH sehen das anders: § 27a Abs 2 Z 7 EStG → KZ 857 mit progressivem Tarif. Was bedeutet das praktisch, wie groß ist die Differenz, und wann lohnt eine BMF-Vorabanfrage?'
keywords: ['IBKR Optionen Steuer Österreich', 'KZ 995 Optionen', 'KZ 857 Optionen', 'verbriefte Derivate', 'nicht verbriefte Derivate', '§ 27a Abs 2 Z 7 EStG', 'CapTrader Optionen Steuer', 'LYNX Optionen E1kv', 'Sondersteuersatz 27,5 %', 'progressiver Tarif Derivate']
tags: ['Optionen', 'IBKR', 'CapTrader', 'LYNX', 'E1kv', 'KZ 995', 'KZ 857', '§ 27a EStG', 'Österreich']
---

# IBKR-Aktien-Optionen: KZ 995 mit 27,5 % oder KZ 857 mit Tarif?

> **Stand:** 2026-06-16 · **Lesezeit:** ~8 Minuten · **Gilt für:** AT-Privatpersonen, die bei IBKR, CapTrader, LYNX, BANX oder Brokerport Aktien- oder Index-Optionen handeln

Die häufigste Auskunft, die Du in Foren und von einzelnen Steuerberatern bekommst: *„Börsennotierte Optionen sind doch wie verbrieft — also KZ 995, 27,5 % Sondersteuersatz."* Klingt logisch, fühlt sich richtig an, ist aber eine **Minderheitsposition ohne Rückhalt im Gesetzestext und ohne expliziten BMF-Erlass**.

Wir haben uns für unser Tool [depottax.at](https://depottax.at) die Frage stellen müssen: welche Default-Klassifizierung setzen wir an? Und dabei festgestellt, dass die literarische Lage **deutlich klarer ist, als sie in der Beraterpraxis oft dargestellt wird** — nur leider in die andere Richtung.

Dieser Artikel ist die ehrliche Zusammenfassung. Inklusive Quellen, damit Du es selbst nachlesen kannst.

## Worum es geht — drei Sätze

1. Realisierte Gewinne aus **verbrieften** Derivaten (Zertifikate, Optionsscheine mit ISIN auf einen wertpapierähnlichen Träger) landen in **KZ 995**, Verluste in **KZ 896** — beide mit **27,5 % Sondersteuersatz**.
2. Realisierte Gewinne UND Verluste aus **nicht-verbrieften** Derivaten (klassische Aktien-Optionen über CBOE, OCC, Eurex etc.) landen als **Saldo in KZ 857** — mit **progressivem Tarif bis 50 %** (55 % bei Einkommen ≥ 1 Mio. EUR).
3. **§ 27a Abs 2 Z 7 EStG** schließt nicht-verbriefte Derivate vom Sondersteuersatz aus, **§ 27 Abs 8 Z 3 EStG** verbietet zusätzlich den Verlustausgleich mit den 27,5 %-Töpfen. Der KZ-857-Topf ist also nach beiden Seiten isoliert.

Die ganze Diskussion dreht sich darum, ob eine **börsengehandelte Standard-Aktien-Option mit ISIN** als „verbrieft" gilt — oder nicht.

## Was „verbrieft" rechtlich heißt

Der Begriff stammt aus dem **KMG (Kapitalmarktgesetz)** und der **MiFID-II-Definition**: ein Wertpapier ist eine **handelbare Urkunde, die ein vermögenswertes Recht verkörpert**. Bei Zertifikaten und Optionsscheinen wird dieses Recht in einem **Globalzertifikat** (heute meist papierlos, sammelverwahrt bei OeKB/Clearstream) urkundlich verkörpert.

Bei einer klassischen **Aktien-Option am US-Markt** — sagen wir, ein AAPL Jan-2027 200 Call — verhält es sich anders:

- Es gibt **kein Globalzertifikat** und keine Urkunde.
- Der OCC (Options Clearing Corporation) führt einen Buchhaltungseintrag, dass Du Long-Position hast.
- Der „Träger" der Option ist ein **standardisierter Vertrag** (das OCC Options Disclosure Document), keine Urkunde.
- Eine ISIN existiert nur, weil OPRA die Symbole standardisiert hat — sie ist **kein Beweis für Verbriefung** im Sinne des KMG.

Eurex-Optionen funktionieren analog: der Clearing-Eintrag bei der Eurex Clearing AG ersetzt jede Urkunde.

Das ist der wesentliche Punkt: **„börsengehandelt" und „verbrieft" sind nicht dasselbe.** Forex-Spots, Futures und CFDs sind ebenfalls börsengehandelt (zumindest Futures), gelten aber unstrittig als nicht-verbrieft.

## Was die Literatur sagt

Wir haben uns durch die zugänglichen Standardquellen gearbeitet. Die Ergebnisse:

| Quelle | Aussage zur Behandlung börsennotierter Aktien-Optionen |
|---|---|
| **KPMG Tax News 06/2022** ([Link](https://kpmg.com/at/de/media/newsletter/tax-news/2022/06/tn-anwendung-des-besonderen-steuersatzes-auch-fuer-im-ausland-abgewickelte-einkuenfte-aus-nicht-verbrieften-derivaten.html)) | Nicht-verbriefte Derivate → progressiver Tarif. Kein Carve-Out für börsengehandelte Optionen. |
| **LeitnerLeitner Newsroom** ([Link](https://www.leitnerleitner.com/news/sondersteuersatz-unverbriefte-derivate/)) | Bestätigt § 27a Abs 2 Z 7 EStG strikt. Sondersteuersatz nur bei tatsächlicher Verbriefung. |
| **VwGH 8.3.2022, Ro 2019/15/0184** ([Link](https://www.vwgh.gv.at/rechtsprechung/aktuelle_entscheidungen/2022/ro_2019150184.html)) | Sondersteuersatz auch ohne KESt-Abzug möglich — **aber nur bei verbrieften Derivaten**. |
| **steuerverein.at, § 27 EStG Teil 6** ([Link](https://www.steuerverein.at/20-einkuenfte-aus-kapitalvermoegen-%C2%A7-27-estg-1988-teil-6/)) | „Verbrieft" ist Voraussetzung für 27,5 %. Klärt nicht, dass Börsenhandel = verbrieft. |
| **broker-test.at, Steuer-Diskussion** ([Link](https://www.broker-test.at/steuern/comment-page-5/)) | In den Kommentaren zitiert ein Leser einen StB mit „27,5 % auf Aktien-Optionen". Der Site-Autor widerspricht und verweist auf § 27a Abs 2 Z 7 EStG. |
| **BMF Findok** (Erlass-Volltextsuche) | Keine Fundstelle, in der das BMF die „wie verbrieft"-Lesart für börsengehandelte Optionen bestätigt. |

**Fazit der Recherche:** die Literatur folgt überwiegend dem **strengen § 27a Abs 2 Z 7-Wortlaut** — KZ 857, Tarif. Die „wie verbrieft"-Position ist ein pragmatischer Beratungs-Reflex einzelner Steuerberater, **nicht** die herrschende Lehre.

## Praxis vs. Recht — warum trotzdem viele 27,5 % ansetzen

Wir wollen das nicht verschweigen: es gibt **stillschweigende Toleranz** in der Praxis, vor allem bei kleineren Volumina. Die Finanzämter prüfen E1kv-Beilagen mit Options-Gewinnen unter ~5.000 EUR pro Jahr in der Regel nicht aktiv. Wer dort KZ 995 ansetzt, hört oft nichts zurück.

Daraus folgt aber **nicht**, dass die Klassifizierung rechtlich richtig ist. Folgendes Risiko trägst Du als Steuerpflichtiger:

- Bei einer **Betriebsprüfung** (auch privat möglich nach § 99 BAO) kann das Finanzamt die Umklassifizierung **fünf Jahre rückwirkend** durchziehen.
- Die Differenz wird verzinst (§ 205 BAO, derzeit ~5 % p. a.).
- Bei **Vorsatz** drohen Strafzuschläge nach § 33 FinStrG — relevant, wenn die Klassifizierung „erkennbar unvertretbar" war.

Bei einem Volumen von 50.000 EUR Options-Gewinnen pro Jahr und 5 Jahren Rückwirkung kommen schnell **50.000–70.000 EUR Nachzahlung + Zinsen** zusammen.

## Beispielrechnung — wie groß ist die Differenz?

Nehmen wir eine realistische Jahres-Bilanz eines AT-IBKR-Optionstraders mit Vollzeitjob:

- Bruttogehalt: **70.000 EUR** (Grenzsteuersatz 48 %)
- Aktien-Optionen-Saldo: **+20.000 EUR** (alle Trades zusammengezählt)

| Variante | KZ | Steuersatz | Steuer auf 20.000 EUR |
|---|---|---|---|
| **„Wie verbrieft"** (Praxis A) | 995 | 27,5 % | **5.500 EUR** |
| **§ 27a Abs 2 Z 7 strikt** (Praxis B) | 857 Saldo | progressiv (48 %) | **9.600 EUR** |
| **Differenz** | | | **4.100 EUR** |

Bei einem **Saldo-Verlust** wird es noch interessanter:

- Aktien-Gewinne 2025: +30.000 EUR
- Options-Saldo 2025: **−15.000 EUR**

| Variante | Was darf saldiert werden? | Zu versteuern |
|---|---|---|
| **„Wie verbrieft"** (KZ 995/896) | Verluste KZ 896 mit Gewinnen KZ 994/995 verrechenbar | 15.000 EUR × 27,5 % = **4.125 EUR** |
| **§ 27a Abs 2 Z 7 strikt** (KZ 857) | Tarif-Topf isoliert, **kein** Ausgleich mit Aktien-Gewinnen (§ 27 Abs 8 Z 3 EStG) | 30.000 × 27,5 % = **8.250 EUR**, Options-Verlust geht verloren |

**Der zweite Fall ist der wirklich bittere.** Wer Aktien-Gewinne und Options-Verluste hat, verliert beim strengen § 27a-Ansatz den Verlustausgleich — was die echte ökonomische Belastung deutlich erhöht.

Genau das ist auch der Hauptgrund, warum viele Trader die „wie verbrieft"-Position lieber annehmen: **strukturell sind sie in Verlustjahren benachteiligt**, ohne dass ihnen das ökonomisch fair vorkommt.

## Wie der Tool-Default entstanden ist

Wir haben [depottax.at](https://depottax.at) zunächst mit Default-Setting `verbrieft` ausgeliefert — weil das die Antwort ist, die die meisten Beta-User „erwarten" und weil die laufende Praxis es so handhabt. Pro Person ist das Setting in den Einstellungen unter **Personen → Bearbeiten → Optionsklassifizierung** umstellbar.

Nach der Recherche zu diesem Artikel **stellen wir die Beschreibung um**:

- **Setting `verbrieft` (27,5 %):** „Minderheitsposition einzelner Berater. Rechtlich umstritten. Pragmatisches Risiko bei BP."
- **Setting `tarif` (Tarif):** „Strenge Auslegung gemäß § 27a Abs 2 Z 7 EStG, gestützt durch KPMG/LeitnerLeitner/VwGH. Konservativ und rechtssicher."

Welches Setting für Dich passt, ist eine **Entscheidung mit Steuerberater** — wir wollen Dir die Wahl nicht abnehmen, aber wir wollen sie ehrlich darstellen.

## Wann eine BMF-Vorabanfrage Sinn macht

Wenn Dein jährliches Options-Volumen (Gewinn-Saldo, nicht Umsatz) **dauerhaft über 30.000 EUR** liegt, ist eine **schriftliche Anfrage beim BMF nach § 118 BAO** die saubere Lösung. Kosten: ab 1.500 EUR Verwaltungsgebühr, Bearbeitungszeit ~4–6 Monate, Bindungswirkung 5 Jahre.

Die Anfrage stellst Du am besten **über einen Steuerberater**, weil das Antragsformular präzise auf Deine konkrete Sachverhalts-Konstellation eingehen muss. Was Du bekommst, ist ein **schriftlicher BMF-Bescheid**, der Dich gegen jede spätere Umklassifizierung absichert.

Bei Volumen darunter ist das Verhältnis Aufwand/Nutzen meist nicht gegeben.

## Was Du jetzt konkret tun solltest

1. **Schau Dir Deinen Options-Saldo der letzten 2 Jahre an.** Bei IBKR im Activity Statement unter „Realized & Unrealized Performance" → Options.
2. **Bestimme Dein persönliches Risiko-Profil:** rechtssicher (KZ 857, Tarif) vs. praxis-konform (KZ 995, 27,5 %).
3. **Bei größeren Volumina:** Konsultiere einen **AT-IBKR-erfahrenen Steuerberater**. Nicht jeder StB ist mit IBKR-Spezifika vertraut.
4. **Konsistenz über die Jahre:** wenn Du einmal eine Variante gewählt hast, bleibe dabei — Wechsel ohne Anlass sind ein Prüfungs-Trigger.

## Verwandte Artikel

- [„KESt-endbesteuert" — was das wirklich heißt](/posts/kest-endbesteuerung-ibkr/) — Voraussetzung dafür, dass Du überhaupt in der E1kv-Klemme landest.
- [E1kv ausfüllen für IBKR-Trader](/posts/e1kv-ausfuellen-ibkr/) — Schritt-für-Schritt-Anleitung der ganzen Beilage.
- [KZ 863 vs KZ 994 — wo trage ich was ein?](/posts/kz-863-vs-kz-994/) — Entscheidungstabelle für alle anderen IBKR-Posten.

## Tool-Hinweis {#tool}

Auf [depottax.at](https://depottax.at) klassifizieren wir Deine Trades automatisch — mit umschaltbarem `verbrieft`/`tarif`-Default pro Person. KZ-Summen, Verlustausgleichs-Logik nach § 27 Abs 8 EStG und PDF-Beilage werden direkt aus Deinen IBKR-FlexQuery-Daten generiert. Du musst nur die Klassifizierungs-Entscheidung treffen — den Rest macht das Tool.

---

> **Disclaimer:** Dieser Artikel ist eine fundierte Recherche, **aber keine Steuerberatung**. Die Klassifizierung Deiner konkreten Options-Trades hängt von Deinem Gesamtbild ab. Bei Volumina über ~10.000 EUR Jahres-Saldo solltest Du den Sachverhalt mit einem AT-IBKR-erfahrenen Steuerberater besprechen.
