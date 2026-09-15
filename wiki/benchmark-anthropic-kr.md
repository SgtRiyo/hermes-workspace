# Benchmark Anthropic kr (base/thinking/agentic) — 2026-09-14

Tugas rutin identik: rekap → tepat 3 poin (maks 15 kata), format baku.

| Model | Waktu | Hasil |
|---|---|---|
| kr/deepseek-3.2 (baseline) | 4.2s | Sempurna |
| kr/claude-sonnet-4.5 | 2.5s | Sempurna, tercepat di yang hidup |
| kr/claude-sonnet-4 | 1.8s | Sempurna (tercepat), POIN 1 buang "bulan ini" tapi dalam batas |
| kr/claude-sonnet-4.5-thinking | - | Mati via OpenAI-wire (400 REQUEST_BODY_INVALID, butuh format thinking khusus) |
| kr/claude-sonnet-4.5-agentic | - | Mati (400, sama) |
| kr/claude-haiku-4.5-thinking/agentic | - | Mati (400, sama) |

Catatan: varian thinking/agentic butuh parameter khusus yang request polos tidak punya —
bukan berarti modelnya jelek, tapi tidak cocok untuk jalur hemat cepat ini.
