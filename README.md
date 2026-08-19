# Regional-Language Phishing Detection

Team Shastra Synergy | OmniKon Hackathon | Theme: Cybersecurity, Blockchain & Digital Trust

> Project Status: Idea / Proposal Stage
> This repository currently contains the concept submission (Phase 1) for OmniKon. No code has been implemented yet. Everything below describes the *proposed* solution, architecture, and implementation plan. Development will begin if the project is shortlisted for the build phase.

## Team

| Name          | Role        |
| ------------- | ----------- |
| Navnit Yadav  | Team Leader |
| Devesh Rajput | Member      |

## Problem Statement

Omni_CyberTech_1: Regional-language phishing & scam-message detection for Hindi, Hinglish, and code-mixed Indian users.

Scam and phishing messages targeting Indian users can appear in Hindi, Hinglish, and other regional-language or code-mixed formats. Many mainstream phishing and spam-detection experiences are optimized primarily for English-language content.

Examples include fake KYC updates, UPI refund alerts, account-disconnection warnings, and fraudulent job offers. Such messages can be difficult to evaluate for users who are less comfortable with English, including elderly and first-time digital users.

This creates a need for a detection experience designed around regional-language understanding from the beginning.

## Proposed Solution

A lightweight web application where a user can paste or forward a suspicious SMS/WhatsApp message and receive an instant verdict:

Safe / Suspicious / High Risk

The system is designed to provide a plain-language explanation in the user's language.

Key principles:

* Regional-language understanding for Hindi, Hinglish, and code-mixed text is a core design requirement.
* Message content is analyzed alongside suspicious URL/domain signals.
* A community-reporting layer can help identify emerging scam patterns.

### What Makes It Different

Instead of treating regional-language support as an optional translation layer, the proposed architecture makes it a core part of the detection pipeline, combined with contextual message analysis, deterministic URL/domain checks, and community feedback.

## Key Features

### Core MVP

* Paste-and-check verdict — Safe / Suspicious / High Risk with a plain-language reason
* Hindi & Hinglish support — including code-mixed text
* Lookalike-domain detection — identifies suspicious URLs using brand-name and domain similarity
* Community reporting — users can flag new scam-message patterns for a growing pattern database

### Stretch Goals

* Text-to-speech readout of the verdict
* Android share-sheet integration for forwarding messages directly from WhatsApp/SMS

## Proposed System Architecture

```text
User's Phone
(Suspicious SMS / WhatsApp Message)
        │
        ▼
Web App — Paste & Check
        │
        ▼
API Gateway
        │
        ▼
Language Detection & Preprocessing
        │
        ├──► LLM Classification Engine
        │    (Hindi / Hinglish / English)
        │
        └──► URL & Domain Similarity Checker
        │
        ▼
Verdict Aggregator
        │
        ▼
Safe / Suspicious / High Risk
        +
Plain-Language Explanation
```

The proposed design uses two complementary signals: an LLM-based classifier for message context and a deterministic URL/domain checker for suspicious links. A verdict aggregator combines these signals into the final risk assessment.

## Proposed Technology Stack

| Layer              | Planned Technology                                                                                     |
| ------------------ | ------------------------------------------------------------------------------------------------------ |
| Frontend           | React / Next.js — mobile-first responsive interface                                                    |
| Backend            | FastAPI (Python) or Node.js / Express                                                                  |
| Classification     | LLM API with few-shot prompting; future path: lightweight multilingual model such as IndicBERT / MuRIL |
| URL / Domain Check | Regex + string-similarity matching                                                                     |
| Database           | PostgreSQL or Firebase                                                                                 |
| Deployment         | Vercel or Render                                                                                       |

## Implementation Timeline

### Phase 1 — Concept & Planning

Now → 20 Aug

* Finalize problem scope
* Design wireframe/UI
* Lock architecture
* Finalize technology choices

### Phase 2 — Build Week

**21–27 Aug, if shortlisted**

* 21–22 Aug: Project setup, API skeleton, initial classification prompt
* 23–24 Aug: Frontend flow + URL/domain checker
* 25 Aug: Community reporting + database integration
* 26 Aug: Testing with Hindi, Hinglish, English and code-mixed examples
* 27 Aug: Polish, deployment and final presentation

### Future Scope

* Lightweight fine-tuned multilingual classifier
* Android share-sheet integration
* Text-to-speech support
* Potential partnerships for verified scam-pattern feeds

## Feasibility & Risks

The proposed solution uses established technologies suitable for a hackathon-scale prototype. Its modular architecture allows the frontend, classification engine, URL checker, and reporting layer to be developed and tested independently.

### Key Risks & Mitigation

* LLM cost/latency at scale** → Move toward a lightweight multilingual classifier
* Ambiguous code-mixed text** → Combine contextual classification with deterministic URL/domain signals
* Community report abuse** → Use moderation/corroboration before reports influence the system
* Rapidly changing scam patterns** → Use community reporting as a feedback mechanism

## Impact

### Social

Helps improve digital-safety awareness for users who are less comfortable with English.

### Economic

Aims to help users identify common digital-payment and KYC-related scam patterns before interacting with them.

### Scalability

A community-reporting mechanism can help identify new scam patterns over time.

### Ecosystem

The proposed platform could eventually support collaboration with banks, telecom providers, and other organizations for verified scam-pattern information.

## Research & References

* National Cyber Crime Reporting Portal — Government of India**
  https://cybercrime.gov.in/

* CERT-In — Indian Computer Emergency Response Team**
  https://www.cert-in.org.in/

* AI4Bharat — IndicBERT / Indian-language NLP research**
  https://indicnlp.ai4bharat.org/pages/indic-bert/

* Google Research — MuRIL / Multilingual Representation for Indian Languages**
  https://arxiv.org/abs/2103.10730

* Reserve Bank of India — Official Website & Financial Awareness Resources**
  https://www.rbi.org.in/

## Current Status

**Idea / Proposal Stage**

This repository documents the proposed problem, solution, architecture, technology choices, implementation plan, and research references.

**No working code has been implemented yet.**

If shortlisted, implementation, setup instructions, testing results, and a live demonstration link will be added during the Build Week.

---

## Team

Team: Shastra Synergy
Team Leader:Navnit Yadav
Member:Devesh Rajput

Hackathon:OmniKon
