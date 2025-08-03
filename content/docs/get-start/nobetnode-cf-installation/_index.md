---
title: "Nöbetnode CF Installation"
next: telegram
weight: 3
---

For ban ip on cloudflare, you need to install Nöbetnode CF on a server.

When an ip cached on Nöbetci, Nöbetnode CF bans the ip using Cloudflare Firewall Rules API.

Install Nöbetnode CF with this command:

```bash
sudo bash -c "$(curl -sL https://github.com/muttehitler/nobetnode-cf/raw/main/script.sh)" @ install
```

During the installation, you must enter your Cloudflare API Token.
You can get API Token from Cloudflare page > Manage Account > Account API Tokens.

- You'd notice the logs, which you could stop watching by pressing `Ctrl+C`; The process will continue running normally.
- the configuration file can be found at `/etc/opt/nobetnode-cf/.env` ([.env file doc](/docs/configuration/nobetnode-cf))
- Data files will be placed at `/var/lib/nobetnode-cf`; e.g. the client certificate.

{{< callout type="warning" >}}
  To install the latest **nightly** release use the `--nightly` flag.
{{< /callout >}}

Then get client certificate using nobetci cli on main server

```bash
nobetci cli node settings
```

After getting client certificate, write it in this file on node server: `/var/lib/nobetnode-cf/client.pem`

```bash
nano /var/lib/nobetnode-cf/client.pem
```

Up the Nöbetnode CF

```bash
nobetnode-cf up
```

After that add your Nöbetnode CF to Nöbetci with this command (Run it on main server and replace your node name with {node_name}):

```bash
nobetci cli node add -n {node_name} -a 127.0.0.1 -p 51032
```

Then restart Nöbetci

```bash
nobetci restart
```

- If you add Nöbetnode CF with api, no need to restart

To see the help message of the Nöbetnode CF script, run the following command

```bash
nobetnode-cf --help
```