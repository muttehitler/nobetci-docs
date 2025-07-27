---
title: "Nöbetci Installation"
# date: 2025-07-23T00:30:53+03:30
# draft: true
next: about
---

To get started, you just need a linux machine.

{{< callout type="info" >}}
TL;DR for installation:

Install Nöbetci app first 

```bash
sudo bash -c "$(curl -sL https://github.com/muttehitler/nobetci/raw/main/script.sh)" @ install
```

Then install Nöbetnode for each nodes (even local node) 

```bash
sudo bash -c "$(curl -sL https://github.com/muttehitler/nobetnode/raw/main/script.sh)" @ install
```

After that add your Nöbetnode to Nöbetci with this command:

```bash
nobetci cli node add -n local -h 127.0.0.1 -p 51031
```

Then restart Nöbetci

```bash
nobetci restart
```

{{< /callout >}}

Nöbetci currently supports the following databases. SQLite is preferred for small setups, while MariaDB is recommended for larger configurations.
{{< tabs items="mariadb,mysql,sqlite" >}}

{{< tab >}}```bash
sudo bash -c "$(curl -sL https://github.com/muttehitler/nobetci/raw/main/script.sh)" @ install --database mariadb

````{{< /tab >}}
  {{< tab >}}```bash
sudo bash -c "$(curl -sL https://github.com/muttehitler/nobetci/raw/main/script.sh)" @ install --database mysql
```{{< /tab >}}
  {{< tab >}}```bash
sudo bash -c "$(curl -sL https://github.com/muttehitler/nobetci/raw/main/script.sh)" @ install
```{{< /tab >}}

{{< /tabs >}}

{{< callout type="warning" >}}
  To install the latest **nightly** release use the `--nightly` flag.
{{< /callout >}}

Once the installation is complete:

- You'd notice the logs, which you could stop watching by pressing `Ctrl+C`; The process will continue running normally.
- the configuration file can be found at `/etc/opt/nobetci/.env` ([.env file doc](/docs/configuration/nobetci))
- Data files will be placed at `/var/lib/marzneshin`; e.g. the sqlite database.

Then install Nöbetnode for ban ip's on current node

```bash
sudo bash -c "$(curl -sL https://github.com/muttehitler/nobetnode/raw/main/script.sh)" @ install
```

Next, you need to add local Nöbetnode to Nöbetci 

```bash
nobetci cli node add -n local -h 127.0.0.1 -p 51031
````

Then restart for update nodes


```bash
nobetci restart
```

- If you add Nöbetnode with api, no need to restart

To see the help message of the Nöbetci script, run the following command

```bash
nobetci --help
```