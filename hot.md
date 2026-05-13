---
updated: 2026-05-11
---

# 🔥 Hot Context

> Šis ir pašreizējais konteksts. Atjauninu pēc katras sesijas.
> Maksimāli ~500 vārdi, lai AI ātri saprot kur darbs apstājās.

## Šobrīd strādāju pie

**Galvenais fokuss:** 7 dienu manuālais eksperiments — vai vienkārša Obsidian sistēma pietiek pirms Hermes uzstādīšanas

**Jaunā ADHD-friendly today.md struktūra ieviesta 2026-05-11:**
- TAGAD (1 uzdevums) → ŠODIEN → INBOX → DEADLINE TUVU → Auto-list
- Pamatā Jāņa pieredze: "tukša lapa + checkbox izsvītrošana = dopamīns"
- Bez gamifikācijas, bez XP, bez streak'iem — tas viņam nestrādā
- Vakara reset rituāls + first-step trick lielajiem uzdevumiem

**AI OS plāns precizēts** (skat [[ai-os-build-plan]]):
- Apstiprināts: Hermes Agent (Nous Research, v0.13, 143k stars) — bet TIKAI pēc 7 dienu manuālā testa
- Apstiprināta arhitektūra: Vault = inter-agent API; Claude Code (Pro) plāno, Hermes (lēts modelis) izpilda
- Hetzner CX22 €4.51/mēn aizvieto Oracle Free Tier
- Modeļi: DeepSeek V4 Flash + Gemini Flash + NVIDIA NIM (visi swappable)

**Pieslēgtie projekti:**
- [[lux-harmonia-cosmic-echoes]] — gaida Distrokid metadatu pabeigšanu
- [[school-9th-grade-spring-2026]] — datu struktūru tēmas plāns

## Šī nedēļa — prioritātes

1. ✅ Obsidian vault uzbūvēts
2. 🔄 DASHBOARD.md ar Dataview
3. ⏳ Syncthing — telefons + dators
4. ⏳ Git + GitHub backup

## Atvērti pavedieni

- [ ] Pabeigt Lux Harmonia metadatus Distrokid
- [ ] Sagatavot kontroldarbu 9. klasei
- [ ] Oracle Cloud konta izveide
- [ ] Hermes uzstādīšana uz cloud

## Pēdējie lēmumi

- **2026-05-09:** Izvēlējos Obsidian + Dataview kā dashboard (nevis localhost)
- **2026-05-09:** Vault atrašanās: `C:\Users\Janis Jekabsons\ai-projects\Janis`
- **2026-05-09:** Mapju nosaukumi angliski, saturs latviski
- **2026-05-09:** Syncthing plānots Obsidian Sync vietā ($0 vs $48/g)
- **2026-05-08:** Gemini API (bezmaksas) Hermes vajadzībām
- **2026-05-07:** Atteicāmies no Hermes Desktop app (Windows bug)

## Pieņemtā arhitektūra

```
Obsidian (atmiņa, teksts)
    ↕ Syncthing
Telefons + Dators + Cloud serveris
    ↕ Git
GitHub (drošības kopija)

Hermes (uz Oracle Cloud) → lasa/raksta vault
n8n → orķestrē automatizācijas
Google Drive → lielie faili (WAV, attēli)
Chrome extension → Suno/Distrokid pipeline
```

## Konteksta limits

Ja šis fails sasniedz 280 rindiņas — saspied (heartbeat cikls).

## Nākamais solis — INTENSĪVAIS PLĀNS

**Lēmums 2026-05-11:** Atteicāmies no 4-6 nedēļu pakāpeniskās pieejas. Tagad 10-dienu intensīvais režīms.

**Pirmais reālais projekts pēc uzbūves:** [[wife-nutrition-business]] (no 19. maija)

→ **ŠOVAKAR (30 min start, līdz 3h):**

### Posms A (10 min) — Plugins instalācija
Settings → Community plugins → Turn on → Browse → instalēt un iespējot:
1. **Dataview**
2. **Tasks**
3. **Templater**
4. **Meta Bind**
5. **Iconize**
6. **Style Settings**

### Posms B (5 min) — Tēma
Settings → Appearance → Themes → Manage → Browse → **Minimal** → Install → Use
Mode → Dark

### Posms C (1 min) — Startup
Settings → core plugin "Page preview"... vai Settings → atvērt lapu pa startēšanu = `05-tasks/today.md`

### Posms D (15 min) — Brain dump
Atver today.md → 📋 ŠODIEN → ieraksti 5 reālus uzdevumus → 1 uz TAGAD ar first-step

**Pēc tam atgriezies šeit** un Claude raksta vizuālo today.md (Meta-Bind pogas, callouts, divkolonnu izkārtojums).

---

**LIELAIS PLĀNS (10 dienas):** Skat [[ai-os-build-plan]]
- D1-D2: Vizuālais dashboard
- D3-D4: Syncthing + Git
- D5-D6: Hetzner + Hermes
- D7-D8: Telegram + workflows
- D9-D10: Polish + sievas projekta start
