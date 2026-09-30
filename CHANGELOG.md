# TJZA Agents Changelog

## v7.0.0 - TJZA rebrand and GPT-6.1 Sol architecture

v7.0.0 is a major orchestration release.

Xrotel Agents is now **TJZA Agents**, and the orchestration model has been redesigned around the stronger
GPT-6.1 Sol engineering tier rather than simply replacing model IDs.

### Brand migration

- Renamed Xrotel Agents to TJZA Agents.
- Renamed Xrotel agent-role files to the `tjza_*.toml` namespace.
- Renamed runtime tooling from `xrotel-tools` to `tjza-tools`.
- New project profile markers use `TJZA_PROFILE_START` / `TJZA_PROFILE_END`.
- Existing Xrotel project profiles can be migrated by the v7 Project Optimizer.
- Installers remove obsolete Xrotel/TJZA role files before installing the current role set.

### Model architecture

Current TJZA runtime families are:

- GPT-6 Luna
- GPT-6.1 Sol
- GPT-6 Astra

GPT-6 Sol is no longer a current TJZA v7 engineering role.

### Efficient

- Primary remains GPT-6 Luna High.
- Luna handles normal exploration, implementation and QA.
- GPT-6.1 Sol Medium is used selectively when stronger engineering judgement is justified.
- High-risk or difficult technical boundaries escalate to GPT-6.1 Sol High.
- Astra remains intent-focused rather than a general engineering escalation.

### Balanced

- Primary remains GPT-6 Luna Max.
- Non-trivial implementation is delegated to Luna High/Max workers.
- Significant engineering changes receive GPT-6.1 Sol Medium review even when tests pass.
- Sol preflight is conditional rather than automatic: it is used when architecture, ownership or replacement
  boundaries are unclear enough to justify it.
- The Balanced Primary should not absorb material implementation merely because it is capable of doing so.

### Power

- Power Primary moves to GPT-6.1 Sol Medium.
- Sol owns engineering direction, decomposition, integration and acceptance.
- Luna High/Max handles implementation volume.
- Independent Sol review is no longer automatic when the Sol Primary can satisfy the engineering-review
  requirement itself.
- Separate review is retained where independence meaningfully improves confidence, such as major replacement,
  repeated failure, competing implementations or sensitive structural work.

### Maximum

- Maximum Primary remains GPT-6 Astra Medium.
- Astra owns intent, ambiguity, contract alignment and final product-level acceptance where needed.
- GPT-6.1 Sol owns engineering translation, architecture and technical review.
- Luna High/Max handles implementation volume.
- Astra is not invoked merely because engineering is difficult; hard engineering stays with GPT-6.1 Sol.

### Subagent lifecycle and capacity protection

- Retains the preferred limit of at most two concurrently active subagents.
- When capacity is unavailable, TJZA first inspects/reclaims completed, failed, cancelled, abandoned or clearly
  idle TJZA workers where supported.
- Legacy/non-current workers are reclaimed before current workers.
- The active Primary, actively useful workers and unrelated user-created threads are not reclaimed.
- Required orchestration is retried after capacity is recovered.
- Completed workers should be reclaimed after their useful result has been consumed.
- If capacity still cannot be recovered, remaining work should be serialized rather than silently skipping
  required review or forcing the Primary to absorb material implementation.

### Runtime identity and reporting

- Agent Usage remains an actual-runtime ledger rather than a configured-model guess.
- Runtime-reporting tools report actual Primary/subagent model and reasoning information where available.
- Unsupported or legacy runtime models are surfaced as mismatches instead of silently reused.
- Agent Usage retains architecture-hygiene, delegation, review and capacity-discipline reporting.

### Upgrade hygiene

The v7 installer removes obsolete:

- `xrotel_*.toml`
- `tjza_*.toml`
- legacy Xrotel runtime-tool directories where applicable

before installing the current TJZA v7 role set and tools.

Existing Codex conversation history is not deleted.

---

## v6.0.4 - Final Xrotel release

- Added GPT-6-only Xrotel role enforcement.
- Added proactive subagent lifecycle and capacity hygiene.
- Added cleanup of stale Xrotel agent TOMLs during installation.
- Added runtime detection of legacy/non-current worker models.
- Retained Efficient, Balanced, Power and Maximum project profiles.

v6.0.4 was the final release under the **Xrotel Agents** name.

---

## v5.2.2 - Power & Maximum orchestration update

### Power

- Improved separation between Primary technical leadership and delegated implementation.
- Improved handling of substantial implementation tasks.
- More transparent Agent Usage reporting.

### Maximum

- Improved delegation of implementation work.
- Improved acceptance and repair-cycle discipline.
- Better visibility into Primary implementation and acceptance behaviour.

### Existing behaviour preserved

- Per-project profile switching remained supported.
- Reasoning level remained flexible within the selected Primary model family.
