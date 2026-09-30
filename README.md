# TJZA Agents

### Codex was built for agents. TJZA helps them work like a team.

**TJZA Agents** is a ready-to-use multi-agent orchestration system for OpenAI Codex.

Instead of treating every development task as one long job for one agent, TJZA gives Codex a structured team of specialised agents for exploration, implementation, validation, engineering review, deeper reasoning, risk review and intent protection.

You choose the orchestration profile.

**TJZA handles how the team works.**

> Previously released as **Xrotel Agents**. v7.0.0 introduces the TJZA name and a major orchestration update built around GPT-6.1 Sol.

---

## 🚀 Latest release: v7.0.0

TJZA Agents v7.0.0 uses the current orchestration stack:

- **GPT-6 Luna** — high-volume exploration, implementation and validation
- **GPT-6.1 Sol** — engineering judgement, architecture, difficult problem solving and risk review
- **GPT-6 Astra** — intent protection and exceptional high-level product or architecture decisions

### Core philosophy

**Luna builds. Sol 6.1 engineers. Astra protects intent.**

👉 **[Download TJZA Agents v7.0.0](https://github.com/hader-campbell/TJZA-Agents/releases/latest)**

---

## 🔒 TJZA does not modify Codex

TJZA does **not** inject into, patch, replace or modify the Codex application.

It does not:

- patch the Codex client;
- inject code into Codex;
- intercept OpenAI traffic;
- proxy your OpenAI requests;
- modify your ChatGPT or Codex subscription;
- bypass usage controls;
- spoof another client;
- share or require your OpenAI credentials; or
- install a background service between you and OpenAI.

TJZA is a configuration and instruction package designed to work with Codex's existing project-instruction and agent functionality.

**Your Codex installation remains Codex.**

### Works with Codex — not around it.

TJZA is an independent third-party project and is not affiliated with, sponsored by or endorsed by OpenAI.

---

# 🤖 Meet the team

The important part is not simply having more agents.

**It is knowing when to use them.**

TJZA separates different kinds of development work across specialised roles.

### 🔎 Repository Explorer

Investigates unfamiliar projects, identifies relevant files and gathers focused context before unnecessary implementation begins.

### 🛠 Implementation Worker

Handles focused implementation once the problem and relevant scope are understood.

### 🧪 Test Runner

Validates implementations independently and reports whether the required checks actually pass.

### 🏗 Engineering Architect / Reviewer

Uses stronger engineering judgement where architecture, ownership, lifecycle, persistence, rendering or replacement hygiene matters.

### 🛡 Risk Reviewer

Examines high-risk or sensitive changes for regressions, security implications, edge cases and architectural failure modes.

### 🧠 Deep Solver

Handles bounded difficult engineering problems when deeper technical reasoning is genuinely warranted.

### 🎯 Intent Agents

Help preserve what you actually asked for so increasingly complicated development work does not drift away from the intended product, gameplay, UX or visual goal.

### 📚 Evidence Curator

Gathers and consolidates focused evidence when decisions need stronger technical grounding.

### 🚀 Frontier Architect

Reserved for exceptional product or architectural ambiguity where stronger intent-level judgement is justified.

---

# Four orchestration profiles

TJZA lets each project use the profile appropriate for the work being performed.

## ⚡ Efficient

**Capability without unnecessary overhead.**

Designed for projects where you want coordinated agents while keeping the workflow deliberately lean.

Recommended starting primary:

**GPT-6 Luna High**

Efficient keeps most work inside the Luna family and selectively calls GPT-6.1 Sol when stronger engineering judgement is justified.

---

## ⚖️ Balanced

**The everyday TJZA profile.**

Designed for normal software-development work where you want strong GPT-6 Luna capability with stronger engineering review for significant changes.

Recommended starting primary:

**GPT-6 Luna Max**

Balanced delegates non-trivial implementation to Luna workers rather than allowing the Primary to absorb routine building. Significant engineering changes receive GPT-6.1 Sol review even when tests pass.

---

## 🔥 Power

**For demanding engineering work.**

Power places GPT-6.1 Sol in the lead for engineering direction while delegating implementation volume to GPT-6 Luna.

Recommended starting primary:

**GPT-6.1 Sol Medium**

The guiding rule is:

**Sol leads. Luna builds.**

A second independent Sol review is used only when separation adds meaningful value rather than being invoked ceremonially.

---

## 🚀 Maximum

**For the difficult jobs.**

Maximum is designed for complex work where product intent, architecture, acceptance and engineering judgement all matter.

Recommended starting primary:

**GPT-6 Astra Medium**

Maximum keeps model responsibilities deliberately separated:

**Astra decides. Sol 6.1 engineers. Luna builds.**

Astra is reserved primarily for intent, ambiguity and final product alignment rather than routine technical difficulty.

---

# 🔄 Switch profiles per project

You do not have to reinstall TJZA every time you want a different workflow.

After the Universal Core has been installed, an individual project can be switched between:

**Efficient → Balanced → Power → Maximum**

The project's TJZA profile changes without replacing your global agent files or modifying your source code.

Start a fresh Codex session after changing a project profile so the new project instructions are loaded cleanly.

---

# ♻️ Subagent lifecycle protection

Long-running Codex use can leave large numbers of completed or stale subagent threads behind.

TJZA includes lifecycle and capacity guidance so that, where the Codex runtime supports it:

- completed, failed, cancelled, abandoned or clearly idle **TJZA** worker threads can be reclaimed;
- stale Xrotel or legacy-model workers are not reused for new work;
- the active Primary thread is never intentionally reclaimed;
- actively useful workers are left alone;
- unrelated user-created threads are not touched;
- stale legacy workers are reclaimed before current GPT-6 workers;
- required orchestration is retried after capacity is recovered; and
- completed workers should be reclaimed after their useful result has been consumed.

If capacity still cannot be recovered, TJZA should serialize the remaining work rather than silently skipping required review or forcing the Primary to absorb material implementation.

---

# 🧹 GPT-6-era upgrade hygiene

TJZA v7.0.0 uses these current runtime model families:

- `gpt-6-luna`
- `gpt-6.1-sol`
- `gpt-6-astra`

The included installer removes old TJZA and Xrotel agent-role files before copying the current role set.

Legacy Xrotel tools are also migrated to the TJZA tool location.

Existing Codex conversation history is **not** deleted.

Old Xrotel or pre-v7 worker threads may remain visible in history, but current TJZA orchestration must not resume or reuse them when they use unsupported model families.

---

# 📊 Agent Usage reporting

TJZA includes Agent Usage reporting so you can see which agents were used for a task, what each one was used for and what outcome it produced.

The current runtime-reporting tools are designed to report the actual model and reasoning level used by the Primary and spawned TJZA workers rather than relying only on configured defaults.

This helps expose:

- which model/reasoning combinations were actually used;
- whether stronger models were invoked and why;
- whether implementation was delegated appropriately;
- whether significant-change review occurred;
- whether a runtime/configuration mismatch occurred; and
- whether legacy or unsupported workers appeared.

---

# ⬇️ Download TJZA Agents

## 🚀 Get the latest release

👉 **[Download TJZA Agents](https://github.com/hader-campbell/TJZA-Agents/releases/latest)**

The **complete package** is recommended if you want all TJZA orchestration profiles:

- ⚡ Efficient
- ⚖️ Balanced
- 🔥 Power
- 🚀 Maximum

Individual profile packages are also available under **Assets** on the release page.

TJZA is free to download and use under the included licence.

---

# 📦 Installation

## Windows

After downloading your chosen TJZA package:

1. Extract the ZIP.
2. Open PowerShell in the extracted package folder.
3. Run:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File ".\\Install\\INSTALL-WINDOWS.ps1"
```

The installer will:

- install the global TJZA `AGENTS.md`;
- remove obsolete Xrotel and TJZA agent TOMLs from previous versions;
- install the current TJZA agent TOMLs;
- migrate/remove obsolete Xrotel runtime tools where applicable; and
- install the current TJZA runtime-reporting tools.

You do **not** need to manually copy the agent TOMLs after running the installer.

Then:

4. Run the included **Project Optimizer** once for existing Xrotel projects or repositories you want to make profile-switchable.
5. Select the appropriate Primary model and reasoning level in Codex.
6. Start a fresh Codex session.

## macOS / Linux

The package also includes:

```bash
sh ./Install/install-macos-linux.sh
```

Then run the Project Optimizer where needed and start a fresh Codex session.

No TJZA server, account or external service is required to run the orchestration package.

---

# 🔁 Upgrading from Xrotel Agents

TJZA v7.0.0 is the successor to Xrotel Agents.

Existing Xrotel users should:

1. install TJZA v7.0.0 using the included installer;
2. run the v7 Project Optimizer once in existing repositories;
3. allow the optimizer to migrate the legacy Xrotel profile block to the TJZA profile format;
4. choose the appropriate profile and Primary model; and
5. start a fresh Codex session.

The optimizer is designed to preserve the selected profile while migrating legacy Xrotel profile markers to TJZA markers.

---

# 🔐 Your code stays where it is

TJZA does not require you to upload your repository to TJZA.

It does not act as an API proxy and does not need access to your OpenAI credentials.

The configuration operates in the Codex environment where you install it.

---

# ❤️ TJZA is free

TJZA Agents is currently available free of charge.

If it improves your Codex workflow, saves you time or helps you build better software, you can optionally support continued development.

### Support once

https://www.paypal.com/ncp/payment/X3YXRNX2WWSZ6

### Support TJZA monthly — $3/month

https://www.paypal.com/webapps/billing/plans/subscribe?plan_id=P-1HU900860L732862RNKMIYKY

Financial support is completely optional and does not purchase additional licence rights.

Can't support financially?

⭐ Star the repository  
🐛 Report an issue  
💬 Share your experience  
📣 Tell another developer about TJZA  

That helps too.

---

# 📝 Licensing

TJZA is free to use under the included **TJZA Agents Personal / Internal Use License**.

You may use and modify TJZA for your own personal or commercial software-development work.

Redistribution, resale, mirroring or repackaging for unrelated third parties is not permitted.

See `LICENSE.md` for the complete terms.

---

# ⚠️ Compatibility

OpenAI may independently change Codex, available models, reasoning levels, configuration behaviour or agent capabilities.

TJZA will continue to evolve alongside supported Codex workflows where practical.

---

# TJZA Agents

**Build with a team, not just an agent.**
