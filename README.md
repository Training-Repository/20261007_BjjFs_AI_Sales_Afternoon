# M365 Copilot Training — Sales Team (Bajaj Finance Limited)

Training materials for a Microsoft 365 Copilot enablement session for the Bajaj Finance Limited (BFL) Sales team, delivered by Technizer India under the **GenAI for Enterprise Teams** program.

The session covers prompt engineering (meta-prompting, RTCFT framework), Copilot in Excel (formulas, pivot tables), and using Copilot Notebooks to work across more files than the chat attachment limit.

## Contents

| File | Description |
|---|---|
| [`MetaPrompting_Guide_Sales.md`](MetaPrompting_Guide_Sales.md) | Introduces meta-prompting — asking Copilot to write your prompt for you. Includes ready-to-use meta-prompts for Sales use cases (customer profiles, lead prioritization, proposals, communication, sales reporting). |
| [`Participant_Practice_Guide_Sales.md`](Participant_Practice_Guide_Sales.md) | Participant guide built around the **RTCFT** (Role–Task–Context–Format–Tone) prompt framework, with a meta-prompt + working-prompt pair for each of the same 5 use cases. |
| [`BFL_Sales_CopilotExcel_Participant_Guide.md`](BFL_Sales_CopilotExcel_Participant_Guide.md) | Hands-on exercises for Copilot in Excel — writing formulas (escalation flags, SLA breach, lead ageing, conversion speed), explaining formulas, and building pivot tables on sales pipeline data. |
| [`BFL_Sales_Excel_CopilotChat_Guide.md`](BFL_Sales_Excel_CopilotChat_Guide.md) | Same Excel formula and pivot exercises **without Excel Agent / Edit with Copilot** — for Copilot Chat (Basic) users, using an RTCFT meta-prompt, manual apply, and expected results to verify. |
| [`Copilot_Notebooks_Guide.md`](Copilot_Notebooks_Guide.md) | Using Copilot Notebooks as a persistent workspace — add all files once as references, set standing instructions, and query across more files than the 3-attachment chat limit. |
| [`Sales_Copilot_Training_Dataset.xlsx`](Sales_Copilot_Training_Dataset.xlsx) | Practice dataset for the meta-prompting exercises. Sheets: Customer Profiles, Lead Pipeline, Proposal Tracker, Communication Log, Sales Performance. |
| [`BFL_Sales_Copilot_Demo.xlsx`](BFL_Sales_Copilot_Demo.xlsx) | Practice dataset for the Excel exercises — 25 rows of sales pipeline leads with columns left blank for participants to fill in using Copilot-generated formulas. |

## How to use this material

1. Start with the meta-prompting guides (`MetaPrompting_Guide_Sales.md` or `Participant_Practice_Guide_Sales.md`) to learn the RTCFT framework and generate working prompts against `Sales_Copilot_Training_Dataset.xlsx`.
2. Move to `BFL_Sales_CopilotExcel_Participant_Guide.md` for hands-on formula and pivot table exercises using `BFL_Sales_Copilot_Demo.xlsx` (requires a Microsoft 365 Copilot licence).
   - **Basic licence / Copilot Chat only?** Use `BFL_Sales_Excel_CopilotChat_Guide.md` instead — same exercises, no Agent required.
3. Use `Copilot_Notebooks_Guide.md` to move all of the above into a single Copilot Notebook — no re-attaching, no 3-file limit.

## Requirements

- Microsoft 365 Copilot (Copilot Chat and Copilot in Excel) — **or**, for Basic licence users, Copilot Chat only (see `BFL_Sales_Excel_CopilotChat_Guide.md`)
- Access to Copilot Notebooks in the M365 Copilot app (for `Copilot_Notebooks_Guide.md`)
- Excel files uploaded to OneDrive so they can be attached in Copilot Chat

---

*Delivered by Technizer India | GenAI for Enterprise Teams*
