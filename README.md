[README.md](https://github.com/user-attachments/files/35017243/README.md)
# SvrGuard

**Intrusion detection and auto-blocking for SSH brute force, web scans and suspicious programs**

[繁體中文](README.zh-TW.md) · [Website](https://svrguard.ofuyuan.com/en/) · [Download](https://svrguard.ofuyuan.com/en/download.html) · [Features](https://svrguard.ofuyuan.com/en/features.html) · [Release notes](https://svrguard.ofuyuan.com/en/release.html) · [Forum](https://forum.ofuyuan.com/)

Built for freelancers, small teams and NAS owners looking after several machines.

> This repository is for project information and feedback. It does not contain source code.

![The three-layer protection loop](https://svrguard.ofuyuan.com/images/three_layer_loop_ring_en.png)

## The three-layer protection loop

Three layers of protection guard your host from three angles: analyzing system logs, checking for suspicious programs, and watching for resource anomalies.

- **Layer 1: Analyzing system logs** — It analyses your web and SSH logs and writes attacking sources into the system firewall. Rules come built in, no regexes to write; every block shows which rule fired and which log lines.
- **Layer 2: Checking for suspicious programs** — Every check looks for what intruders tend to leave behind: backdoors that start at boot, programs running from temp or hidden directories, a tampered preload library, a password login that succeeds after repeated failures, the host connecting out to a mining pool. When it finds one it sends you an alert, and you decide what to do.
- **Layer 3: Watching for resource anomalies** — It keeps watching CPU, memory and disk. If the machine is quietly mining or filling its disk, you are alerted once a threshold is crossed, through the same channel as attack alerts.

## Install

```sh
curl -fsSL https://svrguard.ofuyuan.com/install.sh | sudo sh
```

This one line is for Linux and macOS (Apple Silicon). On a Synology NAS, install the DSM package from the [Download](https://svrguard.ofuyuan.com/en/download.html) page instead; the deb / rpm / tar.gz packages are there too. Which logs each platform reads is on the [Features](https://svrguard.ofuyuan.com/en/features.html) page.

## Screenshots

![Attack map](https://svrguard.ofuyuan.com/images/attack-map-en.png)

![Local dashboard](https://svrguard.ofuyuan.com/images/dashboard-en.png)

![Hub: all your hosts on one screen](https://svrguard.ofuyuan.com/images/fleet-en.png)

## What you get once it is installed

- **Rules come built in** — no regexes to maintain; once something is judged an attack it goes into the system firewall, even on hosts with no internet access.
- **Every block keeps its evidence** — you see which rule fired and which log lines; on a false positive you can unblock or whitelist it yourself.
- **It tells you when a block did not take effect** — if the firewall rejects it the console says so, and repeated failures send an email. Nothing fails quietly.
- **Your logs stay on your host** — analysis happens on the machine; after joining Hub only the few lines judged to be an attack travel as evidence. It does not read your site's content or track your visitors, and its connection to Hub is always opened by the host itself.

## Questions and feedback

Ask on the [forum](https://forum.ofuyuan.com/). Release history is on the [release notes](https://svrguard.ofuyuan.com/en/release.html) page.
