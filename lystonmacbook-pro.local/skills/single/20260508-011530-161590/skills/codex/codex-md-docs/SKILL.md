---
name: codex-md-docs
description: Route Markdown documentation work into the user's Codex Obsidian space, including choosing or creating suitable folders, deciding whether to create/append/update notes, maintaining topic indexes, and keeping operational records separated by device/environment. Use when the user asks Codex to create, write, update, append, record, summarize, save, organize, archive, or maintain any Markdown document, md note, deployment record, operation guide, SOP, troubleshooting note, decision record, or session handoff unless the user explicitly gives a different destination.
---

# Codex Markdown Docs

## Default Root

Use this Markdown documentation root by default:

```text
/Users/lyston/Obsidian/lyston/Codex
```

Prefer this root even if older notes exist elsewhere, unless the user explicitly names another path. Create it if it is missing. Do not write documentation into project source trees, `/tmp`, `/root`, downloads, or ad hoc scratch folders unless the user explicitly asks.

## Placement Model

Use the existing vault structure as the source of truth. The active Codex vault structure is device-first:

```text
Codex/
  lystonmacbook-pro.local/
  lyston11.qzz.io/
```

Top-level folders under `/Users/lyston/Obsidian/lyston/Codex` must be device, host, or environment names. Under each device directory, classify documents by service, project, or content type, such as:

```text
Hermes
Fast Note Sync
Sub2API
基础设施
DBX
GenericAgent
HAPI
MindOS
Codex工具与文档系统
LDStatus Pro
锐鲨
```

Do not put service or project folders directly under the Codex root. Do not create or maintain `README.md`, `索引`, or index files as folder entry points. Use device directories, category directories, clear filenames, headings, and search for discoverability.

Do not create or keep `原始合并归档` folders or original merged documents. When a split is complete, day-to-day entry points are the device folders, category folders, and focused Markdown files only.

## Before Writing

1. If the user gives an exact file path, use that path.
2. If the user gives a folder path, choose or create the `.md` file inside that folder.
3. If the user gives only a title or topic, inspect likely matching device folders and Markdown files under `/Users/lyston/Obsidian/lyston/Codex`.
4. Search device directories, category directories, filenames, and headings for the topic, service name, date, project, domain, path, hostname, device name, or keywords from the request.
5. Identify the device/environment before choosing the directory, appending, or updating. Compare hostname/device name, OS, cloud provider, public domain/IP, deployment root, path style, container runtime, and tunnel/reverse-proxy endpoint when available.
6. Use clear filenames and headings because there are no README or index pages.
7. Hard rule: never merge records across different devices or environments only because the service name matches.
8. Prefer an existing note only when both the device/environment and topic/service match.
9. Preserve existing Markdown structure, frontmatter, headings, Obsidian links, and unrelated content.
10. Do not create database backups, code backups, or duplicate archival files unless the user explicitly asks.

## Create, Append, Or Update

Choose the smallest durable change that fits the request:

- **Create** a new file when no strong match exists, the topic is new, the environment differs, or the user asks for a standalone document.
- **Append** for deployment logs, operational history, incident notes, progress records, meeting notes, dated observations, command outputs, session handoffs, and continuing timelines.
- **Update** an existing section for living guides, SOPs, runbooks, architecture notes, checklists, policies, configuration records, or summaries whose current content should be refined.

For dated append entries, prefer:

```markdown
## 2026-05-06
```

If updating risks overwriting important history, append a dated section instead. If environment cues are missing and multiple notes could match, ask one concise clarifying question.

## Indexes And Discoverability

When creating, moving, splitting, or materially updating a document, keep it discoverable:

- Do not add or update folder `README.md` files.
- Do not create or update `索引` directories or index documents.
- Use clear device directories, category directories, filenames, headings, and related-document links inside the actual notes.
- For sensitive content, record the sensitive boundary inside the relevant document itself without copying secrets or credentials elsewhere.
- Prefer Obsidian wiki links for vault-internal references. Use relative Markdown links only when they are clearer than wiki links for a specific path.

## Organization And Cleanup

If the user asks to organize, archive, index, split, clean up, or says the vault/folder is confusing:

1. Inventory Markdown files, directories, headings, and large mixed documents.
2. Classify by device/environment first, then by service/topic, sensitivity, and document type.
3. Split unrelated sections from large mixed documents into focused topic documents when useful.
4. Do not keep original mixed documents in `原始合并归档`; remove old original archives after confirming the focused documents exist.
5. Create missing service/topic folders inside the appropriate device directory only when the content is likely to recur or when several documents belong together.
6. Do not create index pages; keep discoverability in the folder structure, filenames, headings, and related-document links.
7. Verify final tree shape, no `README.md` files, no `索引` directories, no `原始合并归档`, and no stale links.

Do not keep appending unrelated operational details to a large deployment note just because it mentions the same machine. A server overview can link to service, network, and incident documents; it should not absorb them all.

## Naming

Use Chinese filenames and headings when the user writes in Chinese or the document is mainly Chinese. Use clear, short Markdown filenames.

For operational, deployment, access, tunnel, proxy, or troubleshooting records, include an environment marker in the filename when it prevents cross-device confusion:

```text
Sub2API Docker（OrbStack）部署记录.md
Sub2API Docker（Ubuntu srv-projects）部署记录.md
Cloudflare Tunnel 外网访问配置记录.md
Codex 会话同步与迁移指南.md
```

If the document belongs clearly to a service/topic folder, the environment marker can be in the document metadata instead of the filename.

## Environment Metadata

For operational documents, include ownership/context near the top when relevant:

- Hostname or device name.
- OS/cloud/provider when known.
- Main domain/IP, if public.
- Deployment root path.
- Container/runtime context, if relevant.
- Whether the record is local desktop, server-side, container-only, or tunnel/reverse-proxy related.

## Content Style

Write concise Markdown that is useful when reopened later:

- Include concrete paths, commands, service names, ports, config files, dates, and verification results when relevant.
- Keep facts separate from assumptions.
- Use fenced code blocks for commands, config, logs, and structured output.
- Redact secrets, API keys, passwords, SSH private keys, bearer tokens, and full cookies.
- For operational records, include what changed, where it lives, how to verify it, and rollback or next steps when relevant.

## Reporting Back

After writing, briefly report:

- The exact file path.
- Whether content was created, appended, moved, split, or updated.
- Which device and category folder was selected, created, or updated.
- The device/environment used to choose or separate the document when relevant.
- Any important status or caveat discovered while writing.
