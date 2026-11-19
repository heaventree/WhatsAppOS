# WhatsAppOS - Heaventree OpenWA deployment

Heaventree's fork of [rmyndharis/OpenWA](https://github.com/rmyndharis/OpenWA) (MIT, imported at v0.30.3) used as the
WhatsApp gateway for client **support** in the Heaventree hub. Support/inbound-reply use only; no marketing or bulk sending.

- Runtime: Dokploy, project **AGENT TOOLS**, Compose app `OpenWA` (`deploy/dokploy/docker-compose.yml`)
- Stack: OpenWA API + Postgres 16 + Redis 7, whatsapp-web.js engine, send pacing on
- Secrets: set in Dokploy env only (see `.env.example`); never commit `.env`
- Hub integration: scoped non-admin API key + signed webhook per session (do not give the hub the master key)
- Upstream docs: see `docs/` and the root `README.md`

Notes: docker-socket-proxy omitted on purpose (host-root-equivalent risk). Unofficial WhatsApp clients carry ban risk; use a dedicated number.
