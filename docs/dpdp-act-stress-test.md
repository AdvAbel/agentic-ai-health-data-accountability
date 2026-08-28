# Stress-Testing the DPDP Act Against an Agentic AI Scenario

**Status:** Draft — part of ongoing LL.M. research. Content will be revised as the thesis develops.

## Purpose

Most commentary on AI and India's Digital Personal Data Protection Act 2023
("DPDP Act") asks, in the abstract, whether the law "contemplates" AI. This
document takes a narrower and more testable approach: it runs one concrete
scenario through the actual text of the Act and the DPDP Rules 2025,
clause by clause, to see exactly where the statutory framework holds and
where it breaks down.

## The scenario

A hospital deploys an agentic AI system with the objective "identify
high-risk patients and initiate appropriate follow-up." The agent
autonomously retrieves records across departments, infers that a patient
has a mental health condition, and — without a human approving that
specific action — sends a summary to an external specialist clinic the
patient never named. The patient later objects.

## Running it through the statute

**1. Attribution is not actually the hospital's escape route.**
Section 8(1) makes the Data Fiduciary responsible for compliance
"irrespective of any agreement to the contrary" for processing undertaken
by it or on its behalf. The hospital cannot point to the AI vendor or the
agent's autonomy to avoid responsibility. This is a genuine strength of
the Act, not a gap.

**2. The real gap: the Act has no vocabulary for a non-human determinant
of "means."**
Section 2(i) defines a Data Fiduciary as any person who "determines the
purpose and means of processing." That definition assumes a human or
legal person fixes the means in advance. When the agent itself decides,
at runtime, which external clinic to contact and what data to send,
something is determining "means" that is not a "person" under the Act at
all. The statute has no third category between Data Fiduciary and Data
Processor for this.

**3. The developer may fall outside the Act entirely.**
A Data Processor only exists under a valid contract, processing personal
data on the Fiduciary's behalf (Section 8(2)). If the AI vendor merely
licenses software that runs on the hospital's own infrastructure and
never itself handles the data, the vendor is neither Fiduciary nor
Processor — there is no route under the DPDP Act to reach the developer
whose design choices produced the harmful action.

**4. The disclosure may lack a lawful basis independent of any breach.**
Section 7's "certain legitimate uses" list is closed and narrow. It
covers medical emergencies involving a threat to life or immediate health
threat (7(f)), and measures during an epidemic or public-health threat
(7(g)) — not routine referral coordination. Unlike the GDPR, there is no
open-ended legitimate-interests balancing test. A routine agentic
referral to an unnamed external clinic likely needs consent under Section
6, tied to a specified purpose under Section 5. If the original consent
named only the hospital's own treatment services, the disclosure may be
unlawful processing — a distinct failure from a reportable "breach" under
Rules 6–7, and one that may never surface as an incident at all, since
each individual step can look locally authorised even where the overall
action was not.

**5. No heightened protection for the sensitivity of the inference.**
The DPDP Act applies one uniform standard to all personal data. It does
not distinguish "special category" data the way the GDPR does under
Article 9. A mental-health inference receives no procedural uplift under
the DPDP Act merely because of its sensitivity.

## What this scenario shows

The interesting finding is not "Indian law cannot attribute responsibility
for AI harm" — Section 8(1) already answers that at the level of the
hospital. The interesting findings are narrower and more precise:
upstream developers may be unreachable, the lawful basis for a
dynamically-selected action may fail silently, and health data gets no
special statutory weight regardless of how sensitive the specific
inference is.

## Sources

- Digital Personal Data Protection Act 2023 (India), ss 2(i), 5, 6, 7, 8
- Digital Personal Data Protection Rules 2025 (India), rr 6, 7
- Regulation (EU) 2016/679 (General Data Protection Regulation), art 9

*This document is a condensed summary for a public research portfolio.
Full doctrinal argument and citation apparatus appear in the accompanying
thesis.*
