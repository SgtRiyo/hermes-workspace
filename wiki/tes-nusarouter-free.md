# Tes model free NusaRouter — 2026-09-15

| Model | Hasil |
|---|---|
| meta-llama/llama-3.1-70b-instruct:free | ✅ Hidup, format dipatuhi, Indonesia natural |
| openai/gpt-oss-120b:free | ⚠️ Hidup tapi jawaban masuk `reasoning_content`, `content` kosong — pipeline Hermes (baca content) akan terlihat gagal |
| z-ai/glm-5.3-free | ❌ `upstream_rejected` dari upstream Nusa |

Catatan: request python urllib diblokir proteksi bot Cloudflare (403) — pakai curl/UA browser.
Key Nusa dirotasi setelah tes (terpapar di chat).
