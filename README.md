# Aporto Agent Skills MCP

Minimal MCP client layer for Aporto Agent Skills.

This package should expose a tiny tool surface. The agent sees a few tools, not
thousands of skills.

## MVP Tools

1. `aporto_discover_agent_skills`
   - Input: natural-language intent, optional tags, limit.
   - Output: ranked skill summaries.

2. `aporto_load_agent_skill`
   - Input: skill id.
   - Output: selected `SKILL.md` body.

3. `aporto_run_capability`
   - Input: Aporto capability intent and params.
   - Output: Aporto run result or async run id.

4. `aporto_get_run_result`
   - Input: run id.
   - Output: completed result, artifacts, logs, or status.

## Backend

Discovery and embeddings live on Aporto servers. The MCP package does not store
the full catalog, does not compute embeddings, and does not load every skill
into the model context.

