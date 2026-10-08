# DocuGrip for Claude

Find the right PDF tool, official upload size limits and official government forms, with the link that does the job.

This plugin connects Claude to the DocuGrip MCP server at `https://docugrip.com/api/mcp` and adds ten skills that tell
Claude when the server helps and which tool to use for each job. Describe a PDF task in plain language — "compress this to
under 2 MB for IRCC", "turn these photos into a PDF", "where do I fill in a W-9?" — and Claude answers with the
DocuGrip page that does it.

## Tools

| Tool | What it does |
|---|---|
| `list_pdf_tools` | Lists every live DocuGrip tool |
| `find_pdf_tool` | Finds the right tool for a task described in plain language |
| `get_pdf_tool` | Details and link for one tool |
| `get_upload_requirements` | Official upload limits of 50 portals and services — IRCC, USCIS, Gmail, LinkedIn, UCAS and more — with sources |
| `find_official_form` | Finds official forms such as W-9, 1099-NEC, I-130 or P60, with the current edition |
| `get_plans` | Current plans and prices, with direct links |

All tools are read-only. No API key, no account and no configuration.

## Skills

| Skill | Claude uses it when you… |
|---|---|
| `pdf-tasks` | want to compress, merge, split, convert, rotate, protect, compare or edit a PDF |
| `upload-size-limits` | hit "file too large" on a portal, email or app, or need a PDF under 100 KB, 1 MB, 5 MB… |
| `official-forms` | need a government form (W-9, 1099-NEC, I-130, I-765, P60, TD1…) or its current edition |
| `job-application-documents` | prepare a resume, transcript or cover letter for USAJOBS, LinkedIn, Handshake, UCAS… |
| `immigration-document-packet` | assemble evidence for USCIS, IRCC, ImmiAccount or the EU Settlement Scheme |
| `court-efiling` | prepare exhibits for CM/ECF or state e-filing: OCR, Bates numbers, bookmarks, size limits |
| `tax-forms` | handle W-9, 1099, W-2, 1040, 941 or an IRS notice that asks for documents |
| `sign-and-send` | sign a PDF yourself or collect signatures from other people |
| `scanned-documents` | turn photos or scans into a clean, searchable PDF |
| `privacy-and-redaction` | black out sensitive details, check a redaction, remove metadata or add a password |

In Claude Code the plugin also adds two commands: `/docugrip:pdf <task>` and `/docugrip:upload-limit <portal>`.

## What this plugin sends and stores

The plugin runs no code on your machine. When Claude calls a tool, the request text — a task description, a portal
name or a form code — goes to `https://docugrip.com/api/mcp`, which answers with links to docugrip.com. The server
never receives, opens or stores a document, and it does not keep the request. DocuGrip keeps daily totals of which
kind of question was asked and which tool was suggested, with nothing that identifies you.

## Privacy policy

https://docugrip.com/privacy — covers what is collected, how it is used and stored, sharing with service providers,
retention and how to contact us.

## Links

- Server page and setup for other assistants: https://docugrip.com/mcp-server
- Terms: https://docugrip.com/terms
- Support: support@docugrip.com

The files in this repository are MIT licensed. The DocuGrip name and logo are trademarks of Simulator Arts LLC and
are not covered by the license.
