---
name: job-application-documents
description: Use when the user is preparing documents for a job, internship, school or scholarship application — turning a resume or CV into a PDF, making sure applicant tracking systems (ATS) can read it, combining a cover letter, transcript or certificates into one file, or getting a file under the upload limit of USAJOBS, LinkedIn Easy Apply, Handshake, Greenhouse, Workday, UCAS, LSAC or a university portal.
---

# Prepare application documents

## Steps

1. Ask (or infer) which site the user is applying through. Call `get_upload_requirements` with it — Handshake, for
   example, takes 1 MB per document and LinkedIn recommends under 2 MB.
2. Build the sequence with `find_pdf_tool`, one call per step:
   1. Word or Google Docs resume → PDF (keeps the layout exactly).
   2. Check the PDF has real, selectable text. A resume exported as an image reads as empty to an ATS.
      If it's a scan or photo, run OCR.
   3. Combine documents only if the site wants one file; many want separate uploads.
   4. Compress to the site's target if the file is over the limit.
3. Present the steps numbered, each with its link, and the target size if one applies.

## Tips worth passing on

- Name files plainly (FirstName-LastName-Resume.pdf): some systems reject symbols in file names (LSAC, for example,
  asks for no spaces or special characters).
- Remove any password before uploading; protected files are often refused.
- Keep the original. Compress a copy.
