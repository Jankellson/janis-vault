---
period: today
date: 2026-05-13
updated: 2026-05-13
cssclasses:
  - daily-view
tagad_task: ""
inbox_capture: ""
---

# ⚡ Šodien — 2026-05-13

---

> [!tagad] 🎯 TAGAD — viens uzdevums
> 
> `INPUT[text(placeholder(Ko daru tagad... )):tagad_task]`
> 
> ---
> *(pārvieto šeit vienu uzdevumu no ŠODIEN ↓)*
> 
> *Kad pabeidzu — pārvelku nākamo*

---

> [!sodien] 📋 ŠODIEN
> 
> 5–7 uzdevumi ko plānoju izdarīt šodien. Pirmais solis = smieklīgi mazs.
> 
> - [x] Rotēt Telegram token (@BotFather → /mybots → revoke)
> - [x] Rotēt OpenRouter API atslēgu (openrouter.ai/settings/keys) ✅ 2026-05-13
> - [x] Atjaunināt ~/.hermes/.env ar jaunajiem tokeniem ✅ 2026-05-13
> - [x] Iepazīties ar sistēmu — Obsidian puse ✅ 2026-05-13
> - [ ] D10: VinkaFit projekts vault struktūrā

---

> [!inbox] 📥 INBOX — brain dump
> 
> [[00-inbox/inbox|📥 Atvērt inbox →]]
> 
> *(vakarā 5 min — pārvieto vai izdzēs)*

---

> [!deadline] ⚠️ DEADLINE TUVU
> 
> *(pagaidām tukšs)*

---

> [!rutinas] 🔄 IKDIENAS RUTĪNAS
> 
> - [ ] Aizpildīt vakara log [[07-logs/2026/05/2026-05-13|2026-05-13]] 🔁 every day
> - [ ] Pārbaudīt INBOX un iztukšot 🔁 every day

---

## 📊 Visi atvērtie uzdevumi (auto)

> Lai **dzēstu** uzdevumu — klikšķini uz faila nosaukuma (oranžais) → atrodi tur → dzēs rindiņu.

```dataviewjs
const tasks = dv.pages('"05-tasks"')
  .where(p => !p.file.path.includes("today"))
  .flatMap(p => p.file.tasks.where(t => !t.completed).map(t => ({task: t, file: p.file})));

for (const {task, file} of tasks) {
  dv.el("div", `☐ ${task.text} — ${dv.fileLink(file.path, false, file.name)}`, {cls: "task-row"});
}
if (tasks.length === 0) dv.el("p", "✅ Visi uzdevumi izdarīti!");
```

---

## 🌙 Vakara reset (5 min)

1. **Atķeksē** kas ir pabeigts šodien
2. **Nepabeigto** no ŠODIEN → pārvieto uz rītdienu **vai izdzēs**
3. **Iztukšo INBOX** — vai uz konkrētiem failiem, vai izdzēs
4. **Aizpildi vakara log:** [[07-logs/2026/05/2026-05-13|2026-05-13]]
5. **TAGAD sadaļu atstāj tukšu** rītam

> Šaubu gadījumā: **izdzēs.** Lai paliek tikai tas kas patiešām svarīgs.
