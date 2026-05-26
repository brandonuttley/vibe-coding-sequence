# Framework

This document describes the structure, purpose, and logic of the Vibe 
Coding Sequence — a 10-step framework for building web applications using 
AI coding platforms.

---

## Overview

The Vibe Coding Sequence is organized into three stages. Each stage has 
a specific job, and the stages are sequential — you complete one before 
starting the next.

**Stage 1: Before You Build** (Steps 1–3)
Define what you're building, choose your platform, and produce a written 
plan before any code gets generated. The decisions made here determine 
everything that follows.

**Stage 2: While You Build** (Steps 4–8)
Build incrementally, starting with the foundation only. Two security 
checkpoints are built into this stage — not optional, not post-build.

**Stage 3: Going Live** (Steps 9–10)
Deploy to production and complete a structured human review before the 
application is shared with anyone.

---

## Stage 1: Before You Build

### Step 1: Requirements Interview

**What it does:** Surfaces everything you need to know about your 
application before a single line of code gets written. Through a 
structured conversation with your AI coding platform, you define who 
uses the application, what they do, what data gets stored, and what 
security requirements exist — particularly for multi-user applications.

**Why it comes first:** Most applications built without this step 
are built around assumptions. Requirements discovered during Step 1 
routinely change architectural decisions that would be expensive to 
reverse later. Authentication approach, data isolation, and payment 
handling are all determined here.

**What you produce:** A written requirements summary you save and 
reference throughout the build.

---

### Step 2: Platform Recommendation

**What it does:** Takes your requirements summary and identifies which 
AI coding platform is the best fit for your specific application. 
Different platforms have different strengths — for data modeling, 
for rapid prototyping, for applications requiring fine-grained control. 
This step makes that match deliberately rather than by default.

**Why it comes second:** Platform choice affects what's easy, what's 
difficult, and what security patterns are available to you. Switching 
platforms mid-build is costly. Choosing well at the start is not.

**What you produce:** A platform selection with documented reasoning, 
so you can explain why you chose what you chose if questions arise later.

---

### Step 3: PRD Generator

**What it does:** Transforms your requirements summary into a formal 
Product Requirements Document (PRD) — a structured reference that 
specifies database schema, user roles, API behavior, security 
requirements, and implementation priorities. The PRD is written to be 
used as a direct input to your AI coding platform.

**Why it comes third:** The PRD is the contract between what you 
intend to build and what the platform actually builds. Without it, 
each prompt is a fresh negotiation. With it, every subsequent prompt 
has a shared reference point. Security requirements — including OWASP 
Top 10 considerations relevant to your application — are embedded here, 
not added later.

**What you produce:** A complete PRD document you save and provide to 
your AI coding platform at the start of every build session.

---

## Stage 2: While You Build

### Step 4: Foundation Prompt

**What it does:** Initiates the build — but only the foundation. 
Authentication, user accounts, database schema, and data models. 
Nothing else. No features, no UI beyond the basics, no payment 
integration.

**Why it comes before features:** The foundation is the hardest part 
to change later. Authentication logic and database structure that gets 
built correctly at Step 4 makes every subsequent feature easier to 
build securely. Authentication logic and database structure that gets 
built incorrectly at Step 4 creates compounding problems through 
Steps 5–8.

**What you produce:** A running application with working authentication 
and a database schema that matches your PRD. No features yet.

---

### Step 5: Pre-Launch Audit

**What it does:** The first security checkpoint. Before any features 
are built, you audit what the foundation actually produced. 
Authentication flow, session handling, data isolation between users, 
and database-level access controls are all examined against your PRD.

**Why it comes here:** Security issues in the foundation are cheap to 
fix at Step 5. They are expensive at Step 8 and potentially 
catastrophic in production. This checkpoint exists specifically to 
catch the gap between what you asked the platform to build and what 
it actually built.

**What you produce:** A pass/fail assessment of your foundation's 
security. Any failures must be resolved before proceeding to Step 6.

---

### Step 6: Core Features Prompt

**What it does:** Builds the primary functionality of your application — 
the features that make it useful. Each feature is built against the 
PRD, using the verified secure foundation from Steps 4–5.

**Why it comes after the audit:** Building features on top of an 
unaudited foundation means any security issues in the foundation are 
now embedded in every feature. The Step 5 audit is the gate.

**What you produce:** A functioning application with core features 
working as specified in the PRD.

---

### Step 7: UI/UX Prompt

**What it does:** Refines the user interface, improves responsiveness, 
addresses usability issues, and makes the application feel finished 
rather than functional-but-rough.

**Why it comes after core features:** UI work on top of incomplete 
features creates rework. This step assumes the features are working 
and turns attention to the experience of using them.

**What you produce:** An application that a real user could navigate 
without a guide.

---

### Step 8: Final Security Pass

**What it does:** A comprehensive security review before deployment. 
Covers the OWASP Top 10, multi-tenant data isolation verification, 
input validation, error handling, environment variable exposure, 
dependency vulnerabilities, and deployment configuration. Any issues 
found here must be resolved before Step 9.

**Why it comes before deployment:** This is the last opportunity to 
find problems before real users encounter them. The review is 
structured — not a gut check — because informal security reviews 
reliably miss things that structured ones catch.

**What you produce:** A documented audit result. Issues found and 
resolved. A clear record that the application was reviewed before 
going live.

---

## Stage 3: Going Live

### Step 9: Deployment Prompt

**What it does:** Guides the deployment of your application to a 
production hosting environment — configuring environment variables, 
connecting your domain, enabling HTTPS, and verifying the deployment 
completed correctly.

**Why it's a step:** Deployment is where security misconfigurations 
are most commonly introduced. Environment variables that should be 
secret end up exposed. HTTPS gets skipped. Default settings that are 
fine in development are wrong in production. A structured deployment 
prompt addresses these specifically.

**What you produce:** A live application accessible at a real URL, 
with production configuration verified.

---

### Step 10: Pre-Launch Checklist

**What it does:** A final human-driven review before the application 
is shared with anyone. Not automated. Not delegated to the platform. 
You, working through a checklist, verifying that what got built 
matches what you intended — and that you're prepared for what comes 
after launch.

**Why it comes last:** Every step before this one involved the AI 
coding platform doing work. This step is yours. You are the one who 
knows what this application is supposed to do. This checklist is the 
last moment to catch anything the platform got right technically but 
wrong for your actual requirements.

**What you produce:** A signed-off checklist and a launched 
application.

---

## The Security Checkpoints

Two steps in the sequence are explicitly security checkpoints: 
Step 5 (Pre-Launch Audit) and Step 8 (Final Security Pass).

Both checkpoints reference the OWASP Top 10 — a widely used framework 
for identifying the most critical security risks in web applications. 
The checkpoints are positioned where they are by design: Step 5 
catches foundation issues before features are built on top of them, 
and Step 8 catches everything else before real users are exposed to it.

Skipping either checkpoint is a documented choice with known 
consequences, not an oversight.

---

## What This Repository Does Not Include

The prompts used at each step, the decision trees, a worked example, 
security checklists, glossary, and troubleshooting guides are part of 
the implementation layer, available 
[here](https://171276522580.gumroad.com/l/vibe-coding-sequence).

This document describes the structure. The product provides the means 
to execute it.

---

*Vibe Coding Sequence was created by Brandon Uttley.*  
*Public scaffolding licensed under CC BY-NC 4.0. Implementation layer All Rights Reserved.*
