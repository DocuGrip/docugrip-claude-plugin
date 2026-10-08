---
name: court-efiling
description: Use when the user is preparing PDFs to file with a court or tribunal — federal CM/ECF/PACER, state e-filing (Odyssey, eFileTexas, NYSCEF), the U.S. Tax Court (DAWSON), an appellate court or immigration court — including Bates numbering exhibits, adding bookmarks, making scans text-searchable, splitting an oversized filing, redacting personal identifiers, or meeting a court's file size limit.
---

# Prepare a court filing

## Steps

1. Call `get_upload_requirements` with the court system. Federal courts set their own limits (often 35–50 MB, lower in
   some districts): if the result says "set by each court", ask which court and check its local rules.
2. Build the sequence with `find_pdf_tool`:
   1. OCR scanned exhibits so the court's text search works.
   2. Bates-number the exhibits (prefix, start number, position).
   3. Add bookmarks for each exhibit or section if the court asks for them.
   4. Redact personal identifiers (account numbers, dates of birth) the rules require you to remove — with a tool that
      removes the text, not a black box drawn on top.
   5. Compress, or split by size so every part stays under the limit, labeled in order.
3. Present the steps numbered with links, and the limit with its source.

## Care

- Keep an unaltered copy of every exhibit for the record.
- Filing rules are the court's: when the tool can't confirm a court-specific rule, say so and point to that court's
  local rules rather than guessing.
