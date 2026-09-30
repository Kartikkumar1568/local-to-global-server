<div align="center">

# 🚀 LocalHost Hub
### All-in-One Portable Local Web Server & cPanel Suite

[![Release](https://img.shields.io/badge/Release-v1.0.0-0284c7?style=for-the-badge&logo=github)](https://github.com)
[![Platform](https://img.shields.io/badge/Platform-Windows%20(Standalone%20.EXE)-0f172a?style=for-the-badge&logo=windows)](https://github.com)
[![Zero Dependency](https://img.shields.io/badge/Dependencies-Zero%20(Self--Contained)-10b981?style=for-the-badge)](https://github.com)
[![License](https://img.shields.io/badge/License-MIT-38bdf8?style=for-the-badge)](LICENSE)

<p align="center">
  <b>Turn your PC/Laptop into a powerful, 24/7 web hosting environment with a luxury cPanel dashboard, multi-domain routing, reverse proxy, visual database studio, and instant public Cloudflare tunneling.</b>
</p>

</div>

---

## ✨ Features at a Glance

- **🎛️ Glassmorphic cPanel Dashboard:** Modern, intuitive web interface accessible at `http://localhost:8080/cpanel`.
- **📦 100% Portable (Single `.EXE`):** Zero setup required. No Python, Node.js, or external runtimes needed on the host PC.
- **⚡ High-Performance Reverse Proxy:** Seamlessly proxy traffic to Node.js, Next.js, Python (FastAPI, Flask, Django), React, Go, or PHP backends.
- **🌐 Virtual Hosts & Multi-Domain Manager:** Host multiple static or dynamic websites, custom domains, and subdomains simultaneously.
- **🗄️ Visual SQLite Studio & Instant REST API:** Full database GUI (create tables, browse rows, run SQL queries) plus auto-generated REST CRUD APIs.
- **📝 Zero-Code HTML Form Backend:** Connect any HTML contact or lead form without writing backend code.
- **🌍 1-Click Local-to-Global Tunneling:** Free, instant public HTTPS live URLs powered by **Cloudflare Tunnels** and **Pinggy**.
- **⏰ Cron Jobs & Webhook Scheduler:** Schedule recurring system commands (PHP, Python, Shell) or HTTP Webhook calls.
- **🚀 Ultra-Fast RAM Cache:** In-memory file cache with HTTP `304 Not Modified`, `ETag`, and gzip compression for near-zero CPU and disk load.
- **🛡️ Custom Error Pages & .htaccess Support:** Visual manager for custom 404, 500, 403 error pages and Apache-style rewrite rules.

---

## 🚀 Quick Start Guide

### Option 1: Standalone Portable Executable (Recommended)

1. **Download** the latest `LocalServer.exe` from [Releases](https://github.com).
2. Place `LocalServer.exe` inside any empty folder (e.g., `MyServer/`).
3. **Double-click `LocalServer.exe`**.
4. The cPanel dashboard will automatically open in your browser:
   👉 **`http://localhost:8080/cpanel`**
5. Place your website files (`index.html`, `style.css`, etc.) into the auto-created `public/` directory.

---

### Option 2: Running from Source / Batch Script

If you prefer running from source or customizing the Python code:

1. Clone or extract the repository:
   ```bash
   git clone https://github.com/your-username/localhost-hub.git
   cd localhost-hub
   ```
2. Double-click **`start.bat`** (It will automatically detect your environment, auto-install Python 3.12 if missing, install dependencies, and launch the server).
3. Or launch manually via terminal:
   ```bash
   pip install -r requirements.txt
   python server.py
   ```

---

## 🖥️ cPanel Dashboard Overview

| Section | Description |
| :--- | :--- |
| **📊 System Telemetry** | Real-time CPU, RAM, Disk usage gauges, and live visitor access logs. |
| **🌐 Virtual Hosts & Proxy** | Switch root serving mode (Folder vs Reverse Proxy) and manage subdomains. |
| **📁 File Manager** | In-browser file explorer, zip extraction, and full-screen Dracula code editor. |
| **🗄️ Database Studio** | Visual SQLite manager, table schema builder, SQL query runner, and REST API viewer. |
| **📬 Form Inbox** | Automatic submission collector for website contact forms and lead generators. |
| **🌍 Cloud Tunnel** | 1-Click public HTTPS tunnel generation without router port-forwarding. |
| **⏰ Cron Scheduler** | Task scheduler for background scripts and automated HTTP Webhooks. |
| **⚙️ Server Settings** | Error page customization, caching configuration, and .htaccess rewrite rules. |

---

## 🔌 Built-in REST APIs

LocalHost Hub includes built-in REST API endpoints ready to connect to your frontend:

### 1. Form Submission Endpoint
Submit any HTML form directly to your database:
```html
<form action="http://localhost:8080/api/forms/submit" method="POST">
    <input type="text" name="name" placeholder="Your Name" required />
    <input type="email" name="email" placeholder="Your Email" required />
    <textarea name="message" placeholder="Message"></textarea>
    <button type="submit">Send</button>
</form>
```

### 2. Auto-Generated Database REST API
Perform instant CRUD operations on any SQLite table:
- **List / Query Rows:** `GET /api/db/data?db=main&table=users&page=1&limit=25`
- **Insert Row:** `POST /api/db/insert` (Payload: `{"db": "main", "table": "users", "data": {...}}`)
- **Execute Raw SQL:** `POST /api/db/query` (Payload: `{"db": "main", "sql": "SELECT * FROM users WHERE active = 1"}`)

---

## 📂 Project Structure

```text
d:\local Server\
├── LocalServer.exe          # Standalone Windows Executable
├── start.bat                # 1-Click Auto-Setup & Launcher Script
├── server.py                # Core Gateway & HTTP Server
├── requirements.txt         # Python Dependencies (flask, requests, psutil)
├── bin\                     # Bundled Binaries (cloudflared tunnel client)
├── config\                  # Runtime Configurations (vhosts, tunnels, crons)
├── core\                    # Modular Server Subsystems
│   ├── cache_manager.py     # In-memory RAM file cache & ETag engine
│   ├── cron_manager.py      # Background task & webhook scheduler
│   ├── db_engine.py         # SQLite engine & automated form capture
│   ├── file_manager.py      # File explorer & editor backend
│   ├── htaccess_engine.py   # Rewrite rules & custom error routing
│   ├── system_stats.py      # Hardware telemetry & metrics
│   ├── tunnel_manager.py    # Cloudflare & Pinggy tunnel supervisor
│   └── vhost_router.py      # Virtual host router & reverse proxy
├── data\                    # Persistent Data Storage
│   ├── system.db            # Leads & form submissions database
│   └── databases\           # User SQLite databases
├── public\                  # Default Website Root (HTML, CSS, JS)
├── static\                  # cPanel UI Assets (CSS, JS, Fonts)
└── templates\               # cPanel HTML Templates
```

---

## 🛡️ License

This project is licensed under the **MIT License** — feel free to use, modify, and distribute for personal or commercial projects.

---

<div align="center">
  <sub>Built with ❤️ for developers and creators who want simple, powerful local hosting.</sub>
</div>
