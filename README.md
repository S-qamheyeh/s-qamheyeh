## Shatha A. O. Qamheyeh

QA and test design, Toronto. Computer Science background, ISTQB Foundation Level, PMP.

I build the documentation layer that makes testing hold up when results are contested — reproducible procedures, indexed evidence, and records that can be produced on demand rather than reconstructed afterwards.

---

### What I work on

**Test and evaluation design** — procedures with defined inputs, test data and expected outcomes, written so a third party can execute them and reach the same result. On my last engagement that meant 504 procedures across ten business areas of an enterprise financial system.

**Controlled experiments over assertions** — when figures across four system views disagreed, I built a clean-baseline experiment rather than arguing: new records created from scratch, a defined transaction sequence, every view read at each checkpoint. Nine defects reproduced on data with no history, which removed "that's your test data" as an explanation.

**Falsifiable hypotheses** — I state the test that would disprove a theory before I argue for it, and withdraw it when that test fails. I did that three times in one afternoon on a reconciliation problem. The discipline matters more than being right.

**AI-assisted engineering, documented** — four months working a hard technical problem alongside an AI assistant, with a dated log of where it failed: coincidental pattern-matching presented as cause, single-signal inference in an already-unreliable system, premature severity escalation, conclusions restated instead of retested.

---

### Repositories

| Repo | What it is |
|---|---|
| **qa-evidence-toolkit** | PowerShell evidence capture with CSV indexing, plus daily-log and defect-report templates. Built to cut evidence review cost on a long engagement — roughly 40x in practice. |

---

### Currently building

**ThoughtsMESS** — an anonymous voice-message service. A sender writes something they could never say out loud, it is recorded in a real human voice, and delivered through a private link. Four emotional registers: anger, love, apology, gratitude. In sandbox testing.

TypeScript monorepo, ~17k lines. Node 24, Express 5, PostgreSQL with Drizzle, React and Vite, pnpm workspaces.

The parts I would want reviewed:

- **Contract-first API.** An OpenAPI spec is the single source of truth; Orval generates both the React query hooks and the Zod schemas from it, so client and server cannot drift apart silently.
- **A stated delivery invariant.** Recipient audio is exposed by the API only once a message reaches `delivered`. A message sitting at `pending` or `recorded` cannot leak its recording, by construction rather than by convention.
- **Explicit lifecycle.** `pending → recorded → delivered`, enforced at the route layer rather than inferred from field presence.
- **Degradation that is designed, not accidental.** Email notification is best-effort: delivery succeeds whether or not the mail provider is configured or responding. A non-critical dependency cannot fail the transaction.
- **Signed-URL uploads.** Audio goes from the browser directly to object storage via a signed PUT; the server stores only the object path and never proxies the file.

---

Arabic and English. Open to QA, test engineering and applied AI evaluation work in Toronto or remote.
