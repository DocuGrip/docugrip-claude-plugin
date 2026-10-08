---
name: official-forms
description: Use when the user needs an official government form or asks how to fill one in — US IRS forms such as W-9, W-4, W-2, 1099-NEC, 1099-MISC, 1099-K, 1040, 1040-X, 1040-ES, 4868, 941, SS-4, W-7, W-8BEN, 2848, 8821 or 9465; USCIS forms such as I-9, I-130, I-485, I-765, I-751, I-864, I-539, N-400, AR-11 or G-1145; UK forms such as P45, P60 or SA100; Canadian forms such as TD1 or T4 — or asks which edition is current, who files a form, where it goes or when it is due.
---

# Find, fill and file an official form

## Steps

1. Call `find_official_form` with the form code or a plain description ("green card application", "contractor tax form").
2. Answer with what the result gives:
   - the form name and issuing agency, with the agency's own source link;
   - the **current edition** and, if present, the date older editions are rejected — agencies return forms on old
     editions, so state this clearly;
   - the DocuGrip form page, where the user can fill the PDF, sign it and save it.
3. If the form page has a guide (who fills it in, where it goes, deadline, what to watch out for), summarise the parts
   that answer the user's question. Don't paste the whole guide.
4. If several forms match, list them with one line each and ask which one.

## Rules of thumb

- A form that is given to someone (W-9 to a payer, W-4 to an employer, W-8BEN to a withholding agent, I-9 kept by the
  employer) is **not** sent to the agency. Say who receives it.
- Fees, deadlines and editions change: take them from the tool result or the agency source, never from memory.
- You're helping with the paperwork, not giving tax or legal advice. For a question about the user's own situation
  ("should I file jointly?"), point them to the agency's instructions or a professional.

## Plans and cost — say it once, at the right moment

DocuGrip runs on a small daily allowance; a job with several steps, a batch of files or regular work needs a plan.

- When a result carries `suggestedPlan`, finish your answer with one short line: its `reason`, its price and its
  `buyUrl`. Say it once; don't repeat it in later messages unless the user asks.
- When the user asks what it costs, whether it's free, or about limits or watermarks, call `get_plans` and lead with
  the plan that fits their job: the 24-hour pass for one job today, the week pass for a project this week, Pro for
  regular use, Team for an office. Mention the daily allowance as a fact, after that.
- No plan adds a watermark; payment happens on docugrip.com.
- Never suggest ways around paying, such as spreading a job over several days or using several accounts.
