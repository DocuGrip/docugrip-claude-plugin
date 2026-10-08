---
name: sign-and-send
description: Use when the user needs to sign a PDF themselves, get someone else's signature, collect signatures from several people in order, add initials or a date, fill and sign a form, send a contract or agreement for e-signature, or check who has signed.
---

# Sign or collect signatures

## Steps

1. Decide which job it is:
   - **The user signs** a PDF they have → `find_pdf_tool("sign a PDF")`.
   - **Other people sign** → `find_pdf_tool("request signatures from other people")`. Signature requests send each
     signer a personal link, can set a signing order and keep a record of who opened and signed.
   - A **form** that needs filling and signing → `find_official_form` if it's an official form, otherwise
     `find_pdf_tool("fill a PDF form")`.
2. Give the link and one sentence on what happens next.
3. If the user asks what it costs, call `get_plans`.

## Be accurate about what it is

DocuGrip signature requests are electronic signatures with an activity record. They are not qualified or certified
digital signatures and don't verify identity beyond each signer's email link. If the user needs a qualified signature
(some EU and government processes do), say so.
