---
period: today
date: 2026-05-12
updated: 2026-05-12
cssclasses:
  - daily-view
tagad_task: ""
inbox_capture: braindump
---

# ⚡ Šodien — 2026-05-12

---

> [!tagad] 🎯 TAGAD — viens uzdevums
> 
> `INPUT[text(placeholder(Ko daru tagad... )):tagad_task]`
> 
> ---
> - [x] *(pārvieto šeit vienu uzdevumu no ŠODIEN ↓)*
> 
> *Kad pabeidzu — pārvelku nākamo*

---

> [!sodien] 📋 ŠODIEN
> 
> 5–7 uzdevumi ko plānoju izdarīt šodien. Pirmais solis = smieklīgi mazs.
> 
> - [x] D2: Meta-Bind — pārbaudīt vai INPUT lauki strādā
> - [x] D2: DASHBOARD pogas — izmēģināt navigāciju
> - [ ] Aizpildīt vakara log [[2026-05-12]]

---

> [!inbox] 📥 INBOX — brain dump
> 
> `INPUT[text(placeholder(Met visu šeit. Nedomā par kategoriju...)):inbox_capture]`
> 
> ---
> *(vakarā 5 min — pārvieto vai izdzēs)*

---

> [!deadline] ⚠️ DEADLINE TUVU
> 
> Uzdevumi ar konkrētu termiņu < 14 dienas.
> 
> - [x] *Pagaidām tukšs*

---

> [!rutinas] 🔄 IKDIENAS RUTĪNAS
> 
> - [ ] Aizpildīt vakara log [[2026-05-12]] 🔁 every day
> - [ ] Pārbaudīt INBOX un iztukšot 🔁 every day

---

> [!projekts] 🚀 AKTĪVIE PROJEKTI
> 
> | | Projekts | Nākamais solis |
> |---|----------|----------------|
> | 🟠 | [[AI OS Build Plan\|AI OS — 10 dienu plāns]] | D3: Syncthing |
> | 🎵 | [[lux-harmonia-cosmic-echoes\|Lux Harmonia]] | Manuāli |
> | 🥗 | [[wife-nutrition-business/README\|VinkaFit]] | 19. maijā aktīvs |
> | 🔧 | [[../../../Desktop/distrokid/suno-distrokid-extension/README\|Distrokid Helper]] | Polish fāze |

---

## 📊 Visi atvērtie uzdevumi (auto)

```dataview
TASK
FROM ""
WHERE !completed
  AND !contains(file.path, "today")
  AND !contains(file.path, "04-archive")
  AND !contains(file.path, "ai-os-build-plan")
  AND !contains(file.path, "99-templates")
  AND !contains(file.path, "DASHBOARD")
  AND !contains(file.path, "hot")
  AND !contains(file.path, "index")
  AND !contains(file.path, "README")
GROUP BY file.folder
SORT due ASC
LIMIT 20
```

---

## 🌙 Vakara reset (5 min)

1. **Atķeksē** kas ir pabeigts šodien
2. **Nepabeigto** no ŠODIEN → pārvieto uz rītdienu **vai izdzēs**
3. **Iztukšo INBOX** — vai uz konkrētiem failiem, vai izdzēs
4. **Aizpildi vakara log:** [[2026-05-12]]
5. **TAGAD sadaļu atstāj tukšu** rītam

> Šaubu gadījumā: **izdzēs.** Lai paliek tikai tas kas patiešām svarīgs.
