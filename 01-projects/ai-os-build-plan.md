---
type: project
status: active
created: 2026-05-09
updated: 2026-05-12
priority: high
agent-written: false
tags: [system, ai-os, obsidian, hermes, dashboard]
related: [[CLAUDE]], [[DASHBOARD]], [[today]]
---

# 🧠 AI OS — Personīgā intelektuālā sistēma

> Mērķis: Uzbūvēt personīgu AI sistēmu, kas atceras visu, darbojas 24/7,
> strādā bez datora, automatizē ikdienas uzdevumus, un izskatās labi.

---

## 🎯 Pamatprincipi (lēmumi nofiksēti 2026-05-11)

1. **Vizuāli pirmkārt** — Jānis nevar strādāt ar termināli/nepāredzamu UI. Skaists interfeiss = motivācija.
2. **Vault = inter-agent API** — Markdown faili ir tilts starp Claude Code, Hermes, manuālo darbu. Nav tieša API savienojuma.
3. **Modularitāte obligāti** — modeli, aģenti, frameworks visi swappable. Bez lock-in.
4. **ADHD-friendly** — izsvītrošana = dopamīns. Vienkāršība pār pilnīgumu. Tukšs lapa = uzvara.
5. **Inkrementāli, ne uzreiz** — katrai fāzei 7-14 dienu lietošanas tests pirms iet tālāk.
6. **Reālistisks termiņš:** 4-6 nedēļas, ne 5 dienas (kā oriģinālā plānā).

---

## 🏗️ Galīgā arhitektūra

```
┌──────────────────────────────────────────────────┐
│ DARBA SAJUTA                                     │
│ ├─ Windows dators — primārais                    │
│ │  ├─ Obsidian (vizuāli dashboard)               │
│ │  └─ Claude Code (Pro abonents) — STRATĒĢIS     │
│ └─ Telefons (Telegram) — brain dump + skats      │
└────────────────────┬─────────────────────────────┘
                     ↕ Syncthing
┌──────────────────────────────────────────────────┐
│ STORAGE LAYER (Markdown, mūžīgs)                 │
│ ├─ Vault Markdown                                │
│ ├─ Git → GitHub privāts backup                   │
│ └─ Inter-agent inboxes (00-inbox/tasks, /results)│
└────────────────────┬─────────────────────────────┘
                     ↕ Syncthing
┌──────────────────────────────────────────────────┐
│ EXECUTION LAYER (Hetzner CX22, €4.51/mēn)        │
│ ├─ Hermes Agent — IZPILDĪTĀJS 24/7               │
│ │   ├─ Telegram backend                          │
│ │   ├─ Cron: skenē tasks, izpilda                │
│ │   ├─ Memory: SQLite (~/.hermes/)               │
│ │   └─ Skills: Markdown (agentskills.io std)     │
│ └─ Modeli (swappable):                           │
│     ├─ Smart: DeepSeek V4 Flash (~$3/mēn)        │
│     ├─ Cheap: Gemini 2.5 Flash ($0)              │
│     └─ Backup: NVIDIA NIM ($0)                   │
└──────────────────────────────────────────────────┘
```

**Izmaksas:** ~$28-30/mēn (Claude Pro + Hetzner + DeepSeek lietojums)

---

## 📊 Kopējais progress — INTENSĪVAIS 10-DIENU PLĀNS

**Lēmums 2026-05-11:** Atteicāmies no 4-6 nedēļu pakāpeniskās pieejas. Sistēma jāuzbūvē intensīvi 10 dienās.

**Pirmais reālais projekts pēc uzbūves:** [[wife-nutrition-business/README|VinkaFit]]

| Diena | Datums | Fāze | Cik h | Statuss |
|-------|--------|------|-------|---------|
| **D1** | 2026-05-11 | Plugins + today.md + CSS pamats + Ember Cyber tēma | 2-3h | ✅ PABEIGTS |
| **D2** | 2026-05-12 | Meta-Bind INPUT + DASHBOARD pilnīgs pārskats + CSS | 2h | ✅ PABEIGTS |
| **D3** | 2026-05-12/13 | Syncthing — dators + telefons + Obsidian mobile | 1-2h | ⏳ Nākamais |
| **D4** | 2026-05-13 | Git + GitHub privāts repo + auto-commit | 1h | ⏳ |
| **D5** | 2026-05-14 | Hetzner CX22 + Ubuntu 24.04 + SSH | 2-3h | ⏳ |
| **D6** | 2026-05-13 | Hermes v0.13 config + modeli + vault sync | 2-3h | ✅ PABEIGTS |
| **D7** | 2026-05-13 | Telegram bot + brain dump workflow | 2h | ✅ PABEIGTS |
| **D8** | 2026-05-17 | Daily digest cron + /today /done komandas | 1-2h | ⏳ |
| **D9** | 2026-05-18 | Polish + monitoring + backup | 1-2h | ⏳ |
| **D10** | 2026-05-19 | VinkaFit projekts sistēmā | 2h+ | ⏳ |

**Kopā: ~18-22h darba 10 dienās**

| Bloks | Statuss |
|-------|---------|
| Vault pamati | ✅ 2026-05-09 |
| Vizuālais dashboard (D1-D2) | ✅ 2026-05-12 |
| Sinhronizācija (D3-D4) | ⏳ |
| Hetzner + Hermes (D5-D6) | ✅ 2026-05-13 |
| Telegram + workflows (D7-D8) | 🔄 D8 nākamais |
| Polish + stabilitāte (D9) | ⏳ |
| Pirmais reālais projekts (D10) | ⏳ |

---

## ✅ D1 — Plugins + today.md + CSS pamats (PABEIGTS 2026-05-11)

- [x] today.md pārrakstīts ar ADHD-friendly struktūru
- [x] quick-log-template.md izveidots (3 sadaļas: izdarīju / prātā / rīt)
- [x] Dataview + Tasks + Meta-Bind v1.4.9 instalēti
- [x] orange-dark-theme.css izveidots (`orange-dark-theme.css`)
- [x] Ember Cyber krāsu palete: #FF6B35, #818CF8, #FFB627, #0F0A14
- [x] DASHBOARD.md pamats ar `cssclasses: [dashboard]`
- [x] today.md kā startup lapa

---

## ✅ D2 — DASHBOARD pilnīgs pārskats + Meta-Bind (PABEIGTS 2026-05-12)

- [x] DASHBOARD.md pārstrādāts — pilns multi-kolonnu izkārtojums
- [x] Sveiciena josla ar datumu, dienas žetons, streak
- [x] Nedēļas strip (P-S ar šodienas iezīmi)
- [x] TAGAD (`tagad_task`) + ĀTRĀ PIEZĪME (`inbox_capture`) — Meta-Bind INPUT
- [x] Šodien uzdevumi (Dataview TASK no 05-tasks/today)
- [x] Projektu tabula (AI OS, Lux Harmonia, VinkaFit, Distrokid Helper)
- [x] Build progress josla (D1-D10 vizuāli)
- [x] Sistēmas statusa tabula + Pēdējās izmaiņas (Dataview) + Rīku pogas
- [x] Properties + inline-title paslēpti uz dashboard klases
- [x] Full-width layout bez sānu polsterēšanas
- [x] Thinking tools sagatavots (ooda-loop, inversion, first-principles)

**Kas strādā:** INPUT lauki saglabā uz frontmatter. Dataview rāda uzdevumus reāllaikā.

---

## ⏳ D3 — Syncthing + Obsidian mobile

**Mērķis:** Vault telefonā. Izmaiņas redzamas < 30 sek.

- [x] Syncthing instalēts datorā (syncthing.net) ✅ 2026-05-13
- [x] Vault mape pievienota Syncthing ✅ 2026-05-13
- [x] Syncthing app telefonā (Android: Google Play / iOS: Möbius Sync) ✅ 2026-05-13
- [x] Vault sinhronizēts ✅ 2026-05-13
- [x] Obsidian mobile app → vault atvērts ✅ 2026-05-13
- [x] **Gate:** Rakstu telefonā → datorā parādās < 30 sek ✅ 2026-05-13

---

## ⏳ D4 — Git + GitHub backup

**Mērķis:** Vault automātiski backupējas uz GitHub katru vakaru.

- [x] Git instalēts (`git --version` strādā) ✅ 2026-05-13
- [x] GitHub privāts repo izveidots ✅ 2026-05-13
- [x] `.gitignore` iestatīts (workspace.json, .env, *.tmp) ✅ 2026-05-13
- [x] Pirmais commit + push ✅ 2026-05-13
- [x] Auto-commit skripts (22:00 katru vakaru) ✅ 2026-05-13
- [x] **Gate:** GitHub repo rāda commit pēdējo 3 dienu laikā ✅ 2026-05-13

---

## ⏳ D5 — Hetzner CX22 + SSH

**Mērķis:** Serveris pieejams no Windows termināļa.

- [ ] Hetzner konts izveidots (hetzner.com)
- [ ] CX22 instance palaista (Ubuntu 24.04, €4.51/mēn)
- [ ] SSH atslēga ģenerēta Windows pusē
- [ ] SSH savienojums strādā
- [ ] Syncthing uz servera → vault sinhronizēts
- [ ] **Gate:** `ssh user@server "ls ~/vault"` rāda failus

---

## ✅ D6 — Hermes Agent v0.13 (PABEIGTS 2026-05-13)

**Mērķis:** Hermes lasa vault, atbild uz testa jautājumu.

- [x] Hermes v0.13 instalēts (versija pinnēta) ✅ 2026-05-13
- [x] `config.yaml` aizpildīts ar vault ceļu ✅ 2026-05-13
- [x] `.env` — DeepSeek + OpenRouter API atslēgas ✅ 2026-05-13
- [x] `hermes setup` pabeigts ✅ 2026-05-13
- [x] Skill `personal/inbox-processor.md` izveidots ✅ 2026-05-13
- [x] **Gate:** Hermes atbild uz testa jautājumu, redz vault failus ✅ 2026-05-13

---

## ✅ D7 — Telegram bot (PABEIGTS 2026-05-13)

**Mērķis:** Brain dump no telefona → vault INBOX.

- [x] Bot izveidots (`@jankellson_bot`) ✅ 2026-05-13
- [x] Token pievienots `~/.hermes/.env` ✅ 2026-05-13
- [x] Whitelist: tikai mans `chat_id` (1206710869) ✅ 2026-05-13
- [x] Jebkura ziņa → Hermes atbild ✅ 2026-05-13
- [x] **Gate:** Telegram → Hermes < 5 sek ✅ 2026-05-13

---

## ⏳ D8 — Cron + komandas

**Mērķis:** Rīta digest. `/today` un `/done` komandas.

- [ ] Daily digest 8:00 — TAGAD + šodienas uzdevumi + inbox skaits
- [ ] `/today` → atgriež sarakstu
- [ ] `/done <teksts>` → atķeksē vault, apstiprina
- [ ] **Gate:** Saņemu rīta digest bez manuālas darbības

---

## ⏳ D9 — Polish + stabilitāte

- [ ] Hermes auto-restart pie crash
- [ ] Ping → Telegram ja serveris nestrādā
- [ ] Backup zip 1x nedēļā
- [ ] **Gate:** Sistēma strādā 48h bez iejaukšanās

---

## ⏳ D10 — VinkaFit projekts sistēmā

- [ ] VinkaFit DOCX faili → Markdown konvertēti
- [ ] Projekts vault struktūrā
- [ ] Hermes seko uzdevumiem
- [ ] **Gate:** Reāls projekts darbojas sistēmā

---

## ⏸️ Vēlāk — RAG, balss, citas integrācijas

Tikai pēc 30 dienām ar stabilu pamata sistēmu. Nav ātrāk — ADHD scope-creep risks.

- Hermes skill loop
- RAG / vektoru meklēšana
- Balss komandas (Whisper)
- Gmail, Calendar integrācijas

---

## 🚨 Galvenie riski un mitigācijas

| Risks | Mitigācija |
|-------|------------|
| Plugin auto-update salaiž system | Pin versijas, manuāli atjaunina 1x mēnesī |
| Hermes hallucinē atmiņā | Skill review 1x mēnesī (lasi `~/.hermes/skills/`) |
| ADHD scope creep | Phase gates — neej tālāk, ja iepriekšējais nestrādā |
| Pamešana Fāzē 4 | 14-dienu pauzes starp lielajām fāzēm |
| Sieva/skola/skolēni privātie dati | Atsevišķā šifrētā mapē (Cryptomator) |
| Vault korupcija multi-writer | Skaidras rakstīšanas zonas (Hermes raksta TIKAI noteiktos failos) |

---

## 📅 Lēmumu vēsture

| Datums | Lēmums | Iemesls |
|--------|--------|---------|
| 2026-05-09 | Obsidian kā atmiņas slānis | Markdown future-proof |
| 2026-05-09 | Hetzner CX22 nevis Oracle Free Tier | Stabilitāte > bezmaksas |
| 2026-05-11 | Hermes Agent v0.13 izvēlēts | 143k zvaigznes, MIT, agentskills.io standarts |
| 2026-05-11 | Claude Code (Pro) = stratēģis | Bezmaksas tev, gudrāks domāšanai |
| 2026-05-11 | DeepSeek V4 + Gemini Flash modeli | Modularitāte, lēti, swappable |
| 2026-05-11 | Vault = inter-agent API | Bez tieša API tilta starp aģentiem |
| 2026-05-11 | Vizuāli pirmkārt (Ceļš B) | Jāņa ADHD profilam — UI = motivācija |
| 2026-05-11 | Pāriet uz 10-dienu intensīvo sprinta plānu | Jānis nevar gaidīt 6 nedēļas |
| 2026-05-11 | NAV gamifikācijas (XP, levels) | Jānim nestrādā — izsvītrošana pati par sevi pietiek |
| 2026-05-12 | Ember Cyber krāsu palete (#FF6B35, #818CF8) | Orange + indigo = motivējoši + tehniski |
| 2026-05-12 | Meta-Bind INPUT → frontmatter (ne todo list) | Hermes lasīs frontmatter tieši |
| 2026-05-12 | TAGAD = viens uzdevums, ĀTRĀ PIEZĪME = brain dump | ADHD: viena lieta fokusam, otrs — tukšo galvu |

---

## 🔗 Saistītie faili

- [[CLAUDE]] — aģenta noteikumi
- [[DASHBOARD]] — galvenais vizuālais panelis (D2 pabeigts)
- [[05-tasks/today|today]] — ikdienas darba virsma
- [[07-logs/2026/05/2026-05-12|Šodienas log]]
- [[quick-log-template]] — vakara log template
- [[wife-nutrition-business/README|VinkaFit]] — pirmais reālais projekts (D10)
- [[lux-harmonia-cosmic-echoes]] — albuma release projekts
