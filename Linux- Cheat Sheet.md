# 🐧 Advanced Linux Red Team & Exploitation Cheat Sheet

This is my **Advanced Linux Red Team & Exploitation Cheat Sheet** — focused on **privilege escalation**, **kernel ops**, **wireless hacks**, **network management**, **OPSEC**, and **real-world red teaming**.  
I use this daily to sharpen my offensive skills and build my Black Badge Hacker Arsenal. 🚩

---

## 🔍 1️⃣ **Find Files**

| Command | What it does |
|-------------------------------|-----------------------------|
| `find / -name "*.conf"` | Find all `.conf` files |
| `find /var/www -type f -size +1M` | Find files >1MB in `/var/www` |
| `find /home -user bob -exec chown alice {} \;` | Change owner from `bob` to `alice` |

---

## 📝 2️⃣ **Editing & Viewing Files**

| Command | What it does |
|-------------------------------|-----------------------------|
| `cat` | Show file contents |
| `tac` | Show file contents in reverse |
| `nl` | Number lines |
| `more file` | View page-by-page |
| `less file` | Powerful file viewer |
| `head -n 10 file` | First 10 lines |
| `tail -n 10 file` | Last 10 lines |
| `grep "pattern" file` | Search in file |
| `awk '{print $1}' file` | Extract fields |

---

## 📡 3️⃣ **Network Management**

| Command | What it does |
|-------------------------------|-----------------------------|
| `ifconfig` | Network interfaces |
| `iwconfig` | Wireless config |
| `dhclient eth0` | Get DHCP IP |
| `ifconfig eth0 hw ether 00:11:22:33:44:55` | Spoof MAC address |
| `ip addr` | Modern ifconfig |
| `ip link set eth0 up/down` | Bring NIC up/down |
| `nmcli` | Network manager tool |
| `route -n` | Routing table |
| `netstat -tulnp` | Listening ports |
| `ss -tulwn` | Modern netstat |
| `nmap -A target` | Scan target with OS detection |
| `dig domain.com` | DNS lookup |
| `nslookup domain.com` | DNS lookup |
| `host domain.com` | DNS lookup |

---

## ⚙️ 4️⃣ **Package Management**

| Command | What it does |
|-------------------------------|-----------------------------|
| `apt-cache search snort` | Search packages |
| `apt-get remove snort` | Remove but keep configs |
| `apt-get purge snort` | Remove completely |
| `apt-get update` | Update repo list |
| `apt-get upgrade` | Upgrade packages |
| `dpkg -l` | List installed packages |
| `dpkg -s <pkg>` | Show package info |
| `dpkg -L <pkg>` | Files in package |
| `dpkg -i file.deb` | Install .deb manually |
| `/etc/apt/sources.list` | Repos file |

---

## 👑 5️⃣ **Ownership & Permissions**

| Command | What it does |
|-------------------------------|-----------------------------|
| `chown bob file` | Change owner |
| `chgrp security file` | Change group |
| `chmod 756 file` | Set permissions |
| `umask` | Set default permissions |
| `ls -l` | View permissions |
| `lsattr` | File attributes |
| `chattr` | Change attributes |

---

## 🚩 6️⃣ **Process Management**

| Command | What it does |
|-------------------------------|-----------------------------|
| `ps` | Running processes |
| `ps aux` | All processes |
| `ps aux | grep ssh` | Filter ssh |
| `top` | Live monitor |
| `htop` | Better top |
| `nice -n -10` | Run high priority |
| `renice 20 PID` | Change priority |
| `kill -1 PID` | Restart process |
| `kill -9 PID` | Force kill |
| `killall -9 procname` | Kill by name |
| `jobs` | Show background jobs |
| `fg` | Bring job to foreground |
| `bg` | Send job to background |

---

## ⏰ 7️⃣ **Scheduling & Automation**

| Command | What it does |
|-------------------------------|-----------------------------|
| `at` | One-time task |
| `cron` | Scheduled tasks |
| `crontab -e` | Edit user cron jobs |
| `crontab -l` | List cron jobs |
| `*/5 * * * * /root/script.sh` | Example: run every 5 mins |

---

## 🗂️ 8️⃣ **Environment Variables**

| Command | What it does |
|-------------------------------|-----------------------------|
| `env` | List env vars |
| `set` | List all vars |
| `export VAR=value` | Set variable |
| `.bashrc` | Persistent vars |
| `HISTSIZE=0` | Clear history |
| `unset HISTFILE; export HISTFILE=/dev/null` | Wipe Bash history |

---

## 📦 9️⃣ **Archiving & Backups**

| Command | What it does |
|-------------------------------|-----------------------------|
| `tar -cvf` | Create archive |
| `tar -tvf` | List archive |
| `tar -xvf` | Extract archive |
| `gzip` | Compress |
| `gunzip` | Decompress |
| `dd if= of=` | Bit copy |
| `rsync -av src/ dest/` | Sync folders |
| `scp file user@host:/path/` | Secure copy |

---

## 💽 🔟 **Storage & Mounting**

| Command | What it does |
|-------------------------------|-----------------------------|
| `fdisk -l` | List disks |
| `lsblk` | Block devices |
| `df -h` | Disk usage |
| `du -sh *` | Size of folders |
| `blkid` | UUID, FS type |
| `parted` | Partition disks |
| `mount` | Mount device |
| `umount` | Unmount device |
| `fsck` | Filesystem check |

---

## 📜 ✅ **Logs & Cleaning**

| Command | What it does |
|-------------------------------|-----------------------------|
| `/var/log/auth.log` | Auth logs |
| `journalctl` | Systemd logs |
| `logrotate` | Manage logs |
| `shred` | Secure delete |
| `service rsyslog stop` | Stop logs |
| `last` | Logins |
| `who`, `w` | Who’s online |

---

## 🔐 **Privilege Escalation**

| Command | What it does |
|-------------------------------|-----------------------------|
| `sudo -l` | Show allowed sudo commands |
| `sudo su` | Become root |
| `find / -perm -4000` | Find SUID binaries |
| `find . -perm /4000` | Find local SUID files |
| `GTFOBins` | Search GTFO techniques |
| `ps aux | grep root` | Look for root processes |

---

## 📡 **Wireless Hacking**

| Tool | What it does |
|-------------------------------|-----------------------------|
| `airmon-ng` | Enable monitor mode |
| `airodump-ng` | Packet capture |
| `aireplay-ng` | Packet injection |
| `aircrack-ng` | WPA/WEP crack |
| `hciconfig` | Bluetooth config |
| `hcitool` | Bluetooth info |
| `hcidump` | Bluetooth sniffing |

---

## ⚙️ **Kernel & Modules**

| Command | What it does |
|-------------------------------|-----------------------------|
| `uname -a` | Kernel info |
| `cat /proc/version` | More kernel info |
| `sysctl` | Kernel params |
| `/proc/sys/` | Manual tweaks |
| `lsmod` | Loaded modules |
| `modinfo` | Module info |
| `modprobe` | Add/remove modules |
| `insmod` | Insert module |
| `rmmod` | Remove module |
| `echo 1 > /proc/sys/net/ipv4/ip_forward` | Enable IP forwarding |

---

## 🔒 **Stealth, OPSEC & Anonymity**

| Tool/Command | What it does |
|-------------------------------|-----------------------------|
| `Tor Browser` | Anonymous browsing |
| `VPN` | Hide real IP |
| `proxychains` | Proxy all traffic |
| `torsocks` | Route through Tor |
| `curl --socks5` | Test socks proxy |
| `unset HISTFILE` | Kill shell history |
| `shred` | Wipe logs securely |
| `rsyslog stop` | Stop syslogs |

---

## 🧩 **Bash Scripting & Automation**

| Command | What it does |
|-------------------------------|-----------------------------|
| `#!/bin/bash` | Shebang |
| `$0, $1` | Script arguments |
| `for, while` | Loops |
| `if [ condition ]` | Conditions |
| `echo` | Output |
| `>>` | Append |
| `2>/dev/null` | Suppress errors |
| `cron` | Schedule persistence |

---

## ✅ **Practical Tips**

- Automate scans.
- Automate backups.
- Chain privilege escalation.
- Always test stealth: logs, history, output.

---

## ⚡️ Keep building: Real power = Real practice.  
Push new advanced tricks as you learn — this file is *never finished*. 🏴‍☠️

---
**Made by [YourName] — Black Badge Hacker in training.**
