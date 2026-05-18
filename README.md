# Vibe Coding Sequence

A structured 10-step framework for non-technical builders who want to ship 
web applications without skipping the parts that matter.

---

## The Problem

Most people who build with AI coding tools start the same way: open the 
platform, describe what they want, and let it run. That works — until it 
doesn't. What gets skipped in those first few minutes tends to show up 
later as security gaps, broken multi-user logic, or applications that work 
fine in testing and fail in production.

The Vibe Coding Sequence is a response to that pattern. It's a 10-step 
framework that moves a builder from idea to deployed application in the 
right order — with security requirements defined before the first line of 
code gets written, not patched in afterward.

---

## Who This Is For

Non-technical builders using AI coding platforms. You don't need to know 
how to code. You do need to be willing to slow down before you speed up.

---

## The Framework

The sequence is organized into three stages:

**Before You Build** — Steps 1–3
Establish what you're building, select the right platform, and produce a 
Product Requirements Document before any code gets generated.

**While You Build** — Steps 4–8
Guide the build incrementally, with two security checkpoints built into 
the sequence rather than treated as optional add-ons.

**Going Live** — Steps 9–10
Deploy and verify before sharing with anyone.

### The 10 Steps

1. **Requirements Interview** — Define requirements through a structured 
   conversation before opening any coding platform.
2. **Platform Recommendation** — Select the right AI coding platform for 
   your specific requirements.
3. **PRD Generator** — Produce a Product Requirements Document (PRD) with 
   security built in from the start.
4. **Foundation Prompt** — Begin construction with authentication and data 
   models before any features.
5. **Pre-Launch Audit** — First security checkpoint. Audit auth and data 
   handling before building further.
6. **Core Features Prompt** — Build core features against the PRD, with 
   the foundation verified secure.
7. **UI/UX Prompt** — Refine the interface, responsiveness, and user 
   experience.
8. **Final Security Pass** — Comprehensive OWASP Top 10 review before 
   deployment.
9. **Deployment Prompt** — Deploy to production with a structured 
   deployment prompt.
10. **Pre-Launch Checklist** — Final human review before the application 
    goes live.

See [FRAMEWORK.md](./FRAMEWORK.md) for a full description of each step, 
what it produces, and why it exists in this order.

---

## What's in This Repository

This repository contains the public intellectual scaffolding of the Vibe 
Coding Sequence:

- **FRAMEWORK.md** — Full description of each step and stage
- **PHILOSOPHY.md** — The reasoning behind the sequence approach
- **PROBLEM.md** — A detailed account of the problem this framework solves
- **sequence-map.html** — Visual map of the full 10-step structure

The implementation layer — the actual prompts, decision trees, a worked 
example, security checklists, glossary, and sequencing logic — is 
available at [vibecodesequence.com](https://bit.ly/vcs-gumroad).

---

## Why Sequence Matters

AI coding tools are good at building things. They are not good at knowing 
what order to build them in, or what you forgot to ask for. A prompt that 
describes an entire application at once produces an application that 
reflects your blind spots. A sequence that builds incrementally — with 
checkpoints — produces something you can understand, defend, and ship.

---

## License

The contents of this repository are licensed under 
[Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](https://creativecommons.org/licenses/by-nc/4.0/).

You are free to share and adapt this material for non-commercial purposes 
with attribution.

This license applies to the public scaffolding in this repository only. 
The implementation layer (prompts, sequences, guides, and all content 
within the paid product) is fully proprietary and All Rights Reserved.

---

## About

The Vibe Coding Sequence was created by Brandon Uttley.
