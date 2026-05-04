# Architecture Breakdown

This system is designed as a multi-layer outbound intelligence pipeline.

---

## Core Principle

Outbound should not start with messaging.

It should start with understanding.

---

## Pipeline Design

### 1. Discovery Layer
Uses Google Places API to identify businesses based on:
- keyword
- location
- radius

Includes pagination handling to maximize coverage.

---

### 2. Enrichment Layer

Each business is enriched through multiple sources:

- Website + phone (Google Places)
- Emails (Hunter API)
- Social profiles (Google Custom Search)

This avoids dependency on a single data provider.

---

### 3. Social Intelligence Layer

Profiles are scraped using Apify:

- Instagram → engagement + followers
- Facebook → reviews + activity
- LinkedIn → company data
- X → audience + presence

---

### 4. Analysis Layer (AI)

A structured audit is generated:

- Executive summary
- Opportunity score
- Key gaps
- Quick wins
- Conversion opportunities

This transforms raw data into actionable insight.

---

### 5. Personalization Layer

Emails are generated using:
- real business data
- identified gaps
- behavioral framing

No generic templates.

Each message is context-driven.

---

### 6. Storage Layer

All data is stored in Airtable:
- lead profile
- scoring
- audit
- email draft

---

## Design Decisions

- Multi-source enrichment over single API
- AI used only after data collection (not before)
- Structured JSON outputs for consistency
- Airtable as control + execution layer

---

## Why this matters

Most outbound systems automate actions.

This system automates **understanding before action**.

That is the difference between spam and signal.
