# Etsy — Toko Online

Usaha milik [[../klien/sigit|Sigit]]. Cron deep-work mingguan pernah jalan dari Hermes (job dihapus 2026-08-30, bisa dibuat ulang).

Proyek lanjutan: [[etsy-digital-templates]] — produk digital editable (PRD 2026-09-21).

Proses kerja mengikuti [[../sop/onboarding-agen|onboarding agen]] dan fakta abadi di `../../wiki/faq-etsy.md`.

## 2026-09-15 — Estimasi modal 50 totebag (Finance)

Supplier kain [[../klien/sari|Sari]] kasih kanvas 12oz Rp45.000/meter. Finance bikin estimasi modal produksi 50 totebag: 28 m kain (25 m + 10% waste), total modal **Rp2.455.000** = **Rp49.100/unit**, harga jual saran **Rp89.000/unit** (markup ±81%, sudah cover fee Etsy ±11%). Semua asumsi (lebar kain 150 cm, 0,5 m/bag, tali Rp6.000/m, ongkos jahit Rp12.000/bag, dll) ditulis eksplisit di file dan masih perlu diverifikasi ke supplier.

Detail: [[../../finance/estimasi-modal-50-totebag|Estimasi modal 50 totebag]]

## 2026-09-15 — Supplier baru + estimasi modal

Supplier baru [[../klien/sari|Sari]]: kain kanvas 12oz Rp45.000/meter, kontak 0812-xxxx. Finance mengerjakan rekap Etsy dan estimasi modal 50 totebag.

## 2026-09-15 — Rekap Etsy (Finance): belum ada penjualan

Finance menyelesaikan rekap CSV Etsy → [[../../finance/rekap-etsy-2026-09-15|rekap-etsy-2026-09-15]].

- **Total revenue: data kosong / belum ada penjualan** (Rp 0). Tidak ada baris order.
- **Top-3 produk terlaris: tidak dapat dihitung** — belum ada produk terjual.
- **Komplain: tidak ada** (0 order → 0 komplain/refund/dispute).

File yang dicek: `etsy-orders-2026-08-29.csv`, `etsy-orders-2025-08-25.csv`, `etsy-orders-2025-08-26.csv` (semuanya header saja, 0 baris), dan `etsy-weekly-metrics.csv` (kolom revenue/orders kosong; hanya 2 baris berisi `0`).

Blocker: implementasi listing butuh Canva/Etsy manual — tidak ada akses browser/API (eRank, Etsy, Canva).

## 2026-09-19 — Impor 7 SOP agency-agents (Lead)

Lead mengimpor 7 SOP ringkas dari repo [msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents) (MIT) untuk mendukung rencana 30 hari produk digital planner (fokus: planner digital, 2-3 jam/hari, ads kecil $3/hari). Fakta sumber: [[../../wiki/sop-impor-agency-agents|sop-impor-agency-agents]].

- Lead: `lead/SOP-trend.md` (+ `REFERENCE-trend-researcher.md`)
- Marketing: `marketing/SOP-seo-etsy.md`, `SOP-tiktok.md`, `SOP-mockup.md`, `SOP-listing-copy.md` (+ 4 REFERENCE)
- Finance: `finance/SOP-unit-economics.md` (+ REFERENCE)
- Sales: `sales/SOP-followup.md` (+ REFERENCE)

Aturan pakai: SOP ringkas dibaca rutin, REFERENCE hanya bila butuh detail (anti spiral tool call per [[../../sop/aturan-pencatatan|aturan hemat baca]]). Rencana 30 hari: Fase 0 audit → Fase 1 produksi 10 listing (1 master Canva → 10 varian) → Fase 2 launch + ads → Fase 3 scale/kill per gate hari 14/21/30.

## 2026-09-19 — Tier 1: generator paket-publish (Lead)

Otomatisasi Tier 1 jalan: `scripts/generate-paket-publish.py` membaca 4 spec `etsy-designs/listing-*-spec.json` → generate 4 paket siap-paste di `etsy-designs/paket-publish/`. Tanpa API/Canva/Etsy — sisanya manual per checklist seksi 7 tiap paket.

Output (terverifikasi `ls`):
- `paket-publish-listing-1-2026-08-29.md` (IG Reel Planner $14.99)
- `paket-publish-listing-2-2026-08-29.md` (YT Shorts Calendar $12.99)
- `paket-publish-listing-1-2025-08-26.md` (IG Content Calendar Bundle $14.99)
- `paket-publish-listing-2-2025-08-26.md` (TikTok 30-Day Challenge $12.99)

Hasil validasi: 4 judul kini ≤140 char (judul spec listing-2-2026-08-29 dipangkas dari 143). Anti-kanibalisasi keyword utama lulus (4 keyword berbeda). Warning tersisa: beberapa tag juga muncul di judul (Etsy hitung dobel) — ditandai di tiap paket, perbaikan tag dilakukan saat paste manual bila mau optimal.

Langkah user berikutnya: buka paket → eksekusi checklist seksi 7 (Canva → Etsy), mulai dari listing-1-2026-08-29.
