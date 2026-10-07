# Copilot Notebooks — Participant Guide
### One workspace, all your files, no re-attaching
**Bajaj Finance Limited | M365 Copilot Training — Sales Team**
**Files used:** `Sales_Copilot_Training_Dataset.xlsx`, `BFL_Sales_Copilot_Demo.xlsx`, and the guides in this repo

---

## Why Notebooks?

In a normal Copilot Chat, every new conversation starts from zero. You attach the file again, explain your role again and restate the format you want again. You are also limited to **3 attachments per prompt**.

A **Copilot Notebook** is a saved workspace for one piece of work. You add your files to it once, as **references**, and write your standing instructions once. After that, every chat you start inside the notebook is grounded on those references, and it stays that way across sessions and days.

| | Regular Copilot Chat | Copilot Notebook |
|---|---|---|
| Files | Attached per prompt (max **3** in BFL) | Added once as **references**, then available to every chat in the notebook |
| Context | Lost when you open a new chat | Kept in the notebook across chats and days |
| Instructions (role, tone, format) | Re-typed in every prompt (the RTCFT block) | Set once in the notebook's **Copilot instructions** |
| Grounding | Your prompt + attachments (+ wider M365 / web, depending on settings) | **Only** the references you added, so answers stay focused on your files |
| Outputs | Chat replies | Chat replies, saved pages, and (where enabled) Word / PowerPoint drafts, mind maps, study guides |

> 💡 **Rule of thumb:** use one notebook per piece of work, such as the Q1 pipeline review, a monthly business review or one key-account plan. Don't create a new notebook for every question.

---

## ⭐ Going Beyond the 3-Attachment Limit

This is the most useful reason to use Notebooks at BFL.

- The 3-file limit applies to **attachments in a chat prompt**.
- Notebook **references** are added separately, through the notebook's *Add references* panel rather than the chat box. Copilot then grounds its answers on **all** of them together.
- According to Microsoft's documentation:
  - **Copilot Chat** users can add up to **50 references**, and all 50 are used for grounding.
  - **Microsoft 365 Copilot** (licensed) users can add more than 300 references. The first **300** are used for grounding.
- A **OneDrive or SharePoint folder** can be added as a single reference. Every file you put in that folder later is then available to the notebook without any extra steps.

**In practice:** you can ask one question that draws on customer profiles, leads, proposals, call logs, performance numbers and the pipeline SLA tracker at once, without attaching anything to the prompt.

> ⚠️ **Check in your own tenant:** the 3-attachment cap is BFL's setting for chat. If references in your notebook also appear capped, report it to your trainer or IT, because the admin policy may be set differently. Exercise 2 below is a simple way to test this.

---

## Before You Begin

- [ ] You can sign in to the **M365 Copilot** app (desktop or web) with your BFL work account, and you see **Notebooks** in the left navigation.
- [ ] You have copied the files from this repo to your **OneDrive** (a folder such as `OneDrive › Copilot-Training-Sales`).
- [ ] You have made `.txt` copies of the two Markdown guides. Notebooks accept `.docx, .pptx, .xlsx, .pdf, .loop, .page, .txt, .rtf` and OneNote pages, but **not `.md`**. Download the guides, then rename them:

| Original in repo | Rename to |
|---|---|
| `MetaPrompting_Guide_Sales.md` | `MetaPrompting_Guide_Sales.txt` |
| `Participant_Practice_Guide_Sales.md` | `Participant_Practice_Guide_Sales.txt` |

Your OneDrive folder should now contain **4 files**:

```
Copilot-Training-Sales/
├── Sales_Copilot_Training_Dataset.xlsx   (Customer Profiles, Lead Pipeline, Proposal Tracker,
│                                          Communication Log, Sales Performance)
├── BFL_Sales_Copilot_Demo.xlsx           (25 sales pipeline leads)
├── MetaPrompting_Guide_Sales.txt
└── Participant_Practice_Guide_Sales.txt
```

That is already **more than the 3-attachment limit**, which is intentional for these exercises.

---

# Exercise 1 — Create Your Notebook
**Time:** ~5 minutes

### Step 1 — Create it
1. In the M365 Copilot app, select **Notebooks** → **New notebook**.
2. Name it: `BFL Sales — Q1 FY26-27 Pipeline Review`

### Step 2 — Add references
1. Select **Add references** (at the top of the content pane in the Copilot app, or the **+** next to *References* in OneNote).
2. Choose **one** of these methods:
   - **Option A: files.** Select all 4 files from your OneDrive folder, or use **Upload** to add them from your computer.
   - **Option B: folder (recommended).** Select the `Copilot-Training-Sales` **folder** as a single reference.
3. Select **Add**.

> 💡 **Option B scales better.** When you drop next month's performance sheet into the folder, the notebook can use it without any extra step.

### Step 3 — Set the Copilot instructions (your RTCFT Role, Format and Tone, written once)
Open the notebook's **Copilot instructions** and paste:

```
I work in the Sales team at Bajaj Finance Limited (an NBFC), covering retail, SME and
professional customers across loan, deposit and card products.
The period is Q1 FY2026-27 (April–June 2026). Amounts are in ₹ Lakh unless a column says
otherwise. SLA and ageing are in days.

When you answer:
- Use only the references in this notebook. Name the file and sheet for every number you quote.
- If a number is not in the references, say "not in the data" — do not estimate.
- Lead with a 3-line summary, then a table, then recommendations with a suggested owner.
- Tone: crisp and action-oriented — suitable for an Area Sales Manager or Regional Sales Head.
- Use Green / Amber / Red status where a target or SLA exists.
```

### ✅ Check
Your notebook shows **4 references**, or 1 folder, and the instructions are saved.

---

# Exercise 2 — Validate the Notebook Can See Everything
**Time:** ~5 minutes

Before you rely on any analysis, confirm that Copilot has read every reference.

Start a chat **inside the notebook** and type:

```
List every reference in this notebook. For each one, give:
- the file name
- what it contains (sheets / sections, row counts, periods covered)
- one fact from it that proves you have read it
Then tell me if any file looks incomplete or could not be read.
```

### ✅ Check
- [ ] All **4 files** are listed. This is more than you could attach to one chat prompt.
- [ ] For `Sales_Copilot_Training_Dataset.xlsx`, it names the five data sheets (Customer Profiles, Lead Pipeline, Proposal Tracker, Communication Log, Sales Performance) plus a README sheet.
- [ ] For `BFL_Sales_Copilot_Demo.xlsx`, it mentions 25 leads (SAL-001 to SAL-025) on the *Sales Pipeline Data* sheet.

> If a file is missing, open **References**, confirm it is listed, and check that you have access to it in OneDrive.

---

# Exercise 3 — Ask Across Files (the payoff)
**Time:** ~10 minutes

Neither of these questions could be answered in one regular chat prompt without going past the 3-attachment limit. In the notebook, you don't attach anything.

### 3a — One product, every source

Loan Against Property (LAP) is the secured-lending product in this data, and it appears in several sheets. The pipeline tracker has no LAP rows, so it also tests whether Copilot says so.

```
Secured lending appears in several places in this notebook:
- Customer Profiles, Lead Pipeline, Proposal Tracker, Communication Log and Sales Performance
  (Sales_Copilot_Training_Dataset.xlsx) — product "Loan Against Property"
- Sales Pipeline Data (BFL_Sales_Copilot_Demo.xlsx) — tell me if LAP is present there

Build a one-page view of Loan Against Property:
1. Pipeline: leads, requested amount, score, stage, days in pipeline
2. Proposals: amount, offered ROI, tenure, processing fee, stage, status
3. Communication: latest interaction for each LAP customer
4. Performance: target vs achieved by month, and who carries the product
5. Customers: anyone who holds LAP or is a LAP prospect
Then tell me: is there a single risk that links these? Recommend 3 actions.
```

**What a good answer contains:**
- **Pipeline:** two LAP leads. LD-2603 Govind Traders (₹120L, score 91) and LD-2613 Crown Hospitality (₹200L, score 93), together ₹320L. Both are Hot and in Credit Review, at 21 and 26 days in the pipeline.
- **Proposals:** three open LAP proposals, together ₹365L: PRP-105 (₹110L, 10.5%), PRP-109 (₹200L, 10.25%) and PRP-111 (₹55L, 10.75%). The processing fee is 0.75% on all three.
- **A mismatch to catch:** PRP-105 was revised down from ₹120L after the valuation came in about 8% lower, but Lead Pipeline still shows ₹120L for LD-2603.
- **Communication:** CM-503 (Govind Traders, valuation visit fixed) and CM-514 (Crown Hospitality, title search report expected). Both show *Responded*.
- **Performance:** Rahul Jadhav is the only LAP RM. He achieved ₹182L against ₹200L in April and ₹235L against ₹200L in May, ₹417L against ₹400L overall.
- **Customers:** BFL-C-1003 Vikram Bhosale holds a LAP, and BFL-C-1006 Priya Deshpande is a strong LAP prospect (PRP-111).
- **The link:** the two largest deals are waiting on third-party reports (property valuation and legal title search), and one RM carries the whole LAP book.
- **The pipeline tracker:** `BFL_Sales_Copilot_Demo.xlsx` has no LAP rows. A good answer says so instead of inventing figures. Its nearest SME product is Business Loan, with 6 of the 10 SLA breaches.

### 3b — Data + method in one question

```
Using the RTCFT framework in Participant_Practice_Guide_Sales and the data in the
Lead Pipeline sheet, write me a Working Prompt for my Monday huddle with my ASM:
which leads to call first this week, which ones are stuck, and what each RM should do.
Then run that Working Prompt yourself on the Lead Pipeline data and show the output.
```

### ✅ Check
- [ ] The answer quotes figures with **file and sheet names**, as your instructions asked.
- [ ] 3a draws on **both** workbooks and at least four sheets.
- [ ] You did **not** attach a single file.

> 💡 **Tip:** names differ between sources ("Customer / Lead" in one sheet, "Lead Name" in another). Check that Copilot matched the right rows. Treat its matches as a starting point for you to confirm, not a final answer.

---

# Exercise 4 — Re-run the Five Sales Use Cases Without Re-attaching
**Time:** ~10 minutes

In `Participant_Practice_Guide_Sales.md`, every exercise says *"Type `/`, attach the dataset, and run the Working Prompt."* In the notebook, you skip the attach step.

Pick any two use cases and use the short versions below. The notebook instructions already supply the role, tone and format.

| Use Case | Prompt inside the notebook |
|---|---|
| 1 — Customer Profile Analysis | `From Customer Profiles: a segment-wise summary, the top 5 cross-sell opportunities with the recommended product for each, and relationship risks such as credit score below 720 or EMI delays. Add 3 actions for my ASM.` |
| 2 — Lead Prioritization | `From Lead Pipeline: rank the top 5 leads for this week by lead score and requested amount, flag leads that have been in the pipeline for more than 14 days, and give each RM a two-line action list.` |
| 3 — Sales Proposal Preparation | `From Proposal Tracker: draft a client-ready proposal summary for PRP-104 (Sterling Pharma) that handles the CFO's rate request, and tell me what the won PRP-106 and the lost PRP-108 teach about pricing.` |
| 4 — Customer Communication | `From Communication Log: list the follow-ups with No Response or Awaiting Response, sorted by Days Since Last Contact, and draft a WhatsApp message for the top 3.` |
| 5 — Sales Reporting | `From Sales Performance (Apr–May 2026): overall achievement against target, RM-wise and product-wise performance, the best and weakest areas using the Remarks, and 3 recommendations for June. Under 300 words for the Regional Sales Head.` |

### ✅ Check
- Compare the output with the one you got in the regular chat earlier. The format and tone should be consistent **without** you retyping the RTCFT Role, Format and Tone, because the notebook instructions supply them.
- **Use Case 5:** overall achievement should be about 101% (₹1,503L against ₹1,485L), with 172 conversions from 498 leads.
- **Use Case 2:** three leads are over 14 days in the pipeline: LD-2603 (21), LD-2607 (15) and LD-2613 (26).
- **Use Case 4:** 4 customers show *No Response* and 3 show *Awaiting Response*.
- Always verify rates, fees and product claims against approved terms before sending any draft to a customer.

---

# Exercise 5 — Three Chats, One Notebook
**Time:** ~10 minutes

A regular workflow uses separate chats for planning a prompt and running it, and asks you to attach the file again in the second chat. In a notebook, the chats stay separate but the files and instructions are shared:

1. Start **Chat A** in the notebook. Paste the Meta Prompt for Exercise 2 (Lead Pipeline) from `Participant_Practice_Guide_Sales.txt` and copy the Working Prompt Copilot gives you.
2. Start a **new chat** in the **same notebook** (Chat B) and paste the Working Prompt. The file is already there, so there is no re-attaching.
3. Save the useful output as a **page** in the notebook, so it doesn't sit only in a chat.
4. Start **Chat C** and ask: *"Turn the saved lead-prioritization output into 5 bullet points for my team's WhatsApp group."* If your notebook shows **create options** (Word document / PowerPoint deck), you can also generate a draft from the page.

> 💡 **Why this helps:** each chat stays clean, so earlier answers don't leak into later ones, while the references and instructions are written only once.

---

## Optional Extras (if visible in your tenant)

Microsoft is rolling out Notebook features in stages, so some of these may not appear for you yet.

| Feature | Try this |
|---|---|
| **Mind map** | Create a mind map of the notebook to see how customers, leads, proposals and calls connect. |
| **Study guide** | Generate a quiz or flashcards from `MetaPrompting_Guide_Sales` to test yourself on RTCFT. |
| **Word / PowerPoint from notebook** | Turn your Exercise 3a output into a Word brief or a 5-slide key-account review. |
| **Share the notebook** | Share with a colleague so they work from the same references and instructions. |

---

## Efficiency Rules — Quick Reference

| Do | Avoid |
|---|---|
| One notebook per piece of work (e.g. "Q1 Pipeline Review", "Sterling Pharma account plan") | One giant notebook for everything, because the grounding gets noisy |
| Put role, period, units, tone and format in **Copilot instructions** | Re-typing the RTCFT block in every prompt |
| Add a **folder** reference when sheets keep arriving | Re-uploading each new version by hand |
| Remove outdated references (last month's pipeline, superseded proposals) | Keeping v1, v2 and v3 of the same file, because Copilot may quote the wrong one |
| Ask Copilot to **name file + sheet** for every number | Accepting figures you can't trace |
| Save good outputs as **pages** | Leaving key results only in chat history |
| Start a **new chat in the same notebook** for each new task | One endless chat, where earlier answers leak into later ones |

---

## ⚠️ Data Handling

This is a fictional training dataset. In live work, a notebook can hold real customer data, so apply the same rules as in chat:

- Use only your BFL work account.
- Never add files containing customer PII, account numbers or PAN unless they are approved for Copilot use.
- When in doubt, de-identify first: replace customer names with codes before adding the file.

---

## Troubleshooting

| Problem | What to do |
|---|---|
| `.md` file can't be added | Rename to `.txt`, or copy the content into a notebook page. |
| Copilot says it can't find a number | Check that the file is in **References** and that you can open it. Ask: *"Which sheet contains X?"* |
| Copilot quotes the wrong workbook | Name the file and sheet: *"Use only the Lead Pipeline sheet in Sales_Copilot_Training_Dataset.xlsx."* |
| Answer uses the wrong file version | Remove old versions from References. |
| Notebooks not in the left navigation | Your licence or tenant setting may not include Notebooks yet. Tell your trainer. |
| Folder reference returns partial results | Very large folders are ranked for relevance, so name the specific file in your prompt. |

---

## Further Reading

- [How Microsoft Copilot Notebooks works](https://support.microsoft.com/en-us/microsoft-365-copilot/how-microsoft-365-copilot-notebooks-works)
- [Add references to your Copilot Notebook](https://support.microsoft.com/en-us/microsoft-365-copilot/add-references-to-your-microsoft-365-copilot-notebook)
- [Microsoft 365 Copilot release notes](https://learn.microsoft.com/en-us/microsoft-365/copilot/release-notes)

---

## 📝 Notes

**What I would put in a notebook at work:**

&nbsp;

**My standing Copilot instructions:**

&nbsp;

---

*Bajaj Finance Limited | M365 Copilot Training — Sales Team*
*Training delivered by **Technizer India** | GenAI for Enterprise Teams*
