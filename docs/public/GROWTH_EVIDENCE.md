# Echo Growth Evidence

## Signals of Growth
- **Adaptive responses over turns**: Personality shifts from generic to tailored after ~10–30 interactions as patterns/opinions from the Relationship Log are injected into the system prompt.
- **Opinion formation with confidence**: High-confidence (>=0.8) opinions are expressed directly; moderate opinions are hedged. This keeps Echo honest about what she “believes.”
- **Proactive suggestions**: When confidence is high, Echo proposes next steps aligned to observed preferences (e.g., pragmatism, speed, CLI bias).
- **Semantic recall**: Oracle retrieval injects the top-3 relevant facts instead of raw dumps, so responses stay on-topic while grounded in prior encounters.
- **Teacher-format data capture**: Programmes.jsonl logs clean THOUGHT/ANSWER pairs (THINK/ENDTHINK or <think>) with source tags (lmstudio, groq, groq-direct) for training.

## Evidence Artifacts
- **Relationship Log** (`data/relationship_log.jsonl`): Shows accumulated decisions, patterns, opinion shifts, milestones, and disagreements; acts as Echo’s “memory of how you think.”
- **Programmes Dataset** (`data/programmes.jsonl`): Growing line-by-line with each interaction; analyzer reports counts, thought coverage %, latency, token metrics.
- **Oracle DB** (`data/oracle.db`): Persisted facts with in-memory index; retrieval latency <100 ms in tests.
- **System Prompts in use**: Live prompts now include values, patterns, opinions, oracle snippets, and knowledge facts before every inference.
- **Performance Baseline**: Local LM Studio path has been stable in recent runs; handler times ~8–12s typical after warm-up (per console timing logs).

## How to Observe Growth Yourself
1. Run Echo (LM Studio + optional Groq fallback) and have 30+ turns of mixed questions (pragmatic + reflective).
2. After the session, open `relationship_log.jsonl` and scan the newest entries for patterns/opinions that match your style.
3. Run `node scripts/analyze_programmes.js --last 5` to see the latest logged teacher-formatted samples.
4. Export a fine-tune set: `npm run export:groq -- --source all --emit-metadata --limit 200` and inspect the JSONL for quality.
5. Check `oracle.db` (via sqlite client) to see the facts accumulated and how they’re retrieved.

## What We’re Watching Next
- Fallback reliability: ensure GROQ_API_KEY loads from .env/.env.local; spinner clears on error.
- Prompt budget discipline: cap oracle injections (fact count + snippet length) to keep responses tight.
- Sampling controls: expose ECHO_TEMP / ECHO_TOP_P to tune creativity vs. precision.
- Data quality: curate high-quality programmes for a future Groq fine-tune; monitor thought coverage.

Echo’s growth is visible in the logs: more opinions, tighter recall, cleaner teacher traces, and proactive suggestions that align with observed preferences—all without sharing private code.
