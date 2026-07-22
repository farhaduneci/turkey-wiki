# Docs Review Log

Running notes from periodic documentation reviews. Each entry: what was checked, what was fixed, what was deliberately left alone. Newer sessions should read the latest entry before re-scanning from scratch.

## 2026-07-18

**Scanned:** Full repo — all `.md` files, root `README.md` navigation, every directory `README.md`, relative link integrity (scripted check, no broken relative links found except a non-link example path in `CLAUDE.md`).

**Fixed (top 3):**

1. **DISCLAIMER.md was never linked from README.md.** Given the wiki covers visa/legal/financial topics, a new user had no path to the disclaimer. Added a short "Disclaimer" section to the bottom of `README.md` linking to it.
2. **`mistakes/document-translation.md` was missing a "Related" section.** The other two files in `mistakes/` (`date-number-formats.md`, `document-management.md`) cross-link to each other and to `document-translation.md`, but it didn't link back — one-directional cross-linking. Added the missing `Related` section.
3. **`internet/free-wifi.md` pointed to a non-existent "mobile/SIM section"** for getting a Turkish number for SMS verification. No such section exists yet anywhere in the repo — a dead-end reference for someone trying to actually do the thing. Reworded to be honest that it's not documented yet instead of implying a working link.

**Left alone / flagged for confirmation (not fixed — ambiguous/risky):**

- **`FAQ.md` and `RESOURCES.md` are both completely empty (0 bytes)** — they've been empty since the initial commit and are not linked from anywhere. Two options: fill them in (risks inventing content not backed by personal experience, against content guidelines) or delete them (a deletion, which this review process treats as risky/requires confirmation). Left as-is; **flagging for the repo owner** to decide whether to populate, delete, or keep as intentional placeholders.
- Root `README.md` lists several unlinked bullet topics (Apps & useful services, Student life, Housing, Costs & budgeting, Tips & recommendations, Random discoveries) — these look like intentional placeholders for future topic directories per the repo's stated structure convention, not an error. Not touched.
- `transportation/istanbulkart.md` has a self-flagged gap (student Istanbulkart application steps not yet documented) — already honestly marked as a known gap by the author, no action needed.

**Not yet reviewed in depth:** prose quality/tone consistency across files, whether every "may change" claim is actually flagged as time-sensitive per the Contributing Conventions (spot-checked, looked fine), image/media assets (none present currently).

## 2026-07-18 (later, same day — user-directed additions)

Not a scan-driven review session; the repo owner requested specific additions/fixes directly, applied here and merged to `main`. Logged for continuity with the running review.

**Added:**
- `internet/sim-cards-and-mobile-data.md` — SIM card buying (retailer markup mistake, official pricing), eSIM's before-arrival activation rule, data plans, the 90/180-day SIM validity + residency-linking requirement, the 4-month IMEI registration rule, home broadband, LTE hotspots. Resolves the `FAQ.md`/dangling-reference gap noted above.
- `README.md` — new "Where to Start" section: a curated, ordered reading path (before you leave → landing → first week → settling in → ID-number-gated stage → mistakes → journal), kept distinct from the existing categorical "What you'll find" index.
- New `apps/` directory (`README.md`, `istanbul-senin-app.md` moved here from `internet/`, `istanbulkart-app.md`, `sahibinden.md`) — apps used in daily life, with a 🪪 marker for apps whose main features require a Turkish ID/foreigner ID number (i.e., need an open residence permit application first, not just a phone number). `istanbulkart-app.md` includes a "Mistake I made" callout about missing a PTT delivery of the student card.

**Fixed:**
- `README.md` — linked `DISCLAIMER.md` (previously unreachable from nav) and the previously-unlinked "Apps" placeholder bullet; corrected "Where to Start" so ID-gated apps (İstanbul Senin, İstanbulkart student card) moved out of "First week" into their own later stage — they'd silently fail for anyone without a Turkish ID number yet.
- `mistakes/document-translation.md` — added missing `Related` section (one-directional cross-link gap).
- `transportation/istanbulkart.md` — replaced the old "haven't documented the application steps yet" note with the actual process and a link to `apps/istanbulkart-app.md`.
- Updated all cross-links across `internet/`, `apps/`, and `transportation/` after the `istanbul-senin-app.md` move; verified no broken relative links repo-wide.

**Still open (unchanged from the entry above):** `FAQ.md` and `RESOURCES.md` remain empty and unlinked — still flagging for the repo owner's call (fill in vs. delete) rather than acting unilaterally.

## 2026-07-19

**Scanned:** Full repo again, focused on what changed since the last entry — new `student-life/` directory (`universities-in-istanbul.md`, `finding-and-registering-university.md`) added since. Checked: root README navigation still covers it, every directory README still lists all its files, no broken relative links repo-wide (scripted check), cross-link completeness for the new files against related existing docs.

**Fixed (top 3):**

1. **`student-life/finding-and-registering-university.md` listed "Diploma and transcript ... translated (and typically notarized)" as a required document but didn't link to `mistakes/document-translation.md`** — the existing doc about exactly this (original-vs-copy mistake, notarization cost, the embossing-seal requirement) was invisible to the one audience most likely to need it. Added the link inline, plus a reverse link back from `document-translation.md`'s "Related" section — previously one-directional.
2. **Same file listed "A Turkish phone number" as a requirement with no link** — every other place in the repo that mentions needing a Turkish number (`free-wifi.md`, `sahibinden.md`) links to `internet/sim-cards-and-mobile-data.md`; this one didn't. Added the link for consistency.
3. **`mistakes/document-translation.md`'s "Related" section was missing a link to `visa/90-day-legal-stay.md`** that its two sibling files (`date-number-formats.md`, `document-management.md`) both have — an inconsistency in an otherwise fully cross-linked trio. Added it (translation/notarization timing matters against the 90-day clock).

**Left alone:** The `visa/90-day-legal-stay.md` → `finding-and-registering-university.md` link already existed bidirectionally (added in the file itself when student-life was written), so no action needed there. Root README's "Where to Start" ordered path still doesn't mention `student-life/` — left as-is since it's a niche path (not every reader is a student) already reachable via the categorical index, not a universal-path gap like the others.

**Resolved:** `FAQ.md` and `RESOURCES.md` — the repo owner opted to delete rather than fill in. Removed (confirmed 0 bytes, unlinked from anywhere).

## 2026-07-20

**Scanned:** Full repo again — no commits since the last entry, so this was a from-scratch structural pass rather than a diff review. Checked: broken relative links (scripted, none found beyond the known non-link example path in `CLAUDE.md`), every directory `README.md` lists all files present (all do), root `README.md` nav and "Where to Start" order, cross-link completeness, and read every doc for factual self-consistency (not just link structure) since the last two sessions hadn't done that pass yet.

**Fixed (found 1 real issue, not 3 — see note at bottom):**

1. **Tax number / SIM / bank account prerequisite chain was contradictory and had the causality backwards.** `banking/tax-number.md` claimed "you need a tax number to get a SIM card," and `banking/bank-account.md` repeated that chain (tax number → SIM → bank account). But `internet/sim-cards-and-mobile-data.md`'s own explicit "what you need" list for a SIM is just address + passport — no tax number. Worse, `tax-number.md`'s own instructions list "Phone number" as a **required field** on the online tax number application — meaning the real dependency runs the other way: get a SIM first, use its number to apply for the tax number, then use both to open a bank account. This wasn't a style nit; a new arrival following the guide's own "Where to Start" order would have hit a required field they couldn't fill in. Fixed: reworded `tax-number.md` and `bank-account.md` to state the correct chain (SIM → tax number → bank account), added the missing cross-links between all three docs, and reordered `README.md`'s "First week" step to SIM Cards → Tax Number → Bank Account → Free WiFi → Sahibinden.

**Left alone:** Everything else checked out — no broken links, no missing directory-README entries, `student-life/`, `apps/`, `internet/`, `mistakes/`, `visa/`, `transportation/`, `guides/`, `banking/`, `libraries/`, and `journal/` are all internally consistent and cross-linked both ways. Root README's "Where to Start" still doesn't mention `student-life/` — unchanged from the 07-19 call that this is fine (niche path, reachable via the categorical index).

**Note on scope:** Only one high-impact issue turned up this pass, not three. Per the review rules, not inventing two more just to round out a quota — the repo is otherwise in good shape.

## 2026-07-22

**Scanned:** Diff-focused pass — significant new content landed since the last entry: `visa/address-registration.md`, `visa/closed-neighborhoods.md`, and an `apps/e-devlet.md` (moved from `guides/e-devlet.md`), plus enrichment of `banking/tax-number.md`, `banking/bank-account.md`, and `internet/sim-cards-and-mobile-data.md` with details from an external resource (KU ICO). Checked: broken relative links (scripted, none beyond the known `CLAUDE.md` example path), directory `README.md` completeness (all current), the e-devlet move left no stale references in `guides/README.md`, and cross-link completeness for the newly-added visa docs against existing content that predates them (same class of gap as the 07-19 session).

**Fixed (found 1 real cluster of issues, not 3 — see note at bottom):**

1. **`student-life/finding-and-registering-university.md` predates the new visa docs and never got backlinked to them, and was missing the "Related" footer every sibling doc has.** Specifically: (a) its "Required Documents" section tells students they need a residential address/rental contract but didn't mention `visa/closed-neighborhoods.md` — directly relevant since that doc explicitly warns "don't sign a lease" without checking first; (b) its registration procedure tells students to "go register fingerprints" at a migration office with zero detail, when `visa/address-registration.md` (added since the last review) now documents exactly that appointment — how to book it, what to bring, what to expect; (c) unlike its siblings across `visa/`, `mistakes/`, `apps/`, and `internet/`, this file had no `## Related` footer at all. Fixed all three: added the closed-neighborhoods link inline at the residential-address bullet, added the address-registration link inline at the fingerprinting step, and added a `## Related` section linking to `90-day-legal-stay.md`, `address-registration.md`, and `document-translation.md`.

**Left alone:** Everything else checked out — the new visa docs (`address-registration.md`, `closed-neighborhoods.md`) are already fully cross-linked to each other and to `90-day-legal-stay.md` and `apps/e-devlet.md`; the `guides/e-devlet.md` → `apps/e-devlet.md` move left no dangling references anywhere. The `visa/README.md` "Background" section (general passport/visa history videos) and "Reference" section (Wikipedia link on Iranian citizen visa requirements) are additions of general context rather than actionable how-to content — noted, not touched, since they're not broken or misplaced, just a different register than the rest of the wiki. Root README's "Where to Start" still doesn't call out `student-life/`, `address-registration.md`, or `closed-neighborhoods.md` by name — unchanged from the 07-19/07-20 calls that the categorical index is sufficient for these more specific/niche paths.

**Note on scope:** Only one real cluster of issues turned up this pass (three related gaps in one file), not three independent ones. Per the review rules, not inventing unrelated busywork elsewhere — the rest of the repo, including all the newly-added content, is internally consistent and well cross-linked.
