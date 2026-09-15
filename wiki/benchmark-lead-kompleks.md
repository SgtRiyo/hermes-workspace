# Benchmark Lead Kompleks — 2026-09-14

Tugas: 4 permintaan + jebakan (tugas D dilarang didelegasikan; path output spesifik; aturan no-folder-baru). Format baku RENCANA-DELEGASI/TUGAS-D/FILE-BARU/RISIKO.

| Model | Waktu | Format | Kepatuhan jebakan | Cacat |
|---|---|---|---|---|
| gpt-5.6-luna | 75.2s | Sempurna | Lulus (D dijawab langsung, 3-way split benar) | Sangat lambat |
| glm-5.3-flash | 8.4s | Baik | Lulus (D langsung) | Nama agen ngarang (agent-konten/agent-data); rekap berupa .csv di obsidian |
| deepseek-v4.1-flash | 4.1s | Gagal | Gagal | Bocorkan sintaks tool-call internal (<DSML invoke bash>) ke output; token bloat (7885 in) |
| qwen3.8-flash | - | Gagal | - | Tidak mengembalikan output (gagal 2x pada prompt panjang) |

Biaya/run (Rp): glm ~0.6, deepseek ~2.4, luna ~3.1.

Keputusan: Lead tetap `nara/glm-5.3-flash` untuk harian (9x lebih cepat, 5x lebih murah dari luna, patuh jebakan).
`gpt-5.6-luna` hanya untuk tugas kompleks sesekali via override manual bila akurasi > kecepatan.
`deepseek-v4.1-flash` dan `qwen3.8-flash` didiskualifikasi sebagai Lead.
