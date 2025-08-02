# ⚔️ MASTER LINUX PENTESTER CHEAT SHEET — BASICS

Welcome to my **personal Linux Pentester Cheat Sheet** — a curated set of core Linux commands every aspiring hacker and pentester must know.  
This is part of my **Black Badge Hacker Roadmap** to master Linux for real-world hacking, red teaming, and privilege escalation.

---

## 🔍 1️⃣ Finding Files & Binaries

| Command | What it does |
|----------------|-----------------------------|
| `locate keyword` | Fast find, uses DB — `sudo updatedb` to refresh |
| `whereis binary_name` | Locate binaries, source, man pages |
| `which binary_name` | Show exact binary the shell runs |
| `find [dir] [criteria] [actions]` | Flexible search |

**Examples:**  
```bash
find / -name "*.conf"
find /var/www -type f -size +1M
find /home -user bob -exec chown alice {} \;


📝 2️⃣ Editing & Viewing Files
Command	What it does
cat	Show file contents
tac	Show file contents in reverse
nl	Number lines
more file	View page-by-page
less file	Powerful viewer
head -n 10 file	First 10 lines
tail -n 10 file	Last 10 lines
grep "pattern" file	Search
awk '{print $1}' file	Extract fields

📡 3️⃣ Network Management
Command	What it does
ifconfig	Network interfaces
iwconfig	Wireless config
dhclient eth0	Get DHCP IP
ifconfig eth0 hw ether 00:11:22:33:44:55	Spoof MAC
ip addr	Modern ifconfig
ip link set eth0 up/down	Bring NIC up/down
nmcli	Network manager
route -n	Routing table
netstat -tulnp	Listening ports
ss -tulwn	Modern netstat
nmap -A target	Scan target
dig domain.com	DNS lookup
nslookup domain.com	DNS
host domain.com	DNS

⚙️ 4️⃣ Package Management
Command	What it does
apt-cache search snort	Search packages
apt-get remove snort	Remove but keep configs
apt-get purge snort	Remove completely
apt-get update	Update repo list
apt-get upgrade	Upgrade packages
dpkg -l	List installed
dpkg -s <pkg>	Show package info
dpkg -L <pkg>	Files in pkg
dpkg -i file.deb	Install .deb manually
/etc/apt/sources.list	Repos file

👑 5️⃣ Ownership & Permissions
Command	What it does
chown bob file	Change owner
chgrp security file	Change group
chmod 756 file	Set permissions
umask	Set default perms
ls -l	View perms
lsattr	File attributes
chattr	Change attributes

🚩 6️⃣ Process Management
Command	What it does
ps	Running processes
ps aux	All processes
`ps aux	grep ssh`
top	Live monitor
htop	Better top
nice -n -10	Run high priority
renice 20 PID	Change priority
kill -1 PID	Restart
kill -9 PID	Force kill
killall -9 procname	Kill by name
jobs	Show BG jobs
fg	Bring job FG
bg	Send job BG

⏰ 7️⃣ Scheduling & Automation
Command	What it does
at	One-time task
cron	Scheduled tasks
crontab -e	Edit user cron
crontab -l	List cron jobs
Example: */5 * * * * /root/script.sh	Run every 5 min

🗂️ 8️⃣ Environment Variables
Command	What it does
env	List env vars
set	List all
export VAR=value	Set var
.bashrc	Persistent vars
HISTSIZE=0	Clear history
unset HISTFILE; export HISTFILE=/dev/null	Wipe Bash history

📦 9️⃣ Archiving & Backups
Command	What it does
tar -cvf	Create archive
tar -tvf	List archive
tar -xvf	Extract archive
gzip	Compress
gunzip	Decompress
dd if= of=	Bit copy
rsync -av src/ dest/	Sync folders
scp file user@host:/path/	Secure copy

💽 🔟 Storage & Mounting
Command	What it does
fdisk -l	List disks
lsblk	Block devices
df -h	Disk usage
du -sh *	Size folders
blkid	UUID, FS type
parted	Partition
mount	Mount device
umount	Unmount
fsck	FS check

📜 ✅ Logs & Cleaning
Command	What it does
/var/log/auth.log	Auth logs
journalctl	Systemd logs
logrotate	Manage logs
shred	Secure delete
service rsyslog stop	Stop logs
last	Logins
who, w	Who’s online


This is my **Advanced Linux Red Team & Exploitation Cheat Sheet** — focused on **privilege escalation**, **kernel ops**, **wireless hacks**, and **staying stealthy**.

---

## 🔐 Privilege Escalation

| Command | What it does |
|----------------|-----------------------------|
| `sudo -l` | Show allowed sudo cmds |
| `sudo su` | Become root |
| `find / -perm -4000` | Find SUID binaries |
| `find . -perm /4000` | Find local SUID files |
| `GTFOBins` | Search GTFO techniques |
| `ps aux | grep root` | Look for root processes |

---

## 📡 Wireless Hacking

| Tool | What it does |
|----------------|-----------------------------|
| `airmon-ng` | Enable monitor mode |
| `airodump-ng` | Packet capture |
| `aireplay-ng` | Packet injection |
| `aircrack-ng` | WPA/WEP crack |
| `hciconfig` | Bluetooth config |
| `hcitool` | Bluetooth info |
| `hcidump` | Bluetooth sniff |

---

## ⚙️ Kernel & Modules

| Command | What it does |
|----------------|-----------------------------|
| `uname -a` | Kernel info |
| `cat /proc/version` | More kernel info |
| `sysctl` | Kernel params |
| `/proc/sys/` | Manual tweaks |
| `lsmod` | Loaded modules |
| `modinfo` | Module info |
| `modprobe` | Add/remove modules |
| `insmod` | Insert module |
| `rmmod` | Remove module |
| `echo 1 > /proc/sys/net/ipv4/ip_forward` | Enable IP fwding |

---

## 🔒 Stealth, OPSEC & Anonymity

| Tool/Command | What it does |
|----------------|-----------------------------|
| `Tor Browser` | Anonymous browsing |
| `VPN` | Hide real IP |
| `proxychains` | Proxy all traffic |
| `torsocks` | Route through Tor |
| `curl --socks5` | Test socks proxy |
| `unset HISTFILE` | Kill shell history |
| `shred` | Wipe logs securely |
| `rsyslog stop` | Stop syslogs |

---

## 🧩 Bash Scripting & Automation

| Command | What it does |
|----------------|-----------------------------|
| `#!/bin/bash` | Shebang |
| `$0, $1` | Script args |
| `for, while` | Loops |
| `if [ condition ]` | Conditions |
| `echo` | Output |
| `>>` | Append |
| `2>/dev/null` | Suppress errors |
| `cron` | Schedule persistence |

---

✅ **Practical:**  
- Automate scans.
- Automate backups.
- Chain privilege escalation.
- Always test stealth: logs, history, output.

---

**⚡️ Keep building: Real power = Real practice.  
Push new advanced tricks as you learn — this file is *never finished*.

---

