# FAQ Telegram/Gateway (fakta)

- Bot Telegram terhubung ke gateway Hermes (`telegram: connected`).
- Chat: DM pemilik + grup Superbot (lihat `~/.hermes/channel_directory.json`).
- Gateway: `hermes-gateway.service` (systemd). Restart aman: `sudo systemctl restart hermes-gateway`.
- Jangan menjalankan dua instance gateway (konflik polling Telegram).
- Dashboard: `https://hermes.sigitstudio.com` (tunnel → `127.0.0.1:9119`).
