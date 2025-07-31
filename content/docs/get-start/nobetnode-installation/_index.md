---
title: "Nöbetnode Installation"
next: telegram
---

For ban ip on every marznode, you need to install Nöbetnode on each node server.

When an ip cached on Nöbetci, Nöbetnodes bans the ip using iptables on linux server.

Install Nöbetnode with this command:

```bash
sudo bash -c "$(curl -sL https://github.com/muttehitler/nobetnode/raw/main/script.sh)" @ install
```

- You'd notice the logs, which you could stop watching by pressing `Ctrl+C`; The process will continue running normally.
- the configuration file can be found at `/etc/opt/nobetnode/.env` ([.env file doc](/docs/configuration/nobetnode))
- Data files will be placed at `/var/lib/nobetnode`; e.g. the client certificate.

{{< callout type="warning" >}}
  To install the latest **nightly** release use the `--nightly` flag.
{{< /callout >}}

Then get client certificate using nobetci cli on main server

```bash
nobetci cli node settings
```

After getting client certificate, write it in this file on node server: `/var/lib/nobetnode/client.pem`

```bash
nano /var/lib/nobetnode/client.pem
```

Up the Nöbetnode

```bash
nobetnode up
```

After that add your Nöbetnode to Nöbetci with this command (Run it on main server and replace your node name with {node_name}):

```bash
nobetci cli node add -n {node_name} -a 127.0.0.1 -p 51031
```

Then restart Nöbetci

```bash
nobetci restart
```

- If you add Nöbetnode with api, no need to restart

To see the help message of the Nöbetnode script, run the following command

```bash
nobetnode --help
```