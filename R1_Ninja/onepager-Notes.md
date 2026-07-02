# Meeting Notes — InterviewIQ: AI Interview Agent
**Presented to:** Executive Director  
**Presented by:** [Your Name], [Your Team]  
**Date:** [Date]  
**Duration:** 30 minutes  
**Format:** Briefing + Q&A  

---

## Objective of this meeting

To present the concept, scope, and phased plan for **InterviewIQ** — an AI-powered interview agent that conducts, proctors, scores, and decides on candidates entirely within Microsoft Teams — and to seek approval to proceed with the Discovery & Scoping phase.

---

## The problem we are solving

Current interview processes across the organisation face three structural issues:

**1. Speed.** A typical hire takes 3–5 weeks, with the majority of delay sitting in scheduling coordination across the test, R1, and R2 rounds. Recruiters spend significant time on logistics before any evaluation begins.

**2. Consistency.** Different interviewers ask different questions and apply subjective scoring. There is no standardised rubric applied across candidates for the same role, making cohort comparison unreliable.

**3. Integrity.** Candidates are increasingly using AI tools (ChatGPT, GitHub Copilot), coaching calls, and tab-switching during remote interviews. No existing tool catches this within a Microsoft Teams environment.

---

## What we are proposing

An AI agent — **InterviewIQ** — that:

- Joins a Microsoft Teams call as a bot participant
- Reads the job description and candidate résumé, and generates a tailored question bank automatically
- Conducts a **combined Test + R1 + R2 interview** via voice — no human interviewer required in the room
- **Monitors the candidate's screen, webcam, and audio** for integrity signals in real time
- Delivers a structured **hire / reject verdict with a full scorecard** within minutes of the session ending

The recruiter's role shifts from conducting to reviewing — they configure the interview, monitor optionally via a sidebar, and receive the report.

---

## Key features — summary

| Area | What it does |
|---|---|
| Question engine | Adapts questions based on JD, profile, and previous answers |
| Teams bot | Joins call, speaks via TTS, listens and transcribes via STT |
| Screen analysis | OCR detects open tabs, blocked apps, URLs in real time |
| Eye tracking | Flags sustained off-screen gaze via webcam and MediaPipe |
| Audio monitoring | Detects background coaching voices and audio anomalies |
| Scoring engine | STAR rubric, technical accuracy, communication signals |
| Verdict output | Hire / Strong hire / Marginal / Reject with full report |
| ATS integration | One-click push to Greenhouse, Lever, or Workday |

---

## What is in scope for Discovery & Scoping (Phase 0)

During the first two weeks, the team will:

1. Map current recruiter and interviewer workflows to identify integration points
2. Review data privacy, GDPR/DPDP compliance requirements for AI-conducted interviews
3. Define success metrics — time-to-hire reduction, scoring consistency, flag accuracy
4. Confirm Microsoft Teams API access and Azure environment readiness
5. Scope the ATS integration requirements with the HR tech team
6. Identify one pilot role and business unit for the Phase 1 proof of concept
7. Draft the candidate consent and disclosure framework

**Output of Discovery & Scoping:** A signed-off technical specification and project plan ready for Phase 1 build.

---

## Proposed phased plan

| Phase | Scope | Timeline |
|---|---|---|
| **0 — Discovery & scoping** | Requirements, compliance, workflow mapping | Weeks 1–2 |
| **1 — Proof of concept** | Teams bot + adaptive question engine, basic scorecard | Weeks 3–6 |
| **2 — Proctoring** | Screen, eye, audio monitoring + warning engine | Weeks 7–10 |
| **3 — Verdict engine** | Composite scoring, report, ATS export | Weeks 11–14 |
| **4 — Controlled rollout** | One BU pilot, parallel human validation | Weeks 15–20 |

Full production rollout is targeted at **week 20**, following a 4-week parallel validation period where AI verdicts are compared against human interviewer decisions to calibrate scoring.

---

## Technology choices

The entire stack runs within the **Azure and Microsoft ecosystem**, making it compatible with existing Wissen infrastructure and client environments:

- **AI core:** GPT-4o via Azure OpenAI, LangChain orchestration
- **Speech:** Azure Cognitive Speech (TTS + STT), Whisper
- **Vision / proctoring:** MediaPipe FaceMesh, Azure Computer Vision, Azure Form Recognizer
- **Teams integration:** Microsoft Bot Framework, Azure Graph API
- **Infrastructure:** Azure Kubernetes Service, Azure Service Bus, Cosmos DB
- **Reporting:** Next.js dashboard, Power BI Embedded, ATS API connectors

---

## Risks and mitigations

| Risk | Mitigation |
|---|---|
| Candidate consent and legal exposure | Explicit consent flow before session; GDPR/DPDP legal review in Phase 0 |
| Bias in AI-generated questions | Bias auditor module checks all questions before session; legal guardrails hard-coded |
| Scoring accuracy vs. human judgment | Phase 4 runs AI and human interviews in parallel; weights calibrated against historical hire data |
| Microsoft Teams API limitations | Teams Calling API access confirmed before Phase 1 build begins |
| Candidate perception of fairness | 3-strike verbal warning system (not silent flagging); post-interview candidate feedback survey |

---

## What we are asking for today

1. **Approval to proceed** with the Discovery & Scoping phase (Weeks 1–2)
2. **Nomination** of one pilot role and business unit for the Phase 1 proof of concept
3. **Introduction** to the HR tech and compliance teams to begin ATS and GDPR scoping

---

## Questions anticipated from the ED — suggested responses

**"How is this different from existing video interview tools like HireVue?"**  
HireVue records async video and scores post-session. InterviewIQ is live, conversational, fully integrated into Teams, and conducts the actual interview — it is not a recording tool. The adaptive question engine and real-time proctoring are differentiated capabilities.

**"What happens if the AI makes a wrong hire/reject decision?"**  
The verdict is assistive, not authoritative. The recruiter always sees the full rationale and can override. The integrity gate routes any flagged session to mandatory human review. All output is labelled as AI-generated and requires a Wissen reviewer sign-off before it influences an offer decision.

**"Is this compliant with Indian and EU data protection law?"**  
Compliance review is the first task in Discovery & Scoping. Candidate consent, data retention limits, and right-to-explanation requirements will be addressed before any pilot goes live. The system is designed with data minimisation as a principle — only what the session requires is retained.

**"How long before we see ROI?"**  
If time-to-hire reduces from 5 weeks to 2 weeks for roles going through the system, and recruiter hours per hire drop from ~8 hours to ~1 hour, the system pays for itself within the first quarter of full deployment. Formal ROI modelling will be produced as part of Phase 0.

---

## Next steps post-meeting

| Action | Owner | By when |
|---|---|---|
| Confirm ED approval to proceed with Discovery phase | ED / [Your Name] | End of meeting |
| Identify pilot role and BU sponsor | ED + HR Lead | Within 3 days |
| Schedule kick-off with HR tech and compliance | [Your Name] | Within 5 days |
| Share technical one-pager with Azure team | [Your Name] | Within 3 days |
| Draft candidate consent framework | Legal / Compliance | Week 1 |

---

*Document prepared by [Your Name] · Wissen Internal · Confidential*  
*Do not distribute without approval*
