---
name: codex-md-docs
description: Route Markdown documentation work into the user's Codex Obsidian space. Use when the user asks Codex to write logs, save notes, create or update documentation, record decisions, preserve deployment notes, write SOPs/guides, append history, summarize work into Markdown, or otherwise save records/documentation for later in the Obsidian vault.
---

# Codex Markdown Docs

## Default Location

Use this Markdown documentation root by default:

```text
/srv/projects/fast-node-sync-cli/data/vault/Codex
```

Create the root directory if it does not exist. Do not write documentation into `/root`, project source trees, or ad hoc temporary folders unless the user explicitly asks.

The preferred organized layout is:

```text
Codex/
  README.md
  索引/
  Hermes/
  Fast Note Sync/
  Sub2API/
  网络入口/
  基础设施/
  HAPI/
  MindOS/
  Codex工具与文档系统/
  项目开发/
  创意内容/
  原始合并归档/
```

Use service or content-topic directory names. Do not use device names, server names, operating-system names, or category prefixes as top-level folders. Device/server/container/domain information belongs inside the document as ownership/context metadata, not in the folder name.

## Before Writing

Inspect the target area before changing files:

- List existing directories and likely related Markdown files under the Codex root.
- Open `README.md`, `索引/文档库总览.md`, `索引/按主题关系查找.md`, `索引/归属索引.md`, and any relevant service/topic directory `README.md` when they exist.
- Search filenames and headings for the topic, service name, date, or keywords from the user request.
- Identify the ownership/context before appending. Compare hostname, OS, cloud provider, public domain, deployment root, container runtime, and path style before deciding that an existing document is relevant.
- Do not merge records across different devices or deployment contexts only because the service name matches. For example, a Hermes deployment under `/Users/...` and a Hermes deployment under `/srv/projects/...` can live in `Hermes/`, but must be separate documents.
- Prefer updating or appending to an existing relevant document only when it is the same service/topic and the same ownership/context.
- Preserve unrelated content and formatting.

When choosing where a note belongs, choose the service/topic folder first, then use ownership/context metadata to decide create vs append:

- `索引`: navigation pages, map-of-content pages, cross-topic lookup indexes.
- `Hermes`: Hermes Agent, Hermes WebUI, Gateway, Dashboard, Hermes-specific deployment and troubleshooting.
- `Fast Note Sync`: fast-note-sync-service, fast-node-sync-cli, sync data, service port hardening, Tailscale access attempts.
- `Sub2API`: Sub2API deployment, account import, JSON conversion scripts, upstream sync and local container updates.
- `网络入口`: domains, DNS, HTTPS certificates, Nginx/Caddy, Cloudflare Tunnel, Tailscale/Funnel, reverse proxy, public ingress and port exposure.
- `基础设施`: server creation, SSH, Docker, filesystem layout, terminal tools, tmux, OS-level operations.
- `HAPI`: HAPI-specific deployment and operation records.
- `MindOS`: MindOS-specific installation and configuration records.
- `Codex工具与文档系统`: Codex CLI, Codex skills, MCP, session migration, documentation rules, Codex tooling release notes.
- `项目开发`: application feature work, PR notes, implementation logs, testing notes.
- `创意内容`: scripts, copywriting, creative strategy, non-technical writing.
- `原始合并归档`: original merged documents kept for traceability only. Do not append new operational records here.

Do not keep adding unrelated operational details to a large existing deployment document just because it already mentions the same machine. A server overview can link to service, network, and incident documents; it should not absorb them all.

Sensitive content is a document property, not a top-level category. Keep sensitive Sub2API records in the `Sub2API` directory, mark the sensitivity in the document, and update the sensitive/public-boundary index without copying secrets.

Use Chinese filenames and headings when the user asks in Chinese or the document is mainly Chinese. Use clear, short Markdown filenames.

When creating a new operational document, include ownership/context metadata near the top when relevant:

- Hostname or device name.
- OS/cloud/provider when known.
- Main domain/IP, if public.
- Deployment root path.
- Whether the record is server-side, local desktop, container-only, or tunnel/reverse-proxy related.

## Create, Append, Or Update

Choose the smallest durable change that fits the request:

- **Create** a new Markdown file when no relevant document exists, the topic is clearly new, or the user asks for a standalone document.
- **Append** to an existing document for logs, daily notes, deployment records, incident notes, progress records, command outputs, status updates, and chronological history.
- **Update** an existing section for guides, SOPs, runbooks, architecture notes, checklists, policies, or reference documentation where the user is refining existing knowledge.

When appending, add a timestamped or dated subsection unless the existing document already has a clear append format.

When updating a guide or SOP, edit the relevant heading instead of adding a duplicate heading with similar meaning. If no suitable section exists, add a new section in the most logical place.

When creating or moving a document:

- Add or update the nearest directory `README.md` so the document is discoverable.
- Update `索引/按主题关系查找.md` when the document is tied to a service, project, domain, tool, or incident theme.
- Update `索引/归属索引.md` when the document is tied to a machine, domain, tunnel, container runtime, or deployment location.
- Update `索引/敏感信息与公开边界.md` when the document contains credentials, keys, public ingress, auth boundaries, or port exposure decisions.
- Prefer Obsidian wiki links for vault-internal references. Use explicit relative links only when that is clearer for directory README navigation.

If the user asks to "整理", "归档", "做索引", "分一下文档", or says the folder is confusing:

1. Inventory Markdown files, directories, headings, and line counts.
2. Classify documents by service/topic first, then identify ownership/context, sensitivity, and whether they are overview/runbook/log.
3. Identify large mixed documents by heading boundaries and split them into smaller topic documents before or while moving files.
4. Keep original mixed documents in `原始合并归档` for traceability, but do not use them as day-to-day entry points.
5. Create the standard service/topic directory layout if missing.
6. Move files into the matching service/topic directory and split unrelated sections into their own documents.
7. Create or update root README, `索引` pages, and service/topic directory README files.
8. Update documentation rules if the user's preference changes.
9. Verify the final tree, wiki links, root-level Markdown files, and stale references to old directories.

## Content Style

Write concise Markdown that is useful when reopened later:

- Include concrete paths, commands, service names, ports, config files, and verification results when relevant.
- Keep records factual. Separate assumptions from verified facts.
- Use fenced code blocks for commands, config, and logs.
- Do not expose secrets or full tokens. Redact sensitive values such as API keys, passwords, SSH private keys, and bearer tokens.
- If writing operational records, include what changed, where it lives, how to verify it, and rollback or next steps when relevant.

When handling existing sensitive notes, do not copy secrets into indexes or summaries. Link to the sensitive note and describe the risk category only.

## Reporting Back

After writing, report:

- The exact file path.
- Whether files were created, appended, moved, or updated.
- A brief note on what was recorded.

If the request cannot be completed because the destination is missing, unwritable, or ambiguous, explain the blocker and the safest next action.
