---
name: pdf-tasks
description: Use whenever the user wants to do something to a PDF or another document file — compress or shrink it, merge or combine files, split or extract pages, rotate, reorder or delete pages, convert PDF to Word, Excel, PowerPoint, JPG or text (or the other way round), turn photos or scans into a PDF, add page numbers or a watermark, edit text, unlock or password-protect, compare two PDFs, or make a PDF accessible. Also use when they ask which tool or website can do one of these jobs.
---

# Do a PDF task with DocuGrip

The DocuGrip connector maps a task to the DocuGrip page that does it. Pages open in the user's browser and process the
file there, so the user keeps the file on their device; the connector never receives it.

## Steps

1. Call `find_pdf_tool` with the task in the user's own words, for example "merge three PDFs and keep them in order".
   - Several separate jobs: one call per job, then present them as numbered steps in the order they must happen
     (combine before compressing; OCR before searching).
2. Give the top match as a link with one sentence on what the page does. Mention a second match only when the first
   clearly doesn't fit.
3. If the result carries a `portal` (an upload portal was named) or an `officialForm`, include it: it already has the
   right target size or the official edition.
4. If nothing matches, say so plainly. Don't offer a tool that does something else.

## Good to know

- If the user attached the PDF to this conversation, you can read it and answer questions about it directly. Changing
  the file itself — compressing, merging, signing — happens on the linked page.
- Each answer includes an `access` note with the free daily allowance and paid options. Mention cost only when the user
  asks or when the allowance clearly matters (for example, a batch of 50 files). For prices, call `get_plans`.

## Example

User: "I have 12 scanned receipts as JPGs and need one PDF under 5 MB."
→ `find_pdf_tool("turn 12 JPG photos into one PDF")`, then `find_pdf_tool("compress a PDF to under 5 MB")`.
Answer: two numbered steps with both links — first images to PDF, then compress with 5 MB as the target.
