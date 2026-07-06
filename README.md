<div align="center">

<img src="https://raw.githubusercontent.com/maheshmaximusmax/max-ping-test/main/assets/logo.png" width="96" alt="Max Ping Test Logo">


# Max Ping Test

**Bulk IP Ping Tester & Network Monitor for Windows**

[![Windows](https://img.shields.io/badge/Platform-Windows-blue?logo=windows)](https://github.com/maheshmaximusmax/max-ping-test/releases)
[![Download](https://img.shields.io/github/downloads/maheshmaximusmax/max-ping-test/total?label=Downloads&color=purple)](https://github.com/maheshmaximusmax/max-ping-test/releases)
[![Latest Release](https://img.shields.io/github/v/release/maheshmaximusmax/max-ping-test?color=green)](https://github.com/maheshmaximusmax/max-ping-test/releases/latest)
[![License](https://img.shields.io/badge/License-Free-brightgreen)](LICENSE)

**Upload a CSV or Excel sheet → instantly ping all IPs → live green/red status table.**
Built for industrial networks: energy meters, PLCs, HMIs, IoT gateways, SCADA sites.

[⬇️ Download .exe](https://github.com/maheshmaximusmax/max-ping-test/releases/latest) · [📸 Screenshots](#screenshots) · [⚡ Quick Start](#quick-start) · [✨ Features](#features)

</div>

---

## What is Max Ping Test?

Max Ping Test is a **free, single-file Windows app** for bulk IP ping monitoring.
You upload your IP list (CSV or Excel), and it pings all of them in parallel — showing live **green = online / red = offline** status with real latency, uptime duration, and full history.

No Python. No installation. No command line. Just one `.exe` that runs anywhere.

Designed for network engineers, automation engineers, and SCADA operators who need to monitor **dozens to hundreds of devices** across multiple sites — energy meters, PLCs, HMIs, IoT gateways, routers, cameras — from a single dashboard.

---

## Screenshots

> *(Add your screenshots to the `assets/` folder and they appear here automatically)*

| Dashboard | Login | Admin Panel |
|---|---|---|
| ![Dashboard](assets/screenshot-dashboard.png) | ![Login](assets/screenshot-login.png) | ![Admin](assets/screenshot-admin.png) |

**114 online · 102 offline · 216 total — live, every 6 seconds.**

---

## Quick Start

### Option A — Just run the exe (no install needed)

1. Go to [**Releases**](https://github.com/maheshmaximusmax/max-ping-test/releases/latest)
2. Download `Max Ping Test.exe`
3. Double-click it → browser opens → log in → upload your IP sheet → done

**Nothing else to install. Works on any Windows PC.**

### Option B — Add a desktop icon (optional)

Download the full release zip, extract it, and run `install.bat`.
This adds **Max Ping Test** to your Desktop and Start Menu with the logo icon.

---

## Features

### 📋 Upload Any IP Sheet — No Formatting Required
- Upload **CSV or Excel** files in any layout (multi-table, multi-site, messy headers)
- Auto-detects every IPv4 address and its Site Name from your existing sheet
- Works with **energy meter sheets, PLC lists, IoT gateway tables, SCADA device lists**
- No column renaming. No templates. Upload as-is.

### 🟢 Real ICMP Ping — No False Results
- Uses **TTL-based detection**: a host is UP only if the ping reply contains `TTL=`
- Router "Destination host unreachable" replies are correctly shown as **DOWN**
- Latency is the real reply time (not the timeout wait)
- Parallel pinging (up to 60 simultaneous) with configurable retries

### 📊 Uptime / Downtime History
- **Since** — exact date & time the current status started
- **Duration** — how long in current state (e.g., `3d 04:12:07`)
- **Last Online** / **Last Offline** — full timestamps
- History is **saved to disk** and survives app restarts

### ✏️ Edit Inline — No Spreadsheet Needed
- Click any Site or IP cell to edit it directly in the table
- **Ctrl+S** or "Save setup" button to save the current list as a named setup
- Add rows manually, delete rows with ✕
- Named setups **auto-load on next launch**

### 📤 Export to CSV or Excel
- Export the full table with Status, Latency, Duration, Last Online, Last Offline
- Timestamped filename (e.g., `MySetup_status_20260706_1900.xlsx`)
- Open in Excel or import into your SCADA/report system

### 🔍 Filter & Search
- Filter by site name or IP address (text search)
- Quick filter: **All / Online only / Offline only**
- Instantly see which sites are down without scrolling

### 🔁 Background Monitoring Toggle
- Keep pinging in the background while the window is minimized
- Pause monitoring without closing the app
- Setting is remembered across restarts

### ⚙️ Fully Adjustable
| Setting | Default | What it does |
|---|---|---|
| Interval | 6s | How often all IPs are re-pinged |
| Timeout | 2000ms | Per-host ping wait (raise for VPN/WAN) |
| Parallel | 20 | Simultaneous pings (max 60) |
| Retries | 1 | Re-ping before marking DOWN |

### 🔐 Login & User Management
- Simple login screen (email + password)
- Admin account pre-set — sign in immediately
- Admin panel: view all registered users, disable or delete accounts
- Passwords are hashed (PBKDF2 + salt)

---

## Who Is This For?

| Role | Use case |
|---|---|
| **Automation / SCADA Engineer** | Monitor PLCs, HMIs, energy meters across plant subnets via WireGuard VPN |
| **Network Engineer** | Bulk ping all devices in a subnet, track uptime history |
| **IT Administrator** | Monitor servers, printers, cameras — upload your asset list CSV |
| **Field Engineer** | Carry the exe on a USB, run it on any site PC with no install |
| **Water / Power / Utilities** | Watch IoT gateways and meters across multiple remote sites |

---

## Compared to Other Tools

| Feature | Max Ping Test | PingInfoView | vmPing | Angry IP Scanner |
|---|---|---|---|---|
| Upload CSV/Excel IP list | ✅ Any format | ❌ Manual entry | ❌ Manual | ❌ IP range only |
| Uptime/downtime history | ✅ With timestamps | ⚠️ Count only | ❌ | ❌ |
| Real TTL-based detection | ✅ | ✅ | ✅ | ✅ |
| Export to Excel | ✅ | ✅ CSV | ❌ | ✅ |
| Site Name grouping | ✅ Auto-detect | ❌ | ❌ | ❌ |
| Named setups / profiles | ✅ | ❌ | ❌ | ❌ |
| Single exe, no install | ✅ | ✅ | ❌ .NET | ✅ |
| Industrial / SCADA focus | ✅ | ❌ | ❌ | ❌ |

---

## Use Case: Industrial Multi-Site Monitoring

Max Ping Test was built for a real industrial deployment with:
- **215 devices** across **12+ sites** (energy meters, IoT gateways, PLCs, HMIs)
- Sites on separate subnets connected via **WireGuard VPN** over **Teltonika RUTX50 / RUT200** routers
- Devices on **192.168.25.x, .28.x, .29.x, .31.x, .32.x, .33.x, .34.x** — all in one CSV
- Required detecting true offline vs. "router unreachable" (TTL fix)
- Export report emailed to site supervisor weekly

If your setup looks like this, Max Ping Test was made for you.

---

## How It Works

```
Double-click exe
      ↓
App starts a local web server (no internet required)
      ↓
Browser opens → Login screen
      ↓
Upload CSV / Excel with your IP addresses
      ↓
App auto-detects all IPs + Site Names from the sheet
      ↓
Pings all IPs in parallel every N seconds (real ICMP)
      ↓
Live table: 🟢 UP (with real latency) | 🔴 DOWN
      ↓
History tracked: since when, how long, last seen
      ↓
Export to CSV / Excel anytime
```

**No internet connection required.** Everything runs locally on your PC.

---

## System Requirements

- Windows 10 or Windows 11 (64-bit)
- Any modern browser (Chrome, Edge, Firefox) — opens automatically
- Network access to the devices you want to ping
- **No Python. No .NET. No other software.**

---

## FAQ

**Q: The app shows everything as DOWN. Why?**
Your PC can only reach devices that are routable from your current network. If you're monitoring devices on other subnets (e.g., 192.168.29.x from your 192.168.31.x PC), you need your VPN/gateway routing to be active. Test with `ping 192.168.29.36` in Command Prompt first. If that times out, it's a routing issue, not the app.

**Q: Does it need an internet connection?**
No. Everything runs locally. The browser just displays the app from your local PC.

**Q: Can I run it on a server or leave it running overnight?**
Yes. Minimize the window and leave it running. The monitoring toggle keeps it active. History is saved to disk every 10 seconds.

**Q: Can I monitor devices over WireGuard / OpenVPN?**
Yes. As long as the VPN tunnel is up and the devices are routable from your PC, it pings them normally. Raise the Timeout setting to 2000–3000ms for VPN targets.

**Q: Why does it open in a browser instead of its own window?**
This is what makes it a **single exe with zero dependencies**. A native window requires WebView2 runtime or .NET to be pre-installed — which breaks on many site PCs. The browser is always available.

**Q: Can I use this with Google Sheets?**
Yes. In Google Sheets: **File → Download → Comma-separated values (.csv)** — then upload that file.

**Q: Is the source code available?**
The application is distributed as a compiled Windows executable. Source is not publicly available to protect the implementation.

---

## Release Notes

### v1.0.0
- Bulk IP ping from CSV / Excel upload (any messy format)
- Real TTL-based ICMP detection (no false results)
- Live green/red status table with real latency
- Uptime/downtime history with timestamps and duration in days
- Online/Offline filter + text search
- Inline edit (Site, IP), add rows, delete rows
- Named setups with auto-load on launch (Ctrl+S to save)
- Export to CSV and Excel with full history columns
- Background monitoring toggle
- Login screen with admin panel (user management)
- Single standalone exe — no install, no dependencies

---

## Keywords

`bulk ip ping` · `ip ping tester` · `ip ping monitor` · `mass ping tool` · `bulk ping windows` · `network ip checker` · `multi ip ping` · `ping multiple hosts` · `ping from csv` · `ping from excel` · `industrial network monitor` · `scada ping monitor` · `plc ip monitor` · `energy meter monitor` · `iot device monitor` · `hmi ping test` · `uptime monitor windows` · `ip availability monitor` · `network device monitor` · `ping status dashboard` · `bulk icmp ping` · `ping history windows` · `site ip monitor` · `offline detector` · `lan monitor windows free`

---

## License

Free to use. Executable distributed for personal and commercial use.
Not open source — source code is not included.

---

## Author

**Mahesh Parmar (Max)**
Automation & Site Engineer | Lariox Technologies | Surat, Gujarat, India
GitHub: [@maheshmaximusmax](https://github.com/maheshmaximusmax)

---

<div align="center">

⭐ **If this tool saved you time, give it a star — it helps others find it.** ⭐

[Download Latest Release](https://github.com/maheshmaximusmax/max-ping-test/releases/latest)

</div>
