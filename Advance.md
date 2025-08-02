# ⚔️ ADVANCED LINUX PENTESTER COMMANDS & TACTICS

Welcome to my **Advanced Linux Red Team & Exploitation Cheat Sheet** — focused on real-world tactics for privilege escalation, kernel tuning, stealth, wireless attacks, and OPSEC.  
This is my next level in the **Black Badge Hacker Roadmap**.

---

## 🚩 1️⃣ Privilege Escalation

| Command | What it does |
|----------------|-----------------------------|
| `sudo -l` | Show allowed sudo commands |
| `sudo su` | Become root if allowed |
| `find / -perm -4000` | Find all SUID binaries system-wide |
| `find . -perm /4000` | Find SUID files in current dir |
| `GTFOBins` | Lookup common SUID exploitation tricks |
| `ps aux | grep root` | Find processes running as root |
| `ps -ef` | Another way to list processes |

**Practical:** Abuse misconfigured SUID binaries, escalate to root, patch the system to prevent.

---

## 📡 2️⃣ Wireless & Bluetooth Hacking

| Tool/Command | What it does |
|----------------|-----------------------------|
| `airmon-ng` | Enable monitor mode on WiFi adapter |
| `airodump-ng` | Capture packets |
| `aireplay-ng` | Inject packets, deauth attacks |
| `aircrack-ng` | Crack WPA/WEP keys |
| `iwlist` | Scan for WiFi networks |
| `hciconfig` | Configure Bluetooth device |
| `hcitool` | Query Bluetooth info |
| `hcidump` | Bluetooth packet sniffing |

**Practical:** Use these with caution — stay legal, test on your lab WiFi only.

---

## ⚙️ 3️⃣ Kernel & Modules

| Command | What it does |
|----------------|-----------------------------|
| `uname -a` | Display full kernel info |
| `cat /proc/version` | Kernel version details |
| `sysctl -a` | Show kernel parameters |
| `lsmod` | List loaded modules |
| `modinfo module_name` | Module information |
| `modprobe module_name` | Load/unload kernel modules |
| `insmod module.ko` | Insert module manually |
| `rmmod module_name` | Remove module |
| `echo 1 > /proc/sys/net/ipv4/ip_forward` | Enable IP forwarding |
| `/proc/sys/` | Manually tune kernel params |

**Practical:** For advanced privilege escalation or persistence — root only.

---

## 🔒 4️⃣ Stealth, OPSEC & Anonymity

| Tool/Command | What it does |
|----------------|-----------------------------|
| `Tor Browser` | Browse anonymously |
| `VPN` | Encrypt and hide real IP |
| `proxychains` | Force apps through proxy |
| `torsocks` | Run TCP apps through Tor |
| `curl --socks5` | Test Tor/proxy |
| `unset HISTFILE` | Kill shell history |
| `HISTSIZE=0` | Clear history size |
| `shred` | Securely erase files/logs |
| `service rsyslog stop` | Stop logging |
| `logrotate` | Manage log rotation |
| `journalctl` | Systemd logs |
| `last` | Show login history |
| `who`, `w` | Who’s online |

**Practical:** Use stealth & anti-forensics when testing real targets (with permission!).

---

## 🧩 5️⃣ Bash Scripting & Automation

| Command | What it does |
|----------------|-----------------------------|
| `#!/bin/bash` | Shebang — make script executable |
| `$0, $1, $2` | Script arguments |
| `for`, `while` | Loops |
| `if [ condition ]` | Conditional checks |
| `echo "text"` | Print output |
| `>` `>>` | Redirect output |
| `2>/dev/null` | Suppress errors |
| `cron` | Schedule persistence tasks |
| `at` | One-time tasks |

**Practical:** Automate scans, backups, post-exploitation persistence.

---

## 🧩 6️⃣ Extra Useful Tricks

| Command | What it does |
|----------------|-----------------------------|
| `proxychains nmap -sT target` | Proxy your scans |
| `nc -lvnp PORT` | Netcat listener (reverse shells) |
| `ssh -D 9050 user@host` | Dynamic socks proxy |
| `rsync -av source/ dest/` | Reliable backups |
| `scp file user@host:/path` | Secure copy |
| `curl -s` | Silent curl for recon |
| `wget` | Download files |

---

## 🏴‍☠️ 7️⃣ Live Practical Actions

✅ Always:
- Test **SUID**, **misconfigurations**, **weak perms**
- Check **GTFOBins** for exploitation methods
- Automate with Bash
- Clear logs, shred traces (OPSEC)
- Use VPN/Tor/proxychains to cloak ops

---

## 🔑 REMEMBER

📜 This cheat sheet is **never done**.  
Keep it alive — as you master real red team ops, append your new payloads, tricks, and stealth tactics here.

---

**✅ Author: [Your Name] — Black Badge Hacker Roadmap**  
**🏴‍☠️ Version: Advanced Tactics for Real-World Pentesting**

---
