# SOP Tim Hermes — Onboarding Agen Baru

Prinsip: 1 agen = 1 role + 1 workspace + skill/tool tersendiri. Dilarang membuat agen serba-bisa (mix context menurunkan akurasi).

## Struktur tim

| Agen | Workspace | Model | Tugas |
|---|---|---|---|
| Lead | `hermes-workspace/lead/` | `Coding` (flagship) | Merencanakan, me-manage sub-agent via `delegate_task`, troubleshooting. |
| Finance | `hermes-workspace/finance/` | `Nara-Free` (hemat) | Rekap keuangan, baca nota, ringkasan rutin. |
| Sales | `hermes-workspace/sales/` | `Nara-Free` | Follow-up klien, rekap order (contoh: Etsy). |
| Marketing | `hermes-workspace/marketing/` | `Nara-Free` | Draft konten, riset keyword, jadwal posting. |
| Assistant | `hermes-workspace/assistant/` | `Nara-Free` | Catatan harian, pengingat, tugas umum. |

Fallback otomatis (bila Lead rate-limit): `Nara-Free` → `nara/glm-5.3-free` (lihat `fallback_providers` di `~/.hermes/config.yaml`).

## Onboarding agen baru (dilakukan Lead)

1. Buat folder `hermes-workspace/<nama>/` + `AGENTS.md` berisi role, model, toolset, batasan.
2. Daftarkan skill/SOP spesifik di folder agen (contoh: `SOP.md`), jangan campur antar agen.
3. Catat agen baru di tabel atas + buat 1 cron test kecil (`hermes cron`) bila butuh jadwal.
4. Uji delegasi: Lead panggil `delegate_task` ke agen baru, verifikasi ringkasan kembali.
5. Arsipkan skill tak terpakai via `hermes curator` (tidak pernah hapus permanen).

## Aturan isolasi

- Sub-agent tidak membaca workspace agen lain. Rujukan silang hanya via Lead.
- Fakta/SOP abadi → `hermes-workspace/wiki/`. Pengalaman harian → `hermes-workspace/obsidian/`.
- Kredensial hanya di `~/.hermes/.env` (perm 600), tidak pernah di workspace.

## Aturan pencatatan wajib (setiap agen, tanpa kecuali)

Setiap pesan yang memuat fakta klien / order / proyek / deadline / nominal / keputusan HARUS berakhir dengan file, bukan hanya memori bawaan:

1. Tulis file: `obsidian/klien/<nama>.md`, `obsidian/proyek/<nama>.md`, atau `obsidian/sop/<topik>.md`.
2. Isi: ringkasan 1-2 baris + tanggal + link dua arah (`[[../klien/budi|Budi]]` <-> `[[../proyek/totebag-budi|totebag Budi]]`).
3. Update file terkait (mis. proyek lama yang dapat order baru).
4. Verifikasi: `ls`/baca ulang file sebelum menjawab. Balasan wajib menyebut path file yang ditulis.
5. Bila didelegasikan: induk memverifikasi file anak benar-benar ada sebelum lapor "dicatat". Memori bawaan boleh dipakai sebagai TAMBAHAN, bukan PENGGANTI.
