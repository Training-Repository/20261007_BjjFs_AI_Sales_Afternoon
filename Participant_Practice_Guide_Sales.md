# Meta Prompting Guide — Sales Team
### Microsoft 365 Copilot Training | Bajaj Finance Limited
**Participant Handout | Dataset: `Sales_Copilot_Training_Dataset.xlsx`**

---

## What You'll Practice Today

Five everyday Sales tasks, powered by Copilot:

| # | Exercise | Dataset Sheet |
|---|----------|---------------|
| 1 | Customer Profile Analysis | Customer Profiles |
| 2 | Lead Prioritization | Lead Pipeline |
| 3 | Sales Proposal Preparation | Proposal Tracker |
| 4 | Customer Communication | Communication Log |
| 5 | Sales Reporting | Sales Performance |

---

## The RTCFT Framework

Every great prompt has five parts:

| Element | Ask Yourself | Example |
|---------|--------------|---------|
| **R — Role** | Who should Copilot act as? | "Act as a senior sales analyst at an NBFC" |
| **T — Task** | What exactly do I want done? | "Rank my top 5 leads for this week" |
| **C — Context** | What background does it need? | "Use the attached Lead Pipeline sheet; June closing is on" |
| **F — Format** | How should the answer look? | "A table with Lead, Value, Stage, Next Step" |
| **T — Tone** | What voice should it use? | "Crisp and action-oriented" |

**The shortcut — Meta Prompting:** instead of writing RTCFT prompts yourself, describe your situation in plain words and ask Copilot to *write the prompt for you*. That generated prompt is your **Working Prompt**.

---

## The 3-Step Rhythm (use in every exercise)

1. **Paste the Meta Prompt** into Copilot Chat → Copilot gives you a Working Prompt.
2. **Attach the dataset**: type `/` in Copilot Chat → select `Sales_Copilot_Training_Dataset.xlsx` → paste and run the Working Prompt.
3. **Refine**: ask follow-ups to change the format, audience, or tone.

---

## Exercise 1 — Customer Profile Analysis
**Sheet: `Customer Profiles`**

You manage 15 customers. Find out who they are and where your next sale is hiding.

**Meta Prompt — copy and paste:**

```
I am a Relationship Manager at Bajaj Finance. I have an Excel sheet called "Customer Profiles" with columns: Customer ID, Customer Name, Age, City, Occupation, Segment, Annual Income (₹ Lakh), Products Held, Relationship Tenure (Yrs), Credit Score, Avg Monthly Balance (₹), Last Interaction, Cross-Sell Potential, and Remarks.

Write a detailed working prompt for Microsoft 365 Copilot using the RTCFT framework (Role, Task, Context, Format, Tone) that I can use to analyse my customer base — segment-wise profile summary, top cross-sell opportunities with the recommended product for each customer, and any relationship risks I should act on. Give me only the working prompt, ready to use.
```

**What to do next:**
1. Read the Working Prompt Copilot generates — spot the R, T, C, F, T inside it.
2. Type `/`, attach the dataset, and run the Working Prompt.
3. Check the cross-sell table — do the recommendations match what the Remarks column says?

**Try this yourself:** Ask Copilot — *"Now rewrite this as talking points for my Monday huddle with my ASM."*

---

## Exercise 2 — Lead Prioritization
**Sheet: `Lead Pipeline`**

15 active leads, one week, limited time. Decide who gets called first.

**Meta Prompt — copy and paste:**

```
I am an Area Sales Manager at Bajaj Finance. I have an Excel sheet called "Lead Pipeline" with columns: Lead ID, Lead Name, City, Source, Product Interest, Requested Amount (₹ Lakh), Lead Score (0-100), Stage, Assigned RM, Days in Pipeline, Expected Close, Priority, and Next Step.

Write a working prompt for Microsoft 365 Copilot using the RTCFT framework that helps me prioritize this pipeline for the current week — ranking leads by closure probability and value, flagging stuck or ageing leads, and giving each RM a clear action list. Give me only the working prompt.
```

**What to do next:**
1. Run the Meta Prompt, then attach the file and run the Working Prompt.
2. Look at the ranking — notice how Copilot balances deal *value* against *closure probability*.
3. Find the leads flagged as stuck or ageing. Do you agree?

**Try this yourself:** *"Which of these leads will most likely miss their expected close date, and why?"*

---

## Exercise 3 — Sales Proposal Preparation
**Sheet: `Proposal Tracker`**

Build a client-ready proposal — and learn from your won and lost deals.

**Meta Prompt — copy and paste:**

```
I am a Relationship Manager at Bajaj Finance. I have an Excel sheet called "Proposal Tracker" with columns: Proposal ID, Customer / Lead, Product, Proposed Amount (₹ Lakh), Offered ROI (%), Tenure (Months), Processing Fee (%), Submitted On, Decision Due, RM, Stage, Status, and Key Notes.

Write a working prompt for Microsoft 365 Copilot using the RTCFT framework that drafts a professional sales proposal for one open deal of my choice — covering the offer summary, key terms, customer-specific benefits, objection handling based on the notes, and a clear call to action — and also tells me what the won and lost deals in this sheet teach me about pricing. Give me only the working prompt.
```

**What to do next:**
1. Run the Working Prompt with the file attached. Pick an open deal — try **PRP-104 (Sterling Pharma)**.
2. Check how the proposal handles the CFO's rate request from the Key Notes column.
3. Read the won/lost analysis — what did the Kamal Jewellers deal teach the team?

**Try this yourself:** *"Shorten the proposal to a WhatsApp-friendly summary the CFO can read in 30 seconds."*

---

## Exercise 4 — Customer Communication
**Sheet: `Communication Log`**

Clear your follow-up backlog with personalised, channel-matched drafts.

**Meta Prompt — copy and paste:**

```
I am a Relationship Manager at Bajaj Finance. I have an Excel sheet called "Communication Log" with columns: Comm ID, Customer / Lead, RM, Channel, Type, Last Contact, Next Action Due, Response Status, Days Since Last Contact, and Summary of Last Interaction.

Write a working prompt for Microsoft 365 Copilot using the RTCFT framework that reviews my pending communications, tells me which follow-ups are overdue or most urgent, and drafts personalised follow-up messages (matching the right channel — call script, WhatsApp, or email) for my top 3 priority customers. Give me only the working prompt.
```

**What to do next:**
1. Run both steps with the file attached.
2. Notice each draft refers to the *last interaction* — that's what makes it feel personal, not templated.
3. **Important:** drafts are starting points. Always verify rates, fees, and product claims against approved terms before sending anything to a customer.

**Try this yourself:** *"Rewrite the WhatsApp message in Hinglish, keeping it professional."*

---

## Exercise 5 — Sales Reporting
**Sheet: `Sales Performance`**

Turn two months of raw numbers into a management-ready report in one prompt.

**Meta Prompt — copy and paste:**

```
I am a Regional Sales Head at Bajaj Finance. I have an Excel sheet called "Sales Performance" with columns: Month, RM Name, Region, Product, Target (₹ Lakh), Achieved (₹ Lakh), Achievement %, Leads Assigned, Conversions, Conversion %, Avg Ticket Size (₹ Lakh), and Remarks.

Write a working prompt for Microsoft 365 Copilot using the RTCFT framework that builds a management-ready sales performance report for Apr–May 2026 — overall achievement, RM-wise and product-wise performance, best and weakest areas with reasons from the remarks, and 3 recommendations for June. Give me only the working prompt.
```

**What to do next:**
1. Run the Working Prompt with the file attached.
2. Cross-check one number in the report against the sheet — always verify before it goes to management.
3. See how the Remarks column became the "reasons" in the report.

**Try this yourself:** *"Turn this into 5 bullet points for a leadership WhatsApp group."* Then: *"Now make it a slide outline for the monthly business review."*

---

## Build Your Own Meta Prompt

Use this fill-in-the-blank template for any sheet you own:

```
I am a [your role] at Bajaj Finance. I have an Excel sheet called "[sheet name]" with columns: [list your columns].

Write a working prompt for Microsoft 365 Copilot using the RTCFT framework that [describe what you want — analysis, ranking, draft, report] for [audience]. Give me only the working prompt.
```

---

## Golden Rules

1. **Verify before you forward** — every number in a Copilot report must match the source sheet.
2. **Review before you send** — AI-drafted customer messages need your eyes on rates, fees, and claims.
3. **Protect customer data** — never paste real customer PII into unapproved tools; use only sanctioned environments.
4. **Iterate** — your first output is a draft; the refinement prompts are where the magic happens.

---

## My Notes

_Use this space for prompts and ideas you want to try with your own data:_

-
-
-

---

*Technizer Edge | Microsoft 365 Copilot Training Programme | Bajaj Finance Limited — Sales Team*
*Training dataset is fictional and created solely for instructional use.*
