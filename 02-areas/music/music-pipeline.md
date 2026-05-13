---
type: area
status: active
created: 2026-05-09
updated: 2026-05-09
folder: "C:\\Users\\Janis Jekabsons\\ai-projects\\music-pipeline"
agent-written: true
tags: [music, code, python, automation]
related: [[lux-harmonia]], [[suno-workflow]]
---

# Music Pipeline — Python automatizācija

## Kas tas ir
Python skripti mūzikas failu apstrādei un pārvaldībai.

## Atrašanās
`C:\Users\Janis Jekabsons\ai-projects\music-pipeline\`

## Struktūra
```
artists/          ← mākslinieku dati
queue/            ← gaidāmie uzdevumi
output/           ← apstrādātie faili
done/             ← pabeigti
error/            ← kļūdas
lux_visual_engine/ ← vizuālie rīki (Lux)
tiktok_ready/     ← TikTok gatavie
```

## Galvenās funkcijas
- `authorize.py` — Google Drive autorizācija
- `authorize_drive.py` — Drive piekļuve

## Google Drive integrācija
Izmanto Google Drive API lai augšupielādētu/lejupielādētu failus.

## Saites
- [[lux-harmonia]]
- [[suno-workflow]]
- [[distrokid-helper-v2]]
