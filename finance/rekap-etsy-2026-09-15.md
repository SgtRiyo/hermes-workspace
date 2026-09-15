# Rekap Etsy — 2026-09-15

Bagian: Finance. Terkait: [[../obsidian/proyek/etsy|Etsy — Toko Online]] · klien [[../obsidian/klien/sigit|Sigit]].

## (a) Total Revenue

**data kosong / belum ada penjualan.**

Tidak ada satu pun baris transaksi di seluruh CSV order. Total revenue = **Rp 0 / belum ada penjualan**. Angka tidak dikarang; semua kolom revenue di `etsy-weekly-metrics.csv` juga kosong.

File yang dicek:

| File | Isi | Hasil |
|---|---|---|
| `/home/ubuntu/etsy-orders-2026-08-29.csv` | header saja (order_id,date,buyer,items,total,shipping_cost,status,tracking,label_printed,shipped_date,notes) | 0 baris order |
| `/home/ubuntu/etsy-orders-2025-08-25.csv` | header saja, sama | 0 baris order |
| `/home/ubuntu/etsy-orders-2025-08-26.csv` | header saja, sama | 0 baris order |
| `/home/ubuntu/etsy-weekly-metrics.csv` | 7 baris minggu, kolom `revenue`/`orders` KOSONG (kecuali 2 baris berisi `0`) | tidak ada nilai revenue |

Catatan `etsy-weekly-metrics.csv`: hanya baris `2025-08-26` dan `2025-08-28` yang terisi eksplisit `revenue=0, orders=0`. Baris mingguan 2026 (18–24 Agu s/d 15–21 Sep) seluruhnya kosong, belum diisi.

## (b) Top-3 Produk Terlaris

**data kosong / belum ada penjualan — tidak ada produk terjual, sehingga top-3 tidak dapat dihitung.**

Kolom `items` di semua CSV order kosong (0 baris). Tidak ada dasar untuk ranking produk.

Produk yang *direncanakan* (belum terjual, dari log deep-work — bukan data penjualan):
- Instagram Calendar Bundle — $14.99
- TikTok 30-Day Challenge — $12.99
- IG Reel Planner — $14.99
- YT Shorts Calendar — $12.99

## (c) Daftar Komplain

**Tidak ada komplain.** 0 order → 0 komplain, 0 refund, 0 dispute, 0 case.

Pencarian kata kunci (`komplain`, `complaint`, `refund`, `dispute`, `chargeback`, `sengketa`) di seluruh `/home/ubuntu` hanya menemukan teks template/role, bukan catatan komplain nyata:
- `hermes-workspace/sales/AGENTS.md` — aturan "eskalasi ke Lead bila komplain sensitif" (prosedur, bukan kasus).
- `etsy-deep-work/daily-checklist-template.md` — checklist template balasan customer ("□ refund"), bukan komplain tercatat.
- Beberapa file `etsy-canvas-plan/*` — materi riset/rencana, bukan kasus.

## Kesimpulan

Toko Etsy **belum menghasilkan penjualan** per 2026-09-15. Semua file order kosong; metrik mingguan belum diisi. Tidak ada komplain. Tidak ada angka yang dikarang.

Blocker yang tercatat di log: implementasi listing butuh Canva/Etsy manual (tidak ada akses browser/API untuk eRank, Etsy, Canva).

## Aksi lanjut

1. Isi `etsy-weekly-metrics.csv` tiap minggu (revenue, orders, AOV, views).
2. Setelah order pertama masuk, salin ke `etsy-orders-*.csv` agar rekap ini bisa dihitung ulang.
