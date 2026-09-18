# Nara Watch v2 — 2026-09-18

Skrip `~/.hermes/scripts/nara_free_watch.sh` ditulis ulang:
- Kandidat 13 → 5 model yang dipakai (ID resmi, tanpa suffix `-free` palsu):
  `glm-5.3-flash`, `deepseek-v4.1-flash`, `gpt-5.6-luna`, `qwen3.8-flash`, `mimo-v2.5`.
- Tambah cek harga Rp/1M dari `GET /v1/models` + snapshot `cron/nara_price_last.txt`
  (format `model:in:out`); SEMUA perubahan dilapor ke Telegram.
- Jadwal `0 */12 * * *`, deliver telegram, no-agent — tidak berubah.

Dry-run 08:48 UTC: hidup 3/5 (gpt-5.6-luna + mimo-v2.5 flapping — 200 saat benchmark,
mati saat dry-run; bynara free-tier memang flapping). Harga tercatat semua.
Baris "Mati: agnes-2.5-flash,deepseek-v4-flash-vision-exp" = noise sekali saja
(sisa snapshot era 13 kandidat, snapshot sudah tertimpa).
