# Echo Public Progress Overview

## What Echo Is
Echo is a continuity-first desktop assistant that grows through structured context (relationship log + oracle semantic retrieval) instead of long-term model memory.

## Current State (Dec 20, 2025)
- Runtime: Electron app + LM Studio (local) primary; Groq API fallback (llama-3.3-70b-versatile).
- Context layers: Relationship Log (JSONL), Oracle semantic retrieval (SQLite + in-memory index), Knowledge Base facts.
- Prompting: System prompt built from values + patterns/opinions + oracle snippets + relevant facts.
- Safety/routing: Uncertainty gating (question patterns; sigma when available) decides when to call fallback.
- Data capture: Programmes logged with THINK/ENDTHINK or <think> extraction, plus export script for Groq fine-tuning.
- Opinion expression: High-confidence opinions expressed plainly; moderate ones with tentative tone; proactive suggestions when confidence is high.
- Tooling: Headless LM Studio runner; dataset analyzer; Groq export script; Oracle test harness.

## What Works Reliably
- LM Studio path with DeepSeek-R1 family models (local server) and prompt injection of relationship + oracle context.
- Groq fallback path (once GROQ_API_KEY is set) with clean teacher formatting.
- Relationship logging: decisions, patterns, opinions, milestones, disagreements, insights.
- Oracle retrieval: top-3 semantic facts injected instead of dumping large context.
- Save/restore: Session log JSONL + conversation_state.json writes safely after normalization hardening.

## Major Recent Milestones
- Phase 1: Personalized system prompt wired into live inference (no more stub).
- Phase 2 (opinion expression): Confidence-based tone + proactive suggestion scaffold.
- Oracle layer: SQLite-backed semantic retrieval with in-memory index.
- Teacher enforcement: THINK/ENDTHINK and <think> support; clean separation of thought vs answer.
- Dataset tooling: analyze_programmes.js and export_groq_dataset.js for Groq fine-tune format.

## Near-Term Roadmap
- Verify Groq fallback end-to-end with env loading (.env + .env.local) and spinner clearing on errors.
- Cap oracle injections via env (ECHO_MAX_ORACLE_FACTS / ECHO_ORACLE_SNIPPET_CHARS).
- Propagate sampling knobs (ECHO_TEMP / ECHO_TOP_P) to LM Studio calls.
- Continue Phase 2: richer opinion surfacing in UI and proactive nudges.
- Collect higher-quality programmes and curate a gold set for fine-tuning.
 

## How to Try (Public Repo)
- Repo: https://github.com/sirspyr0/echo-public
- Run: npm install; start LM Studio local server with a chat-capable model; set GROQ_API_KEY for fallback; npm start.
- Inspect: data/relationship_log.jsonl (how Echo learns), data/programmes.jsonl (teacher-formatted traces), data/oracle.db (facts), data/groq_finetune.jsonl (exported dataset).
