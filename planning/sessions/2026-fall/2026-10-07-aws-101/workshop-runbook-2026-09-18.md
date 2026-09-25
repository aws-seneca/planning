# Event 2 — AWS 101 Workshop
## AWS Student Builder Groups @ Seneca Polytechnic

---

**Format:** In-person, hands-on workshop
**Duration:** 90 minutes
**Goal:** Every attendee leaves with something real deployed on AWS. Teams compete to extend a base project with add-ons. Architecture reasoning throughout ties directly into the System Design event.
**Tone:** Collaborative, fast-paced, no unnecessary theory. Teach by doing.

---

## Before the Event

### Room setup
- Arrive 30 minutes early
- Projector connected, AWS Console open and logged in on presenter laptop
- Pre-built HTML project file ready to share (Google Drive link, GitHub link, or QR code) — attendees download this, not build it from scratch
- EC2 instance pre-warmed and tested on presenter account so you know exactly what clicks are coming
- RDS Postgres instance pre-created on presenter account for the demo — just show setup, not a live creation from scratch
- Extra exec members positioned to float and help during the hands-on sections
- Food out before people arrive

### Pre-event requirement (communicated in advance)
- Every attendee must set up an AWS Free Tier account before arriving
- Send reminder in Discord 48 hours out and day-of
- Have a fallback plan: one or two exec members available to pair with anyone who hasn't done it — do not let account setup eat into event time

### Pre-event checklist
- [ ] Presenter laptop: AWS Console logged in, EC2 instance running, RDS instance created
- [ ] Project files shared via link/QR (HTML site with basic user account form — no backend wiring)
- [ ] Discord reminder sent 48 hours out with account setup instructions
- [ ] Exec team briefed on floating roles during hands-on sections
- [ ] Add-on challenge sheet ready (physical printout or shared doc)
- [ ] Prize/merch details confirmed for winners

---

## Event Flow Overview

| Phase | Time | What's happening |
|---|---|---|
| Intro + framing | 0–5 min | Quick recap of Kickoff, what today actually is |
| Five categories overview | 5–20 min | Compute, Storage, IAM, Databases, Serverless — why each exists |
| Architecture decisions | 20–30 min | Why EC2 over Lambda? Why RDS? Translate to System Design thinking |
| Guided build — EC2 | 30–55 min | Deploy the HTML project to EC2, step by step together |
| RDS setup demo | 55–65 min | Spin up a Postgres instance, explain what it does and why |
| Challenge — teams build | 65–80 min | Teams work on add-ons, exec floats and helps |
| Close + prize + what's next | 80–90 min | Award winners, preview Event 3, Discord and next date |

---

## Phase 1 — Intro + Framing (0–5 min)

- Don't re-teach the Kickoff. Reference it in one line: *"Last time you watched it happen. Today you're the one doing it."*
- Frame the session: we're going to cover the services that show up in almost every real architecture, then actually deploy something using them
- Today is not a lecture — hands go on keyboards, not just on chins

---

## Phase 2 — Five Categories Overview (5–20 min)

Walk through each category at a conceptual level. The goal is not comprehension — it's the map. They'll fill it in during the build.

**Compute — EC2**
- What it is: a virtual server you rent and control
- Why it exists: you need a machine that runs your code 24/7 without you managing physical hardware
- Why you'd choose it: you need full control of the environment — OS, dependencies, ports. If you need to install specific software or run a long-running process, EC2 is your answer
- Why you wouldn't: if you're just running a function on demand, Lambda is cheaper and simpler. EC2 makes sense when you're running a server, not a function

**Storage — S3**
- What it is: file storage accessible from anywhere on the internet
- Why it exists: you need somewhere to put files that isn't tied to one server
- Quick connection back to Kickoff: *"This is what we deployed the HTML file to last time. Today we're using EC2 instead — different tool, different reason."*

**Identity & Access — IAM**
- What it is: the permissions layer for everything in AWS
- Why it matters: without IAM, any service can talk to any other service. IAM is what controls who can do what
- The mental model: IAM is the bouncer. Every request in AWS goes through IAM first
- This comes up again the moment anyone tries to connect EC2 to RDS — that's an IAM decision

**Databases — RDS**
- What it is: a managed relational database — Postgres, MySQL, etc. — without you managing the server it runs on
- Why managed: database administration is a full-time job. RDS handles backups, patching, failover. You just connect to it
- Why Postgres specifically: industry standard, open source, used everywhere

**Serverless — Lambda (brief)**
- What it is: run code without managing a server at all. You upload a function, AWS runs it when triggered
- Why it exists: not everything needs a server running 24/7. If you only need code to run when someone hits an endpoint, Lambda is cheaper
- Don't go deep here — this is a preview for later in the curriculum

---

## Phase 3 — Architecture Decisions (20–30 min)

This section is what makes your workshop different from a tutorial. Don't just describe the services — explain the reasoning behind choosing them.

**The core question to frame this section:** *"Given a problem, how do you pick the right AWS service?"*

Walk through a real scenario:

> *"You're building a web app where users can create accounts and log in. What do you actually need?"*

Draw it out on screen or whiteboard:
- A server to handle requests → **EC2**
- Somewhere to store user data → **RDS (Postgres)**
- A way to control what has access to what → **IAM roles**
- Somewhere to store static files or images → **S3**

*"Notice we didn't pick Lambda. Why? Because this is a server that needs to be running and listening for requests all the time. Lambda is great for on-demand functions — not for a persistent web server. That's the decision."*

**Why this matters beyond today:**
*"In our next event — System Design × AWS — we're going to take this further. You'll see how these same services appear in the architectures of companies like Netflix and Airbnb, and why they're structured the way they are. Today is the foundation for that."*

---

## Phase 4 — Guided Build: EC2 Deploy (30–55 min)

Everyone follows along on their own AWS account. Exec team floats and helps anyone stuck.

**What you're deploying:** A simple HTML site with a user account creation form — frontend only, no backend wiring yet. That's part of the challenge.

**Step by step:**

**1. Launch an EC2 instance**
- Open EC2 console → Launch instance
- Name it something memorable: `aws-sbg-workshop`
- Choose Amazon Linux 2023 (free tier eligible)
- Instance type: t2.micro (free tier)
- Create a new key pair — explain what this is and why it exists (SSH access = secure login to your server)
- Security group: allow HTTP (port 80) and SSH (port 22) — explain what a security group is and why you're opening these specific ports

**2. Connect to the instance**
- Use EC2 Instance Connect (browser-based SSH — no local setup needed, lowers friction significantly)
- Say out loud: *"We just logged into a server running in a datacenter in Montreal. That's what cloud computing is."*

**3. Install a web server and deploy the file**
```bash
sudo dnf update -y
sudo dnf install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
```
- Upload the HTML file (use `nano` or `wget` from your shared link)
- Move it to the web server directory: `sudo mv index.html /var/www/html/`
- Open the public IP in a browser

**The moment:** *"That URL is live. Anyone in the world can open it right now."*

**Speaker note:** Narrate every command as you type it. Don't just run it and move on. *"We're installing Apache — that's the web server software that listens for HTTP requests and serves files. The `systemctl enable` makes sure it starts automatically if the server restarts."*

---

## Phase 5 — RDS Setup Demo (55–65 min)

You demo this, they watch. The goal is to show it exists and understand what it does — wiring is a challenge add-on.

**Steps:**
- Open RDS console → Create database
- Choose PostgreSQL, free tier template
- Set a DB identifier, username, password (say these out loud: *"In real production you'd store these in AWS Secrets Manager, not type them in a form. We'll cover that another time."*)
- VPC and security group settings — briefly explain: *"This controls which services can talk to this database. Right now it's locked down — nothing can reach it yet. To wire it to your EC2 instance, it needs to allow traffic from your EC2 security group. That's one of the add-ons."*
- Create database (takes 3-5 minutes to spin up — use this time for Q&A)

---

## Phase 6 — Challenge: Teams Build (65–80 min)

Form teams of 2-3. The base project is already deployed from Phase 4.

**Add-ons — complete as many as you can before time is called:**

| # | Add-on | Description |
|---|--------|-------------|
| 1 | Wire the database | Connect your EC2 instance to the RDS Postgres instance so form submissions actually save to the DB |
| 2 | Nice design | Make the frontend look actually good — CSS, layout, branding |
| 3 | Add a second page or route | Add an `/about` page, a confirmation page after form submit, or any meaningful second route |
| 4 | Custom domain or URL | Point a domain at your EC2 public IP using Route 53 or a free DNS service |

**Scoring:** First team to complete all 4 wins. If no team completes all 4, the team with the most add-ons wins. Tiebreaker: exec team judges quality.

**Prize:** Merch — coming soon. Winners will be recognized publicly in Discord and on socials.

**Exec roles during challenge:**
- Float and help stuck teams — don't just watch
- If someone's completely lost, pair them with a stronger team rather than leaving them idle
- Keep an eye on time — give a 5-minute warning before calling it

---

## Phase 7 — Close + What's Next (80–90 min)

- Call time on the challenge
- Announce winners, recognize effort publicly
- Post the winning team's work in Discord after the event
- Preview Event 3: *"Next time we're going into System Design × AWS. You now have enough context to understand why real companies make the infrastructure decisions they do. Bring your laptop again."*
- Remind them: Event 3 date, it's in the Discord
- *"Before you leave — if you haven't already added the next event to your calendar, do it now."*

---

## Post-Event Actions (within 24 hours)

**Discord:**
- Post a recap: how many people deployed, who won the challenge
- Drop the winning team's deployed URL if they're happy to share
- Post the Event 3 date and what to expect

**Social:**
- Photo or clip from the room during the hands-on section — real people on laptops, not posed
- One post: "X people deployed to AWS tonight. Event 3 is coming."

**Exec debrief:**
- What got stuck most often during the guided build? Fix the instructions for next time
- Did the RDS setup timing work or was it too rushed?
- Challenge add-on difficulty — was it too hard, too easy, right amount?

---

## Notes

- The wiring add-on (connecting EC2 to RDS) is intentionally hard for this level — most teams won't complete it. That's fine. It's there to give the strongest attendees a real challenge and to show everyone what's possible.
- The architecture decisions section bridges directly to Event 3 (System Design × AWS). Plant that seed explicitly — *"you'll see these same decisions at Netflix scale next time."*
- IAM will frustrate people during the challenge, specifically around connecting EC2 to RDS. That's a feature, not a bug — IAM confusion is one of the most useful real-world experiences you can give them in a controlled setting.

---

*Document version: Event 2 AWS 101 Workshop — AWS Student Builder Groups at Seneca Polytechnic*
*Part of the AWS × Seneca master plan. Event 3 runbook to follow.*
