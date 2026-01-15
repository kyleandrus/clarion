# Clarion PRD (One-Page) — v0 Executive Summary

**Product:** Clarion  
**Purpose:** AI-assisted relationship analysis and sentiment timeline engine  
**Status:** Draft v0  
**Primary Outcome:** Convert raw communication logs into a navigable timeline of emotional patterns, events, and context

---

## 1) What Clarion Is
Clarion helps users make sense of confusing or emotionally destabilizing relationship dynamics by transforming message history (Telegram/SMS/WhatsApp) into:

- Sentiment-over-time visualization  
- Annotated events (spikes, drops, tone shifts, bursts, triggers)  
- Click-to-drill message context windows  
- Exportable artifacts (timeline image, CSV annotations, HTML report)

**Value Proposition:**  
> Turn messy relationship history into a clear, navigable timeline of emotional patterns, context, and behavior.

---

## 2) Problem
Raw chat logs are overwhelming and hard to interpret. Under stress, users struggle with:
- memory distortion and rumination
- inability to clearly explain patterns to others
- difficulty connecting emotional spikes to specific message context

Traditional sentiment tools lack structure and context navigation.

---

## 3) MVP Scope (Base Feature Set)
**Clarion MVP = Import → Analyze → Timeline → Annotate → Drill Down → Export**

### Core Capabilities
- Project-based workspace (one relationship/time window per project)
- Data ingestion + normalization (Telegram/SMS/WhatsApp)
- Sentiment scoring per message + daily/weekly aggregation
- Interactive timeline visualization (zoom/pan, tooltips)
- Annotation engine (event detection + labeling)
- Context drill-down viewer (messages before/after)
- Filters + search (sender/date/sentiment/keyword)
- Exports (PNG timeline, CSV annotations, HTML report, context excerpt)

---

## 4) Primary Users
- **Self-reflective user:** wants clarity, patterns, and grounding
- **Therapist/coach (secondary):** review patterns efficiently with a client
- **Documentation user (secondary):** build evidence-supported timelines (non-legal conclusions)

---

## 5) Success Metrics
- **Time-to-insight:** import → first timeline render (< 2 min)
- **Engagement:** annotation clicks per session
- **Utility:** exports per project
- **Quality:** “useful annotation?” feedback (👍/👎)

---

## 6) Key Risks / Constraints
- Sentiment can mislead without context
- Behavioral labeling must be careful and non-diagnostic
- Privacy: local-first preferred for trust
- Format drift in exports (platform parsing complexity)

---

## 7) Next Iterations (Post-MVP)
- Manual annotation creation/editing
- AI segment summaries + “why flagged” explanations
- Multi-source ingestion (email, transcripts)
- Evidence bundling workflows (selected excerpts + attachments)
- Advanced pattern detection and trend comparisons
