# Ubuntu Linux Training Module — 5-Day Training

A hands-on Training covering Ubuntu Linux fundamentals, system administration, networking, security hardening, production server deployment, and building a profitable freelance Linux service.

![Duration](https://img.shields.io/badge/Duration-5%20Days-blue)
![Level](https://img.shields.io/badge/Level-Beginner%20to%20Advanced-orange)
![Format](https://img.shields.io/badge/Format-Hands--on%20Labs-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## Overview

Ubuntu Linux is the world's most widely deployed open-source server operating system — powering cloud infrastructure, web servers, DevOps pipelines, VoIP systems, and enterprise workloads at scale. This Training takes participants from zero to a fully operational, production-hardened Ubuntu Linux server with web hosting, automated deployments, monitoring, and disaster recovery. Every concept is reinforced with a practical lab that produces a portfolio-ready deliverable. Day 5 packages all skills into a market-ready Upwork service offering targeting the global Linux freelance marketplace.

## Learning Objectives

By the end of this Training, participants will be able to:

- Navigate and operate the Ubuntu Linux CLI with confidence
- Manage users, groups, permissions, and filesystem structure
- Install, configure, and manage services using `apt` and `systemd`
- Configure networking, DNS, firewalls, and SSH on Ubuntu servers
- Deploy production-ready web servers (Nginx/Apache) with SSL/TLS
- Automate tasks with bash scripting and cron jobs
- Harden an Ubuntu server against common security threats
- Monitor system health, logs, performance, and disk usage
- Perform backups, snapshots, and disaster recovery operations
- Deploy and manage Docker containers on Ubuntu
- Migrate services and data across Linux servers
- Create and market professional Ubuntu Linux services on Upwork

---

## Prerequisites

- Basic computer literacy (file management, browser use)
- No prior Linux experience required — beginner-friendly from Day 1
- A laptop or desktop (Windows, macOS, or Linux)
- A VPS or cloud account for remote labs (DigitalOcean/AWS/Linode/Vultr)
- SSH client: Terminal (macOS/Linux), Windows Terminal, or PuTTY
- Upwork/Fiverr freelancer account (for Day 5)

### Recommended Lab Environment

| Resource | Specification |
|----------|--------------|
| OS       | Ubuntu 22.04 LTS (Jammy Jellyfish) |
| vCPU     | 2            |
| RAM      | 2 GB         |
| Storage  | 25 GB SSD    |
| Access   | SSH (port 22)|

---

## Technologies Used

| Category              | Technology                                              |
|-----------------------|---------------------------------------------------------|
| Operating System      | Ubuntu 22.04 LTS / 24.04 LTS                           |
| Package Manager       | APT (Advanced Package Tool), snap, dpkg                 |
| Service Manager       | systemd, journald                                       |
| Web Server            | Nginx, Apache2                                          |
| SSL                   | Let's Encrypt / Certbot                                 |
| Firewall              | UFW (Uncomplicated Firewall), iptables                  |
| Security              | fail2ban, SSH hardening, AppArmor, unattended-upgrades  |
| Scripting             | Bash, cron, at                                          |
| Containers            | Docker, Docker Compose                                  |
| Monitoring            | htop, glances, netstat, ss, journalctl, Prometheus+Grafana (intro) |
| Networking            | ip, nmcli, netplan, dig, nmap, tcpdump                 |
| Storage & Backup      | rsync, tar, scp, snapshots, LVM basics                 |
| Remote Access         | SSH, SFTP, tmux, screen                                |
| Version Control       | Git                                                     |
| DNS                   | BIND9 (intro), systemd-resolved, /etc/hosts            |
| Deployment            | VPS (DigitalOcean/AWS/Linode/Vultr), cloud-init        |

---

## 5-Day Training Schedule

---

### Day 1 — Ubuntu Linux Fundamentals & CLI Mastery

#### Theory
- Linux history, distributions, and why Ubuntu dominates the server market
- Ubuntu release cycles: LTS vs interim releases
- Linux kernel, shell, and userland — how they fit together
- Filesystem hierarchy standard (FHS): `/etc`, `/var`, `/home`, `/usr`, `/tmp`, `/proc`

#### Hands-on Topics

**Getting Started:**
- Provisioning an Ubuntu 22.04 VPS on DigitalOcean/AWS/Vultr
- Connecting via SSH: `ssh root@IP`, SSH key generation and setup
- Terminal navigation: `pwd`, `ls`, `cd`, `mkdir`, `rmdir`, `touch`, `rm`, `cp`, `mv`
- File viewing and editing: `cat`, `less`, `head`, `tail`, `nano`, `vim` basics
- Searching: `find`, `locate`, `grep`, `which`, `whereis`

**Users & Permissions:**
- Creating and managing users: `adduser`, `usermod`, `deluser`, `passwd`
- Groups: `addgroup`, `usermod -aG`, `id`, `whoami`, `groups`
- File permissions: `chmod`, `chown`, `chgrp`, `umask`
- Understanding `rwx`, octal notation, and special bits (SUID, SGID, sticky)
- `sudo` configuration and the `/etc/sudoers` file

**Package Management:**
- `apt update`, `apt upgrade`, `apt install`, `apt remove`, `apt autoremove`
- `apt search`, `apt show`, `dpkg -l`, `dpkg -i`
- snap packages: `snap install`, `snap list`, `snap refresh`
- Adding PPAs and third-party repositories

**System Information:**
- `uname -a`, `lsb_release -a`, `hostnamectl`, `uptime`
- `df -h`, `du -sh`, `free -h`, `lscpu`, `lsblk`, `lspci`
- Process management: `ps aux`, `top`, `htop`, `kill`, `pkill`, `nice`, `renice`

#### Lab
> **Lab 1:** Provision an Ubuntu 22.04 VPS, connect via SSH with key authentication, create a sudo user, explore the filesystem hierarchy, manage files and directories, install packages with APT, and set correct permissions on a practice directory tree.

---

### Day 2 — Networking, SSH Hardening & Firewall Configuration

#### Theory
- Linux networking stack: interfaces, IP addressing, routing, DNS resolution
- TCP/IP fundamentals: ports, protocols, sockets
- SSH protocol: key-based auth, port forwarding, tunneling
- Firewall concepts: stateful vs stateless, allow/deny rules, UFW vs iptables

#### Hands-on Topics

**Network Configuration:**
- Viewing network interfaces: `ip addr`, `ip link`, `ip route`, `nmcli`
- Configuring static IP with Netplan (`/etc/netplan/*.yaml`)
- DNS configuration: `/etc/resolv.conf`, `systemd-resolved`, `resolvectl`
- Testing connectivity: `ping`, `traceroute`, `mtr`, `curl`, `wget`
- Port and service inspection: `ss -tulnp`, `netstat -tulnp`, `lsof -i`
- Network diagnostics: `nmap`, `tcpdump`, `dig`, `nslookup`, `host`

**SSH Hardening:**
- SSH config file deep dive: `/etc/ssh/sshd_config`
- Disabling root login: `PermitRootLogin no`
- Disabling password authentication: `PasswordAuthentication no`
- Changing default SSH port
- SSH key management: `ssh-keygen`, `ssh-copy-id`, `~/.ssh/authorized_keys`
- SSH config shortcuts: `~/.ssh/config` client aliases
- Two-factor authentication for SSH (Google Authenticator / TOTP)
- `tmux` and `screen` for persistent SSH sessions

**Firewall with UFW:**
- UFW basics: `ufw enable`, `ufw status`, `ufw allow`, `ufw deny`, `ufw delete`
- Port-based rules: `ufw allow 22/tcp`, `ufw allow 80,443/tcp`
- Application profiles: `ufw app list`, `ufw allow 'Nginx Full'`
- Source-based rules: `ufw allow from X.X.X.X to any port 22`
- Logging: `ufw logging on`, viewing UFW logs in journalctl
- iptables basics: `iptables -L`, `-A`, `-D`, `-I`, save and restore rules

**fail2ban:**
- Installing and configuring fail2ban
- Jail configuration: `/etc/fail2ban/jail.local`
- SSH jail, Nginx jail, custom application jails
- Monitoring: `fail2ban-client status`, `fail2ban-client status sshd`
- Banning and unbanning IPs manually

#### Lab
> **Lab 2:** Configure a static IP with Netplan, harden SSH (key-only auth, custom port, disable root login), set up UFW with allow rules for HTTP/HTTPS/SSH, install and configure fail2ban with an SSH jail, and verify all settings with network diagnostic tools.

---

### Day 3 — Web Server Deployment, Domain, SSL & Service Management

#### Theory
- Web server architecture: Nginx vs Apache — when to use each
- Virtual hosts and server blocks: hosting multiple domains on one server
- SSL/TLS: certificates, CA, Let's Encrypt, ACME protocol
- systemd: units, targets, journald — managing services the modern way

#### Hands-on Topics

**Nginx Web Server:**
- Installing and starting Nginx
- Nginx directory structure: `/etc/nginx/nginx.conf`, `/etc/nginx/sites-available/`, `/etc/nginx/sites-enabled/`
- Creating a server block (virtual host) for a custom domain
- Serving static HTML/PHP sites
- Nginx as a reverse proxy: proxying to Node.js / Python / other apps
- Nginx performance tuning: worker processes, gzip, caching headers
- Nginx security headers: X-Frame-Options, CSP, HSTS

**Apache2 Web Server:**
- Installing and starting Apache2
- Virtual host configuration in `/etc/apache2/sites-available/`
- Enabling/disabling sites: `a2ensite`, `a2dissite`
- Enabling/disabling modules: `a2enmod rewrite`, `a2enmod ssl`
- `.htaccess` and `mod_rewrite` URL rewriting

**Domain & SSL Setup:**
- DNS A record configuration: pointing domain to server IP
- Installing Certbot: `apt install certbot python3-certbot-nginx`
- Issuing SSL certificate: `certbot --nginx -d yourdomain.com -d www.yourdomain.com`
- Auto-renewal: `certbot renew --dry-run`, systemd timer verification
- Manual SSL: generating self-signed certificates with OpenSSL
- SSL testing with `openssl s_client` and SSL Labs

**systemd Service Management:**
- systemd units: service, socket, timer, target
- Managing services: `systemctl start/stop/restart/reload/enable/disable/status`
- Creating a custom systemd service unit file
- journald log management: `journalctl -u nginx`, `-f`, `--since`, `--until`
- System targets: `systemctl get-default`, `isolate`, runlevel equivalents
- systemd timers as cron replacements

#### Lab
> **Lab 3:** Deploy Nginx and Apache2 on the same server with separate virtual hosts, configure a custom domain with a Let's Encrypt SSL certificate, create a custom systemd service unit that auto-starts on boot, and verify logs via journalctl.

---

### Day 4 — Bash Scripting, Automation, Docker, Monitoring & Backup

#### Theory
- Bash scripting: why automation is the core Linux superpower
- Docker containerization: images, containers, volumes, networks
- Monitoring philosophy: proactive vs reactive, metrics vs logs
- Backup strategies: 3-2-1 rule, full vs incremental, local vs remote

#### Hands-on Topics

**Bash Scripting:**
- Script structure: shebang, variables, input, output
- Conditionals: `if/elif/else`, `case`
- Loops: `for`, `while`, `until`
- Functions, arguments (`$1`, `$@`, `$#`), and return codes (`$?`)
- String manipulation, arithmetic, and arrays
- Error handling: `set -e`, `set -u`, `trap`
- Reading files line by line, parsing CSV data
- Practical scripts: user creation, disk usage alerts, service health checks

**Cron & Automation:**
- `crontab -e`: cron syntax (`* * * * *`), user vs system cron
- `/etc/cron.d/`, `/etc/cron.daily/`, `/etc/cron.hourly/`
- `at` command for one-time scheduled tasks
- `systemd` timers as cron alternatives
- Automation with `unattended-upgrades` for security patches

**Docker on Ubuntu:**
- Installing Docker CE and Docker Compose on Ubuntu 22.04
- Docker fundamentals: `docker pull`, `run`, `ps`, `stop`, `rm`, `images`, `logs`
- Writing a `Dockerfile` and building custom images
- Docker volumes and bind mounts for persistent data
- Docker networking: bridge, host, and custom networks
- Docker Compose: writing `docker-compose.yml`, `up -d`, `down`, `logs`
- Deploying a real app stack: Nginx + Node.js + PostgreSQL via Compose
- Container security basics: non-root users, read-only filesystems

**System Monitoring:**
- Real-time monitoring: `htop`, `glances`, `iotop`, `iftop`
- Disk usage: `df -h`, `du -sh /*`, `ncdu`
- Log monitoring: `journalctl -f`, `/var/log/syslog`, `/var/log/auth.log`
- Process monitoring: `ps aux --sort=-%cpu`, `pstree`, `lsof`
- Network monitoring: `ss -s`, `nload`, `vnstat`
- Uptime and load average: `uptime`, `w`, `/proc/loadavg`
- Introduction to Prometheus + Node Exporter + Grafana dashboard

**Backup & Recovery:**
- File-level backup with `rsync`: local and remote over SSH
- Archive and compress: `tar -czf`, `tar -xzf`, `gzip`, `zip`
- Secure copy: `scp`, `sftp`
- Automated rsync backup script with cron
- LVM snapshots for consistent live backups
- VPS snapshots via cloud provider API
- Restoring from backup: full and selective file restore
- Testing backup integrity

#### Lab
> **Lab 4:** Write a bash script that checks disk usage and emails an alert when > 80%, set up a cron job for automated nightly rsync backup to a remote server, deploy a Nginx + Node.js app with Docker Compose, and set up Grafana with Node Exporter to visualize server metrics.

---

### Day 5 — Production Hardening, Migration & Upwork Service Development

#### Hands-on Topics

**Production Server Hardening:**
- Security audit checklist for Ubuntu production servers
- AppArmor: status, profiles, enforcing vs complaining mode
- Disabling unused services and open ports
- `/etc/sysctl.conf` kernel hardening parameters
- Shared memory and core dump restrictions
- Lynis security audit tool: `lynis audit system`
- ClamAV antivirus for Linux: install, scan, automate
- rkhunter and chkrootkit rootkit detection
- Automatic security updates: `unattended-upgrades` configuration
- Two-factor SSH authentication in production

**Server Migration:**
- Planning a Linux server migration (inventory, dependencies, downtime window)
- Migrating web servers: Nginx/Apache config, SSL certs, document root
- Migrating databases: `mysqldump`, `pg_dump`, restore on new server
- Migrating Docker stacks: export images, transfer volumes, redeploy Compose
- DNS cutover strategy: TTL reduction, zero-downtime migration
- Full server clone with `rsync` over SSH
- Validating migration success: service checks, log review, smoke testing

**Upwork Marketplace Service Development:**

*Service Niches to Target:*
- Ubuntu Linux VPS setup and hardening
- Nginx/Apache web server deployment and SSL configuration
- Linux server migration (cPanel, Plesk, shared → VPS)
- Docker and Docker Compose deployment on Ubuntu
- Bash scripting and task automation
- Linux server monitoring and performance tuning
- Backup and disaster recovery setup
- Linux troubleshooting and emergency support
- UFW, fail2ban, and security hardening
- Ubuntu server upgrade (20.04 → 22.04 → 24.04)

*Upwork Profile & Gig Development:*
- Writing a high-converting Upwork profile headline and overview for Linux niche
- Crafting gig titles, descriptions, and search tags
- Tiered pricing packages (Basic / Standard / Premium)
- Building a portfolio using Day 1–4 lab screenshots, config files, and Loom screen-capture demos
- Writing client proposal templates for Linux server projects
- Handling common client objections (why self-hosted vs managed hosting)
- Upsell opportunities: monthly server monitoring retainers, security audits, SLA agreements
- Tools: Loom (demo videos), Notion (SOW templates), Calendly (client discovery calls)

#### Lab
> **Lab 5:** Run a full Lynis security audit on your production Ubuntu server and remediate the top 5 findings, perform a complete web server migration to a new VPS including DNS cutover, then publish a live Upwork gig for "Ubuntu Linux VPS Setup & Hardening" with a Loom demo video, three tiered packages, and a ready-to-send proposal template.

---

## Project Outcomes

After completing all 5 days and labs, participants will have built and documented:

| Project | Description |
|---------|-------------|
| **Hardened Ubuntu VPS** | Production Ubuntu 22.04 server with SSH key auth, UFW, fail2ban, AppArmor |
| **Dual Web Server Setup** | Nginx + Apache2 with virtual hosts, custom domain, and Let's Encrypt SSL |
| **Custom systemd Service** | Auto-starting application service unit managed by systemd |
| **Bash Automation Suite** | Disk alert script, user creation script, service health check script |
| **Docker App Stack** | Nginx + Node.js + PostgreSQL deployed via Docker Compose |
| **Automated Backup System** | Nightly rsync backup to remote server with cron scheduling |
| **Grafana Monitoring Dashboard** | Prometheus + Node Exporter + Grafana server metrics visualisation |
| **Full Server Migration** | Documented web server + database migration to a new VPS with DNS cutover |
| **Lynis Security Audit** | Full security audit report with documented remediation steps |
| **Upwork Service Listing** | Published gig with Loom demo video and client proposal templates |

---

## Career Opportunities

| Role | Relevant Skills Gained |
|------|------------------------|
| Linux System Administrator | Ubuntu server management, systemd, networking, security |
| DevOps Engineer | Docker, bash scripting, automation, CI/CD foundations |
| Cloud Engineer | VPS provisioning, cloud-init, cloud provider CLI |
| Web Hosting Engineer | Nginx/Apache, virtual hosts, SSL, DNS, server migration |
| Security Engineer | UFW, fail2ban, AppArmor, Lynis auditing, SSH hardening |
| Site Reliability Engineer | Monitoring, alerting, backup, disaster recovery |
| Freelance Linux Specialist | Upwork gig development, client project scoping and delivery |
| Linux Trainer / Instructor | Training facilitation, documentation, lab design |

---

## Quick Reference Commands

```bash
# ── SYSTEM ──────────────────────────────────────────────────────────────────
uname -a                          # Kernel and OS info
lsb_release -a                    # Ubuntu version
hostnamectl set-hostname myserver # Change hostname
timedatectl set-timezone UTC      # Set timezone
uptime                            # System uptime and load average
who                               # Logged-in users

# ── USERS & PERMISSIONS ─────────────────────────────────────────────────────
adduser username                  # Create user interactively
usermod -aG sudo username         # Add user to sudo group
passwd username                   # Set/change user password
chmod 755 /path/to/file           # Set permissions (rwxr-xr-x)
chown user:group /path/to/file    # Change ownership
find /var/www -type f -name "*.php" -exec chmod 644 {} \;

# ── PACKAGE MANAGEMENT ───────────────────────────────────────────────────────
sudo apt update && sudo apt upgrade -y
sudo apt install -y nginx git curl wget ufw fail2ban
sudo apt autoremove -y && sudo apt clean
sudo dpkg -l | grep nginx         # Check installed package

# ── SERVICES ────────────────────────────────────────────────────────────────
sudo systemctl start|stop|restart|reload|enable|disable|status nginx
sudo journalctl -u nginx -f       # Follow service logs
sudo journalctl --since "1 hour ago"

# ── NETWORKING ───────────────────────────────────────────────────────────────
ip addr show                      # Show IP addresses
ip route show                     # Show routing table
ss -tulnp                         # Show listening ports and processes
dig yourdomain.com A              # DNS lookup
nmap -sV -p 22,80,443 IP         # Scan open ports
tcpdump -i eth0 port 80          # Capture HTTP traffic

# ── SSH ──────────────────────────────────────────────────────────────────────
ssh-keygen -t ed25519 -C "your@email.com"
ssh-copy-id -i ~/.ssh/id_ed25519.pub user@server_ip
sudo nano /etc/ssh/sshd_config    # Edit SSH config
sudo systemctl restart sshd       # Apply SSH changes

# ── UFW FIREWALL ─────────────────────────────────────────────────────────────
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh
sudo ufw allow 'Nginx Full'
sudo ufw enable
sudo ufw status verbose

# ── FAIL2BAN ─────────────────────────────────────────────────────────────────
sudo fail2ban-client status
sudo fail2ban-client status sshd
sudo fail2ban-client set sshd unbanip X.X.X.X

# ── NGINX ────────────────────────────────────────────────────────────────────
sudo nginx -t                     # Test Nginx config
sudo nginx -s reload              # Reload without downtime
sudo ln -s /etc/nginx/sites-available/yourdomain /etc/nginx/sites-enabled/

# ── SSL / CERTBOT ────────────────────────────────────────────────────────────
sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com
sudo certbot renew --dry-run      # Test auto-renewal
sudo openssl s_client -connect yourdomain.com:443  # Verify SSL

# ── DOCKER ───────────────────────────────────────────────────────────────────
sudo apt install -y docker.io docker-compose-plugin
sudo usermod -aG docker $USER
docker ps -a                      # List all containers
docker images                     # List images
docker compose up -d              # Start Compose stack
docker compose down               # Stop Compose stack
docker logs -f container_name     # Follow container logs
docker exec -it container_name bash  # Shell into container
docker system prune -af           # Clean unused resources

# ── DISK & STORAGE ───────────────────────────────────────────────────────────
df -h                             # Disk usage by filesystem
du -sh /var/log/*                 # Directory sizes
ncdu /                            # Interactive disk usage explorer
lsblk                             # Block device overview

# ── BACKUP ───────────────────────────────────────────────────────────────────
rsync -avz --progress /local/path/ user@remote:/backup/path/
tar -czf backup_$(date +%F).tar.gz /path/to/directory
scp backup.tar.gz user@remote:/backup/

# ── MONITORING ───────────────────────────────────────────────────────────────
htop                              # Interactive process viewer
glances                           # All-in-one system monitor
iotop                             # I/O usage per process
iftop -i eth0                     # Network bandwidth per connection
watch -n 5 "df -h && free -h"    # Watch disk and memory every 5s

# ── SECURITY AUDIT ───────────────────────────────────────────────────────────
sudo apt install -y lynis
sudo lynis audit system
sudo apt install -y rkhunter && sudo rkhunter --check
```

---

## Sample Bash Scripts

### Disk Usage Alert Script
```bash
#!/bin/bash
# /usr/local/bin/disk-alert.sh
THRESHOLD=80
EMAIL="admin@yourdomain.com"

while IFS= read -r line; do
  USAGE=$(echo "$line" | awk '{print $5}' | tr -d '%')
  MOUNT=$(echo "$line" | awk '{print $6}')
  if [ "$USAGE" -ge "$THRESHOLD" ]; then
    echo "ALERT: Disk usage on $MOUNT is at ${USAGE}% on $(hostname)" \
      | mail -s "Disk Alert: ${USAGE}% on $MOUNT" "$EMAIL"
  fi
done < <(df -h | grep -vE '^Filesystem|tmpfs|cdrom' | tail -n +2)
```

### Automated Remote Backup Script
```bash
#!/bin/bash
# /usr/local/bin/remote-backup.sh
SOURCE="/var/www /etc/nginx /etc/ssl"
DEST="backup_user@backup-server:/backups/$(hostname)"
DATE=$(date +%F)
LOG="/var/log/backup.log"

echo "[$DATE] Starting backup..." >> "$LOG"
for DIR in $SOURCE; do
  rsync -avz --delete "$DIR" "$DEST$DIR" >> "$LOG" 2>&1
done
echo "[$DATE] Backup complete." >> "$LOG"
```

### Service Health Check Script
```bash
#!/bin/bash
# /usr/local/bin/health-check.sh
SERVICES=("nginx" "mysql" "docker" "ssh")
EMAIL="admin@yourdomain.com"

for SERVICE in "${SERVICES[@]}"; do
  if ! systemctl is-active --quiet "$SERVICE"; then
    echo "SERVICE DOWN: $SERVICE on $(hostname) at $(date)" \
      | mail -s "Alert: $SERVICE is DOWN" "$EMAIL"
    systemctl restart "$SERVICE"
    echo "Attempted restart of $SERVICE" | mail -s "Restart: $SERVICE" "$EMAIL"
  fi
done
```

---

## Sample Docker Compose Stack

```yaml
# docker-compose.yml — Nginx + Node.js + PostgreSQL
version: "3.9"

services:
  db:
    image: postgres:16-alpine
    restart: always
    environment:
      POSTGRES_DB: appdb
      POSTGRES_USER: appuser
      POSTGRES_PASSWORD: ${DB_PASSWORD}
    volumes:
      - pgdata:/var/lib/postgresql/data

  app:
    build: ./app
    restart: always
    environment:
      DATABASE_URL: postgres://appuser:${DB_PASSWORD}@db:5432/appdb
    depends_on:
      - db
    ports:
      - "3000:3000"

  web:
    image: nginx:alpine
    restart: always
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx/conf.d:/etc/nginx/conf.d:ro
      - /etc/letsencrypt:/etc/letsencrypt:ro
    depends_on:
      - app

volumes:
  pgdata:
```

---

## Resources

- `/configs` — Nginx server block templates, SSH config, UFW rules, fail2ban jail config, sysctl hardening
- `/scripts` — VPS setup script, disk alert, backup, health check, Docker install automation
- `/docker` — Sample Dockerfiles and docker-compose.yml stacks
- `/templates` — Upwork gig copy, SOW templates, client proposal scripts, security audit checklist
- [Ubuntu Official Docs](https://ubuntu.com/server/docs)
- [Ubuntu Packages Search](https://packages.ubuntu.com)
- [Nginx Docs](https://nginx.org/en/docs/)
- [Certbot Docs](https://certbot.eff.org)
- [Docker Docs](https://docs.docker.com)
- [fail2ban Docs](https://www.fail2ban.org/wiki/index.php/Main_Page)
- [Lynis Security Tool](https://cisofy.com/lynis/)
- [Ubuntu Security Notices](https://ubuntu.com/security/notices)
- [Upwork Linux Jobs](https://www.upwork.com/freelance-jobs/linux/)
