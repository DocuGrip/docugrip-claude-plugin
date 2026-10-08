---
name: upload-size-limits
description: Use when a website, portal or email refused a file because it is too large, or the user asks what size limit a site has or how small a PDF must be — for example IRCC, USCIS, ImmiAccount, EU Settlement Scheme, IRS, HealthCare.gov, HMRC, Companies House, a court e-filing system, USAJOBS, LinkedIn, Handshake, Greenhouse, UCAS, LSAC, Turnitin, Gmail, Outlook, Yahoo, iCloud or Proton Mail, ChatGPT, Claude, Notion, Docusign, Etsy, Shopify or Kindle. Also for "compress my PDF to 100 KB / 200 KB / 1 MB / 2 MB".
---

# Get a PDF under an upload limit

## Steps

1. Call `get_upload_requirements` with the portal or service name.
2. If it returns a requirement, answer with:
   - the official limit, in the provider's words, and its source with the date it was checked;
   - the target to type (it sits a little under the limit, so the file passes however the portal counts megabytes);
   - the compressor link from the result, which opens with that target already set;
   - any note from the result (file count, accepted formats, one file per field).
3. If several requirements come back, the name was ambiguous ("visa", "email"). Ask which one, listing them briefly.
4. If none comes back, the portal isn't in DocuGrip's table. Ask the user for the limit their upload screen shows, then
   call `find_pdf_tool` with "compress a PDF to under N MB" and give that link with N slightly reduced.

## When compressing isn't enough

Compression shrinks images; a long, text-heavy PDF may not get much smaller. Then suggest, in this order:
splitting by size into parts that each fit (if the portal accepts several files), converting color scans to grayscale,
or removing pages the portal didn't ask for. Use `find_pdf_tool` for each.

## Don't

- Don't quote a limit from memory when the tool has one: portals change limits and the tool carries the checked date.
- Don't promise an exact output size. The page aims for the target and says if a file can't reach it.
