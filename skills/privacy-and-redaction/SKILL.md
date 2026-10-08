---
name: privacy-and-redaction
description: Use when the user wants to black out or remove sensitive information from a PDF — account numbers, Social Security numbers, names, addresses, medical details — check whether a redacted PDF really hides the text, remove hidden metadata, add or remove a password, restrict printing or copying, or prepare a document safely before sharing it.
---

# Remove or protect sensitive information

## Steps

1. Redaction → `find_pdf_tool("redact a PDF")`. Explain the difference that matters: real redaction removes the text
   under the black box; a box drawn on top leaves the text copyable.
2. Already redacted elsewhere → `find_pdf_tool("check a redacted PDF for hidden text")` to verify nothing remains.
3. Hidden details (author, software, dates) → remove metadata before sharing.
4. Password or restrictions → protect the PDF (password to open, or limits on printing and copying).
5. Give the steps in order with links. Redact first, then remove metadata, then protect.

## Care

The DocuGrip pages process the file on the user's device, which matters for exactly these documents. Don't ask the user
to paste sensitive details into the chat to "check" them.
