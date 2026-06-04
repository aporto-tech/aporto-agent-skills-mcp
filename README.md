# Aporto Agent Skills MCP

Optional MCP entrypoint for Aporto Agent Skills.

You do not need MCP for the product to work. The canonical product is the Aporto
API. MCP is a convenience layer for agents and IDEs that already understand MCP.

The important rule is the same either way: the agent sees a tiny Aporto surface,
not thousands of skills.

## Tools

1. `aporto_discover_agent_skills`
   - Input: intent, optional tags, limit.
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

## Why MCP Exists

Some agent hosts prefer tools over raw HTTP. MCP lets those hosts add Aporto with
one config block. Users who do not need MCP can call the same Aporto endpoints
directly.

## Backend

Discovery and embeddings live on Aporto servers. This package does not store the
full catalog, does not compute embeddings, and does not load every skill into
model context.

