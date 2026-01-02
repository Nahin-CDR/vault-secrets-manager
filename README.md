
# vault-secrets-manager

Run **HashiCorp Vault locally** on Ubuntu using **Docker Compose**, with **KV Secrets Engine v2** enabled for secure and versioned secret management.

This repository demonstrates a clean, practical setup of Vault for local development, DevOps practice, and learning secure secrets handling.

---

## Features

- HashiCorp Vault running in Docker
- Persistent file storage
- KV Secrets Engine (Version 2)
- Web UI enabled
- Suitable for CLI, UI, and Postman usage

---

## Tech Stack

- HashiCorp Vault  
- Docker & Docker Compose  
- Linux (Ubuntu)

---

## Project Structure

```text
vault-secrets-manager/
├── docker-compose.yml
├── config/
│   └── vault.hcl
├── data/        # persistent data (gitignored)
├── logs/        # logs (gitignored)
└── README.md
````

---

## Usage

### Start Vault

```bash
docker compose up -d
```

## To unseal key
```bash

docker exec -e VAULT_ADDR=http://127.0.0.1:8200 -it vault vault operator init -key-shares=5 -key-threshold=3

```


### Open UI

```
http://127.0.0.1:8200
```

### Restart

```bash
docker compose down
docker compose up -d
```

Vault will require unsealing after restart, but secrets remain intact.

---

## Notes

* Secrets are stored using KV v2 with versioning
* Root token is used only for local testing
* `data/` and `logs/` are excluded from Git for security

---

## Author

**Nazmul Haque Nahin** <br>
Software Engineer | DevOps & Infrastructure

GitHub: [https://github.com/Nahin-CDR](https://github.com/Nahin-CDR)



---

