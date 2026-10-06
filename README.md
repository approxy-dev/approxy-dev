# Hi, I'm Approxy 👋

**I build Windows desktop tools that respect your time and your machine — and the
static sites that document them.**

I work on small, self-contained utilities: no accounts, no telemetry, no
phone-home, no dark patterns. If a tool makes a claim, the code that backs it is
something you can read.

---

## What I'm working on

### 🌙 SleepGuardian — a Windows bedtime commitment device

SleepGuardian shuts your PC down at curfew and locks it until your wake time.
It is a commitment device, not a reminder app: there is no snooze button and no
dialogue to dismiss.

- **Enforced by a Windows service**, backed by a per-minute watchdog — closing
  the tray app or killing the process does not end enforcement.
- At curfew the machine powers off; on boot it goes straight into a full-screen
  lock counting down to your wake time, with Task Manager, Command Prompt and
  the Windows key restricted while locked.
- **No network requests, no telemetry, no analytics, no update check.** Everything
  lives locally in `C:\ProgramData\SleepGuardian` (SQLite), and any admin
  password is stored only as a PBKDF2 hash, verified inside the service.
- Schedules of 7 or 8 hours, daily/weekday/weekend/custom recurrence, streak
  targets, a calendar heatmap, and CSV + JSON export.

📖 **Site & docs:** [`approxy-dev/sleep-guardian`](https://github.com/approxy-dev/sleep-guardian)

### 💻 PCReady — fresh PC, ready faster

PCReady rebuilds your Windows software environment after a fresh install.

- **336 curated apps across 23 categories**, 5 setup profiles, automated
  installation through **WinGet** and direct installers.
- Ships as a **self-contained portable binary** — no installer and no .NET
  runtime required; extract anywhere and run. SHA-256 published alongside it.

📖 **Site & docs:** [`approxy-dev/PCReady`](https://github.com/approxy-dev/PCReady)

---

## How I build the sites

Both product sites are static-first and deliberately boring:

| | SleepGuardian site | PCReady site |
| --- | --- | --- |
| Framework | Next.js 15 (App Router) | TanStack Start |
| UI | React 19, Tailwind CSS v4 | React 19, Vite 8, Tailwind CSS v4 |
| Output | Fully static — no database, no API route, no form handler, no analytics, no third-party script | Statically prerendered (SSG) |
| Extras | Self-hosted fonts, WCAG AA contrast, JSON-LD | Prerendered to 9 routes, deployable anywhere |

I care about the unglamorous parts: canonical URLs, `sitemap.xml`, `robots.txt`,
Open Graph tags, JSON-LD, and keeping the rendered page free of third-party
scripts. Every product claim on the SleepGuardian site is traceable to a line of
source — see [`DISCOVERY.md`](https://github.com/approxy-dev/sleep-guardian/blob/master/DISCOVERY.md).

---

## Toolbox

**Languages & runtime** — TypeScript, JavaScript, C#, PowerShell
**Front end** — React, Next.js, TanStack Start, Vite, Tailwind CSS
**Platform** — Windows (WPF, Win32 services, scheduled tasks, WinGet)
**Shipping** — GitHub Releases, Vercel, static prerendering

---

## Get in touch

- 📧 Email: [approxydev@gmail.com](mailto:approxydev@gmail.com)
- 🐦 GitHub: [@approxy-dev](https://github.com/approxy-dev)

I'm always happy to talk to people who build careful, honest software.
