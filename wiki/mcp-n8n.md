# MCP / n8n Bridge (status 2026-09-14)

Infra jadi: n8n jalan lokal (`127.0.0.1:5678`, container `n8n`), terekspos via
`https://n8n.sigitstudio.com` (tunnel ingress + CNAME ok, 200 verified).
Katalog MCP Hermes: `comfy-cloud`, `figma`, `linear`, `n8n`, `unreal-engine`.

Langkah terakhir (butuh manusia via browser, ~5 menit):
1. Buka `https://n8n.sigitstudio.com`, buat owner account.
2. Settings → API → buat API key.
3. Di VPS: `N8N_API_KEY=<key> hermes mcp install n8n` (N8N_BASE_URL sudah di `.env`).
4. Verifikasi: `hermes mcp list` harus menunjukkan `n8n`.
5. Opsional: Figma via `hermes mcp install figma` (OAuth di browser).

Setelah itu Hermes bisa memanggil workflow n8n = "colokan USB" ke Google
Workspace, Canva (via HTTP node), dan aplikasi kustom.
