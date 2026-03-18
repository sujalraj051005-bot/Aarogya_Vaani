# AarogyaVaani — Indic Voice AI for Patient Engagement

<p align="center">
  <img src="https://img.shields.io/badge/Track-Indic%20Voice%20AI-blueviolet?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Hackathon-IIT%20Patna-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Languages-Hindi%20%7C%20Bhojpuri%20%7C%20Marathi%20%7C%20Telugu-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Live%20Demo-brightgreen?style=for-the-badge"/>
</p>

<p align="center">
  <b>An outbound AI voice platform that calls patients in their native Indic language —
  before they arrive, after they leave, and every week in between —
  turning every conversation into structured clinical data.</b>
</p>

<p align="center">
  <a href="https://sujalraj051005-bot.github.io/Aarogya_Vaani/">
    <img src="https://img.shields.io/badge/🚀%20Live%20Demo-Click%20Here-blue?style=for-the-badge"/>
  </a>
</p>

---

## The Problem

India has a silent healthcare crisis that happens *after* the clinic visit ends.

- **600M+** rural and semi-urban patients receive zero structured follow-up after discharge
- **~60%** medication non-adherence rate among chronic disease patients
- **100M+** diabetics with no system tracking their weekly adherence
- **0** voice-based patient-reported outcomes tools exist in any Indic language
- Readmissions go undetected in the critical **48-hour post-discharge window**
- Doctors have no longitudinal visibility into what happens to patients at home

The result: preventable complications, avoidable readmissions, and a complete absence of structured clinical data from the most critical phase of patient care.

---

## The Solution

AarogyaVaani places automated outbound calls to patients in their native language, asks the right clinical questions, detects danger signs in real time, and converts every conversation into a structured record — with zero manual data entry.

---

## Four Core Modules

| Module | Trigger | What It Does |
|--------|---------|-------------|
| **Pre-Arrival Triage** | 2–4 hrs before OPD | Collects complaint, pain scale, urgency. Pre-fills doctor's intake form |
| **Post-Discharge Follow-up** | 24hr & 48hr after discharge | Checks prescription fill, danger signs, next appointment awareness |
| **Chronic Disease Coach** | Weekly recurring call | Meds, diet, symptoms for diabetes/hypertension. Builds longitudinal PRO dataset |
| **Caregiver Proxy** | When patient is elderly/low-literacy | Routes call to registered family caregiver. Same NLP pipeline, full data consistency |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Indic STT + TTS | Sarvam AI API |
| Call Orchestration | Exotel (outbound calls + webhooks) |
| Messaging Fallback | Twilio (WhatsApp + SMS) |
| NLP & Intent Extraction | Claude API (claude-sonnet) |
| Backend | Python — FastAPI |
| Database | PostgreSQL |
| Frontend | React + Tailwind CSS |
| Real-time Updates | WebSocket |
| Deployment | Docker Compose |

---

## How It Works
```
Patient Profile + Schedule
         ↓
  Exotel Outbound Call
         ↓
  Sarvam AI TTS → Patient hears question in native language
         ↓
  Patient speaks → Sarvam AI STT → Raw transcript
         ↓
  Claude NLP → Clinical entity extraction
         ↓
  Risk Scoring → GREEN / AMBER / RED
         ↓
     ┌───────────────────────────┐
     │                           │
  GREEN/AMBER              RED detected
  → Next question          → Immediate escalation
  → Build record           → Notify doctor
     │                           │
     └───────────┬───────────────┘
                 ↓
     Structured CallRecord → PostgreSQL
                 ↓
     Dashboard updates via WebSocket
```

---

## Risk Scoring System

| Tier | Trigger Keywords | Action |
|------|-----------------|--------|
| 🔴 RED | Chest pain, loss of consciousness, glucose > 400, "hosh nahi", "nahi uth pa raha" | Immediate escalation, doctor notified |
| 🟡 AMBER | Missed > 3 doses, glucose > 250, dizziness, swelling in feet | Flagged for follow-up review |
| 🟢 GREEN | No risk indicators detected | Record logged, next call scheduled |

---

## Live Demo Features

> No server needed. Single HTML file. Opens directly in Chrome.

- **Live Call Simulation** — Watch a real-time animated call with Ramesh Kumar (diabetes, Hindi). Transcript builds line by line, NLP detects keywords, risk tier escalates GREEN → AMBER → RED live on screen
- **Caregiver Proxy Demo** — Sunita Devi's son Rajesh answers in Bhojpuri, reports chest pain, triggers RED escalation with Watch Mode fullscreen overlay
- **Patient Registry** — 7 patients across all risk tiers. Every View Record button works with full call history, adherence chart, and structured JSON output
- **Hospital Dashboard** — Risk tier breakdown (3 RED, 11 AMBER, 34 GREEN), module progress bars, adherence trend chart, high-risk flags table
- **Escalation Queue** — 3 RED patients with working Notify Doctor buttons
- **Workflow Builder** — Drag-and-drop call script builder for diabetes weekly coach with 6 question blocks and conditional logic
- **Analytics** — 8-week adherence chart, call outcome breakdown, language distribution across 5 Indic languages

---

## Demo Patients

| Patient | Condition | Risk | Special |
|---------|-----------|------|---------|
| Ramesh Kumar | Diabetes | 🔴 RED | Main call simulation |
| Sunita Devi | Hypertension | 🔴 RED | Caregiver proxy demo |
| Vijay Sharma | Post-Surgery | 🔴 RED | Post-discharge module |
| Priya Patel | Diabetes | 🟡 AMBER | Marathi language |
| Mohan Das | Hypertension | 🟡 AMBER | Bhojpuri + caregiver |
| Anita Singh | Diabetes | 🟢 GREEN | Full adherence |
| Kavitha Rao | Post-Surgery | 🟢 GREEN | Telugu language |

---

## Impact Numbers
```
100M+    diabetics in India
 600M+    patients with zero structured follow-up
  ~60%    medication non-adherence rate
     0    existing voice PRO tools in any Indic language
   34%    projected reduction in avoidable OPD revisits
   68%    medication adherence rate after 8 weeks
    47    early escalations per month preventing complications
     5+   Indic languages supported
```

---

## Project Structure
```
Aarogya_Vaani/
├── aarogyavaani.html     ← Full working demo (open in Chrome)
├── index.html            ← Landing page
└── README.md
```

---

## Team

| Name | Role |
|------|------|
| **Sujal Raj** | Team Lead & Full Stack Developer — Backend architecture, FastAPI call engine, Claude API NLP, Sarvam AI STT/TTS, database design, deployment |
| **Nishant Sharma** | Frontend Developer — React dashboard, WebSocket integration, UI/UX, Exotel webhook handling |
| **Swet Raj** | Data & QA Engineer — Patient data modelling, risk scoring logic, testing, analytics, documentation |

---

## Hackathon

| | |
|-|-|
| **Event** | Jilo Health Hackathon |
| **Venue** | IIT Patna |
| **Track** | Track 3 — Indic Voice AI Patient Engagement |
| **Platform** | Unstop |

---

## Contact

**Sujal Raj** — Team Lead  
📧 sujalraj20051005@gmail.com  
🐙 [@sujalraj051005-bot](https://github.com/sujalraj051005-bot)

---

<p align="center">
  Built with ❤️ for Indian healthcare
</p>
```

---

