# Clarion UI Copy / Labels Spec (MVP)

This spec defines consistent product language for the UI so Clarion feels like a real, coherent application.

---

## Global UI Tone
- Neutral, calm, non-judgmental
- Avoid clinical or diagnostic language
- Prefer “pattern,” “shift,” “change,” “context,” “segment”
- Avoid definitive claims like “abuse detected” or “manipulation confirmed”

---

## Navigation Labels
- **Projects**
- **Import**
- **Timeline**
- **Annotations**
- **Exports**

Optional:
- **Settings**
- **About**

---

## Project Dashboard

### Header
- Title: **Clarion**
- Subtitle (optional): *Relationship timeline and sentiment analysis*

### Primary CTA
- Button: **New Analysis**

### Project Card Fields
- **Participants:** “Me + [Name]” (or “2 participants”)
- **Date Range:** “YYYY-MM-DD → YYYY-MM-DD”
- **Messages:** “12,483 messages”
- **Last Run:** “Analyzed 2 days ago”

### Empty State
- Title: **No projects yet**
- Body: *Import a message history to generate a sentiment timeline and event annotations.*
- CTA: **Start New Analysis**

---

## Import Wizard

### Step Labels
- **Choose Source**
- **Upload Export**
- **Preview Data**
- **Run Analysis**

### Source Tiles
- **Telegram Export**
- **SMS Export**
- **WhatsApp Export**

### Upload Area
- Title: **Upload your export file**
- Helper: *Your data stays on your device in this prototype.*
- Button: **Choose File**
- Secondary: **Drag and drop here**

### Preview Panel
- Title: **Preview**
- Summary stats:
  - **Messages Detected**
  - **Date Range**
  - **Participants**
- CTA: **Run Analysis**

### Processing States
- “Parsing messages…”
- “Scoring sentiment…”
- “Generating annotations…”
- “Preparing timeline…”

---

## Timeline View

### Page Title
- **Timeline**

### Search
- Placeholder: **Search messages…**

### Filters
- Section header: **Filters**
- Date range: **Date Range**
- Sender: **Sender**
  - **Me**
  - **Them**
  - **Both**
- Sentiment slider: **Sentiment Range**
- Toggle: **Smoothing**
  - On: “Smoothed”
  - Off: “Raw”

### Annotations Panel
- Header: **Annotations**
- Empty state: *No annotations found in this range.*
- Row labels:
  - “Sharp drop”
  - “Sharp rise”
  - “High volume burst”
  - “Tone shift”
  - “Keyword trigger”

### Tooltip / Click Action
- Button: **View Context**

---

## Drill-Down Viewer

### Header
- Title: **Context View**
- Subheader: “25 messages before and after”

### Buttons
- **Export Excerpt**
- **Close**

### Optional AI Summary
- Button: **Summarize this segment**
- Output label: **Segment Summary**
- Helper: *This summary is generated and may be imperfect. Always review the underlying messages.*

---

## Exports

### Page Title
- **Exports**

### Export Types
- **Timeline Image (PNG)**
- **CSV Annotations**
- **HTML Report**
- **Context Excerpt**

### Scope
- Checkbox: **Apply current filters**
- Date range selector label: **Export Range**

### Actions
- Button: **Generate Export**
- Button: **Download**

### Export Complete Message
- “Export generated successfully.”

### Export Error Message
- “Something went wrong while generating this export. Please try again.”
