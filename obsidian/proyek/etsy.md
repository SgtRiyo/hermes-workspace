# Etsy — Toko Online

Usaha milik [[../klien/sigit|Sigit]]. Cron deep-work mingguan pernah jalan dari Hermes (job dihapus 2026-08-30, bisa dibuat ulang).

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
