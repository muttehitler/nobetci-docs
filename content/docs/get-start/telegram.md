---
title: "Telegram"
---

Sends status and banned ips logs from telegram

### Setup

- You need to create a Telegram bot through [BotFather](https://t.me/BotFather) and copy the bot token to use it in the next step.

- Since access to this bot will only be available to you or a limited list of administrators, you need to specify the Telegram IDs of those who are authorized to use it. To get your own Telegram ID, refer to the [IDBot](https://t.me/myidbot).

- Now you need to define all the variables in Nöbetci. To do this, you need to enable the variables in the .env file by removing the leading # comments from them and entering the required values in the file.

```sh
TELEGRAM_API_TOKEN = 123456789:AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA
TELEGRAM_ADMIN_ID = 987654321, 123456789
```

| Variable           | Description                                                                                  |
| ------------------ | -------------------------------------------------------------------------------------------- |
| TELEGRAM_API_TOKEN | Telegram bot API token (get token from [@botfather](https://t.me/botfather))                 |
| TELEGRAM_ADMIN_ID  | Numeric Telegram ID of admin (use [@myidbot](https://t.me/myidbot) to found your ID) |

Then, restart Nöbetci using the following command to apply the changes.

```bash
nobetci restart
```