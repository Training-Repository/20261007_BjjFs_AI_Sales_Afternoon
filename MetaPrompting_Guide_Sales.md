# Meta-Prompting Guide — Sales
**Microsoft Copilot Training | Bajaj Finance Limited**

---

## What Is Meta-Prompting?

Instead of writing a prompt yourself, you ask Copilot to write the prompt for you — by telling it your role, your task, and what you need.

You are essentially saying:

> *"You are a prompt expert. You know how to talk to AI. Write me a prompt I can use for my actual work."*

The output becomes your **reference prompt** — something you refine and reuse across customer analysis, lead management, proposals, and sales reporting tasks.

---

## The Core Meta-Prompt Formula

```
Act as a Microsoft Copilot prompt expert.
I am a [YOUR ROLE] at [COMPANY/CONTEXT].
I need to [WHAT YOU WANT TO DO].
My audience is [WHO WILL READ THE OUTPUT].
Write me a detailed, structured Copilot prompt I can use to complete this task.
The prompt should specify: role, task, context, constraints, output format, and tone.
```

---

## Meta-Prompts for Sales — Bajaj Finance

Use these as your starting point. Copy, paste, and run in Copilot. Use the output as your working prompt for your exercises. Attach `Sales_Copilot_Training_Dataset.xlsx` (using `/` in Copilot Chat) when you run the working prompt.

---

### 1. Customer Profile Analysis

```
Act as a Microsoft Copilot prompt expert.
I am a Relationship Manager at Bajaj Finance Limited, an NBFC. I manage a portfolio of retail,
SME, and professional customers across loan, deposit, and card products. I need to analyse my
customer base from an attached Excel sheet ("Customer Profiles") — understanding customer
backgrounds by segment, identifying the top cross-sell opportunities with the right Bajaj Finance
product for each customer, and flagging relationship risks such as repayment concerns or low
engagement.

My audience is my Area Sales Manager and the Regional Sales Head, who will use this analysis to
plan the week's customer outreach and cross-sell focus.

Write me a detailed, structured Copilot prompt I can use to complete this customer profile
analysis. The prompt should specify: my role, the task, what to look for in each customer record
(income, products held, credit score, tenure, remarks), the exact output format (segment summary
table, cross-sell opportunity table with justification, risk flags with actions), and the
appropriate analytical, action-oriented tone.
```

---

### 2. Lead Prioritization

```
Act as a Microsoft Copilot prompt expert.
I am an Area Sales Manager at Bajaj Finance Limited. My team works a live pipeline of leads
across Business Loans, Personal Loans, Loan Against Property, and deposit products — sourced from
channel partners, branch walk-ins, the app, and referrals. I need to prioritize this pipeline from
an attached Excel sheet ("Lead Pipeline") — ranking leads by closure probability and value,
flagging stuck or ageing leads, and producing a clear RM-wise action list for the week.

My audience is my Relationship Managers (who need their daily call priorities) and the Regional
Sales Head (who needs a view of which deals will close this month).

Write me a Copilot prompt I can use to prioritize my lead pipeline. The prompt should tell Copilot
exactly how to weigh the data (lead score, requested amount, stage, days in pipeline, expected
close date), how to present it (ranked priority table + ageing/stuck lead flags + RM-wise action
list), and what tone to use (direct, operational, sales-huddle ready).
```

---

### 3. Sales Proposal Preparation

```
Act as a Microsoft Copilot prompt expert.
I am a Relationship Manager at Bajaj Finance Limited. I prepare structured sales proposals for
high-value customers and leads — covering loan amount, ROI, tenure, and processing fee — and I
negotiate against competing offers from other banks and NBFCs. I need to draft a client-ready
proposal for an open deal from an attached Excel sheet ("Proposal Tracker"), including offer
summary, key terms, customer-specific benefits, objection handling based on the deal notes, and a
clear call to action — and I also want to learn pricing lessons from the won and lost deals in
the same sheet.

My audience is two-fold: the customer's decision-maker (often a business owner or CFO) for the
proposal itself, and my own sales team for the internal pricing lessons.

Write me a detailed Copilot prompt I can use to prepare this proposal. The prompt should specify:
my role, the task, the proposal structure (Offer Summary, Key Terms, Why Bajaj Finance, Addressing
Your Ask, Next Steps), the internal won/lost analysis section, and the tone — professional and
confident for the client, candid for the internal note.
```

---

### 4. Customer Communication

```
Act as a Microsoft Copilot prompt expert.
I am a Relationship Manager at Bajaj Finance Limited. I handle ongoing follow-ups with customers
and leads across phone, WhatsApp, email, and branch meetings — proposal follow-ups, document
reminders, rate negotiations, renewal reminders, and onboarding assistance. I need to review my
pending communications from an attached Excel sheet ("Communication Log"), identify which
follow-ups are overdue or most urgent, and draft personalised follow-up messages for my top
priority customers — matched to the right channel and referencing the last interaction so they
feel personal, not templated.

My audience is the customers themselves — so every draft must be warm, professional, and
customer-first, with no pressure tactics, and must be reviewed against approved rates and terms
before sending.

Write me a Copilot prompt I can use to manage my follow-up communication. The prompt should
specify format (urgency-sorted follow-up list + channel-matched drafts: call script, WhatsApp
message, formal email), tone (warm, professional, customer-first), and how to use the last
interaction summary to personalise each draft.
```

---

### 5. Sales Reporting

```
Act as a Microsoft Copilot prompt expert.
I am a Regional Sales Head at Bajaj Finance Limited. I report monthly sales performance to the
National Sales Head and senior leadership — covering targets versus achievement, RM-wise and
product-wise performance, conversion rates, and the reasons behind wins and misses. I need to
produce a management-ready sales performance report for Apr–May 2026 from an attached Excel sheet
("Sales Performance"), including overall achievement, RM rankings, product trends, top wins and
concerns, and specific recommendations for the coming month.

My audience is the National Sales Head and the senior leadership team — who need a factual,
board-ready report with reasons and recommendations, not a verbatim restatement of the numbers.

Write me a Copilot prompt that will produce this sales performance report. The prompt should
specify format (headline summary + RM-wise ranked table + product-wise view + top 3 wins and
top 3 concerns + 3 data-backed recommendations), tone (factual, concise, management-ready), and
how to use the remarks column to explain the reasons behind over- and under-performance.
```

---

## Still Confused? Run This.

If the prompt Copilot wrote doesn't feel right — too generic, wrong format, wrong tone — don't rewrite it yourself. Use this follow-up prompt instead:

```
The prompt you wrote is a good start, but I need you to adjust it.
Here is what I want to change:

- [Describe what felt off — e.g., "the format doesn't match what my Regional Sales Head expects"]
- [Describe what's missing — e.g., "it doesn't tell Copilot to flag leads at risk of missing their close date"]
- [Describe the tone issue — e.g., "it sounds too generic — it needs to sound like an NBFC sales review, not a textbook"]

Please rewrite the prompt with these corrections.
Keep the same structure (Role / Task / Context / Format / Tone) but fix the parts I've described.
```

---

## What to Do With the Output

Once Copilot gives you a well-structured prompt:

1. **Read it** — does it reflect your actual sales role and BFL's product context?
2. **Replace the placeholders** — swap generic text with the specific sheet, customer, or deal you are working on.
3. **Run it** — attach `Sales_Copilot_Training_Dataset.xlsx` using `/` and use the generated prompt in Copilot Chat.
4. **Save it** — this is your reusable reference prompt for that sales task type.

---

*Bajaj Finance Limited | AI Academy — Sales | Microsoft Copilot Training Programme*
