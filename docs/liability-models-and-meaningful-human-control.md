# Liability Models and Meaningful Human Control for Agentic AI

**Status:** Draft — part of ongoing LL.M. research. Content will be revised as the thesis develops.

## Purpose

The [DPDP Act stress test](dpdp-act-stress-test.md) in this repository shows
that Indian law can usually identify *someone* liable — Section 8(1) pins
responsibility on the Data Fiduciary regardless of whether an AI agent's
autonomy contributed to the harm. That answers "is anyone liable?" It does
not answer the harder question this document addresses: **how should
responsibility be distributed across the actors who built, deployed, and
supervised the system**, and **what standard should be used to judge
whether the human oversight in that chain was real rather than nominal?**

## Five competing models

Each model below answers "who should bear responsibility" differently.
None is adopted wholesale in this project's analysis; they are evaluated
against each other and against the scenarios in the DPDP stress test.

**1. Developer responsibility.**
The actor who designed the underlying model or agent architecture bears
responsibility, on the theory that design choices (how the agent selects
actions, what constraints it operates under) are the proximate cause of
harmful autonomous behaviour. The obvious problem: the developer typically
has no visibility into, or control over, how a specific deployer configures
and uses the system. Kolt (2025) and O'Keefe and others (2025) discuss
design-stage interventions (law-following agent design) that bear on this
model without fully resolving the control-vs-foreseeability tension.

**2. Deployer responsibility.**
The organisation that chooses to deploy the system (the hospital, in the
health-data context) bears responsibility, since it selected the tool and
put it into a live environment. This aligns with how Section 8(1) of the
DPDP Act already allocates responsibility to the Data Fiduciary. The
problem is symmetrical to Model 1: a deployer may have no meaningful way
to anticipate an agent's behaviour in a novel situation, particularly
where the agent's decision-making is not fully interpretable even to its
own developer.

**3. Data Fiduciary responsibility (the DPDP Act's default).**
A variant of Model 2 specific to data protection law: responsibility
attaches to whoever determines the purpose and means of processing. As
the stress test shows, this model works cleanly until the agent itself
starts determining *means* at runtime — at which point the model's
foundational assumption (a person fixes means in advance) no longer
holds, and the statute has no answer for who "stands in" for the agent's
autonomous choices.

**4. Human supervisor responsibility.**
Responsibility falls on the specific individual overseeing the agent's
operation. This has intuitive appeal but risks producing what this
project calls **human-in-the-loop theatre**: a human is technically
present in the workflow but lacks the time, information, or authority to
meaningfully evaluate what the agent is doing. A supervisor asked to
approve batch outputs from an agent that has already processed thousands
of records is a legal fiction of oversight, not oversight in substance.

**5. Distributed accountability (the model this project favours).**
Rather than asking "who is responsible," this model asks how
responsibility should be distributed across the AI lifecycle — design,
deployment configuration, ongoing supervision, and audit — with each
actor answerable for the parts of the outcome they could reasonably
foresee and control. Bottomley and Thaldar (2023) survey comparable
multi-actor liability structures (product liability, principal-agent,
strict liability) in a healthcare-AI context and reach a broadly similar
conclusion: no single-actor model maps well onto a multi-stage AI
pipeline. Matthias's (2004) concept of the "responsibility gap" is the
theoretical starting point for why single-actor models fail here — as
autonomous systems become less predictable to their own designers,
fault-based liability aimed at any one actor becomes harder to justify.

## Meaningful human control as the evaluative standard

Whichever model is used, Models 2–4 all depend on an assumption that
human involvement in the pipeline is *meaningful*. This project adopts
**meaningful human control (MHC)** as the standard for testing that
assumption, adapted from its origin outside AI-accountability discourse.

**Origin.** The phrase was coined by the NGO Article 36 in a 2013
briefing on UK policy toward fully autonomous weapons, arguing that
lethal decisions should never be delegated without meaningful human
control over the decision. Horowitz and Scharre's 2015 CNAS primer
further develops the concept as a set of design and process requirements
rather than a single test. The concept later migrated into general
AI-governance discourse. **This project's contribution is adapting it
specifically to health-data processing, not originating the concept.**

**Why nominal involvement isn't enough.** A human "in the loop" is not
the same as a human with meaningful control. Consider: an agent processes
50,000 patient records, flags 500 as high-risk, and generates a report; a
supervising clinician receives the report and clicks "approve all."
Human involvement, technically, is present. Meaningful control is not —
the clinician had no realistic way to evaluate 500 individual
determinations.

**Operational criteria adapted for the health-data context.** For MHC to
be more than an aspiration, it needs to be testable. This project applies
the following criteria (used directly in this repository's `/checklist`
tool):

- **Information adequacy** — does the supervising human have enough
  context, in a form they can actually process, to evaluate the agent's
  action?
- **Ability to intervene** — can a human act *before* the consequence
  occurs, not only review it afterward?
- **Ability to override** — is there a real, tested mechanism to reverse
  or halt an agent's action, or only a theoretical one?
- **Auditability** — can a human reconstruct, after the fact, why the
  agent took a specific action?
- **Foreseeability** — could a reasonably diligent supervisor have
  anticipated this category of action, or was it outside any plausible
  expectation set at deployment?

## How this feeds into the distributed model

Under Model 5, these MHC criteria become the mechanism for allocating
responsibility across the lifecycle rather than a single-actor test: a
developer is answerable for foreseeability failures baked into system
design; a deployer for information-adequacy and override-mechanism
failures in how the system was configured; a supervisor for intervention
failures within their actual authority. This lifecycle-stage mapping is
developed further as an accountability matrix elsewhere in this project's
research.

## Sources

- Article 36, *Killer Robots: UK Government Policy on Fully Autonomous
  Weapons* (2013) — origin of "meaningful human control"
- Horowitz M C and Scharre P, *Meaningful Human Control in Weapon
  Systems: A Primer* (CNAS Working Paper, 2015)
- Matthias A, "The Responsibility Gap: Ascribing Responsibility for the
  Actions of Learning Automata" (2004) *Ethics and Information Technology*
- Kolt N, "Governing AI Agents" (2025) *Notre Dame Law Review*
- O'Keefe C and others, "Law-Following AI: Designing AI Agents to Obey
  Human Laws" (2025) *Fordham Law Review*
- Bottomley D and Thaldar D, "Liability for Harm Caused by AI in
  Healthcare: An Overview of the Core Legal Concepts" (2023) *Frontiers
  in Pharmacology*
- Digital Personal Data Protection Act 2023 (India), s 8(1)

*This document is a condensed summary for a public research portfolio.
Full doctrinal argument and citation apparatus appear in the accompanying
thesis.*
