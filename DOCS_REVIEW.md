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
