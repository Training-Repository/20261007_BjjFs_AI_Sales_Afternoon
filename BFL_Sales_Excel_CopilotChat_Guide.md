# Excel with Copilot Chat — No Agent Required
### Formulas & Pivot Tables for the Sales Team, using Copilot Chat + Meta-Prompting
**Bajaj Finance Limited | M365 Copilot Training**
**File:** `BFL_Sales_Copilot_Demo.xlsx`
**Companion guides:** `MetaPrompting_Guide_Sales.md` · `Participant_Practice_Guide_Sales.md` · `BFL_Sales_CopilotExcel_Participant_Guide.md` (Agent version)

---

## Who This Guide Is For

`BFL_Sales_CopilotExcel_Participant_Guide.md` uses **Edit with Copilot** in Excel, which used to be called Agent Mode. In that mode Copilot writes formulas into your cells and builds pivot tables for you, and it needs a **paid Microsoft 365 Copilot licence**.

This guide produces **the same eight results** with **Copilot Chat only**:

- **Copilot does the thinking.** It writes the formula, explains the logic and gives you the pivot layout.
- **You do the clicking.** You paste the formula and build the pivot in Excel yourself, which takes about 30 seconds per exercise.

### Which one do you have?

Check the label on Copilot in the Microsoft 365 app or in Excel:

| Label you see | What works for you |
|---|---|
| **Microsoft 365 Copilot (Premium / Pro)** | Either guide. The Agent guide is faster. |
| **Microsoft 365 Copilot (Basic)** | **This guide.** You can run the prompts in Copilot Chat **or** in the Copilot pane inside Excel, but Copilot will not edit the workbook for you. |
| **Copilot Chat (Basic)** | **This guide**, using Copilot Chat in the M365 Copilot app or at `m365copilot.com`. |

---

## How Every Exercise Works

```
Step 1 → Paste the Excel Meta Prompt with that exercise's TASK filled in
Step 2 → Read the Working Prompt Copilot generates
Step 3 → Attach BFL_Sales_Copilot_Demo.xlsx and run the Working Prompt
Step 4 → Apply Copilot's answer in Excel yourself (paste formula / build pivot)
Step 5 → Verify against the expected numbers in this guide
```

> 💡 **Why Step 5 matters:** without an agent, nobody checks the result but you. The expected numbers below let you spot a wrong formula in seconds.

---

## Before You Begin

1. Open `BFL_Sales_Copilot_Demo.xlsx` in **Excel** (desktop or web) and go to the **Sales Pipeline Data** sheet.
2. Open **Copilot Chat** in a second window, either the M365 Copilot app or `m365copilot.com`.
3. Keep both windows side by side.

### What's in the file

- Row 1 is a title and **row 2 holds the headers**. **Data runs in rows 3–27** (25 leads, SAL-001 to SAL-025). Row 28 is a note.
- Columns **N–Q already have headers** (`➕ Escalation Flag`, `➕ SLA Breach`, `➕ Lead Ageing (Days)`, `➕ Conversion Speed`) and empty cells below them. You will fill those cells.
- ⚠️ **Lead Date (G) and Closed Date (H) are stored as text**, for example `1 Jun 2026`, not as real Excel dates. This matters in Exercise 3.
- The workbook has this one sheet only. There are no ready-made pivot sheets, so **build your pivots on a new sheet** and check them against the expected results in this guide.

| Column | Field | Column | Field |
|---|---|---|---|
| A | Lead ID | H | Closed Date *(blank if open)* |
| B | Sales Team | I | Days to Close *(blank if open)* |
| C | Team Code | J | SLA (Days) |
| D | Region *(West / Central)* | K | Deal Size |
| E | Product | L | Priority (Normal / High / Urgent) |
| F | Sales RM | M | Status (Converted / In Progress / Escalated) |
| G | Lead Date | N–Q | **You fill these** |

---

## ⚡ The Excel Meta Prompt — Your Starting Point

This follows the RTCFT pattern from `Participant_Practice_Guide_Sales.md`, adapted for Excel. The file layout is already filled in, so for each exercise you only replace **[TASK]**.

```
Act as a Microsoft Copilot prompt expert specialising in Excel for sales pipeline analysis.

Role:    I am a Sales Analyst at Bajaj Finance Limited. I use Copilot Chat,
         which cannot edit my workbook — I will apply the result in Excel myself.
Task:    I need to: [TASK]
Context: Sheet "Sales Pipeline Data" in BFL_Sales_Copilot_Demo.xlsx.
         Headers are in row 2; data is in rows 3 to 27 (25 leads).
         Columns: A Lead ID, B Sales Team, D Region, E Product, F Sales RM,
         G Lead Date, H Closed Date, I Days to Close, J SLA (Days), K Deal Size,
         L Priority, M Status.
         Dates in G and H are stored as TEXT like "1 Jun 2026". Open leads have blank H and I.
Format:  The prompt must ask Copilot for:
         1. The exact result (formula for row 3, or pivot/table layout) ready to copy
         2. Step-by-step instructions to apply it manually in Excel
         3. How to handle blanks and text dates
         4. A quick way to verify the result is correct
Tone:    Clear and step-by-step, for a sales user who is not an Excel expert.

Write me a detailed, ready-to-use Copilot prompt I can use in Copilot Chat with this file attached.
```

> ✏️ **Short on time?** Once you've done this for Exercise 1, you can reuse the Working Prompt Copilot gave you and swap in the new task for the later exercises.

---

---

# Exercise 1 — Formula Column: Escalation Flag (N)
**Time:** ~8 minutes

### Step 1 — [TASK] to paste into the Meta Prompt
```
write a formula for column N ("Escalation Flag") that returns "Escalate" if Priority (L) is
"Urgent" OR Status (M) is "Escalated", otherwise "OK", for rows 3 to 27
```

### Step 2 — Check the Working Prompt
- [ ] Does it mention row 3 and filling down to row 27?
- [ ] Does it ask for manual steps and a verification check?

### Step 3 — Attach the file and run
Attach `BFL_Sales_Copilot_Demo.xlsx` → paste the Working Prompt → send.

### Step 4 — Apply in Excel
1. Click **N3** and paste the formula Copilot gave you.
2. Fill it down to **N27**: select **N3:N27** and press **Ctrl + D**, or double-click the fill handle at the bottom-right corner of N3.

### Step 5 — Verify
Type this in any empty cell, such as **T3**:
```excel
=COUNTIF(N3:N27,"Escalate")
```
**Expected: 6** (SAL-005, 006, 010, 016, 017, 021). The other 19 rows show **OK**.

<details><summary>Reference formula (open only if stuck)</summary>

```excel
=IF(OR(L3="Urgent",M3="Escalated"),"Escalate","OK")
```
</details>

> **Discussion Point:** Which products and deal sizes attract a hot (Urgent) or Escalated status? Four of the six flagged leads are Business Loans. Are the high-value leads (> ₹1Cr) getting the fast RM attention they need before they go cold?

---

# Exercise 2 — Formula Column: SLA Breach (O)
**Time:** ~6 minutes

### Step 1 — [TASK]
```
write a formula for column O ("SLA Breach") that returns "In Progress" if Days to Close (I) is
blank, "Breach" if Days to Close is greater than SLA (J), otherwise "On Time", for rows 3 to 27
```

### Steps 2–4
Same as Exercise 1, but paste in **O3** and fill down to **O27**.

### Step 5 — Verify
```excel
=COUNTIF(O3:O27,"Breach")
```
**Expected: 10 Breach · 8 On Time · 7 In Progress.**
- **Why 7 In Progress when column M shows only 5?** The 2 Escalated leads are also still open, so their Days to Close is blank too.
- **West has 8 of the 10 breaches** and Central has 2.

<details><summary>Reference formula</summary>

```excel
=IF(I3="","In Progress",IF(I3>J3,"Breach","On Time"))
```
</details>

> **Try this:** ask Copilot, *"What happens if I don't check for the blank first?"* A blank cell counts as 0, so every open lead would wrongly show "On Time".

> **Discussion Point:** Business Loans account for 6 of the 10 breaches. What slows large-ticket conversions: document collection, credit assessment or sanction turnaround?

---

# Exercise 3 — Formula Column: Lead Ageing (P) ⚠️ the text-date trap
**Time:** ~10 minutes

### Step 1 — [TASK]
```
write a formula for column P ("Lead Ageing (Days)") that returns 0 if the lead is closed
(Closed Date H is not blank), otherwise the number of days from the Lead Date (G) to today.
Remember G is stored as text like "1 Jun 2026". Rows 3 to 27.
```

### Steps 2–4
Paste in **P3** and fill down to **P27**.

### Step 5 — Verify
- **18 rows show 0**, one for each closed lead.
- **7 rows show a number of days**: SAL-003, 006, 008, 011, 017, 019, 023.
  - On 7 Oct 2026, those values are 127, 131, 126, 133, 126, 127 and 128 days, in that order.
  - They go up by one each day, because the formula uses `TODAY()`.

### ❗ If you see `#VALUE!` on the open rows
Your Excel could not read the text date. This depends on your regional settings. Tell Copilot:
```
The formula returns #VALUE! for open rows because DATEVALUE cannot read "1 Jun 2026" in my
regional settings. Give me a version that builds the date from the text without DATEVALUE.
```

<details><summary>Reference formulas</summary>

Try this first. It works in most English regional settings:
```excel
=IF(H3<>"",0,TODAY()-DATEVALUE(G3))
```
This version works in any regional setting:
```excel
=IF(H3<>"",0,TODAY()-DATE(RIGHT(G3,4),MATCH(MID(G3,FIND(" ",G3)+1,3),{"Jan","Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec"},0),LEFT(G3,FIND(" ",G3)-1)))
```
If the result shows as a date instead of a number, set the column format to **Number**.
</details>

> **Lesson:** Copilot's first formula is a *draft*. When a formula errors, don't fix it by hand. Paste the error back into Copilot Chat along with the reason.

> **Discussion Point:** Which open leads have waited the longest? Three of the seven belong to Anita Desai and four to Pooja Nair. Are the stale leads clustered under a particular RM, sales team or product, and are any of them hot or high-value leads at risk of going cold?

---

# Exercise 4 — Formula Column: Conversion Speed (Q)
**Time:** ~6 minutes

### Step 1 — [TASK]
```
write a formula for column Q ("Conversion Speed") that returns: "In Progress" if Days to Close (I)
is blank; "Fast" if Days to Close is 50% or less of SLA (J); "Within SLA" if Days to Close is
within the SLA; "Moderate Breach" if it exceeds SLA by up to 50%; "Critical Breach" if more
than 50%. Rows 3 to 27.
```

### Steps 2–4
Paste in **Q3** and fill down to **Q27**.

### Step 5 — Verify
**Expected: 8 Within SLA · 5 Moderate Breach · 5 Critical Breach · 7 In Progress · 0 Fast.**
- **Moderate Breach:** SAL-002, 004, 009, 010, 024.
- **Critical Breach:** SAL-005, 013, 016, 020, 021.

> 💡 **Zero "Fast" is correct.** No lead converted in half its SLA or less. An empty category doesn't mean the formula is wrong, so always check against the data.

<details><summary>Reference formula</summary>

```excel
=IF(I3="","In Progress",IF(I3<=J3*0.5,"Fast",IF(I3<=J3,"Within SLA",IF(I3<=J3*1.5,"Moderate Breach","Critical Breach"))))
```
</details>

> **Bonus prompt:** *"Rewrite this using IFS instead of nested IFs."* Which version would you rather hand over to a colleague to maintain?

---

# Exercise 5 — Ask Copilot to Explain a Formula
**Time:** ~3 minutes

This works exactly as it does in the Agent version. No meta prompt or attachment is needed.

Copy the formula from **Q3** and paste it into Copilot Chat:
```
Explain this Excel formula in simple terms for a sales user. What does each part
do, and in what order are the conditions checked?
[paste formula here]
```

**What to look for:**
- The explanation should state that the conditions are checked **in order**.
- Each `IF` only runs if the one before it was not true.

> 💡 **Try it on your own tracker:** paste the ugliest formula from your live sheet and ask the same question. It is the most useful habit from this session.

---

# Exercise 6 — Pivot Table: Leads by Product and Status
**Time:** ~8 minutes

### Step 1 — [TASK]
```
design a pivot table showing the count of leads for each Product (rows) broken down by
Status (columns: Converted, In Progress, Escalated). Give me the exact field placement and
click-by-click steps to build it in Excel, plus the expected result table so I can check my pivot.
```

### Steps 2–3
Run the Working Prompt with the file attached, as before.

### Step 4 — Build it in Excel
1. On **Sales Pipeline Data**, select **A2:Q27** exactly. Don't include the title in row 1 or the note in row 28.
2. Go to **Insert → PivotTable → New Worksheet → OK**.
3. Place the fields:
   - **Product** → Rows
   - **Status** → Columns
   - **Lead ID** → Values. It shows as *Count of Lead ID*.

### Step 5 — Verify

| Product | Converted | Escalated | In Progress | Total |
|---|---|---|---|---|
| Business Loan | 6 | 1 | | 7 |
| Consumer Durable Loan | 5 | | | 5 |
| Credit Card | 3 | | 1 | 4 |
| Insurance | 1 | 1 | 2 | 4 |
| Personal Loan | 3 | | 2 | 5 |
| **Grand Total** | **18** | **2** | **5** | **25** |

*Excel sorts rows and columns alphabetically by default, so your order may differ from the Agent guide.*

> 💡 **No pivot tables allowed on your machine?** Ask Copilot for a `COUNTIFS` grid instead. For example, `=COUNTIFS($E$3:$E$27,"Insurance",$M$3:$M$27,"Converted")` returns **1**.

> **Discussion Point:** Insurance has only 1 of 4 leads converted, with 2 still open and 1 escalated. What does that say about how cross-sell leads are followed up compared with how they are logged?

---

# Exercise 7 — Pivot Table: Average Days to Close by RM
**Time:** ~8 minutes

### Step 1 — [TASK]
```
design a pivot table showing the AVERAGE Days to Close for each Sales RM (rows) broken down by
Product (columns). Give me the field placement, click-by-click steps, how to switch the
value from Count to Average and show one decimal place, and the expected row totals.
```

### Step 4 — Build it in Excel
1. Select **A2:Q27** → **Insert → PivotTable → New Worksheet**.
2. Place the fields:
   - **Sales RM** → Rows
   - **Product** → Columns
   - **Days to Close** → Values
3. Excel may default the value to **Count** or **Sum**. To change it:
   - Click the value field → **Value Field Settings → Average → OK**.
   - In the same dialog, choose **Number Format → Number → 1 decimal place**.
   - Blank cells (open leads) are ignored in the average.

### Step 5 — Verify (Grand Total column)

| Sales RM | Average Days to Close | Closed leads |
|---|---|---|
| Anita Desai | 9.5 | 2 |
| Vikram Joshi | 8.0 | 4 |
| Pooja Nair | 7.3 | 4 |
| Rahul Sharma | 5.0 | 4 |
| Ravi Kumar | 5.0 | 4 |
| **Grand Total** | **6.7** | **18** |

*Pooja Nair's exact average is 7.25, which shows as 7.3 at one decimal place. The Grand Total is 6.67, which shows as 6.7.*

> 💡 **Average of all leads vs average of averages:** the Grand Total of 6.67 averages **every closed lead**. Averaging the five RM figures above gives 6.95 instead. Ask Copilot: *"What is the difference between an average of all leads and an average of averages?"*

> **Discussion Point:** Anita Desai has the highest average, 9.5 days, but it rests on only 2 closed leads: a 3-day Personal Loan and a 16-day Business Loan above ₹1Cr. How many leads does an average need before you act on it? Which product breaches SLA across several RMs?

> 💡 **Formula alternative:** `=AVERAGEIFS(I3:I27,F3:F27,"Rahul Sharma")` returns **5**.

---

# Exercise 8 — Bonus: Ask Copilot for Insights
**Time:** ~5 minutes

This works directly in Copilot Chat with the file attached. No manual steps are needed.

```
Look at the Sales Pipeline Data sheet in the attached file. Which sales teams have the most SLA
breaches (Days to Close greater than SLA)? Summarise the key pipeline-risk areas for the sales
team in 3 bullet points, quoting Lead IDs as evidence.
```

**Expected:**
- **SME Sales is the clear top**, with 3 breaches: SAL-002, 013 and 021, all Business Loans.
- **Telesales is next with 2** (SAL-004 and 020). Partnerships, Wealth Sales, Retail Sales, Rural Sales and Cross-Sell have 1 each.
- **6 of the 10 breaches** are Business Loans, and **8 of the 10** are in the **West** region.

> 💡 **Lesson:** check every Lead ID Copilot quotes against column O. A summary that sounds right can still cite a lead that did not breach.

---

## Reference: What Your Results Should Show

| Check | Expected |
|---|---|
| Total leads | 25: 18 Converted · 5 In Progress · 2 Escalated |
| Escalation Flag = Escalate | 6 |
| SLA Breach | 10 Breach (8 West, 2 Central) · 8 On Time · 7 In Progress |
| Business Loan | Highest volume (7), and 6 of the 10 breaches |
| Insurance | Weakest conversion: 1 of 4 converted |
| Conversion Speed | 8 Within SLA · 5 Moderate · 5 Critical · 7 In Progress · 0 Fast |
| Highest average Days to Close | Anita Desai, 9.5 days (2 closed leads) |
| Sales team with most breaches | SME Sales, 3 |

---

## Agent vs Copilot Chat — What Changes

| | Edit with Copilot (Agent) | Copilot Chat + Meta Prompt (this guide) |
|---|---|---|
| Licence | Microsoft 365 Copilot (paid) | Copilot Chat / Basic |
| Writes formula into cells | ✅ Automatic | ✍️ You paste and fill down |
| Builds pivot table | ✅ Automatic | ✍️ You build it using Copilot's layout |
| Explains formulas, gives insights | ✅ | ✅ Same |
| Handles errors | Agent retries | You paste the error back and ask for a fix |
| What you learn | Prompting | Prompting **plus** checking the formula logic yourself |

---

## ⚠️ Data Handling

This is a fictional training dataset, so it is safe to attach. In live work:

- Use Copilot Chat only when signed in with your BFL work account.
- Never paste customer PII, account numbers or PAN, or anything under compliance restriction.
- When in doubt, replace names with RM-1, RM-2 and share only the columns the question needs.

---

## Troubleshooting

| Problem | What to do |
|---|---|
| Formula refers to row 2 or the wrong column | Remind Copilot: *"Headers are row 2, data starts row 3."* |
| `#VALUE!` in Lead Ageing | This is the text-date issue. See Exercise 3. |
| `#NAME?` after pasting | Curly quotes crept in. Retype the `"` characters in Excel. |
| Pivot shows *Count* or *Sum* instead of *Average* | Change it in **Value Field Settings → Average**. |
| Pivot includes the title or the note text | Rebuild it from **A2:Q27** only. |
| Copilot answers from the wrong file | Name the file and sheet: *"Use only the Sales Pipeline Data sheet in BFL_Sales_Copilot_Demo.xlsx."* |
| Copilot says it can't open the file | Re-attach it from OneDrive, or paste the relevant rows as text. |

---

## Further Reading

- [Microsoft Copilot overview: Basic vs Premium experiences](https://learn.microsoft.com/en-us/copilot/overview)
- [Microsoft 365 Copilot overview: in-app features for Basic](https://learn.microsoft.com/en-us/microsoft-365/copilot/microsoft-365-copilot-overview)
- [Microsoft 365 Copilot release notes: Edit with Copilot in Excel](https://learn.microsoft.com/en-us/microsoft-365/copilot/release-notes)

---

*Bajaj Finance Limited | AI Academy — Sales | Microsoft Copilot Training Programme*
*Training delivered by **Technizer India***
