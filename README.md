# Internal Knowledge Base — SOC Guidelines Portal

> ⚠️ \*\*Disclaimer:\*\* This project was created purely for portfolio purposes. All document titles, section names, procedures, and operational content are entirely fictional and do not represent any real organization, company, or security operation. No real data, real guidelines, or real personnel information was used at any point in the development of this project.

\---

## Project Background

As part of managing a Security Operations Center (SOC), one of the most persistent day-to-day challenges is **information fragmentation** — agents arriving for a shift having to hunt across shared drives, email threads, or physical binders to find the procedure they need, often under time pressure when an alert is already active.

I designed and built this project to solve that problem directly. The **Internal Knowledge Base** is a centralized, locally-hosted guidelines portal created so that my agents always have a single, reliable place to go during a shift. Whether they need to verify a call intake procedure, look up the correct escalation path for a Tier 2 incident, or check which SIEM playbook applies to a given alert type — it is all one click away, structured, and always available.

The goal was not just to organize documents, but to create a tool that feels native to the operational environment: a dark interface that is easy on the eyes during long shifts, clear visual section separation so agents can orient quickly under pressure, and a live status indicator that reinforces that the portal is active and ready.

\---

## The Business Problem It Solves

In a SOC environment, speed and accuracy during an incident are directly tied to how quickly an analyst can locate and apply the correct procedure. When guidelines are scattered or inaccessible, agents improvise — and improvisation in security operations introduces risk.

This portal addresses that by:

* **Centralizing all operational documentation** into one access point, eliminating the need to search across multiple locations
* **Organizing guidelines by operational function** so agents know exactly where to look depending on what they are dealing with — whether it is a signal, an incoming call, a software tool, or a general policy question
* **Being locally hostable** with no internet dependency, meaning it remains accessible even in network-restricted or isolated environments
* **Requiring zero training to use** — the interface is self-explanatory, fast to scan, and consistent in its layout so new agents can navigate it from day one
* **Supporting shift continuity** by ensuring the same information is available to every analyst regardless of shift, seniority, or location

\---

<img width="1895" height="745" alt="image" src="https://github.com/user-attachments/assets/43aba70c-5e31-447e-a236-3c9abce2e427" />
<img width="1890" height="681" alt="image" src="https://github.com/user-attachments/assets/f098179d-d208-4c9a-9a02-f9a14f058d68" />


## What the Portal Contains

The portal organizes **40 guidelines** across four operational sections, each colour-coded for fast identification:

|Section|Accent Colour|What It Covers|
|-|-|-|
|01 — Type of Signals \& Procedures|Red `#C51E2D`|How to identify, classify and respond to security signals including intrusion detection, malware alerts, DDoS, phishing, privilege escalation, data exfiltration, and false positive triage|
|02 — Incoming Calls Procedures|Blue `#25A0D5`|Full call-handling workflow from intake and caller verification through to escalation, executive communication, logging, and call closure|
|03 — Software Procedures|Blue `#25A0D5`|Operational use of SOC tooling — SIEM platform, ticketing system, threat intelligence platform, EDR, firewall management, vulnerability scanner, log management, SOAR playbooks, and VPN monitoring|
|04 — General Info|Red `#E93945`|Organizational reference material — SOC structure, shift handover protocol, incident severity definitions, on-call directory, compliance references, data handling policy, training resources, reporting templates, and business continuity|

\---

## Features

* **Single-file architecture** — the entire portal is self-contained in one `index.html` file with all CSS and JavaScript inline; no build tools, no frameworks, no server required
* **Option for Dark UI (Dark mode)** — purpose-built for shift work in low-light environments, reducing eye strain across extended operational hours
  <img width="421" height="52" alt="image" src="https://github.com/user-attachments/assets/bede8f9b-db07-48e4-93e9-28da5ca89813" />
  <img width="410" height="46" alt="image" src="https://github.com/user-attachments/assets/75e219b8-5a96-42bf-8429-11593075c983" />


* **Per-section colour coding** — each of the four panels has a distinct accent colour applied consistently to its top border, icons, section label, PDF markers, and hover interactions, making it fast to visually locate the right section
* **Live clock** — real-time display updated every second, matching the temporal awareness expected in an active operations environment
* **Animated system status indicator** — a pulsing green dot signals that the portal is live and operational
* **Hover interactions** — document rows reveal a colour-matched directional arrow and border accent on hover, providing clear interactive feedback
* **Scrollable panels** — each section panel scrolls independently with a slim custom scrollbar styled to match the dark theme
* **PDF links** — every document row links directly to its corresponding PDF, opening in a new tab without navigating away from the portal

\---

## Tech Stack

|Layer|Choice|
|-|-|
|Markup|HTML5|
|Styling|CSS3 — custom properties, grid, flexbox, keyframe animations|
|Scripting|Vanilla JavaScript — live clock only|
|Icons|[Tabler Icons](https://tabler.io/icons) via CDN webfont|
|Fonts|[Google Fonts](https://fonts.google.com) — Barlow, Barlow Condensed, Share Tech Mono|

No npm. No build step. No framework. Intentionally lightweight so it can run on any machine, intranet server, or static host without setup overhead.

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

## Design Rationale

The dark theme is a deliberate operational choice, not an aesthetic one. SOC analysts work long shifts, often in low-light rooms with multiple monitors. A bright white interface adds unnecessary visual fatigue. The dark palette keeps contrast high where it matters — on the document titles and section labels — while keeping backgrounds recessive.

Colour coding by section serves a functional purpose: under the pressure of an active incident, an analyst should be able to glance at the portal and immediately know which quadrant to reach for. The consistent application of each accent colour across every element of a panel — border, icon, label, hover state — reinforces that mapping without requiring the analyst to read anything first.

The decision to keep all interactivity CSS-driven (except the clock) means the portal loads instantly, works without JavaScript enabled for all core navigation, and has no external dependencies that could fail during a network issue.

\---

## License \& Copyright

© 2026 Konstantina Gianniou. All rights reserved.

This project, including its structure, design, and code, was created by Konstantina Gianniou and is shared here for portfolio and demonstration purposes only. It may not be reproduced, distributed, or used as the basis for a commercial product without explicit written permission from the author.

\---

*Built by Konstantina Gianniou — Security Operations · Internal Tools · Portfolio 2026*

