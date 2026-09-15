# Benchmark Sub-Agent Tak-Bias (langsung) — 2026-09-14

Tugas identik via API (tanpa bias jalur): 2 ide konten, format `IDE n: judul | hook ≤12 kata | CTA`.

| Model | Waktu | Token in/out | Kualitas hook |
|---|---|---|---|
| kr/deepseek-3.2 | 9.0s | 5036/45 | Terbaik — natural, on-topic |
| kr/glm-5 | 1.5s | 5841/39 | Baik, ada slang janggal ("ngeprul") |
| kr/qwen3-coder-next | 1.2s | 17109/45 | Baik, tapi token bloat 3x |

Keputusan: sub-agent tetap `kr/deepseek-3.2` (kualitas bahasa terbaik + token wajar + sudah terbukti di produksi dengan fallback hidup).
