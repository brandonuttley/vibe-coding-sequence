# The Problem

## Who This Is For

The Vibe Coding Sequence was built for a specific person: someone who 
is not a software developer, has access to an AI coding platform, and 
wants to build a real web application.

Not a prototype. Not a demo. Something with actual users, actual data, 
and actual consequences if it fails or gets compromised.

This person exists in large and growing numbers. AI coding tools have 
made it genuinely possible for non-technical builders to produce 
functional applications without writing code. That's a real shift. 
What hasn't shifted is the underlying complexity of building something 
secure and reliable — it's just less visible now.

---

## What Goes Wrong Without a Sequence

The pattern is consistent. A non-technical builder opens a coding 
platform, describes what they want, and iterates until something 
functional appears. The application works. It does what they asked for.

Then one of a few things happens.

**The data isolation problem.** The application has multiple users. 
Each user's data was never explicitly defined as belonging to that user 
at the database level. With the right URL or API manipulation, one user 
can access another's records. The builder never tested for this because 
they didn't know it was a risk category. Fixing it after the fact means 
reworking the database schema, the API layer, and every feature that 
touches user data.

**The authentication afterthought.** Login was added late in the build, 
after features were already working. The session handling is fragile. 
Password reset doesn't properly verify email ownership. There's no 
email verification at all. The builder assumed the platform handled 
these correctly. It handled them the way it was asked to — which wasn't 
carefully enough.

**The deployment misconfiguration.** The application goes live with 
development settings still active. API keys that should be environment 
variables are visible in client-side code. Error messages return stack 
traces to the browser. HTTPS wasn't verified. None of this was caught 
because there was no structured review before launch.

**The requirements that surface too late.** Three features into the 
build, the builder realizes the application needs to support multiple 
organizations, each with their own users and data. The foundation 
wasn't designed for this. Starting over is the only real option.

These aren't rare outcomes. They're the predictable result of building 
without a sequence — of letting the platform determine the order rather 
than bringing one to it.

---

## Why the Platform Can't Solve This

AI coding platforms are capable of producing secure, well-structured 
code. They are not capable of knowing what you forgot to specify.

A platform asked to build a client management tool will build one. It 
won't ask whether clients should be isolated by user, whether the 
application will eventually need multi-organization support, or whether 
the payment integration needs to meet specific compliance requirements. 
It answers the question it was asked.

The sequence exists to make sure the right questions get asked, in the 
right order, before the platform starts building.

---

## The Cost of Getting This Wrong

For a personal project, a security failure is embarrassing. For an 
application handling client data, it's a breach. For an application 
processing payments, it's a liability. The stakes scale with the 
application.

The Vibe Coding Sequence is built around the premise that the cost of 
doing this correctly upfront is always lower than the cost of fixing it 
after. Requirements gathered before the first prompt take an hour. 
Requirements discovered after three features are built cost days. A 
security audit before deployment takes an afternoon. A security audit 
after a breach is someone else's job, and it's not a good day.

---

## What a Sequence Provides

A defined sequence doesn't make building slower. It makes the time 
spent building more useful.

Requirements gathered upfront mean the Product Requirements Document 
(PRD) reflects what you actually need — not what you remembered to ask 
for in the moment. A PRD means the coding platform has a precise target 
instead of an approximation. Security checkpoints built into the process 
mean problems get found when they're still cheap to fix. A structured 
launch process means the application that goes live is the one you 
intended to build.

The sequence doesn't add steps so much as it moves them. Work that 
would have happened reactively — debugging, reworking, patching — 
happens proactively instead, at the stage where it costs the least.

---

## Where to Go From Here

Read [FRAMEWORK.md](./FRAMEWORK.md) for a full description of each 
step and what it produces.

The implementation layer — the prompts, decision trees, a worked 
example, and sequencing logic that make the framework executable — is 
available at [vibecodesequence.com](https://bit.ly/vcs-gumroad).

---

*Vibe Coding Sequence was created by Brandon Uttley.*  
*Public scaffolding licensed under CC BY-NC 4.0. Implementation layer All Rights Reserved.*
