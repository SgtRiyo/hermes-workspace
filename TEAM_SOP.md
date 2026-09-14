# SOP Tim Hermes — Onboarding Agen Baru

Prinsip: 1 agen = 1 role + 1 workspace + skill/tool tersendiri. Dilarang membuat agen serba-bisa (mix context menurunkan akurasi).

## Struktur tim

| Agen | Workspace | Model | Tugas |
|---|---|---|---|
| Lead | `hermes-workspace/lead/` | `nara/glm-5.3-flash` (Nara, khusus Lead) | Merencanakan, me-manage sub-agent via `delegate_task`, troubleshooting. |
| Finance | `hermes-workspace/finance/` | `kr/deepseek-3.2` (hemat) | Rekap keuangan, baca nota, ringkasan rutin. |
| Sales | `hermes-workspace/sales/` | `kr/deepseek-3.2` | Follow-up klien, rekap order (contoh: Etsy). |
| Marketing | `hermes-workspace/marketing/` | `kr/deepseek-3.2` | Draft konten, riset keyword, jadwal posting. |
| Assistant | `hermes-workspace/assistant/` | `kr/deepseek-3.2` | Catatan harian, pengingat, tugas umum. |

Fallback otomatis (bila Lead rate-limit): `nara/glm-5.3-flash` → `kr/deepseek-3.2` → `kr/qwen3-coder-next` (lihat `fallback_providers` di `~/.hermes/config.yaml`).

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
2. DILARANG membuat folder baru di dalam `obsidian/` — hanya `klien/`, `proyek/`, `sop/` yang boleh ada. Butuh kategori baru? Minta Lead memutuskan dulu.
2. Isi: ringkasan 1-2 baris + tanggal + link dua arah (`[[../klien/budi|Budi]]` <-> `[[../proyek/totebag-budi|totebag Budi]]`).
3. Update file terkait (mis. proyek lama yang dapat order baru).
4. Verifikasi: `ls`/baca ulang file sebelum menjawab. Balasan wajib menyebut path file yang ditulis.
5. Bila didelegasikan: induk memverifikasi file anak benar-benar ada sebelum lapor "dicatat". Memori bawaan boleh dipakai sebagai TAMBAHAN, bukan PENGGANTI.

## Aturan batch delegasi (anti-duplikat, anti file-hantu)

1. Satu batch = satu dispatch. DILARANG me-dispatch ulang batch yang sudah parsial sukses hanya karena 1 task gagal — ambil hasil parsial, dispatch ULANG HANYA task yang gagal.
2. Jangan `kill` delegasi yang masih berjalan kecuali macet >10 menit tanpa output. Kill = kerja + token terbuang.
3. VERIFIKASI SEBELUM LAPOR: setiap path file yang disebut di jawaban HARUS sudah dicek ada via `ls`/baca ulang di turn yang sama. Path yang belum terverifikasi = tidak boleh dilaporkan. Melaporkan file yang tidak ada (file hantu) adalah pelanggaran SOP.
4. Semua output anak WAJIB di dalam workspace agen masing-masing (lihat ATURAN OUTPUT PATH di tiap `AGENTS.md`). File di luar workspace = tolak, minta anak tulis ulang di path benar.
