# Security

**TJZA Agents** is a configuration and instruction package for use with **OpenAI Codex**.

TJZA does **not** require users to provide OpenAI account credentials, API keys, or ChatGPT authentication information to TJZA.

TJZA does **not** operate an intermediary proxy between the user and OpenAI and does **not** intentionally intercept Codex network traffic.

TJZA does **not** install a background network service between the user and OpenAI.

---

## Security design notes

TJZA's installer and runtime helpers are intended to operate **locally in the user's Codex environment**.

The current package may:

- install or replace TJZA's global Codex instruction file;
- remove obsolete TJZA/Xrotel agent-role files before installing the current role set;
- install TJZA runtime-reporting helpers; and
- read local Codex runtime/session metadata needed for **Agent Usage** reporting.

These operations are intended to remain local to the user's environment.

TJZA does **not** require these helpers to send repository content, Codex credentials, or runtime metadata to a TJZA-operated server.

### Subagent lifecycle safety

TJZA's subagent lifecycle guidance is designed to reclaim only:

- completed workers;
- failed workers;
- cancelled workers;
- abandoned workers; or
- clearly idle TJZA worker threads,

where the Codex runtime supports that operation.

TJZA must **not intentionally terminate**:

- the active Primary;
- an actively useful worker; or
- unrelated user-created threads.

---

## Reporting a security concern

If you discover a security issue relating specifically to **TJZA Agents**, please avoid publishing sensitive exploitation details in a public issue until the matter has been reviewed.

A useful security report should contain:

- the affected TJZA version;
- the affected file or component;
- reproduction information;
- the potential impact;
- the operating system / Codex environment where relevant; and
- any suggested remediation, if known.

### Do not include sensitive information

Please do **not** include:

- passwords;
- API keys;
- access tokens;
- private keys;
- session cookies;
- personal information; or
- other credentials

in security reports.

---

## Scope

Issues that are in scope include vulnerabilities introduced by TJZA's own:

- distributed files;
- installer scripts;
- runtime helpers; or
- orchestration instructions.

Problems caused solely by:

- OpenAI Codex;
- the operating system;
- third-party models;
- third-party software; or
- unrelated repositories

should be reported to the appropriate vendor or project.

---

## Independence

**TJZA is an independent third-party project and is not affiliated with, sponsored by, or endorsed by OpenAI.**
