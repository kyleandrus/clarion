# Clarion PRD (v0) — AI-Assisted Relationship Analysis & Sentiment Timeline Engine

**Document Owner:** (Richard Andrus)  
**Last Updated:** 2026-01-15  
**Status:** Draft / v0  
**Audience:** Portfolio Reviewers, Hiring Managers, Engineers, Designers

---

## 1. Summary

**Clarion** is an AI-assisted analysis tool that helps users understand emotional and behavioral dynamics in message-based relationships (e.g., SMS, Telegram, WhatsApp) by transforming raw communication history into:

- Sentiment timelines
- Annotated behavioral events
- Context drill-down (“what happened before/after this spike?”)
- Searchable, reviewable evidence trails
- Exportable reports for reflection, therapy, or documentation

**Core value proposition:**

> Turn messy relationship history into a clear, navigable timeline of emotional patterns, context, and behavior.

---

## 2. Problem Statement

When people are inside high-conflict, confusing, or emotionally destabilizing relationship dynamics, they often experience:

- memory distortion from stress
- rumination loops
- difficulty explaining patterns clearly to others (therapist, lawyer, trusted friend)
- “I know something is wrong but I can’t map it or explain it”

Raw chat logs are overwhelming and non-navigable. Traditional sentiment tools are often too generic and miss context.

Clarion solves this by providing **structure + visual clarity + evidence navigation**.

---

## 3. Goals (MVP / Base Feature Set)

### Primary Goals
1. Ingest conversation logs into a normalized dataset
2. Generate sentiment + key event annotations
3. Visualize the timeline interactively
4. Enable drill-down into message context around spikes/events
5. Support basic filtering and export for portfolio/demo value

### Guiding Principle
**Time-to-insight matters:** users should reach their first meaningful insight quickly after import.

---

## 4. Non-Goals (MVP)

Clarion MVP will *not* include:

- real-time chat integrations (e.g., WhatsApp API live sync, iMessage sync)
- clinical diagnosis claims (Clarion is not a medical device)
- automated “relationship advice” or coercive recommendations
- multi-user collaboration / shared workspaces
- enterprise admin controls / permissions
- heavy personalization across users (beyond local project history)

---

## 5. Target Users / Personas

### Persona A: Self-Reflective User (Primary)
A user trying to understand:
- why they feel unstable after certain exchanges
- recurring patterns (stonewalling, deflection, love-bombing, blame-shifting)
- their own emotional trend over time

### Persona B: Therapist / Coach Use Case (Secondary)
A professional helping a client:
- quickly review patterns
- identify triggers
- build narrative clarity without reading thousands of messages

### Persona C: Documentation / Legal Support (Secondary)
A user assembling a timeline with evidence references:
- custody/divorce
- harassment patterns
- repeated promises/violations

> Note: Clarion should support documentation workflows without making legal conclusions.

---

## 6. Core Workflows (MVP)

### Workflow 1: Create Project → Import Messages
User creates a “project” representing one relationship/time window and imports:
- Telegram export (JSON/HTML)
- SMS export (CSV)
- WhatsApp export (TXT/JSON)

### Workflow 2: Analyze → Generate Timeline
System runs:
- sentiment scoring per message
- smoothing / aggregation (daily/weekly)
- annotation generation (events/spikes)
- metadata extraction (sender, timestamp, length)

### Workflow 3: Explore Timeline → Drill into Context
User clicks a spike/annotation and sees:
- messages before/after
- a threaded view
- optional AI “context summary” of that segment

### Workflow 4: Filter → Compare → Export
User filters by:
- sender
- date range
- sentiment threshold
- keyword search

Exports:
- PDF/HTML report
- CSV of annotations
- “evidence pack” excerpts (selected message windows)

---

## 7. MVP Feature Set (Base Clarion)

### 7.1 Project Management (Base)
**User story:** As a user, I want separate analysis workspaces so I can keep relationships/time windows organized.

**Requirements:**
- Create project
- Select project
- Basic project metadata (name, date range, participants)
- View project stats (message count, participants, date range)

---

### 7.2 Data Ingestion + Normalization (Base)
**User story:** As a user, I want to import chat logs so Clarion can analyze them.

**Requirements:**
- Parse messages into a standard schema:
  - `timestamp`
  - `sender`
  - `text`
  - `platform`
  - `message_id`
- De-duplication
- Handle missing fields gracefully
- Parsing preview (first N rows/messages)

---

### 7.3 Sentiment Scoring (Base)
**User story:** As a user, I want a sentiment score over time so I can see emotional patterns.

**Requirements:**
- sentiment score per message
- optional confidence score
- aggregation by day/week
- smoothing toggle (on/off)

---

### 7.4 Timeline Visualization (Core)
**User story:** As a user, I want to see patterns over time so I can quickly identify spikes and trends.

**Requirements:**
- interactive chart (scatter and/or line)
- hover tooltips
- zoom + pan
- show annotations on timeline
- highlight selected point/event

---

### 7.5 Annotation Engine (Core)
**User story:** As a user, I want important events detected and labeled so I can focus on what matters.

**Annotation types (initial):**
- sentiment spikes/drops
- abrupt tone shifts
- high-volume bursts
- keyword triggers (e.g., “divorce”, “sorry”, “promise”)
- detected behavior patterns (optional, careful labeling)

**Each annotation stores:**
- timestamp
- type
- short label
- severity score (optional)
- link to context window (message range)

---

### 7.6 Context Drill-Down Viewer (Core)
**User story:** As a user, I want to click an event and view surrounding messages so I can understand context.

**Requirements:**
- show N messages before/after (default 10–25)
- scrollable thread view
- highlight the anchor message(s)
- optionally summarize that segment
- export excerpt (copy/share)

---

### 7.7 Search + Filters (Base)
**User story:** As a user, I want to filter the dataset so I can isolate relevant patterns.

**Requirements:**
- filter by sender
- filter by date range
- filter by sentiment range
- keyword search within messages
- filter by annotation type (optional in MVP)

---

### 7.8 Export (Portfolio-Critical)
**User story:** As a user, I want to export results so I can share insights and preserve documentation.

**MVP exports:**
- export timeline image (PNG)
- export CSV annotations
- export HTML report
- export context excerpt for selected annotation

---

## 8. UX / UI Requirements (Base Screens)

### Screen A — Project Dashboard
**Purpose:** Manage and select analysis projects  
**Includes:**
- list of projects
- “New Analysis” button
- project stats: date range, message count, participants

---

### Screen B — Import Wizard
**Purpose:** Import and validate message data  
**Includes:**
- choose platform: Telegram / SMS / WhatsApp
- upload file
- parsing preview (first 20 rows/messages)
- “Run Analysis” button

---

### Screen C — Timeline View (Main)
**Purpose:** Explore sentiment and events over time  
**Includes:**
- chart panel (sentiment over time)
- sidebar filters (date range, sender, sentiment)
- annotations list (clickable)
- search bar

---

### Screen D — Annotation Drill-Down Panel / Modal
**Purpose:** View message context around an event  
**Includes:**
- annotation details
- thread view (messages before/after)
- highlight anchor message
- “Summarize this segment” (optional)
- “Export excerpt” button

---

### Screen E — Exports / Reports
**Purpose:** Generate shareable artifacts  
**Includes:**
- choose export type: HTML / CSV / PNG
- select date range + filters
- generate + download

---

## 9. Success Metrics (MVP)

### Activation
- % of users who successfully import data and generate a timeline

### Time-to-Insight
- median time from import → first timeline render (**target:** < 2 minutes)

### Engagement
- '#' of annotation clicks per session

### Utility
- exports generated per project
- % of sessions where a drill-down occurs

### Quality
- thumbs up/down on annotation usefulness
- “Was this insight accurate?” feedback

---

## 10. Risks / Constraints

- Sentiment analysis can be misleading without context
- Over-labeling behavior can become judgmental or unsafe
- Privacy concerns: local-first is preferable for trust
- Must clearly label: “assistive analysis, not diagnosis”
- Data ingestion complexity across platforms (format drift, missing fields)

---

## 11. Open Questions

- Should the default view be **sentiment timeline** or **annotation list**?
- What annotation types provide the most value early?
- How much AI explanation is needed (“why was this flagged?”)?
- What is the ideal context window size (10 vs 25 vs adaptive)?
- Should users be able to manually add/edit annotations in MVP?

---

## 12. MVP Scope Summary (One Line)

**Clarion MVP = Import → Analyze → Timeline → Annotate → Drill Down → Export**
