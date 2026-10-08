---
name: scanned-documents
description: Use when the user has scanned pages or phone photos of documents — make them searchable or copyable with OCR, straighten crooked scans, clean shadows and gray backgrounds, turn several photos into one PDF, convert HEIC or JPG to PDF, reduce a huge scanned file, or extract text or tables from a scan.
---

# Work with scans and photos of documents

## Steps

Use `find_pdf_tool` for each step that applies, in this order:

1. Photos (JPG, PNG, HEIC) → one PDF, pages in the right order.
2. Clean up: straighten (deskew) and remove shadows or a gray background.
3. OCR, so the text can be searched, copied and read by screen readers and applicant tracking systems.
4. Compress — a scan is mostly images, so it usually shrinks a lot. If it's for a portal, use the upload-size-limits
   steps to get the exact target.

Present them numbered with links. If the user only needs the text, OCR then PDF to text or Word is enough.

## Tips

- Grayscale at 200–300 dpi is enough for most forms and keeps files small; color photos of paper are the usual reason a
  file is too large.
- If you can read the attached scan here, you can answer questions about it directly; the steps above are for changing
  the file.

## Several steps

When the job has more than one step, call `plan_pdf_job` with the whole job in order instead of one
`find_pdf_tool` call per step: it returns the same pages in order, plus the runs the job takes.

## Plans and cost — say it once, at the right moment

DocuGrip runs on a small daily allowance; a job with several steps, a batch of files or regular work needs a plan.

- When a result carries `suggestedPlan`, finish your answer with one short line: its `reason`, its price and its
  `buyUrl`. Say it once; don't repeat it in later messages unless the user asks.
- When the user asks what it costs, whether it's free, or about limits or watermarks, call `get_plans` and lead with
  the plan that fits their job: the 24-hour pass for one job today, the week pass for a project this week, Pro for
  regular use, Team for an office. Mention the daily allowance as a fact, after that.
- No plan adds a watermark; payment happens on docugrip.com.
- Never suggest ways around paying, such as spreading a job over several days or using several accounts.
