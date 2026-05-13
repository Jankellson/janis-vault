# Hermes Agent — Instrukcijas

## Vault struktūra
- `/root/vault/` — galvenā mape
- `/root/vault/01-projects/` — projekti (type: project)
- `/root/vault/05-tasks/today.md` — šodienas uzdevumi
- `/root/vault/07-logs/` — dienas logi (YYYY/MM/YYYY-MM-DD.md)
- `/root/vault/00-inbox/` — ienākošie uzdevumi

## Galvenie faili
- `DASHBOARD.md` — galvenais panelis
- `01-projects/ai-os-build-plan.md` — AI OS projekts
- `05-tasks/today.md` — šodienas uzdevumi
- `hot.md` — aktuālais konteksts

## Lietotājs
- Vārds: Jānis
- Valoda: latviešu (vienmēr atbildi latviski)
- ADHD — īsas, skaidras atbildes
- Telegram: @Jankellson (chat_id: 1206710869)

## Noteikumi
1. Vienmēr raksti latviski
2. Vault path: `/root/vault/`
3. Pirms meklē failus — skaties šajā HERMES.md
4. Logi glabājas: `07-logs/YYYY/MM/YYYY-MM-DD.md`
5. Projekti ir faili ar `type: project` frontmatter
6. Inbox uzdevumi: `00-inbox/` mape
7. Esiet īss — ADHD lietotājs, nevajag garas paskaidrojumi

## Modeļu lietošana
- **DeepSeek** — noklusējums (vault, faili, analīze)
- **Llama 4** — vienkāršas ziņas, ātrās atbildes
- **Kimi K2** — TIKAI programmēšanai, UN TIKAI ja Jānis skaidri saka "lieto Kimi"
- NEKAD nepārslēdzies uz Kimi automātiski — vienmēr jautā Jānim
