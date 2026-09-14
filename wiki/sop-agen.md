# SOP Agen (fakta)

1. Satu agen = satu role + satu workspace + skill/tool sendiri.
2. Lead (`Coding`, flagship): merencanakan, me-manage sub-agent, troubleshooting.
3. Sub-agent (`Nara-Free`, hemat): tugas rutin — rekap, baca teks, draft.
4. Fallback otomatis: `Coding` → `Nara-Free` → `nara/glm-5.3-free` (config `~/.hermes/config.yaml` → `fallback_providers`).
5. Gateway berjalan sebagai `hermes-gateway.service` (systemd, auto-restart). Dashboard di `hermes.sigitstudio.com`.
6. Backup otomatis tiap malam via cron (lihat `sbeats` / `hermes cron`).
