# MCP / n8n Bridge (status 2026-09-14 — DONE)

Infra jadi: n8n jalan lokal (`127.0.0.1:5678`, container `n8n`), terekspos via
`https://n8n.sigitstudio.com` (tunnel ingress + CNAME ok, 200 verified).
MCP `n8n` di Hermes: INSTALLED + TESTED (`mcp test n8n` → connected, 11 tools,
8 enabled: health, list/get/find workflows, executions, activate/deactivate...).
Env key di `~/.config/n8n-mcp/env` (600). Bridge venv di-pin `mcp<2` (SDK v2 tidak kompatibel).
Gateway restart 2026-09-14 agar tool n8n termuat di sesi Telegram.
Katalog MCP Hermes: `comfy-cloud`, `figma`, `linear`, `n8n`, `unreal-engine`.

Langkah terakhir (butuh manusia via browser, ~5 menit):
1. Buka `https://n8n.sigitstudio.com`, buat owner account.
2. Settings → API → buat API key.
3. Di VPS: `N8N_API_KEY=<key> hermes mcp install n8n` (N8N_BASE_URL sudah di `.env`).
4. Verifikasi: `hermes mcp list` harus menunjukkan `n8n`.
5. Opsional: Figma via `hermes mcp install figma` (OAuth di browser).

Setelah itu Hermes bisa memanggil workflow n8n = "colokan USB" ke Google
Workspace, Canva (via HTTP node), dan aplikasi kustom.
