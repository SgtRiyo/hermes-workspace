# SOP Agen (fakta)

1. Satu agen = satu role + satu workspace + skill/tool sendiri.
2. Lead (`nara/glm-5.3-flash`, Nara khusus Lead): merencanakan, me-manage sub-agent, troubleshooting.
3. Sub-agent (`kr/deepseek-3.2`, hemat): tugas rutin — rekap, baca teks, draft.
4. Fallback otomatis: `nara/glm-5.3-flash` → `kr/deepseek-3.2` → `kr/qwen3-coder-next` (config `~/.hermes/config.yaml` → `fallback_providers`).
5. Gateway berjalan sebagai `hermes-gateway.service` (systemd, auto-restart). Dashboard di `hermes.sigitstudio.com`.
6. Backup otomatis tiap malam via cron (lihat `sbeats` / `hermes cron`).

7. GitHub sync: repo private SgtRiyo/hermes-workspace (branch main). Cron backup push otomatis tiap 00:00. Vault Obsidian = clone repo ini.
