---
created: 2026-05-09
updated: 2026-05-09
agent-written: false
tags:
  - ai-prompts
  - system
---

# 🤖 AI promptu bibliotēka

## Sesijas sākums (Resume)
```
Sveiks. Pirms atbildi uz manu jautājumu, izlasi:
1. CLAUDE.md
2. hot.md
3. 05-tasks/today.md
4. Pēdējās dienas log

Pēc tam pavaicā kā šodien gribu strādāt:
A) Konkrēts uzdevums
B) Brainstorming
C) Pārskats par pēdējām dienām
```

## Memory Save — Lēmums
```
Saglabā šo lēmumu:
Decision: [kas tika nolemts]
Context: [kāpēc, kāds bija fons]
Owner: [kurš atbild]
```

## Memory Save — Atziņa
```
Saglabā šo atziņu:
Insight: [kāda atziņa]
Triggered by: [kas to izraisīja]
```

## Daily Review (vakarā)
```
Tu esi mans Obsidian asistents. Atver šodienas log failu vai izveido jaunu.
Apkopo:
- Galvenās uzvaras
- Izaicinājumus
- Atziņas
- Top 3 prioritātes rītdienai
- Atvērtos pavedienus

Atbildi tikai ar Markdown. Lieto [[wikilinks]].
Neuzraksti neko, ko nezini.
```

## Weekly Review (svētdien)
```
Apkopo šo nedēļu pa darba VIENĪBĀM (ne dienām):
- Kas tika izdarīts
- Kāda problēma atrisināta
- Kādi rezultāti svarīgi nākotnē
- Kuras piezīmes savienot
```

## Heartbeat (klusais cikls)
```
Analizē šīsdienas log:
1. Galvenie lēmumi un pamatojumi → 02-areas/decisions.md
2. Jauni iemācītie fakti → atbilstoša area
3. Atvērti pavedieni → 05-tasks/today.md
4. Atjaunini hot.md
```

## Wiki Lint (veselības pārbaude)
```
Health check vault:
- Atrod orphan piezīmes (nav saišu)
- Atrod broken wikilinks
- Atrod dublikātus
- Iesaki uzlabojumus struktūrā
```

## Auto-tagging
```
Analizē šīs piezīmes saturu un iesaki 3-5 tagus.
Salīdzini ar esošajiem tagiem vault.
Saturs: [piezīmes teksts]
```

## Contradiction Gate
```
Pārbaudi vai šī jaunā informācija ir pretrunā ar esošo:
[jaunā info]

Ja jā:
- NEPĀRRAKSTI veco
- Izveido [!warning] Contradiction callout
- Citē abus apgalvojumus burtiski
```
