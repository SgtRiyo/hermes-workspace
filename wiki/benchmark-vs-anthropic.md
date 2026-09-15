# Benchmark vs Anthropic — 2026-09-14

Tugas identik: 2 ide konten, format `IDE n: judul | hook ≤12 kata | CTA`.

| Model | Waktu | Hasil |
|---|---|---|
| kr/deepseek-3.2 (9router) | 1.7s | Bersih, Indonesia natural, tanpa halusinasi promo |
| kr/claude-haiku-4.5 (9router) | 3.0s | Format ok, tapi campur Inggris + halusinasi "diskon 20%" |
| claude-3-haiku (Experiential) | - | Terkunci (429 model_requires_purchase) — butuh beli kredit dulu |

Keputusan: sub-agent tetap `kr/deepseek-3.2`. Haiku kalah kualitas bahasa + ngarang promo.
Catatan: akun Experiential belum bisa pakai model Anthropic tanpa top-up.
