# Self-hosted Resin (binary) example

Copy these files when running the Resin gateway without Docker:

- `resin.service.example` → `/etc/systemd/system/resin.service`
- `resin.env.example` → `/etc/resin.env` (mode 0600)

Then:

```bash
install -m 0755 resin /opt/resin/resin
mkdir -p /var/lib/resin
systemctl daemon-reload
systemctl enable --now resin
```

Admin UI listens on `RESIN_PORT` (2260 by default). Put the sticky HTTP/SOCKS gateway on a dedicated port via Resin config if you split UI and proxy.
