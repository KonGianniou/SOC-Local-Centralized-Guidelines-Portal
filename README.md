# Internal Knowledge Base — SOC Guidelines Portal

> ⚠️ \*\*Disclaimer:\*\* This project was created purely for portfolio purposes. All document titles, section names, procedures, and operational content are entirely fictional and do not represent any real organization, company, or security operation. No real data, real guidelines, or real personnel information was used at any point in the development of this project.

\---

## Why I built this

Managing a SOC, one of the more annoying day-to-day problems is information fragmentation with agents starting a shift and having to dig through shared drives, old email threads, or a physical binder to find the procedure they need, usually while an alert is already active.

I built this to fix that for my own team. It's a centralized, locally-hosted guidelines portal so agents have one place to go during a shift instead of hunting around. Need the call intake steps? The escalation path for a Tier 2 incident? Which guideline applies to an alert type? It's one click away.


I wanted it to feel like it belongs in the operational environment it's used in with a dark interface for long shifts and clear separation between sections so people can find things fast under pressure.

\---

## The Business Problem It Solves

In a SOC, how fast you can find and apply the right procedure matters. When guidelines are scattered, people start improvising, and improvisation in security ops is where things go wrong.


This tries to fix that by:

* Putting all the documentation in one place instead of several
* Organizing guidelines by what an agent is actually dealing with: a signal, an incoming call, a tool, or a policy question
* Running locally with no internet dependency, so it still works on isolated or network-restricted machines
* Being easy enough to use with zero onboarding — new agents shouldn't need a walkthrough
* Keeping the same info available to every shift, regardless of who's on or where they're working from

\---

  <img width="1895" height="745" alt="image" src="https://github.com/user-attachments/assets/43aba70c-5e31-447e-a236-3c9abce2e427" />
  <img width="1890" height="681" alt="image" src="https://github.com/user-attachments/assets/f098179d-d208-4c9a-9a02-f9a14f058d68" />


## What's in it

40 guidelines split across four sections, each with its own accent colour so they're easy to tell apart at a glance:

| Section | Accent Colour | Covers |
|---|---|---|
| 01 — Type of Signals & Procedures | Red `#C51E2D` | Identifying, classifying and responding to signals — intrusion detection, malware alerts, DDoS, phishing, privilege escalation, data exfiltration, false positive triage |
| 02 — Incoming Calls Procedures | Blue `#25A0D5` | Call handling end-to-end: intake, caller verification, escalation, executive comms, logging, closure |
| 03 — Software Procedures | Blue `#25A0D5` | Using the SOC tooling — SIEM, ticketing, threat intel platform, EDR, firewall management, vulnerability scanner, log management, SOAR playbooks, VPN monitoring |
| 04 — General Info | Red `#E93945` | SOC structure, shift handover, incident severity definitions, on-call directory, compliance references, data handling policy, training resources, reporting templates, business continuity |


\---

## Features

* **Single-file architecture** — the entire portal is self-contained in one `index.html` file with all CSS and JavaScript inline; no build tools, no frameworks, no server required
* **Option for Dark UI (Dark mode)** — purpose-built for shift work in low-light environments, reducing eye strain across extended operational hours

  <img width="421" height="52" alt="image" src="https://github.com/user-attachments/assets/bede8f9b-db07-48e4-93e9-28da5ca89813" />  <img width="410" height="46" alt="image" src="https://github.com/user-attachments/assets/75e219b8-5a96-42bf-8429-11593075c983" />  


* **Colour-coded sections** — each panel's accent colour carries through its border, icons, label, PDF markers, and hover states, so you can find the right section without reading anything
* **Live clock** — updates every second
* **Status indicator** — pulsing green dot to show the portal's live
* **Hover feedback** — document rows show a colour-matched arrow and border accent on hover
* **Independent scrolling panels** — each section scrolls on its own, with a slim scrollbar matching the theme
* **PDF links** — every row opens its PDF in a new tab, no navigating away from the portal


\---

## Tech Stack

|Layer|Choice|
|-|-|
|Markup|HTML5|
|Styling|CSS3 — custom properties, grid, flexbox, keyframe animations|
|Scripting|Vanilla JavaScript — live clock only|
|Icons|[Tabler Icons](https://tabler.io/icons) via CDN webfont|
|Fonts|[Google Fonts](https://fonts.google.com) — Barlow, Barlow Condensed, Share Tech Mono|

No npm, no build step, no framework. It runs on basically any machine, intranet server, or static host with zero setup.

\---

## File Structure

```
internal-knowledge-base/
│
├── index.html          # Complete portal — all CSS and JS inline
│
└── pdfs/               # 40 PDF guidelines linked by the portal
    ├── s1\_01\_intrusion\_detection\_signals.pdf
    ├── s1\_02\_malware\_alert\_classification.pdf
    ├── s1\_03\_network\_anomaly\_procedures.pdf
    ├── ... 
    └── s4\_10\_glossary\_of\_terms.pdf
```

\---

## How to Deploy

**Locally (intranet / shift machine):**

1. Clone or download the repository
2. Place the 40 PDF files inside a `/pdfs` folder alongside `index.html`
3. Open `index.html` in any modern browser — no server needed



\---



## License \& Copyright

© 2026 Konstantina Gianniou. All rights reserved.

This project, including its structure, design, and code, was created by Konstantina Gianniou and is shared here for portfolio and demonstration purposes only. It may not be reproduced, distributed, or used as the basis for a commercial product without explicit written permission from the author.

\---

*Built by Konstantina Gianniou — Security Operations · Internal Tools · Portfolio 2026*

