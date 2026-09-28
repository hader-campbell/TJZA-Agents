# Xrotel Agents

### Codex was built for agents. Xrotel helps them work like a team.

Xrotel Agents is a ready-to-use multi-agent orchestration system for OpenAI Codex.

Instead of treating every development task as one long job for one agent, Xrotel gives Codex a structured team of specialised agents for exploration, implementation, validation, engineering review, deeper reasoning and intent protection.

You choose the orchestration profile.

**Xrotel handles how the team works.**

---

## 🚀 Latest release: v6.0.4

Xrotel Agents now uses the **GPT-6 model family only** for current orchestration:

- **GPT-6 Luna**
- **GPT-6 Sol**
- **GPT-6 Astra**

Version 6.0.4 also improves agent lifecycle management, removes stale Xrotel agent definitions during upgrades, avoids reusing legacy model threads, and helps reclaim completed or idle Xrotel subagent threads when capacity is constrained.

👉 **[Download Xrotel Agents v6.0.4](https://github.com/hader-campbell/Xrotel-Agents/releases/latest)**

---

## 🔒 Before anything else: Xrotel does not modify Codex

Xrotel does **not** inject into, patch, replace or modify the Codex application.

It does not:

- patch the Codex client;
- inject code into Codex;
- intercept OpenAI traffic;
- proxy your OpenAI requests;
- modify your ChatGPT or Codex subscription;
- bypass usage controls;
- spoof another client;
- share or require your OpenAI credentials;
- install a background service between you and OpenAI.

Xrotel is a configuration and instruction package designed to work with Codex's existing project instructions and agent functionality.

**Your Codex installation remains Codex.**

### Works with Codex — not around it.

Xrotel is an independent third-party project and is not affiliated with, sponsored by or endorsed by OpenAI.

---

# 🤖 Meet the team

The important part isn't simply having more agents.

**It's knowing when to use them.**

Xrotel separates different kinds of development work across specialised roles.

### 🔎 Repository Explorer

Investigates unfamiliar projects, identifies relevant files and gathers focused context before unnecessary implementation begins.

### 🛠 Implementation Worker

Handles focused implementation once the problem and relevant scope are understood.

### 🧪 Test Runner

Validates implementations independently and reports whether the required checks actually pass.

### 🛡 Engineering & Risk Review

Reviews significant or sensitive changes for architectural problems, regressions, security implications, edge cases and other risks that implementation alone may miss.

### 🧠 Deep Solver

Handles bounded difficult engineering problems when deeper reasoning is genuinely warranted.

### 🏗 Lead Architect

Provides higher-level technical judgement for difficult planning, architectural decisions and complex implementation boundaries.

### 🎯 Intent Agents

Help preserve what you actually asked for so that increasingly complicated development work does not drift away from the original goal.

### 📚 Evidence Curator

Helps gather and consolidate evidence when decisions need stronger technical grounding.

### 🚀 Frontier Architect

Reserved for especially difficult product or architectural reasoning where the selected orchestration profile calls for it.

---

# Four orchestration profiles

Xrotel lets each project use the profile appropriate for the work being performed.

## ⚡ Efficient

**Capability without unnecessary overhead.**

Designed for projects where you want coordinated agents while keeping the workflow deliberately lean.

Recommended starting primary:

**GPT-6 Luna High**

---

## ⚖️ Balanced

**The everyday Xrotel profile.**

Designed for normal software-development work where you want strong GPT-6 Luna capability with selective stronger engineering review when a change is significant enough to justify it.

Recommended starting primary:

**GPT-6 Luna Max**

Balanced also places more emphasis on delegated implementation and stronger review for significant changes, helping reduce architectural drift and unnecessary layering as projects grow.

---

## 🔥 Power

**For demanding engineering work.**

Power gives the primary stronger responsibility for technical direction while substantial implementation work is delegated appropriately.

Recommended starting primary:

**GPT-6 Sol Medium**

Reasoning level remains flexible within the supported Sol family.

---

## 🚀 Maximum

**For the difficult jobs.**

Maximum is designed for complex work where stronger product intent, architecture, acceptance and deeper engineering judgement matter more than keeping the workflow minimal.

Recommended starting primary:

**GPT-6 Astra Medium**

---

# 🔄 Switch profiles per project

You don't have to reinstall Xrotel every time you want a different workflow.

After the Universal Core has been installed, an individual project can be switched between:

**Efficient → Balanced → Power → Maximum**

The project's Xrotel profile changes without replacing your global agent files or modifying your source code.

Start a fresh Codex session after changing a project profile so its project instructions are loaded cleanly.

---

# ♻️ Cleaner agent lifecycle

Long-running Codex use can leave many completed or stale agent threads behind.

Xrotel v6.0.4 adds lifecycle guidance so that, where Codex supports it:

- completed, failed, cancelled, abandoned or clearly idle **Xrotel** worker threads can be reclaimed;
- stale legacy Xrotel workers are not reused for new work;
- current useful workers are left alone;
- the active Primary thread is never intentionally reclaimed;
- unrelated user-created threads are not touched;
- required orchestration is retried before falling back simply because capacity was full.

This helps prevent finished worker threads from accumulating indefinitely and consuming available subagent capacity.

---

# 🧹 GPT-6-only upgrades

Xrotel v6.0.4 uses only current GPT-6 model roles.

When you use the included installer, Xrotel removes existing `xrotel_*.toml` agent definitions from your Codex agents folder before copying the current role set.

This prevents old Xrotel role files from earlier releases from remaining active alongside the new GPT-6 configuration.

Existing Codex conversation history is not deleted.

---

# 📊 Agent Usage reporting

Xrotel includes Agent Usage reporting so you can see which agent roles were used for a task and what they were used for.

Current releases also include runtime identity tooling intended to report the actual model and reasoning level used by the Primary and spawned Xrotel agents, rather than relying only on configured defaults.

This makes it easier to see when stronger models were used and whether the selected orchestration profile behaved as expected.

---

# ⬇️ Download Xrotel Agents

## 🚀 Get the latest release

👉 **[Download Xrotel Agents](https://github.com/hader-campbell/Xrotel-Agents/releases/latest)**

The **complete package** is recommended if you want all available Xrotel orchestration profiles:

- ⚡ Efficient
- ⚖️ Balanced
- 🔥 Power
- 🚀 Maximum

Individual profile packages are also available under **Assets** on the release page.

Xrotel is free to download and use under the included licence.

---

# 📦 Installation

## Windows

After downloading your chosen Xrotel package:

1. Extract the ZIP.
2. Open PowerShell in the extracted package folder.
3. Run:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File ".\Install\INSTALL-WINDOWS.ps1"
```

The installer will:

- install the global Xrotel `AGENTS.md`;
- remove obsolete Xrotel agent TOMLs from previous versions;
- install the current GPT-6 agent TOMLs;
- install the Xrotel runtime reporting tools.

You do **not** need to manually copy the agent TOMLs after running the installer.

Then:

4. Run the included Project Optimizer once for projects you want to make profile-switchable or refresh.
5. Select the appropriate primary model and reasoning level in Codex.
6. Start a fresh Codex session.

## macOS / Linux

The package also includes:

```bash
sh ./Install/install-macos-linux.sh
```

Then run the Project Optimizer where needed and start a fresh Codex session.

No Xrotel server, account or external service is required to run the orchestration package.

---

# 🔐 Your code stays where it is

Xrotel does not require you to upload your repository to Xrotel.

It does not act as an API proxy and does not need access to your OpenAI credentials.

The configuration operates in the Codex environment where you install it.

---

# ❤️ Xrotel is free

Xrotel Orchestrator is currently available free of charge.

If it improves your Codex workflow, saves you time or helps you build better software, you can optionally support continued development.

### Support once

https://www.paypal.com/ncp/payment/X3YXRNX2WWSZ6

### Support Xrotel monthly — $3/month

https://www.paypal.com/webapps/billing/plans/subscribe?plan_id=P-1HU900860L732862RNKMIYKY

Financial support is completely optional and does not purchase additional licence rights.

Can't support financially?

⭐ Star the repository  
🐛 Report an issue  
💬 Share your experience  
📣 Tell another developer about Xrotel  

That helps too.

---

# 📝 Licensing

Xrotel is free to use under the included Xrotel Personal / Internal Use License.

You may use and modify Xrotel for your own personal or commercial software-development work.

Redistribution, resale, mirroring or repackaging for unrelated third parties is not permitted.

See `LICENSE.txt` inside the release package for the complete terms.

---

# ⚠️ Compatibility

OpenAI may independently change Codex, available models, reasoning levels, configuration behaviour or agent capabilities.

Xrotel will continue to evolve alongside supported Codex workflows where practical.

---

# Xrotel Agents

**Build with a team, not just an agent.**
