---
name: codex-md-docs
description: Route Markdown documentation work into the user's Codex Obsidian space using project-first folders and device/environment suffixes in filenames. Use when the user asks Codex to create, write, update, append, record, summarize, save, organize, archive, or maintain any Markdown document, md note, deployment record, operation guide, SOP, troubleshooting note, decision record, or session handoff unless the user explicitly gives a different destination.
---

# Codex Markdown Docs

## Default Root

Use this Markdown documentation root by default:

```text
/Users/lyston/Obsidian/lyston/Codex
```

Prefer this root even if older notes exist elsewhere, unless the user explicitly names another path. Create it if it is missing. Do not write documentation into project source trees, `/tmp`, `/root`, downloads, or ad hoc scratch folders unless the user explicitly asks.

## Placement Model

The active Codex vault structure is project-first:

```text
Codex/
  Hermes/
    Hermes WebUI 本地部署与端到端测试记录（lystonmacbook-pro.local）.md
    Hermes Ubuntu 服务器部署记录（lyston11.qzz.io）.md
  Sub2API/
    Sub2API OrbStack 本机部署与敏感凭据记录（lystonmacbook-pro.local）.md
  Fast Note Sync/
    fast-note-sync-service 端口加固记录（lyston11.qzz.io）.md
```

Top-level folders under `/Users/lyston/Obsidian/lyston/Codex` should be project, service, product, topic, or stable workstream names, not device names.

Good top-level folders include:

```text
Hermes
Fast Note Sync
Sub2API
DBX
GenericAgent
HAPI
MindOS
Codex工具与文档系统
LDStatus Pro
锐鲨
天命AI写作
学习笔记
基础设施
```

Use `基础设施` only for cross-project infrastructure or server/network records that do not belong naturally to one project. If a device or domain is itself the subject, still put it under the closest project/topic folder and use the device/domain as the filename suffix.

Do not create top-level folders named only after devices, hosts, servers, operating systems, container runtimes, or dates. Do not create or maintain `README.md`, separate catalog folders, summary entry pages, or original archive folders. Use project folders, clear filenames, headings, and search for discoverability.

## Filename Device Suffix

Every operational, deployment, troubleshooting, access, tunnel, proxy, configuration, or environment-specific document must end with a device/environment suffix before `.md`.

Preferred format:

```text
主题（设备或环境）.md
```

Examples:

```text
Hermes/Hermes WebUI 下线与清理记录（lyston11.qzz.io）.md
Hermes/Hermes WebUI 本地部署与端到端测试记录（lystonmacbook-pro.local）.md
Sub2API/Sub2API OrbStack 本机部署与敏感凭据记录（lystonmacbook-pro.local）.md
Fast Note Sync/fast-note-sync-service 端口加固记录（lyston11.qzz.io）.md
基础设施/DigitalOcean Ubuntu 服务器初始化与基础运维（lyston11.qzz.io）.md
```

Use the most useful marker for the suffix:

- Hostname or device name: `lystonmacbook-pro.local`, `lyston11.qzz.io`.
- Deployment environment: `Ubuntu srv-projects`, `OrbStack`, `Cloudflare Tunnel`.
- Domain or public endpoint when it identifies the environment better than the hostname.

Do not rely only on frontmatter or body metadata to distinguish devices. The filename suffix is required when the document is environment-specific.

Documents that are purely conceptual, creative, study notes, or project-agnostic may omit the device suffix if no environment ownership exists.

## Before Writing

1. If the user gives an exact file path, use that path.
2. If the user gives a folder path, choose or create the `.md` file inside that folder, using the filename suffix rule when relevant.
3. If the user gives only a title or topic, first identify the project/service/topic folder under `/Users/lyston/Obsidian/lyston/Codex`.
4. Search project folders, filenames, and headings for the topic, service name, date, domain, path, hostname, device name, or keywords from the request.
5. Identify the device/environment before choosing whether to append or create. Compare hostname/device name, OS, cloud provider, public domain/IP, deployment root, path style, container runtime, and tunnel/reverse-proxy endpoint when available.
6. Prefer an existing note only when both the project/topic and the filename suffix or environment metadata match.
7. Hard rule: never merge records across different devices or environments only because the project/service name matches.
8. Preserve existing Markdown structure, frontmatter, headings, Obsidian links, and unrelated content.
9. Do not create database backups, code backups, duplicate archival files, root landing pages, or folder entry pages unless the user explicitly asks.

## Create, Append, Or Update

Choose the smallest durable change that fits the request:

- **Create** a new file when no strong match exists, the topic is new, the environment differs, the suffix differs, or the user asks for a standalone document.
- **Append** for deployment logs, operational history, incident notes, progress records, meeting notes, dated observations, command outputs, session handoffs, and continuing timelines that belong to the same project and same environment suffix.
- **Update** an existing section for living guides, SOPs, runbooks, architecture notes, checklists, policies, configuration records, or summaries whose current content should be refined.

For dated append entries, prefer:

```markdown
## 2026-05-26
```

If updating risks overwriting important history, append a dated section instead. If environment cues are missing and multiple notes could match, ask one concise clarifying question.

## Discoverability

When creating, moving, splitting, or materially updating a document, keep it discoverable through folder and filename design:

- Use the project/topic as the top-level folder.
- Put device/environment ownership in the filename suffix.
- Use clear headings and related-document links inside the actual notes.
- Do not add or update folder `README.md` files.
- Do not create or update separate catalog folders or summary entry pages.
- For sensitive content, record the sensitive boundary inside the relevant document itself without copying secrets or credentials elsewhere.
- Prefer Obsidian wiki links for vault-internal references. Use relative Markdown links only when they are clearer than wiki links for a specific path.

## Organization And Cleanup

If the user asks to organize, archive, split, clean up, or says the vault/folder is confusing:

1. Inventory Markdown files, directories, headings, and large mixed documents.
2. Classify by project/service/topic first, then by device/environment suffix, sensitivity, and document type.
3. Move device-first files into project-first folders. For example, move `lyston11.qzz.io/Hermes/Hermes WebUI 下线与清理记录.md` to `Hermes/Hermes WebUI 下线与清理记录（lyston11.qzz.io）.md`.
4. Split unrelated sections from large mixed documents into focused topic documents when useful.
5. Do not keep original mixed documents in original archive folders; remove old original archives after confirming the focused documents exist.
6. Create missing project/topic folders only when the content is likely to recur or when several documents belong together.
7. Do not create summary entry pages; keep discoverability in the folder structure, filenames, headings, and related-document links.
8. Verify final tree shape: project folders at the root, no device-only root folders unless the device/domain is truly the project, no `README.md`, no separate catalog folders, no original archive folders, and no stale links.

Do not keep appending unrelated operational details to a large deployment note just because it mentions the same machine. A project overview can link to service, network, and incident documents; it should not absorb them all.

## Naming

Use Chinese filenames and headings when the user writes in Chinese or the document is mainly Chinese. Use clear, short Markdown filenames.

For operational, deployment, access, tunnel, proxy, or troubleshooting records, include the environment suffix even if the title already mentions a host or runtime:

```text
Sub2API Docker 部署记录（OrbStack）.md
Sub2API Docker 部署记录（Ubuntu srv-projects）.md
Cloudflare Tunnel 外网访问配置记录（lystonmacbook-pro.local）.md
Codex 会话同步与迁移指南（lystonmacbook-pro.local）.md
```

If a file already has useful environment text in the title, keep the title readable and still ensure the final suffix is the canonical device/environment marker.

## Environment Metadata

For operational documents, include ownership/context near the top when relevant:

- Hostname or device name.
- OS/cloud/provider when known.
- Main domain/IP, if public.
- Deployment root path.
- Container/runtime context, if relevant.
- Whether the record is local desktop, server-side, container-only, or tunnel/reverse-proxy related.

The metadata supports the filename suffix; it does not replace it.

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
- Which project/topic folder was selected, created, or updated.
- The device/environment suffix used when relevant.
- Any important status or caveat discovered while writing.
