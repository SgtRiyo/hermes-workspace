# SOP Mockup & Prompt Gambar (Marketing)

Sumber: ringkasan `design-image-prompt-engineer` dari [msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents) (MIT). File lengkap: `REFERENCE-image-prompt-engineer.md`.

Kapan dipakai: bikin prompt untuk mockup listing digital planner (foto produk AI / ilustrasi cover) via tool `image_gen`.

## Struktur prompt 5 lapis (urutan wajib)

1. **Subject**: apa persisnya — "digital planner PDF di iPad Pro, halaman weekly spread terlihat".
2. **Environment**: surface/background — "di atas meja kayu terang, coffee cup di samping, estetik minimalis".
3. **Lighting**: "soft natural window light dari kiri, bayangan lembut".
4. **Technical**: "eye-level angle, 4:5 portrait, tajam, resolusi tinggi".
5. **Style**: "commercial product photography, clean, warm neutral palette".

## Template siap pakai — mockup planner

```
[Produk: nama planner + halaman yang terlihat] displayed on [device: iPad/laptop/printed],
positioned on [surface], styled with [props 1-2 saja],
soft natural window lighting from left, gentle shadows,
eye-level angle, 4:5 aspect ratio, sharp focus on screen/page,
commercial product photography, [brand palette] aesthetic, clean post-processing
```

Negative prompt (bila platform mendukung): `blurry text, distorted hands, watermark, cluttered background, oversaturated`.

## Aturan

1. Spesifik > samar: "soft window light dari kiri" bukan "nice lighting".
2. 1 mockup = 1 prompt terdokumentasi di file ini bila berhasil (append, jangan timpa) — biar bisa direproduksi.
3. Teks di gambar AI sering rusak → hindari minta AI menulis kata; teks judul tambahkan via Canva setelahnya.
