# JobFlow — what the client asked for (from voice notes, Nov 10–11 2026)

- Every job is a project; client CRM with paid / owed.
- Big projects contain small jobs; each job runs Request → Details → Estimate → Approval → Deposit → Schedule → Handoff → Done.
- One owner per project; tasks hand over between assignees while the owner stays responsible.
- Plans & documents vault with revisions/versions.
- Estimates, invoices, change orders.
- Crew scheduling with continuity: when a job is stuck, crew moves to the next job and confirms.
- "No task falls through the cracks": Needs-attention list, gone-quiet flags.
- Financials per project and per job: contract + change orders, budget, spent, invoiced, paid, owed, profit.
- Every cost itemized (date, type labor/materials/sub, what, qty × price, vendor, who logged it, receipt, billed or not).
- Quick-add cost pop-up ("Add & enter another") and CSV upload for many transactions at once.
- Invoice from unbilled costs with a markup %; lines then marked billed so nothing is charged twice.

## Files
- index.html — the whole app (HTML/CSS/JS in one file, sample data in memory, hash routes like #p/p1/fin, #costs/p1/0).
- jobflow-costs-template.csv — CSV import format.
- screenshots/ — desktop (1280) and phone (390) captures.

## Step workflow (inside each job)
| Step | Who | Fields | Can't move on until |
|---|---|---|---|
| 1 Request | Office | what's needed, trade, requested by, urgency, owner, photos | an owner is assigned |
| 2 Details | Estimator | site visit date, measurements/scope, photos/plans | scope is written |
| 3 Estimate | Estimator | labor, materials, subs, markup % (live client price), sent | estimate is sent |
| 4 Approval | Client | Signed / Changes requested (→ back to Estimate as new version) | client signed |
| 5 Deposit | Office | amount (defaults 30%), method, date | deposit received |
| 6 Schedule | Owner | crew, start date, materials ordered, permit, crew confirmed | crew confirmed; permit waiting = Blocked |
| 7 Handoff | Crew lead | accepted, daily notes, photos, work complete | work complete |
| 8 Done | Owner | walkthrough, punch list, final invoice, paid | closed |

## Phases & tasks
- Each project: 7 phases → stages → tasks, % done per phase/stage, late flags, + Task (optionally as a job).
- Phases view (accordion) or List view (one table) with filters Open / Late / Done / All.

## Stage handoff & service level
- Finishing a stage = sign off ("complete and correct") + choose who takes the next stage (or Myself) + note.
- The job then waits for that person to Accept (or Send back if the previous stage isn't complete); it is locked until then.
- Not accepted: manager is messaged at 4h, owner at 24h, and it appears in Needs attention (times to be confirmed by client).
- Every sign-off, accept and send-back is logged in History.
