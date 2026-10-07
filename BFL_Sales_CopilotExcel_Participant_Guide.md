# Copilot in Excel — Participant Exercise Guide
### Formulas & Pivot Tables for the Sales Team
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `BFL_Sales_Copilot_Demo.xlsx`

---

## Before You Begin

- Use **Copilot agent** to open the agent in the Copilot panel
- Add `BFL_Sales_Copilot_Demo.xlsx` from OneDrive
- Keep the Copilot panel open throughout all exercises
- The file has **25 rows of sales pipeline data** — one sheet, no formula columns yet
- Columns N–Q are intentionally blank — you will fill these using Copilot

### Dataset Overview

Each row is a **sales lead** — a financing or cross-sell opportunity raised by a sales team and worked to conversion by a Relationship Manager, against a committed response/conversion SLA.

| Column | Field | Description |
|--------|-------|-------------|
| A | Lead ID | Unique lead reference (SAL-001 to SAL-025) |
| B | Sales Team | Sales vertical that owns the lead |
| C | Team Code | Short team identifier |
| D | Region | West / Central |
| E | Product | Consumer Durable Loan, Personal Loan, Business Loan, Credit Card, Insurance |
| F | Sales RM | Relationship Manager working the lead |
| G | Lead Date | When the lead was created |
| H | Closed Date | When it converted / closed (blank if still open) |
| I | Days to Close | Actual days from lead to conversion |
| J | SLA (Days) | Committed conversion SLA for that product |
| K | Deal Size | ≤ ₹1L, ₹1–5L, ₹5–25L, ₹25L–1Cr, > ₹1Cr |
| L | Priority | Normal, High, Urgent *(Urgent = hot lead)* |
| M | Status | Converted, In Progress, Escalated |
| **N–Q** | *(blank)* | **You will add these using Copilot** |

---

## Exercise 1 — Add a Formula Column: Escalation Flag

### Your Turn
Type into the Copilot panel:

```
In column N, add a formula that flags each lead as "Escalate" or "OK"
based on its Priority and Status:
- "Escalate" if Priority is "Urgent" OR Status is "Escalated"
- "OK" for all other cases
Label the column "Escalation Flag". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(OR(L3="Urgent",M3="Escalated"),"Escalate","OK")
```
Copilot will name the column, write the formula, and fill it down to N27.

> **Discussion Point:** Which products and deal sizes attract a hot (Urgent) or Escalated status? Are the high-value leads (> ₹1Cr) getting the fast RM attention they deserve before they go cold?

---

## Exercise 2 — Add a Formula Column: SLA Breach

### Your Turn
Type into the Copilot panel:

```
In column O, add a formula that checks whether each lead breached its
conversion SLA. Compare the Days to Close in column I against the SLA in
column J. If Days to Close is greater than the SLA, return "Breach".
Otherwise return "On Time". If Days to Close is blank (lead still open),
return "In Progress".
Label the column "SLA Breach". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(I3="","In Progress",IF(I3>J3,"Breach","On Time"))
```

> **Discussion Point:** Business Loans show the most SLA breaches by a wide margin. What upstream factors — document collection, credit assessment, sanction turnaround — slow down large-ticket conversions and let leads drift past SLA?

---

## Exercise 3 — Add a Formula Column: Lead Ageing

### Your Turn
Type into the Copilot panel:

```
In column P, calculate the number of days each lead has been open. If
the lead has already closed (column H has a date), return 0. If it is
still open, return the number of days since the lead was created
(column G) up to today.
Label the column "Lead Ageing (Days)". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(H3<>"",0,TODAY()-DATEVALUE(G3))
```
Closed leads show 0. Open leads show how many days they have been ageing in the pipeline.

> **Discussion Point:** Which open leads are ageing the most? Are the stale leads clustered under a particular RM, sales team, or product — and are any of them hot or high-value leads at risk of going cold?

---

## Exercise 4 — Add a Formula Column: Conversion Speed

### Your Turn
Type into the Copilot panel:

```
In column Q, classify each closed lead into a conversion-speed category
based on how the actual Days to Close (column I) compares to the SLA
(column J):
- "Fast" if Days to Close is 50% or less of the SLA
- "Within SLA" if Days to Close is within the SLA
- "Moderate Breach" if Days to Close exceeds SLA by up to 50%
- "Critical Breach" if Days to Close exceeds SLA by more than 50%
- "In Progress" if Days to Close is blank
Label the column "Conversion Speed". Apply to all 25 rows.
```

### What Copilot Will Produce
```excel
=IF(I3="","In Progress",IF(I3<=J3*0.5,"Fast",IF(I3<=J3,"Within SLA",IF(I3<=J3*1.5,"Moderate Breach","Critical Breach"))))
```

---

## Exercise 5 — Ask Copilot to Explain a Formula

### Your Turn
Copy the formula from cell **Q3** and paste it into the Copilot panel:

```
Explain this formula to me in simple terms. What does each part do?
```

### What Copilot Will Explain
> *"This formula first checks if the Days to Close in I3 is blank — if so, the lead is still In Progress. Then it checks if Days to Close is at most half the SLA, which means the RM converted it very Fast. Next it checks if it is within the full SLA — that's Within SLA. If it went over the SLA but not by more than 50%, it's a Moderate Breach. Anything beyond 150% of the SLA is a Critical Breach. Each IF only runs when the previous condition wasn't true."*

---

## Exercise 6 — Create a Pivot Table: Leads by Product and Status

### Your Turn
Type into the Copilot panel:

```
Create a pivot table that shows the count of leads for each Product,
broken down by Status (Converted, In Progress, Escalated). I want to see
which products have the most unconverted or escalated leads.
```

### What Copilot Will Produce
A new sheet with a Pivot Table:
- **Rows:** Product (Consumer Durable Loan, Personal Loan, Business Loan, Credit Card, Insurance)
- **Columns:** Status (Converted, In Progress, Escalated)
- **Values:** Count of Lead ID

> **Discussion Point:** Insurance carries a high escalated-plus-open ratio relative to its volume (only 1 of 4 converted). What does that signal about how cross-sell leads are being followed up versus simply logged and left?

---

## Exercise 7 — Create a Pivot Table: Average Days to Close by RM

### Your Turn
Type into the Copilot panel:

```
Now create a pivot table showing the average Days to Close for each
Sales RM, broken down by Product. I want to identify which RMs or
products are taking the longest to convert.
```

### What Copilot Will Produce
- **Rows:** Sales RM (Pooja Nair, Rahul Sharma, Anita Desai, Vikram Joshi, Ravi Kumar)
- **Columns:** Product
- **Values:** Average of Days to Close

> **Discussion Point:** Anita Desai carries the highest overall average time-to-close (9.5 days), driven by a single > ₹1Cr Business Loan that ran to 16 days. Is that a capacity issue, a large-deal sanction issue, or a lead-quality issue — and which product consistently breaches SLA across multiple RMs?

---

## Exercise 8 — Bonus: Ask Copilot for Insights

### Your Turn
Type into the Copilot panel:

```
Look at the data in this sheet. Which sales teams have the most SLA
breaches? Summarise the key pipeline-risk areas for the sales team in
3 bullet points.
```

### What to Expect
Copilot will scan the data and generate a natural-language summary — no formula needed. This shows how Copilot moves from *calculation* to *analysis* to *insight* within the same Excel session.

---

## Reference: What Your Pivots Should Show

Once you've built the pivots in Exercises 6–7, sanity-check them against these figures:

- **25 leads total** — 18 Converted, 5 In Progress, 2 Escalated
- **Business Loans** are the highest-volume product (7) and the largest source of SLA breaches (6 of 10 total breaches)
- **Insurance** shows the weakest conversion profile — only 1 of 4 converted, the rest open or escalated
- **10 SLA breaches** in total: 8 in West, 2 in Central

*(Trainers: the full pre-built pivot answer key is available separately, so the participant file stays clean for the exercises.)*

---

*Bajaj Finance Limited | AI Academy — Sales | Microsoft Copilot Training Programme*
