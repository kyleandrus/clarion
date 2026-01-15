# Clarion UI Prototype Checklist (Base Screens + Components)

This checklist defines the **minimum UI surfaces** needed to prototype Clarion MVP end-to-end in Figma.

---

## Screen A — Project Dashboard

### Purpose
Entry point for managing and launching analysis projects.

### Components
- App header (Clarion logo + project switcher)
- Primary CTA: **New Analysis**
- Project cards/list with:
  - Project name
  - Participants (e.g., “Me + Kelsie”)
  - Date range (e.g., “2023-05 → 2024-12”)
  - Message count
  - Last analyzed timestamp
- Quick actions:
  - Open project
  - Export report (disabled until analyzed)
  - Delete/archive (optional)
- Empty state:
  - “No projects yet” + CTA to import first dataset

---

## Screen B — Import Wizard

### Purpose
Upload and validate message export data.

### Step 1: Select Source
- Source tiles/buttons:
  - Telegram Export
  - SMS Export
  - WhatsApp Export
- Helper text: “Clarion runs locally and keeps your data private.” (optional)

### Step 2: Upload File
- Drag/drop upload component
- File requirements helper:
  - Allowed formats per platform (JSON/HTML/CSV/TXT)
- Error states:
  - Unsupported file type
  - Parse failure
  - Empty file

### Step 3: Parsing Preview
- Preview table/list (first 20 messages)
  - Timestamp
  - Sender
  - Snippet
- Summary stats panel:
  - Total messages detected
  - Date range detected
  - Participants detected
- CTA: **Run Analysis**

### Step 4: Processing State
- Progress indicator (parsing → scoring → annotating)
- Cancel button (optional)

---

## Screen C — Timeline View (Main)

### Purpose
Primary analysis workspace for exploring sentiment + events.

### Layout
- Left sidebar: filters + annotation list
- Main panel: timeline visualization
- Optional right panel: details/context (or use modal)

### Components (Main Panel)
- Chart: sentiment over time
  - points or line (or both)
  - annotation markers
- Hover tooltip:
  - timestamp
  - sentiment score
  - sender (if single message point)
  - “View context” action
- Zoom/pan controls
- Smoothing toggle (on/off)
- Legend (sentiment scale + annotation types)

### Components (Sidebar)
- Search bar (search within messages)
- Filters:
  - Date range picker
  - Sender toggle (Me / Them / Both)
  - Sentiment range slider
  - Annotation type filter (optional)
- Annotation list (clickable):
  - label (e.g., “Sharp drop”)
  - timestamp
  - severity indicator (optional)

### States
- No annotations found (empty list)
- Loading state when filters applied
- “Select an event to view context”

---

## Screen D — Annotation Drill-Down Viewer (Panel/Modal)

### Purpose
Context inspection: show message thread around an event.

### Components
- Header:
  - Annotation label + timestamp
  - Buttons: Export excerpt, Close
- Message thread window:
  - scrollable list
  - grouped by sender (visual distinction)
  - timestamps shown
  - highlight anchor message(s)
- Context window selector:
  - 10 / 25 / 50 messages before/after (optional)
- Optional AI assist:
  - Button: **Summarize this segment**
  - Output box: short neutral summary + key points
  - “Copy summary” action

### States
- If messages missing/unavailable (edge case)
- If summary generation fails

---

## Screen E — Exports / Reports

### Purpose
Generate shareable artifacts for review or documentation.

### Components
- Export type selector:
  - Timeline Image (PNG)
  - CSV Annotations
  - HTML Report
  - Context Excerpt (for selected event)
- Scope selector:
  - Full project vs date range
  - Apply current filters (checkbox)
- Generate button
- Download button / link
- Export history list (optional)

### States
- Export generation loading
- Export error state
