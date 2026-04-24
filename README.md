## Local TLS Baseline for Future API Consumers

If a future repo created from this template will call the VaultWares API during local development, standardize on:

- `mkcert` for local development certificates
- `https://localhost:8000` for the local API base URL
- `https://localhost:5174` for a local web frontend when using Vite

Do not introduce new local API consumers that default to plaintext `http://localhost:*` when HTTPS is available.
