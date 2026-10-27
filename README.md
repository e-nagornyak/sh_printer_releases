<p align="center">
  <img src="assets/icon.png" width="128" height="128" alt="MyOrders icon">
</p>

<h1 align="center">MyOrders</h1>

<p align="center">
  Desktop companion for order processing: prints shipping labels and invoices
  automatically and drives your fiscal cash register — no clicks required.
</p>

<p align="center">
  <a href="https://github.com/e-nagornyak/sh_printer_releases/releases/latest"><img src="https://img.shields.io/github/v/release/e-nagornyak/sh_printer_releases?label=latest&color=8b5cf6" alt="Latest release"></a>
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20macOS-111111" alt="Platforms: Windows, macOS">
  <a href="https://github.com/e-nagornyak/sh_printer_releases/releases"><img src="https://img.shields.io/github/downloads/e-nagornyak/sh_printer_releases/total?color=111111" alt="Downloads"></a>
</p>

<p align="center">
  <a href="https://github.com/e-nagornyak/sh_printer_releases/releases/latest"><b>⬇ Download the latest version</b></a>
  &nbsp;·&nbsp;
  <a href="https://github.com/e-nagornyak/sh_printer_releases/releases">All releases</a>
</p>

---

## What it does

MyOrders runs quietly in the system tray and stays connected to the MyOrders
server. When an order needs a label, an invoice or a fiscal receipt, the server
sends the job and the app executes it on your local hardware right away:

- **Labels and invoices** are downloaded and sent to the printer you assigned
  to each role.
- **Fiscal commands** — receipts, receipt cancellation, cash drawer, Z-report —
  go straight to the cash register over the network or a COM port.

## Features

- 🖨️ **Automatic printing** to two independent printers: invoices and labels
- 🧾 **Fiscal register support** — Elzab (EZLAB protocol) and Postnet / Novitus,
  over TCP/IP or COM port, with paper status monitoring
- 📊 **Live dashboard** — connection status of every server and device, plus a
  feed of all jobs processed in the session
- 🔄 **Automatic updates** — the app checks for new versions and installs them
  for you
- 🚀 **Starts with the system**, minimised to the tray
- 🪵 **Built-in logs and a one-click diagnostics report** for support
- 🌐 English and Russian interface

## Download

| Platform | File | Requirements |
| --- | --- | --- |
| **Windows** | `Sh-Printer-Setup-<version>.exe` — installer | Windows 10 / 11, 64-bit |
| **macOS** | `Sh-Printer-<version>.dmg` — disk image | macOS 10.13+, Intel or Apple Silicon |

Get both from the **[latest release](https://github.com/e-nagornyak/sh_printer_releases/releases/latest)**.
Previous versions and their change notes are on the
**[releases page](https://github.com/e-nagornyak/sh_printer_releases/releases)**.

## Installation

### Windows

1. Download and run `Sh-Printer-Setup-<version>.exe`.
2. If Windows shows **“Windows protected your PC”**, click **More info → Run anyway**.
3. Follow the installer. Everything needed for printing is included; the
   WebView2 runtime is installed automatically if it is missing.

### macOS

1. Open the `.dmg` and drag the app into **Applications**.
2. The build is not notarized by Apple, so the first launch needs one extra step:
   - right-click the app → **Open** → **Open**, or
   - on macOS 15 and newer: try to open the app once, then go to
     **System Settings → Privacy & Security** and click **Open Anyway**.

This is only needed the first time.

## First-time setup

Open **Settings** from the dashboard:

1. **Authorization token** — paste the token from the admin panel. The server
   cards on the dashboard switch to **Connected** once it is accepted.
2. **Printers** — choose a system printer for **Factura Printer** (invoices)
   and **Label Printer** (shipping labels). Use **Test** next to each one to
   print a test page.
3. **Cash register** — pick the protocol that matches your device
   (*EZLAB (Elzab)* or *Postnet / Novitus*), then the connection type:
   - **TCP / network** — IP address and port
   - **COM port** — port name and baud rate

   Click **Test register connection** to verify it. Until a protocol is
   selected, fiscal tasks from the server are not processed.
4. **Startup** — enable **Start with the system** so the app is always running.

## Updates

The app checks this repository shortly after launch and then every few hours.
When a new version is available you get a notification and a window with the
list of changes:

- **Windows** — click **Update now**: the update installs silently and the app
  restarts in the tray.
- **macOS** — the new `.dmg` opens; drag the app into **Applications** to
  replace the old one.

You can also check manually: **Settings → Updates → Check for updates**.

## Troubleshooting

The quickest way to get help is a **diagnostics report**: open the **Logs** tab
and click **Report**. It collects the app version, OS, available printers,
settings (with the token masked), connection status and recent log entries into
a single file and opens its folder — just send that file to support.

Log files are stored here:

| OS | Location |
| --- | --- |
| Windows | `%APPDATA%\sh-printer\logs\` |
| macOS | `~/Library/Application Support/sh-printer/logs/` |

Common issues:

- **“Invalid token”** — the server rejected the token; update it in Settings
  and the connection resumes on its own.
- **Printer is not installed on this system** — the printer chosen in Settings
  was renamed or removed; pick it again from the list.
- **Cash register is not responding** — check the cable or network, the IP
  address / COM port, and that the right protocol is selected.

---

<sub>This repository hosts release builds only; the source code is private.</sub>
