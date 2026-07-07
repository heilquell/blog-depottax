---
title: '„Upload-fertiges FinanzOnline-XML" — warum dieses Feature gefährlicher ist, als es klingt'
date: 2026-07-07
lastmod: 2026-07-07
description: 'Einige Steuertools werben damit, ein fertiges XML für den FinanzOnline-Upload zu erzeugen. Was dabei verschwiegen wird: Der Erklärungs-Upload reicht sofort die KOMPLETTE Einkommensteuererklärung ein — alles, was nicht im XML steht, gilt als leer, und die elektronische Berichtigung ist danach gesperrt. Wir haben das selbst erlebt. Hier ist, was wirklich passiert, und wie Du es sicher machst.'
keywords: ['FinanzOnline XML Upload', 'E1kv XML einreichen', 'Erklärungs-Upload FinanzOnline', 'FinanzOnline Testübermittlung', 'E1 versehentlich eingereicht', 'Steuererklärung XML Österreich', 'E1kv Upload Gefahr']
tags: ['FinanzOnline', 'E1kv', 'E1', 'XML-Upload', 'Österreich', 'Praxisbericht']
---

# „Upload-fertiges FinanzOnline-XML" — warum dieses Feature gefährlicher ist, als es klingt

> **Stand:** 2026-07-07 · **Lesezeit:** ~7 Minuten · **Gilt für:** AT-Privatpersonen, die ihre Steuererklärung (E1 + Beilage E1kv) selbst über FinanzOnline abgeben

Es klingt nach dem perfekten Feature: Dein Steuertool rechnet Deine Kapitalerträge aus und erzeugt daraus ein **fertiges XML, das Du nur noch in FinanzOnline hochladen musst**. Kein Abtippen von Kennzahlen, kein Vertippen, ein Klick — fertig.

Wir hätten dieses Feature längst bauen können. Das Schema ist öffentlich, unsere Kennzahlen sind dieselben, die im PDF- und Excel-Report stehen, und ein schema-valides E1kv-XML hatten wir in einem Nachmittag erzeugt.

Wir bieten es trotzdem **bewusst nicht** an. Der Grund ist keine technische Hürde, sondern eine Eigenschaft von FinanzOnline, die in keiner Werbung für „upload-fertige XMLs" vorkommt — und die wir aus eigener, unangenehmer Erfahrung kennen.

## Was der XML-Upload in FinanzOnline wirklich ist

Zuerst das Missverständnis, das dem Feature seinen harmlosen Anstrich gibt: Man könnte glauben, man lädt „die Beilage E1kv" hoch — so wie man ein PDF an eine E-Mail hängt — und füllt den Rest der Erklärung später aus.

So funktioniert es nicht.

Der FinanzOnline-Erklärungs-Upload ist ein **Jahreserklärungs-Datenstrom**. Das XML, das dort hineingeht, ist strukturell immer die **gesamte Einkommensteuererklärung E1** — die Kapitaleinkünfte (E1kv) sind darin nur ein optionaler Block unter mehreren:

```
ERKLAERUNGS_UEBERMITTLUNG
└── JAHRESERKLAERUNG (art="JAHR_ERKL")
    └── ERKLAERUNG (art="E1")          ← die GANZE E1, nicht eine Beilage
        ├── … allgemeine Daten …
        ├── … Einkünfte aus Lohn, Vermietung, Sonderausgaben, … 
        └── EINKUENFTE_KAPITALVERMOEGEN ← E1kv-Kennzahlen (optional!)
```

Dass der Kapitalvermögen-Block „optional" ist, heißt nur: Ein XML **ohne** ihn ist technisch gültig. Es heißt **nicht**, dass ein XML **nur mit** ihm als „Teil-Erklärung" behandelt wird. Es gibt keinen Teil-Upload und kein Zusammenführen mit dem, was Du sonst noch erklären wolltest.

Daraus folgt der entscheidende Satz dieses Artikels:

> **Wer ein XML produktiv hochlädt, das nur die Kapitaleinkünfte enthält, reicht eine vollständige Einkommensteuererklärung ein, in der alles andere leer ist.**

Keine Werbungskosten aus dem Job. Keine Sonderausgaben. Keine Vermietung. Nichts von dem, was ein Tool für Kapitalerträge naturgemäß gar nicht kennen kann. Für das Finanzamt steht da nicht „unvollständig, bitte warten" — da steht: *Dieser Steuerpflichtige erklärt, dass es sonst nichts gibt.*

## „Dann schau ich es mir halt vorher an" — leider nein

Der zweite Einwand liegt nahe: FinanzOnline wird schon nachfragen, bevor etwas Bindendes passiert. Auch hier ist die Realität unangenehmer:

| Erwartung | Realität in FinanzOnline |
|---|---|
| „Der Upload ist erst mal ein Entwurf" | Der Produktions-Upload **gilt sofort als eingebracht** |
| „Es gibt sicher eine große Warnung" | Der erfolgreiche Upload sieht aus wie ein Erfolg — keine Rückfrage, keine rote Box |
| „Zum Testen gibt es bestimmt einen Sandkasten" | Gibt es (die **Testübermittlung**) — aber sie ist in der Maske leicht zu übersehen, und **Produktion ist der Default** |
| „Falsch eingereicht? Reiche ich einfach nochmal ein" | Die elektronische Berichtigung ist danach **gesperrt**: „für diesen Zeitraum ist bereits ein Antrag eingelangt" |

Die Testübermittlung ist übrigens genau das richtige Werkzeug, wenn man mit dem Datenstrom experimentieren will: Sie validiert das XML, das Ergebnis landet im Nachrichten-Protokoll, und sie „gilt nicht als eingebracht". Das Problem ist nicht, dass FinanzOnline keinen sicheren Weg hätte — das Problem ist, dass der **gefährliche Weg der bequemere und voreingestellte** ist.

## Unser Praxisfall: Wie schnell es passiert

Das ist keine theoretische Warnung. Beim Testen unseres eigenen E1kv-XML-Prototyps ist uns im Sommer 2026 genau dieser Fehler passiert: Ein Test-XML — nur der Kapitalvermögen-Block, der Rest der E1 leer — wurde versehentlich als **Produktions**-Übermittlung statt als Testübermittlung hochgeladen.

Was dann passierte, in Echtzeit:

1. **Keine Warnung, kein Zwischenschritt.** Der Upload lief durch und sah exakt so aus wie ein gelungener Vorgang.
2. Die unvollständige Erklärung galt **im selben Moment als eingebracht** — mit Zeitstempel, wie eine ganz normale Abgabe.
3. Der Versuch, elektronisch zu korrigieren, wurde blockiert: für den Zeitraum war „bereits ein Antrag eingelangt".
4. Ab da läuft der Papier-Weg: **schriftliches Anbringen ans Finanzamt** mit der Bitte, die Erklärung anzuhalten bzw. die Korrektur freizuschalten — und als Sicherheitsnetz die **Bescheidbeschwerde nach § 243 BAO binnen eines Monats** ab Bescheid, falls das Finanzamt schneller veranlagt, als das Anbringen wirkt.

Wohlgemerkt: Das ist einem Nutzer passiert, der das System kennt, der wusste, dass es eine Testübermittlung gibt, und der aktiv danach gesucht hat. Ein Anleger, der zum ersten Mal ein „upload-fertiges XML" aus seinem Steuertool bekommt, hat diese Chance realistisch nicht.

## Warum „upload-fertig" trotzdem beworben wird

Weil es großartig klingt und der Haken unsichtbar ist. Ein XML-Export ist für den Anbieter billig zu bauen (das Schema ist öffentlich), er demonstriert technische Reife, und in 100 % der Demos funktioniert er — der Schaden entsteht ja erst beim Kunden, Monate später, in Form einer eingereichten Erklärung, in der der Lohnzettel-Teil, die Sonderausgaben und alles andere fehlen.

Uns ist wichtig, fair zu bleiben: Ein XML-Upload ist nicht per se schlecht. In der Hand eines **Steuerberaters**, der ohnehin die *gesamte* Erklärung seines Mandanten befüllt und den Datenstrom-Workflow kennt, ist er ein legitimes Werkzeug. Gefährlich wird er als Convenience-Feature für Selbstausfüller, verkauft mit dem Versprechen „nur noch hochladen".

## Wie Du es sicher machst

**Wenn Du Deine Erklärung selbst abgibst (der Normalfall):**

1. **Tippe die Kennzahlen selbst in FinanzOnline ein.** Das klingt nach dem Rückschritt, den Dir das XML ersparen sollte — aber es sind bei Kapitaleinkünften typischerweise **unter zehn Kennzahlen** (KZ 862/863, 897/898, 892, 937, 994/998, ggf. 857/861). Der Aufwand liegt bei wenigen Minuten, und Du siehst dabei jede Zahl noch einmal, bevor irgendetwas bindend wird. Welche Kennzahl wohin gehört, haben wir hier ausführlich beschrieben: [E1kv ausfüllen für IBKR-User](/posts/e1kv-ausfuellen-ibkr/).
2. **Schicke die Erklärung erst ab, wenn ALLE Teile drin sind** — Lohn, Werbungskosten, Sonderausgaben, Vermietung, was immer bei Dir dazugehört. Die E1kv ist eine Beilage, keine eigene Erklärung.
3. Falls Du trotzdem mit XML experimentieren willst: **ausschließlich über die Testübermittlung**, und kontrolliere im Nachrichten-Protokoll, dass es wirklich eine Testübermittlung war — *bevor* Du irgendetwas produktiv anfasst.

**Wenn ein Steuerberater für Dich einreicht:** Gib ihm die Kennzahlen-Übersicht und die Belege — die Übermittlungsmechanik ist dann sein Handwerk, und er reicht die vollständige Erklärung ein.

**Wenn es schon passiert ist:** Nicht auf den Bescheid warten und hoffen. Sofort schriftliches Anbringen ans zuständige Finanzamt (Sachverhalt schildern, um Anhalten der Veranlagung bzw. Korrekturmöglichkeit ersuchen, vollständige Erklärung ankündigen) — und den Kalender auf die **einmonatige Beschwerdefrist ab Bescheidzustellung (§ 243 BAO)** stellen.

## Unser Weg bei DepotTax

DepotTax erzeugt Dir bewusst **kein „upload-fertiges" XML**, sondern eine **kontrollierbare Kennzahlen-Übersicht**: jede E1kv-Kennzahl mit Betrag, Beilagen-Kontext („mit" vs. „ohne KESt-Abzug") und der Herleitung dahinter — im PDF zum Prüfen, im Excel bis auf jede einzelne Transaktion nachvollziehbar. Du trägst die Werte in FinanzOnline ein, wenn *Deine ganze* Erklärung fertig ist, und behältst den einen Schritt in der Hand, der rechtlich zählt: das Absenden.

Das ist eine Minute mehr Arbeit als ein Upload-Button. Es ist auch der Unterschied zwischen einem Report und einer versehentlich eingereichten Steuererklärung.

---

*Dieser Artikel ist keine Steuerberatung, sondern ein Erfahrungsbericht zur Übermittlungsmechanik von FinanzOnline. Für Deine konkrete Erklärung gilt: im Zweifel Steuerberater fragen.*
