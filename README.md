# Customer 360 Prototype — working demo

A hands-on prototype for stakeholder testing. **Open `index.html` directly in a
browser** — double-click it or drag it onto a window. No server, no build, no
internet. Everything runs and saves in that one browser.

## What's real about it

- **It persists.** Every decision — merges, notes, tickets, offers, audiences,
  field mappings, feedback, the theme — is saved in the browser (`localStorage`)
  and survives a reload. It opens where you left off.
- **The screens are connected.** Confirm a match in *Identity resolution* and the
  customer's *Customer 360* profile gains that source system and a timeline entry.
  Build a list in *Operator console* and it appears in *List sync* to map and
  export. Actions land in the activity feed on *Home*.
- **Reset for the next tester.** Sidebar → *Reset demo data* clears everything and
  reloads the seeded sample.
- **Collect feedback while you test.** The **Feedback** button (bottom-right) is
  always there — rate the screen, jot a note, hit send. Everything collected shows
  on *Home* with a *Copy all (JSON)* button.

## Guided tours

Every end-to-end use case has a **step-by-step walk-through** on the live screens.
Start one from **How it works**, or hit *Take the tour* on Home. A dock at the
bottom explains each step and highlights the element to look at; Next / Back move
through it, and it navigates you between screens automatically.

- Resolve a customer's identity (data steward)
- Act on an at-risk customer (campaign ops)
- Build & sync a campaign audience (marketing ops)
- The B2B tax-ID account (enterprise / account team)

## The six sections

| Section | What you can actually do |
|---|---|
| **Home** | Day-at-a-glance: click a stat tile to jump to its screen, confirm auto-merge matches inline, open a customer from an alert, read the activity feed, review collected feedback. Plus a **Beyond CRM + CVM** panel. |
| **How it works** | The management demo. Opens with **The end goal** (the vision + three pillars: Retain / Grow / Trust the data) and **The impact** (a business-case table — where teams are today vs. the target, and what drives it, with a back-of-envelope at DCT's scale). Then **how every capability ladders up to the goal** — each advanced capability, the CRM/CVM comparison, what it unlocks, the outcome it drives, and which goal it serves. Then the end-to-end pipeline you can click through, three journey swimlanes, and the four guided tours. |
| **Rules & scoring** | The business owns the logic; engineering builds against the spec. **Plug fields in and out of each score** — add from a library grouped by source system (each with a data-coverage bar), or tap the **app's recommendations** (known signals it suggests for that score, with a suggested weight); remove any field with one click. Tune weights with steppers. The app **warns when a field's coverage is too low** to trust. Every change recalculates every score on every screen instantly, and each card shows a sample customer's factor-by-factor breakdown. **Export full build spec (JSON)** hands engineering the formulas, active fields, weights, input definitions and coverage. Thresholds (at-risk churn, auto-merge confidence, score bands) live here too. |
| **Identity resolution** | Work the match queue: nudge a confidence score, then Confirm (merges that source into the customer), Review or Reject. Filter by state. Click any **match ID** for the full case in the right-hand panel. "Confirm all auto-merge". Toggle the intercompany cross-sell exclusion on the tax-ID-anchored B2B account. |
| **Customer 360** | Search the directory, open any of 14 customers. See the merged profile by source (click a source block to inspect it), computed scores, usage trend (30d/90d/12m). Open or resolve support tickets, add internal notes — all saved, all shown on the timeline. |
| **Operator console** | Filter by source, search, read the 3 KPIs. Open a customer → identity + profile halves → **Send offer** (pick a type) or **Add to audience**. **Build a list**: filter, tick customers, **Save as audience**. |
| **List sync** | Capability comparison vs CRM / CVM. Pick a saved audience → edit its field mapping → choose one-time vs live sync → **Run export** (appends to that audience's export history). |

## Tech

Plain HTML + CSS + JS in one file. **Typography and layout follow the DCT CDP
console prototype** — IBM Plex Sans for text, IBM Plex Mono for labels, table
headers and IDs, sidebar + top-bar shell, 1400px content width. The two IBM Plex
webfonts load from Google Fonts (the only external request); with no internet the
page falls back to the system UI font and still works.

Light/dark follows the OS; the ☀/☾ button overrides it. Cellcard brand palette
(Primary `#FF9F18` / deep `#F56300`, Pearl White `#FBF8F4`, Ultramarine
`#0D90CE`, Pink `#DF1683`). No data is sent anywhere — all sample data, all
saved locally. All figures are in USD.

## The mascot & the info drawer

- **The little face bottom-right** (above *Feedback*) is the shortcut to the
  advanced story. Click it for the four things this platform does that a CRM or
  CVM can't; pick one and it starts that guided tour on the live screens.
- **A slide-in panel from the right** opens whenever you click into a detail:
  a **match ID** in *Identity resolution* (the full case for that match, with
  Confirm / Review / Reject in the panel), a **source block** in *Customer 360*
  (what that system is, its operating company, and which scores it feeds), or the
  **Details** button on a capability in *How it works*. Esc or click-away closes it.

## First run & tooltips

- **First visit opens a short "what this is for" panel** — take the guided tour or
  explore on your own; picking "explore" points an arrow at **How it works** so a
  new viewer knows where to start. It reappears after *Reset demo data* for the
  next tester.
- **Hover for an explanation.** Recurring controls carry tooltips — the score
  weight steppers, the confidence steppers, coverage bars, recommendation chips,
  the "Only here" tags, the range switch, the theme and reset buttons.
- The **− / +** on every stepper is colour-coded: pink **−** lowers a
  value, ultramarine **+** raises it.
