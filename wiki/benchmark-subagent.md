# Benchmark Sub-Agent — 2026-09-14

Tugas rutin: rekap teks jadi TEPAT 3 poin (maks 15 kata/poin), format baku. Semua non-Nara via 9router.

| Model | Waktu | Token in/out | Format | Kata/poin | Status |
|---|---|---|---|---|---|
| kr/deepseek-3.2 | 3.4s | 5103/51 | Sempurna | Patuh | Juara bertahan |
| kr/glm-5 | 4.6s | 5921/41 | Sempurna | Patuh, paling ringkas | Runner-up |
| kr/qwen3-coder-next | 1.2s | 17457/52 | Sempurna | Patuh | Tercepat tapi token bloat 3x |
| kr/claude-haiku-4.5 | 2.5s | 6411/68 | Baik | Langgar (17 kata) | - |
| kr/MiniMax-M2.5 | - | - | - | - | Mati (400 Invalid model ID) |
| nvidia/nemotron-3-ultra-550b-a55b | - | - | - | - | Mati (404) |

Keputusan: sub-agent tetap `kr/deepseek-3.2` (format paling disiplin, cepat, token wajar).
Catatan: token input menggembung di semua rute kiro (overhead sistem 9router) — perbandingan relatif tetap valid.
