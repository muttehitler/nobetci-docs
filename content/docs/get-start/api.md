---
title: "API"
weight: 4
---

## Setup

To setup api, you need to set three env variable on `/var/lib/nobetci/.env`

```sh
SECRET_KEY="super_secret"
API_USERNAME="user"
API_PASSWORD="pass"
```

Then restart Nöbetci for apply changes

```bash
nobetci restart
```

### SECRET_KEY

You must generate a strong key like lkdsf#!@2131

Its for generate jwt tokens

### API_USERNAME

Username for API

### API_PASSWORD

Password for user

## Doc for API

For see api doc, you need to set this environment:

```sh
DOCS=True
```
Then restart Nöbetci for apply changes

```bash
nobetci restart
```

Now you can see docs on `https://<your_ip>:<port>/docs` and `https://<your_ip>:<port>/redoc`
