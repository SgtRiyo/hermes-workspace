# Benchmark 4 kandidat sub-agent Nara — 2026-09-18

Tugas: TEPAT 2 ide konten, format `IDE n: <judul> | <hook ≤12 kata> | <CTA>`, tanpa teks lain.

| Model | Waktu | Token | Format | Nilai |
|---|---|---|---|---|
| gpt-5.6-luna | 8s | 224 | Sempurna | 🥇 tercepat + termurah |
| deepseek-v4.1-flash | 11s | 809 | Sempurna, hook natural | 🥈 primer sub-agent (pilihan user) |
| qwen3.8-flash | 22s | 1023 | OK, hook mentok 12 kata | 🥉 |
| mimo-v2.5 | 26s | 7525 (overhead cache) | Cacat (`CTA:` dobel) | 4 |

Keputusan: primer `nara/deepseek-v4.1-flash`, fallback `gpt-5.6-luna → qwen3.8-flash → mimo-v2.5 → kr/*`.
Harga (in/1M Rp): luna 531, v4.1-flash 531, mimo 372, qwen 664.
