---
type: project
status: active
created: 2026-05-09
updated: 2026-05-09
priority: high
folder: "C:\\Users\\Janis Jekabsons\\ai-projects\\distrokid v2"
agent-written: true
tags: [music, music/distrokid, chrome-extension, code]
related: [[lux-harmonia]], [[distrokid-process]], [[suno-workflow]]
---

# Chrome Extension — Suno/Distrokid Helper v2

## Kas tas ir
Chrome pārlūka extension kas automatizē:
1. **Suno** → masveida WAV lejupielāde no albuma lapas
2. **Distrokid** → autopaste mākslinieka profila datus + WAV augšupielāde

## Atrašanās
`C:\Users\Janis Jekabsons\ai-projects\distrokid v2\suno-distrokid-extension\`

## Statuss
- ✅ Pamata struktūra (manifest, popup, content scripts)
- 🔄 Suno lejupielāde (testēts, strādā)
- ⏳ Distrokid autopaste (papildināšana notiek)

## Soļi
- [x] Manifest.json
- [x] Popup HTML/CSS/JS
- [x] Content scripts (suno + distrokid)
- [ ] Pilna Distrokid aizpildīšanas loģika
- [ ] Kļūdu apstrāde
- [ ] Pārtraukt poga

## Instalēšana Chrome
1. `chrome://extensions`
2. Developer mode ON
3. "Load unpacked" → izvēlies `suno-distrokid-extension\`

## Saites
- [[distrokid-process]] — secība
- [[suno-workflow]] — Suno lejupielādes flow
- [[lux-harmonia]] — galvenais mākslinieks
