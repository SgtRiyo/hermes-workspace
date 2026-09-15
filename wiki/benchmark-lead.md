# Benchmark Lead — 2026-09-14

Tugas identik ke 4 model: rancang delegasi paralel (rekap CSV + 2 ide konten + ringkas SOP), format baku TUJUAN/BAGIAN/KRITERIA/LANGKAH.

| Model | Waktu | Token in/out | Biaya/run (Rp) | Format | Catatan |
|---|---|---|---|---|---|
| glm-5.3-flash | 8.7s | 182/465 | ~0.46 | Sempurna | Kriteria konkret (nama file, top-3, tabel); split tepat |
| deepseek-v4.1-flash | 8.2s | 7748/1291 | ~3.4 | Baik | Token bloat 7x lipat vs glm |
| gpt-5.6-luna | 19.0s | 169/657 | ~1.47 | Cukup | Terlambat; tambah agen Sales ke-4 tanpa diminta |
| qwen3.8-flash | 15.7s | 219/608 (+1140 reasoning) | ~1.68 | Baik minus | Salah hierarki: suruh sub-agent menjalankan delegate_task; run pertama gagal |

Keputusan: Lead tetap `nara/glm-5.3-flash` — termurah, tercepat, format paling patuh, stabil di produksi.
