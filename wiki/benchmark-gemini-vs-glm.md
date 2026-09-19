# Gemini 3.8 Flash High vs GLM 5.3 Flash — 2026-09-18

## Harga resmi (Rp/1M, in-out)
- glm-5.3-flash: 264 - 881 | 1M ctx, vision+reasoning
- gemini-3.8-flash-high: 662 - 3311 | 1M ctx, vision (no reasoning flag)

## Tes 1 — format ketat (2 ide, hook ≤12 kata)
Keduanya SEMPURNA. gemini 15s/159 tok (Rp0.34), glm 12s/196 tok (Rp0.14).

## Tes 2 — nalar (harga jual + laba)
Soal: modal 25rb + ongkir 10rb + fee 8%, target untung 15rb; lalu laba 40pcs.
Keduanya BENAR (P≈Rp54.348, laba Rp600.000).
- gemini: rumus LaTeX rapi + saran pembulatan. 12s/350 tok (Rp0.87).
- glm: menurunkan persamaan langkah-demi-langkah + VERIFIKASI balik
  (54.500 → laba 15.140 ✅). 5s/397 tok (Rp0.29). Terpotong limit (finish=length).

## Vonis
- Pintar: seri cenderung glm (verifikasi mandiri; gemini presentasi lebih rapi).
- Cost: glm ~3x lebih murah per tugas.
- Speed: glm menang (5-12s vs 12-15s).
- Keseluruhan: PERTAHANKAN glm-5.3-flash sebagai Lead. Gemini tidak
  menawarkan keunggulan yang membenarkan harga 2.5-3x lipat.
