# SOP Unit Economics & Rekap (Finance)

Sumber: ringkasan `finance-financial-analyst` dari [msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents) (MIT). File lengkap: `REFERENCE-financial-analyst.md`.

Kapan dipakai: rekap revenue Etsy, hitung fee, keputusan ads.

## Aturan analisis (wajib)

1. **Asumsi dulu, kesimpulan belakangan**. Setiap angka proyeksi wajib punya baris asumsi + sumber.
2. **Fakta ≠ proyeksi**: label jelas. Data historis (`etsy-weekly-metrics.csv`) = fakta. "Kalau 10 sales/bulan" = proyeksi.
3. **Selalu 3 skenario**: base / upside / downside. Jangan satu angka tunggal.
4. **Sensitivitas**: jika kesimpulan berubah saat 1 asumsi geser 15%, tulis eksplisit "rekomendasi ini rapuh".
5. **Tanpa data = "data kosong"**. Tidak ada angka karangan (preseden: rekap-etsy-2026-09-15).

## Formula tetap Etsy digital

```
Net per sale = harga - fee Etsy (listing $0.20 + transaction 6.5% + payment ~3% + $0.25) - ads per sale
≈ harga × 0.90 - $0.45 - ads per sale
```

Contoh base case (tulis ulang per listing di rekap):

| Skenario | Sales/bln | Harga | Net/sale | Net/bln |
|---|---|---|---|---|
| Downside | 3 | $11.99 | ±$10.30 | ±$31 |
| Base | 10 | $12.99 | ±$11.20 | ±$112 |
| Upside | 25 | $14.99 | ±$13.00 | ±$325 |

(Net = harga × 0.90 - $0.45; ads dihitung terpisah, jangan digabung sebelum ada data spend.)

## Kill-rule ads (dari rencana 30 hari)

- Kill campaign jika spend $10 tanpa favorite/save.
- Scale jika ROAS > 2.5 selama ≥5 hari.
- Spend $30 tanpa sales tapi fav rate >3% → lanjut optimasi (thumbnail/judul), bukan kill.

## Output

Rekap bulanan/mingguan di workspace ini → link dua arah ke `../obsidian/proyek/etsy.md`. Anomali (angka tidak konsisten antar file) = lapor Lead, jangan diputuskan sendiri.
