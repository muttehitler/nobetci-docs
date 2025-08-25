---
title: "Nöbetci Configuration"
weight: 1
---

> You can set settings below using environment variables or placing them in `.env` file.

## Basic

| Variable                        | Description                                                                                           |
| ------------------------------- | ----------------------------------------------------------------------------------------------------- |
| UVICORN_HOST                    | Bind application to this host (default: `0.0.0.0`)                                                    |
| UVICORN_PORT                    | Bind application to this port (default: `8307`)                                                       |
| UVICORN_UDS                     | Bind application to a UNIX domain socket                                                              |
| UVICORN_SSL_CERTFILE            | SSL certificate file to have application on https                                                     |
| UVICORN_SSL_KEYFILE             | SSL key file to have application on https                                                             |
| SQLALCHEMY_DATABASE_URL         | Database URL ([SQLAlchemy's docs](https://docs.sqlalchemy.org/en/20/core/engines.html#database-urls)) |
| JWT_ACCESS_TOKEN_EXPIRE_MINUTES | Expire time for the Access Tokens in minutes, `0` considered as infinite (default: `1440`)            |


## Limit Configurations

| Variable           | Description                                                            |
| ------------------ | -----------------------------------------------------------------------|
| DEFAULT_LIMIT      | Default limit for unrecorded users (0 to unlimited)(default: 0)        |
| BAN_INTERVAL       | Ban time for ip (default: 10)                                          |
| STL                | Same time limit (default: 10)                                          |
| IUL                |                                                                        |
| BAN_LAST_USER      | Ban last connected ip (default: False)                                 |

## Panel Configuration

| Variable           | Description                                                            |
| ------------------ | -----------------------------------------------------------------------|
| PANEL_ADDRESS      | Panel Address (Must be without https:// or http:// : pnl.example.com)  |
| PANEL_USERNAME     | Panel username                                                         |
| PANEL_PASSWORD     | Panel password                                                         |

## API

| Variable           | Description                                                 |
| ------------------ | ------------------------------------------------------------|
| SECRET_KEY         | Secret key for JWT                                          |
| API_USERNAME       | API username                                                |
| API_PASSWORD       | API password                                                |
| ALGORITHM          | JWT authentication encryption algorithm (default: "HS256")  |


## Telegram

| Variable           | Description                                                                          |
| ------------------ | -------------------------------------------------------------------------------------|
| TELEGRAM_API_TOKEN | Telegram bot API token (get token from [@botfather](https://t.me/botfather))         |
| TELEGRAM_ADMIN_ID  | Numeric Telegram ID of admin (use [@myidbot](https://t.me/myidbot) to found your ID) |
| TELEGRAM_LOGS      | Send logs from telegram (default: True)                                              |

## Development and Documentation

| Variable | Description                                                                                 |
| -------- | ------------------------------------------------------------------------------------------- |
| DOCS     | Whether API documents should be available on `/docs` and `/redoc` or not (default: `False`) |
| DEBUG    | Debug mode for development (default: `False`)                                               |

## .env File Example

```sh
UVICORN_HOST = "0.0.0.0"
UVICORN_PORT = 8307
UVICORN_UDS: "/run/nobetci.socket"
UVICORN_SSL_CERTFILE = "/var/lib/nobetci/certs/example.com/fullchain.pem"
UVICORN_SSL_KEYFILE = "/var/lib/nobetci/certs/example.com/key.pem"
BAN_INTERVAL=300
DEFAULT_LIMIT=0
STL=10
IUL=50
PANEL_USERNAME="user"
PANEL_PASSWORD="pass"
PANEL_ADDRESS="address"
SECRET_KEY="super_secret"
API_USERNAME="user"
API_PASSWORD="pass"
TELEGRAM_API_TOKEN = 123456789:AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
TELEGRAM_ADMIN_ID = 987654321, 123456789
TELEGRAM_LOGS = True
SQLALCHEMY_DATABASE_URL = "sqlite:///db.sqlite3"
SQLALCHEMY_CONNECTION_POOL_SIZE = 10
SQLALCHEMY_CONNECTION_MAX_OVERFLOW = -1
DOCS=true
DEBUG=true
ACCESS_TOKEN_EXPIRE_MINUTES = 1440
ALGORITHM=HS256
```