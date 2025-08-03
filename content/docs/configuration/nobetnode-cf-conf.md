---
title: "Nöbetnode CF Configurations"
weight: 4
---

> You can set settings below using environment variables or placing them in `.env` file.

## Basic

| Variable                        | Description                                                                                           |
| ------------------------------- | ----------------------------------------------------------------------------------------------------- |
| SERVICE_ADDRESS                 | Bind application to this host (default: `0.0.0.0`)                                                    |
| SERVICE_PORT                    | Bind application to this port (default: `51031`)                                                      |
| INSECURE                        | Connection security                                                                                   |
| SSL_CLIENT_CERT_FILE            | Client certificate path (default: /var/lib/marznode/client.pem)                                       |
| SSL_CERT_FILE                   | SSL cert file path                                                                                    |
| SSL_KEY_FILE                    | SSL key file path                                                                                     |

## Cloudflare
| Variable                        | Description                                                                                           |
| ------------------------------- | ----------------------------------------------------------------------------------------------------- |
| CF_TOKEN                        | Cloudflare API Token                                                                                  |
| UNBAN_ALL_IN_STARTUP            | Unban all users that banned on cloudflare (defaulat: False)                                           |

## Development and Documentation

| Variable | Description                                                                                 |
| -------- | ------------------------------------------------------------------------------------------- |
| DEBUG    | Debug mode for development (default: `False`)                                               |

## .env File Example

```sh
SERVICE_ADDRESS="0.0.0.0"
SERVICE_PORT=51031
INSECURE=True
CF_TOKEN="token"
UNBAN_ALL_IN_STARTUP=True
SSL_CLIENT_CERT_FILE=/var/lib/nobetnode/client.pem
SSL_KEY_FILE=/var/lib/nobetnode/server.key
SSL_CERT_FILE=/var/lib/nobetnode/server.cert
DEBUG=True
```