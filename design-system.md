# Work by PK — Design System (derived)

Derived from pages already built for workbypk.com. Nothing here is invented: every rule cites the file and line it came from. Where the sources disagreed, Patrick resolved each conflict (2026-09-21). The winning value is stated as a MUST, and the losing option is kept as a *Superseded (for reference)* line with its trace. Where the sources are silent, the rule is marked **UNSPECIFIED**.

---

## 0. Provenance and pinning

**Repo HEAD at extraction:** `d4cdebf6334cb51dd1e70cbf1b159e46862a5444`
**Working tree:** A1, A2 and A3 were read from the working tree as it stood, not from HEAD. At extraction, `index.html` and `projects/index.html` had uncommitted edits, and `build-log/` is untracked.

**Traces are valid only against these hashes.** If a hash no longer matches, re-verify the traces that point into that file.

| ID | File (repo-relative unless absolute) | sha256 |
|---|---|---|
| A1 | `index.html` | `9e553e220151065e4bca62dbec585caad17f3a44352ffb32e426b704ee808026` |
| A1 | `styles.css` | `ead10f9d6fc64384004c00dbe798831a021e84b1e07f5411c43be369f8dc61ae` |
| A2 | `projects/index.html` | `947b008f99092bca8fa65b4b6d382c9321b32a232dcd143d77c6d03d76244e4f` |
| A3 | `build-log/index.html` | `f29e635422689186b1f40deba2f6731ff7277b17f6fa14fdb4be9e03ae58bb9b` |
| A3 | `build-log/log.css` | `4c549c8cdc0a37a8347cddb274d52611463b5694e034eae901b8dac634adce7f` |
| A4 | `exhibits/index.html` | `c71a32484c8e629d1a0a6bf7df743f260d00e64b323cb0011065da3081f3745c` |
| A5 | `exhibits/shape-of-time/index.html` | `8d8fc91edd3d89a6d0af1cf313228d15a7dd5f2692fb42417f9332a01304a4dc` |
| B1 | `local file PKAIOS_ARCHITECTURE_MAP.html (not shipped)` | `2ed881317a5f2509ed750fbe9d6af0fcf5b1946379b7e7d5d6376546a829018a` |
| N1 | `waveminer/spend-map/index.html` | `504d03373f0751c39dab7ccc19d7c7980dfc5c61320d3898d351186a9ed43d1e` |
| R1 | `waveminer/spend-map/atlanta/index.html` | `fab07eb2c09bef3abedaa81fc570d80fef62a8af14ab6af04a78781c22a28c70` |
| R2 | `waveminer/spend-map/northern-virginia/index.html` | `3acdb5499114b11dde7c638ba56cff116405fde3417ddba780017bed42f783ab` |
| N2 | `waveminer/agents-as-consumers/index.html` | `b744e335aa65d42e44bac5fcd2b48c97e12af403d19bd55838c1fa7f3c65301d` |

**Re-pin (2026-09-26, Patrick: "recheck and update as needed"):** A2 was re-pinned again after the placeholder copy landed; no line numbers moved. A2, A3 and A4 were re-pinned again after the D8 fix, A4 once more after D2, and A2 and A4 after D6 (one line changed in each, so no line numbers moved). A1, A2 and A3 are re-pinned to the files as committed with this change. The original extraction pins could not be recovered, because those working-tree versions were never committed. So every trace into these five files was re-derived by content against the current files, and the line numbers were updated. Traces to *Superseded (for reference)* hub values cite the last pre-D5 versions as `styles.css@1344aab` and `index.html@1344aab` (`git show 1344aab:styles.css`). A5, N1, R1, R2 and N2 match their pins (A4 was re-pinned after D8, D2 and D6, below). The earlier drift notes for A2 (the N1 card at `projects/index.html:170-187` and the N2 card at `:188-206`) are folded into this re-pin.

**Corpus rule:** Corpus = pages that make up Patrick's own site (hub and section pages), regardless of which model produced the first draft. Exhibits displayed as specimens of other models' work (gpt, grok, fable, shape-of-time) are excluded because they are shown as comparisons, not adopted as house style. KN Lab is excluded as out of scope (not part of workbypk). Research notes (N1 onward) are Patrick's own work but are not corpus: they are data documents that keep their own design by decision (2026-09-24), and they are governed by §11, not by §1–§7.

**Which sources are binding:**
- **Binding rules come only from A1–A4.**
- **A5 (`shape-of-time`) is excluded as a specimen** under the corpus rule. Its values are kept in §9 for reference only, because the lineage hypothesis below depends on them. They count toward no rule.
- **B1 is reference only.** It is not part of workbypk (it lives in `~/Downloads`). It is recorded in the Appendix.

**Lineage:** [H] Section tokens overlap A5's (subset). Direction unknown: A2 was committed 47 min before A5 per git. Not attributed to Patrick.

**Excluded under the corpus rule:**
- **Specimens:** `exhibits/gpt/`, `exhibits/grok/`, `exhibits/fable/`, `exhibits/shape-of-time/` (A5)
- **Out of scope:** the KN Lab source page `SecondBrain/_dropzone/index.html`. It shares 817 of its 852 unique lines with `exhibits/gpt/index.html`.

**Independence caveat:** `build-log/log.css:2-5` says its tokens and base rules were "copied from exhibits/index.html". A3 and A4 are separate files but not independent evidence. When a rule is supported only by A3 + A4, that is noted.

**Recon correction:** an earlier recon pass claimed IBM Plex Mono is used nowhere. That was wrong. The regex `font-family:[^;"]*` stopped at the opening quote. IBM Plex Mono is used in B1 only (see Appendix). No A-file uses it.

**Rule threshold:**
- A value becomes a rule only with evidence in ≥2 site-scope files (A1–A4), or ≥3 uses within one site-scope file.
- Thinner evidence is labeled **single-source**.
- A5 is a specimen (§0) and contributes no evidence; its values are reference-only in §9.

---

## 1. The two systems inside A1–A4

A1–A4 contain two systems. **The section system governs all new pages (P0, resolved).**

- **Hub system (A1, superseded; the hub itself migrated off it 2026-09-26, see D5):** `styles.css` tokens `--bg / --ink / --ink-strong / --ink-muted / --line / --accent` (`styles.css@1344aab:1-8`). Fixed px sizes, weight 500 headings.
- **Section system (A2, A3, A4):** tokens `--garnet / --garnet-deep / --paper / --gold / --ink / --ink-soft / --rule / --mono / --s-*`. These are identical in `projects/index.html:11-25`, `build-log/log.css:8-21` and `exhibits/index.html:11-24`. Fluid `clamp()` sizes, weight 700 headings.

**What both systems share** (these are firm rules):

- **MUST** use `#E4E5E2` as the page background. [`styles.css:4`, `projects/index.html:14`, `build-log/log.css:11`, `exhibits/index.html:14`]
- **MUST** use `#6E1E28` as the single accent: links, and the brand color. [`styles.css:2`, `styles.css:40`, `projects/index.html:12`, `projects/index.html:52`, `build-log/log.css:9`, `build-log/log.css:48`, `exhibits/index.html:12`]. A4 calls garnet and paper "the house garnet and paper" (`exhibits/index.html:127`). It also describes a page that "abandons the house palette" as a departure (`exhibits/index.html:113`).
- **MUST** set all text in Switzer, loaded from Fontshare, with the fallback `ui-sans-serif, system-ui, sans-serif`. [`styles.css:25`, `index.html:9`, `projects/index.html:9,28`, `build-log/index.html:16`, `build-log/log.css:24`, `exhibits/index.html:9,27`]
- **MUST** be light-only (research notes: see §11). No A-file has `prefers-color-scheme`, `data-theme` or `color-scheme` (checked with `rg`, no hits).
- **MUST** use 1px solid hairlines as the only structural border. [`styles.css:84-85,150`, `projects/index.html:69,75`, `build-log/log.css:53,56`, `exhibits/index.html:64,68`]
- **MUST NOT** use `box-shadow`, gradients or rounded corners on containers. There are zero `box-shadow`, `gradient` or container `border-radius` declarations in A1–A4 (`rg`). The only radius is `50%` on 8px status dots (`projects/index.html:61,64`).
- **MUST** be a single centered column with a reading-width cap. [`styles.css:34-37`, `projects/index.html:37`, `build-log/log.css:33`, `exhibits/index.html:36`] The cap is `66ch` (P7).

**P0 — resolved.**
- **MUST** build every new page on the section system (A2–A4 tokens, scale and chrome), with one exception: links follow A1 (P9). Research notes are out of scope for this rule; they follow §11.
- The existing hub (A1) was not changed by this decision. *Update 2026-09-26 (D5, Patrick: "update"):* the hub's styles now use the section system (P1–P4, P6, P7); its masthead and footer frame is unchanged (see D5). Its values are recorded below as *Superseded (for reference)*.
- *Superseded (for reference):* the hub system, built from `styles.css` tokens (`styles.css@1344aab:1-8`).

---

## 2. Color

Each color's role is inferred from the selector it styles.

### 2a. Shared

| Hex | Token(s) | Role | Trace |
|---|---|---|---|
| `#E4E5E2` | `--bg` / `--paper` | Page background. Also the far end of every section-system `color-mix()`. | `styles.css:4,23`; `projects/index.html:14,29`; `build-log/log.css:11,25`; `exhibits/index.html:14,28` |
| `#6E1E28` | `--accent` / `--garnet` | **Interactive and brand.** Link text, focus ring, wordmark tile, selection background, uppercase label text inside panels, SVG primary strokes. | `styles.css:2,40,51`; `projects/index.html:12,35,43,52,79`; `build-log/log.css:9,31,39,48`; `exhibits/index.html:12,34,42,62,83` |

### 2b. Section system (A2–A4)

| Hex / value | Token | Role | Trace |
|---|---|---|---|
| `#41111A` | `--garnet-deep` | **Heading ink.** h1 and h2 text, and h2 link text. | `projects/index.html:13,49,84`; `build-log/log.css:10,45,60`; `exhibits/index.html:13,48,73` |
| `#221317` | `--ink` | **Body text.** Also the bold emphasis inside muted paragraphs. | `projects/index.html:17,30,87`; `build-log/log.css:13,26`; `exhibits/index.html:16,29` |
| `#CDA96A` | `--gold` | **Ordinal and directional marks:** wordmark letters, `ISSUE NO.` / `EXHIBIT` index labels, the `→` arrow in link rows, SVG secondary strokes, the left rule on the quoted brief, the "specced" status. It is never used for body text. | `projects/index.html:15,43,66,80,117`; `build-log/log.css:12,39,58,71`; `exhibits/index.html:15,42,55,72,75` |
| `#E2C48C` | (literal) | **Selection text** on a garnet selection background. | `projects/index.html:35`; `build-log/log.css:31`; `exhibits/index.html:34` |
| `color-mix(in oklch, var(--ink) 70%, var(--paper))` | `--ink-soft` | **Secondary text:** deks, descriptions, dates, legend, footnote paragraphs, the "parked" status. | `projects/index.html:18,58,85,86,93`; `build-log/log.css:14,47,68,78`; `exhibits/index.html:17,50,77,85` |
| `color-mix(in oklch, var(--ink) 55%, var(--paper))` | (inline) | **Metadata line:** the dates and the tech fingerprint under list items. Lighter than `--ink-soft`. | `build-log/log.css:66`; `exhibits/index.html:81` (A3 + A4, and A3 copies A4; since 2026-09-26 also the hub stamp as `--ink-meta`, `styles.css:8,115`) |
| `color-mix(in oklch, var(--garnet) 22%, var(--paper))` | `--rule` | **Hairline dividers** between list items, and the image border. | `projects/index.html:19,69,75,92`; `build-log/log.css:15,53,56`; `exhibits/index.html:18,64,68` |
| `#3F6B3A` | (literal) | **Status "running" (in use now).** Text and dot. | `projects/index.html:65,116`. Single file with 3 uses, so it meets the threshold, but only A2 has status. |
| `#B4402F` | `--ember` | **No role.** Declared but never referenced. See Known page defects, D3. | `projects/index.html:16` |

**Tints (single-source, A4):**
- `color-mix(garnet 5%, paper)`: panel background for the quoted brief (`exhibits/index.html:56`).
- `color-mix(garnet 4%, paper)`: row hover background (`exhibits/index.html:71`).
- `color-mix(ink 85%, paper)`: italic brief text (`exhibits/index.html:59`).

### 2c. Color rules (resolved)

- **P1 — MUST** use `#221317` (`--ink`) for body text. [`projects/index.html:17`, `build-log/log.css:13`, `exhibits/index.html:16`]
  *Superseded (for reference):* `#33353A`, hub body ink [`styles.css@1344aab:3,17`].
- **P2 — MUST** use `#41111A` (`--garnet-deep`) for h1 and h2. [`projects/index.html:49,84`, `build-log/log.css:45`, `exhibits/index.html:48,73`]
  *Superseded (for reference):* `#1A1B1E`, hub `--ink-strong` [`styles.css@1344aab:4,59,92,100,124`].
- **P3 — MUST** use `--ink-soft` (`color-mix(in oklch, var(--ink) 70%, var(--paper))`) for secondary text. [`projects/index.html:18`, `build-log/log.css:14`, `exhibits/index.html:17`]
  *Superseded (for reference):* `#61636A`, hub `--ink-muted` [`styles.css@1344aab:5,65,106,127,142`].
- **P4 — MUST** use `--rule` (`color-mix(in oklch, var(--garnet) 22%, var(--paper))`) for hairlines. [`projects/index.html:19`, `build-log/log.css:15`, `exhibits/index.html:18`]
  *Superseded (for reference):* `#D2D3D0`, hub `--line` [`styles.css@1344aab:6,78,140`].
- **P5 — MUST** color the "parked" status with `--ink-soft`, both the legend dot and the status text/dot. [`projects/index.html:67`]
  *Known inconsistency:* the A2 legend dot is a literal `#8a8a86` (`projects/index.html:118`). This is logged as D4 and has not been edited.
- **Related observation (not a rule):** "specced" uses a plain gold dot in the legend (`projects/index.html:117`) but gold at `filter: brightness(0.75)` for the status text (`projects/index.html:66`). The darkening is presumably for legibility on paper. That reason is inferred, not stated in the source.

---

## 3. Typography

### 3a. Family and loading
- **MUST** use Switzer for all text, loaded from `api.fontshare.com` with `display=swap` (the sources are in §1).
- **MUST** use the system mono stack for labels and metadata in the section system: `ui-monospace, 'SF Mono', SFMono-Regular, Menlo, Consolas, monospace` via `--mono`. [`projects/index.html:20`, `build-log/log.css:16`, `exhibits/index.html:19`] A1 has no monospace at all.
- **MUST NOT** use IBM Plex Mono, Space Grotesk or Inter. None of them appear in A1–A4. They appear only in B1 and in the excluded pages.
- **MUST** load Switzer weights 400–700. [`projects/index.html:9`, `build-log/index.html:16`, `exhibits/index.html:9`]
  *Superseded (for reference):* 400, 500 and 600 on the hub [`index.html@1344aab:9`].
- The wordmark requests weight 800, which isn't loaded. See D1.

### 3b. Scale

**Section system:** four fluid steps, identical in A2, A3 and A4 [`projects/index.html:21-24`, `build-log/log.css:17-20`, `exhibits/index.html:20-23`]:

| Token | Value | Used for |
|---|---|---|
| `--s--1` | `clamp(0.8rem, 0.76rem + 0.2vw, 0.9rem)` | labels, metadata, back-link, footnote paragraphs |
| `--s-0` | `clamp(1rem, 0.94rem + 0.3vw, 1.15rem)` | body |
| `--s-1` | `clamp(1.25rem, 1.1rem + 0.7vw, 1.6rem)` | h2 (list-item titles) |
| `--s-2` | `clamp(1.9rem, 1.4rem + 2.4vw, 3.2rem)` | h1 (page title) |

- **h1:** weight 700, `letter-spacing: -0.02em`, `line-height: 1.08`, `text-wrap: balance`. [`projects/index.html:49`, `build-log/log.css:45`, `exhibits/index.html:48`]
- **h2:** weight 700, `letter-spacing: -0.01em`. [`projects/index.html:84`, `build-log/log.css:59`, `exhibits/index.html:73`]
- **Body:** `line-height: 1.62`, and `text-wrap: pretty` on paragraphs. [`projects/index.html:32,50`, `build-log/log.css:28,46`, `exhibits/index.html:31,49`]

- **P6 — MUST** use the four fluid `--s-*` steps above, with 700-weight h1 and h2. [`projects/index.html:21-24,49,84`, `build-log/log.css:17-20,45,59`, `exhibits/index.html:20-23,48,73`]
  *Superseded (for reference):* the hub's fixed px scale with one 600px breakpoint and 500-weight headings [`styles.css@1344aab:20-21,56-58,90-91,97-99,64,73,105,141,145-149`]:
  - body 18px / 17px
  - name 26px / 23px
  - lead 20px / 19px
  - h2 20px/500
  - role and nav 17px
  - stamp and footer 15px
- **P7 — MUST** use a body `line-height` of `1.62`. [`projects/index.html:32`, `build-log/log.css:28`, `exhibits/index.html:31`]
  *Superseded (for reference):* `1.68` [`styles.css@1344aab:21`].
- **P7 — MUST** cap the page column at `max-width: 66ch` and secondary paragraphs at `58ch`. [`projects/index.html:37,86`, `build-log/log.css:33,68`, `exhibits/index.html:36,77`]
  *Superseded (for reference):* `max-width: 660px` [`styles.css@1344aab:27`].

---

## 4. Labels, captions and metadata (section system unless noted)

**Rules:**
- **MUST** set index labels (`ISSUE NO. 4`, `EXHIBIT 01`) in mono, 600, `--s--1`, `line-height: 1`, `letter-spacing: 0.12em`, gold. The uppercase is in the copy itself, not produced by CSS. [`build-log/log.css:58` + `build-log/index.html:53`; `exhibits/index.html:72` + `exhibits/index.html:111`] (A3 + A4 only; A3 copies A4.)
- **MUST** set metadata lines in mono, 500, `--s--1`, `line-height: 1.7`, `letter-spacing: 0.03em`, colored ink 55% into paper. This covers dates and tech fingerprints. [`build-log/log.css:62-67`, `exhibits/index.html:78-82`]
- **MUST** separate metadata fields with ` · ` (middle dot). [`projects/index.html:132`, `exhibits/index.html:114`, `index.html:99`]
- **MUST** end link rows with `→`. In A3 and A4 the arrow is gold and nudges 4px on hover. [`build-log/log.css:71-72`, `exhibits/index.html:75-76`; A2 uses the plain `→` character in link text, `projects/index.html:135`]
- **MUST** sign section pages with a `.sig` line reading `— Patrick King, CMT`, set 2.2–2.4rem below the content. [`projects/index.html:101,293`; `build-log/log.css:79`, `build-log/index.html:90`; `exhibits/index.html:87,142`]
- **Section page titles end with a period** in all three section pages: "Projects." "Build log." "Exhibits." [`projects/index.html:112`, `build-log/index.html:27`, `exhibits/index.html:98`]. This is a copy pattern. Under the §10 contract a builder never writes titles anyway.

**Single-source patterns:**
- **Status chip:** mono 600, `letter-spacing: 0.1em`, uppercased by CSS, preceded by an 8px round dot in the status color. [`projects/index.html:63-67`]
- **Legend and dates:** mono 500, not uppercased. [`projects/index.html:57,85`]
- **Panel label:** Switzer (not mono), 600, `--s--1`, `letter-spacing: 0.12em`, uppercase, garnet. [`exhibits/index.html:62`]
- *Superseded (for reference):*
  - the hub's ` — state` suffix [`index.html:45`, `styles.css@1344aab:127`]
  - the hub's 15px "Updated" stamp [`index.html:73`, `styles.css@1344aab:104-108`]

**Figure captions:** CSS exists (`projects/index.html:91-93`), but the only `<figure>` is inside a commented-out template (`projects/index.html:268-287`). No rendered caption existed at extraction, so captions are **UNSPECIFIED** in practice. *Update 2026-09-24:* the N1 card now renders the template figure (`projects/index.html:182-185`). That is a single use, and it sets no rule. *Update 2026-09-26:* the N2 card repeats it (`projects/index.html:201-204`). Both are research-note cards, so it is still no rule for other cards.

---

## 5. Borders, corners, shadows, marks

- **MUST** separate list items with a hairline: a top border on the list container and a bottom border on each item. [`projects/index.html:69,75`; `build-log/log.css:53,56`; `exhibits/index.html:64,68`]
- **MUST** keep corners square. There is no `border-radius` on any box. The wordmark is a square tile: 40px, `aspect-ratio: 1`, garnet ground, gold "PK". [`projects/index.html:40-45`, `build-log/log.css:36-41`, `exhibits/index.html:39-44`]
- **MUST NOT** add shadows (see §1).
- **Accent rule (single-source):** a 3px gold left border on a tinted panel, used for the quoted brief. [`exhibits/index.html:55-56`]
- **Focus — MUST** on every page (research notes: see §11): `:focus-visible` gets `outline: 2px solid #6E1E28` with `outline-offset: 3px`. [`styles.css:50-53`] This is promoted from A1 (2026-09-21). A3 has had one since `1a64faf` (`build-log/log.css:49`). A2 and A4 got the same rule with D6 (`projects/index.html:52`, `exhibits/index.html:86`).
- **Project marks (single-source, 9 uses):** 52px inline SVGs (40px ≤560px). Garnet primary stroke and gold secondary stroke, both `stroke-width: 2` with round caps. Garnet fills for nodes. [`projects/index.html:78-81,97`]

---

## 6. Spacing and layout

**Base unit:** none can be derived. Values don't cluster on a single unit in either system, so reuse the literal values below rather than a computed scale.

**Section system (rem):**
- Page padding: `clamp(3rem, 8vh, 5.5rem)` top and bottom, `clamp(1.25rem, 5vw, 2rem)` at the sides. [`projects/index.html:37`, `build-log/log.css:33`, `exhibits/index.html:36`]
- Header row to title: `margin-bottom: 2.6rem`; title to intro: `1.2rem`. [same three files, lines 39/49, 35/45, 38/48]
- List block: `margin-top: 2.6rem`. [`projects/index.html:69`, `build-log/log.css:53`, `exhibits/index.html:64`]
- List item padding is `1.6rem 0 1.7rem` in `build-log/log.css:55` and `exhibits/index.html:67`, but `1.8rem 0 2rem` in `projects/index.html:74`. That difference is minor and the A2 rows are taller because they carry an icon column. It is not raised as a PICK.
- h2 margins: `0.45rem 0 0.2rem`. [`build-log/log.css:59`, `exhibits/index.html:73`]
- Paragraph rhythm: `margin-block: 1em`. [`projects/index.html:50`, `build-log/log.css:46`, `exhibits/index.html:49`]
- Row layout (A2 only): a grid of `64px 1fr`, gap `clamp(1rem, 3vw, 1.8rem)`, collapsing to one column at ≤560px. [`projects/index.html:70-76,95-99`]

*Superseded (for reference):* the hub's px spacing.
- body padding `clamp(36px, 7vh, 60px) 22px clamp(72px, 12vh, 120px)` [`styles.css@1344aab:23`]
- paragraph gap 20px [`styles.css@1344aab:85`]
- nav gap 22px [`styles.css@1344aab:71`]
- divider margin 34px [`styles.css@1344aab:79`]
- h2 top margin 44px [`styles.css@1344aab:96`]
- footer: 56px margin, 22px padding [`styles.css@1344aab:138-139`]
- breakpoint 600px [`styles.css@1344aab:145`]

- **P8 — MUST** frame every page the same way (research notes: see §11; the hub: see the exception below):
  - **Top:** the PK wordmark and a `← workbypk.com` back-link.
  - **Bottom:** the `— Patrick King, CMT` signature.
  - **Traces:** [`projects/index.html:107-110,293`, `build-log/index.html:22-25,90`, `exhibits/index.html:93-96,142`]
- **Hub exception (Patrick, 2026-09-26: "ratify"):** the hub keeps its own frame: the masthead (name, role, nav), the divider and the footer line "Patrick King · Bay Miles Group LLC · 2026" [`index.html:16-27,98-100`]. It has no wordmark, back-link or `.sig`, because a back-link to workbypk.com on workbypk.com would point at itself.

---

## 7. Links, motion, theme

**Links:**
- **P9 — MUST** use A1's tuned underline on every page (research notes: see §11). That means:
  - `#6E1E28` text
  - `text-decoration: underline`, with `text-decoration-thickness: 1px` and `text-underline-offset: 3px`
  - `text-decoration-color: rgba(110, 30, 40, 0.35)` at rest, going to full `#6E1E28` on hover
  - a `160ms ease` transition
  - Trace: [`styles.css:39-48`]
- *Superseded (for reference):* before D8 (2026-09-26), the section pages used `a { color: garnet }` with the browser-default underline [`projects/index.html@f821a1c:52`, `build-log/log.css@f821a1c:48`]. They now carry the P9 rule on the same lines [`projects/index.html:52`, `build-log/log.css:48`, `exhibits/index.html:86`]. The section-specific exceptions stay as observed: the back-link and h2 title links show no underline until hover, and the h2 hover offset is 4px [`projects/index.html:46-47`, `build-log/log.css:42-43,60-61`, `exhibits/index.html:45-46`].

**Motion:**
- **MUST** keep motion to short transitions (0.15–0.16s): hover color, the arrow nudge, the row tint. [`styles.css:45`, `build-log/log.css:71`, `exhibits/index.html:69,75`]
- **MUST** honor `prefers-reduced-motion`. [`styles.css:55-58`, `build-log/log.css:74-76`, `exhibits/index.html:86`] A4 since D2 was fixed (`exhibits/index.html:86`).

**Theme:**
- **MUST** be light-only (see §1; research notes: see §11). A dark theme is **UNSPECIFIED**: nothing in A1–A4 shows one. A5 uses dark garnet *bands* within a light page (a specimen, reference-only in §9). That is not a dark theme.

---

## 8. UNSPECIFIED (not represented in A1–A4; do not fill)

- **Forms and inputs:** A5 has toggles and a range input, but A5 is a specimen, not house style.
- **Buttons:** none in A1–A4.
- **Tables:** none anywhere.
- **Long-form body copy:** A1's prose is short paragraphs. There are no article-length pages, no h3, no blockquote in prose, no footnotes and no inline code.
- **Rendered images and figure captions:** these existed only in a commented template at extraction. There has been one rendered use since, the N1 card (see §4).
- **Data visualization and charts:** none.
- **Dark theme:** none.
- **Role of `--ember` / `#B4402F`:** none (see D3).
- **Status colors beyond running, specced and parked:** none.
- **Error, empty and loading states:** none.
- **Navigation beyond the hub's 4 anchor links:** none.

---

## 9. A5 — specimen values (reference only, not binding)

These are recorded so they aren't lost. They don't count toward any rule and must not be used on site pages without an explicit decision. Source: `exhibits/shape-of-time/index.html`, the Fable-drafted essay (`exhibits/index.html:124-127`), which the corpus rule excludes as a specimen. Its tokens overlap the section tokens (see the §0 Lineage hypothesis [H]), but the direction of that relationship is unknown.

**Extra tokens beyond the section set:**
- `--garnet-black: #24090E`: the hero and colophon ground (`:21,89,337`)
- `--gold-bright: #E2C48C`: emphasis on dark grounds (`:24,119,211`)
- `--measure: 62ch` (`:28`)
- A six-step scale `--step--1` … `--step-4` (`:29-34`). `--step-1` equals the section system's `--s-1`. The rest differ slightly.

**Other treatments:**
- Uppercase `0.14em` gold/garnet eyebrows and kickers (`:127-131,151-156`)
- Margin notes with a 2px gold left rule (`:180-189`)
- Soft shadows on the wordmark and the instrument frame (`:110-111,233`). Shadows appear **nowhere** in A1–A4.
- A square toggle switch and a garnet button with gold text (`:267-292`)
- Scroll-driven animation (`:41,79,165`)

**Provenance note:** A2 was first committed with gold tokens at 2026-08-22 06:18 (`1aa4b3d`). A5 was first committed at 07:05 the same day (`681ac56`), carrying a superset of the same tokens. Git records commit order, not authoring order, so the direction of the overlap is unknown (§0 [H]).

---

## Known page defects (recorded, not fixed)

| ID | Defect | Trace |
|---|---|---|
| D1 | The wordmark requests `font-weight: 800`, but pages load Switzer only up to 700. The browser falls back to or synthesizes the weight. *A3 fixed in `1a64faf` (`build-log/log.css:40` is 700).* | `projects/index.html:9,44`; `exhibits/index.html:9,43` |
| D2 | **Resolved 2026-09-26 (Patrick: "d2").** `exhibits/index.html` had transitions (`:69,75`, plus the D8 link fade at `:86`) and no `prefers-reduced-motion` block. It now has A3's guard (`* { transition: none !important; }`) on line 86, so no line numbers moved. | `exhibits/index.html:69,75,86` |
| D3 | `--ember: #B4402F` is declared but never used (0 `var(--ember)` references). | `projects/index.html:16` |
| D4 | The "parked" legend dot uses a literal `#8a8a86` instead of `--ink-soft` (the P5 rule). | `projects/index.html:118` vs `:67` |
| D5 | **Resolved 2026-09-26.** The A1 styles now use the section system (Patrick: "update"). That covers tokens and colors (P1–P4), the fluid scale with 700-weight headings (P6), line-height 1.62 and the 66ch column (P7), section spacing, Switzer 400–700, and the mono metadata style for the "Updated" stamp. The hub name is set as the h1 style (`--s-2`) and the lead as `--s-1`. The hub's masthead and footer frame is ratified as the P8 hub exception (Patrick: "ratify"; see §6). | `styles.css`; `index.html:16-27,98-100` |
| D6 | **Resolved 2026-09-26 (Patrick: "d6").** A2 and A4 had no `:focus-visible` style, which the focus MUST in §5 requires. Both now carry A3's rule (`a:focus-visible { outline: 2px solid var(--garnet); outline-offset: 3px; }`), appended to an existing line so no line numbers moved. Checked by keyboard: the first four links on each page get a 2px garnet ring with a 3px offset, including the exhibit rows. A3 was fixed earlier in `1a64faf` (`build-log/log.css:49`). | `projects/index.html:52`, `exhibits/index.html:86` |
| D7 | ~~R1, R2 and N2 link to "contact form on workbypk.com", but the site has no form.~~ **Resolved 2026-09-26 (Patrick):** the link text is now `patrick@workbypk.com` with `href="mailto:patrick@workbypk.com"`, which matches the hub's Contact section. "the" before the link was dropped so the sentence still reads. | `waveminer/spend-map/atlanta/index.html:299`, `waveminer/spend-map/northern-virginia/index.html:299`, `waveminer/agents-as-consumers/index.html:442`; `index.html:92` |
| D8 | **Resolved 2026-09-26 (Patrick: "lets go to d8").** A2, A3 and A4 broke P9 (the tuned link underline is a MUST on every page), using `a { color: garnet }` with the browser's default underline. All three now carry A1's rule: 1px thickness, 3px offset, 35% garnet at rest going to full garnet on hover, and a 160ms fade. On A2, which had no transitions before this change, the fade is switched off under `prefers-reduced-motion` on the same line (A3 already had a guard; A4 got one with D2). The listed exceptions are unchanged: back-links and build-log title links have no underline until hover, and the exhibit rows are block links with no underline. | `projects/index.html:52`, `build-log/log.css:48`, `exhibits/index.html:86` |
| D9 | *Added 2026-09-26 by the builder; approved by Patrick ("log").* Dead CSS in A3: `.dim` (`build-log/log.css:47`) and `.dek` (`:68`) have no users in `build-log/index.html` since the `1a64faf` restructure. The §2b ink-soft trace and the §3b 58ch trace into `log.css:68` point at this unused rule. | `build-log/log.css:47,68` |

---

## 10. BUILD CONTRACT

Any page built from this system is bound by the following.

1. **Approved copy is preserved verbatim.** Every word, punctuation mark, capitalization and line of copy Patrick has approved goes onto the page exactly as supplied. No rewording, trimming, reordering, "tightening" or typographic substitution.
2. **Nothing is added.** The builder must not add headlines, labels, claims, stats, testimonials or explanatory captions. That includes eyebrows, kickers, section intros, tooltip text, alt-text that makes claims, and "fingerprint" or metadata lines not in the supplied copy.
3. **Self-written text is listed before publishing.** Any text the builder wrote itself, of any length and for any reason (including placeholder, alt, `aria-label`, `<title>` and meta description), is listed for Patrick's approval **before** the page is published. Nothing ships until that list is approved.
4. Bracketed placeholders present in the corpus stay as placeholders until Patrick supplies the copy. No placeholders remain in the corpus as of 2026-09-26. The last ones, on the "research system" card (`projects/index.html:231-234`), were replaced with copy Patrick approved ("a"). The build-log DEK placeholder was removed by `1a64faf`. A builder must never fill them.

---

## 11. Research notes (own design)

**Decision (Patrick, 2026-09-24):** research notes keep their own design. The map, filters, bar charts, graded sources and dark mode are data-document needs that §1–§7 were never derived from (§8 lists tables, charts and dark theme as UNSPECIFIED). Rebuilding N1 on the section system was considered and rejected (Patrick's "draft it", 2026-09-24).

**Scope:** pages published as a numbered research note in a series. First instance: N1, `waveminer/spend-map/index.html` (WaveMiner · Research note 01), published 2026-09-24. Regional editions of a note (R1 Atlanta, R2 Northern Virginia, added 2026-09-24 as N1 v2) are part of that note and follow the same rules, with one exception: their back-link goes to `../` (the national note), not `/`, per the package README. They share N1's `fonts/`, and the same garnet link patch was applied to them. Second note: N2, `waveminer/agents-as-consumers/index.html` (WaveMiner · Research note 02), added 2026-09-26. It was copied in unchanged apart from the same garnet link patch and its `data-contact-link` (now `mailto:patrick@workbypk.com`, see D7). It ships its own `fonts/` (byte-identical to N1's).

**Shared with the site** (every note MUST; these are the shared basics Patrick agreed to):
- **Link color is house garnet** `#6E1E28` in light mode, matching the §1 accent. [`waveminer/spend-map/index.html:36,79`]
  - *Builder-chosen, pending Patrick (not a rule):* only the color is shared. N1 keeps its own underline, not P9's.
- **Dark-mode link color is N1's own blue `#8AADE6`** (Patrick, 2026-09-24: "keep it blue"; cyan is the fallback if it ever changes). [`waveminer/spend-map/index.html:52,65`] That is 8.1:1 contrast on `#0F1514`. A builder-chosen `#E8A0A8` was tried and rejected.
- **A visible `:focus-visible` outline** in the link color. [`waveminer/spend-map/index.html:80`] N1's outline is 2px with a 2px offset, not §5's 3px offset. That offset is N1's own and is not a defect.
- **Honor `prefers-reduced-motion`.** [`waveminer/spend-map/index.html:227`]
- **A `← workbypk.com` back-link to `/`.** [`waveminer/spend-map/index.html:234`]
- **A byline and date line with ` · ` separators** (§4). [`waveminer/spend-map/index.html:238`]
- **`og:site_name` set to `Work by PK`.** [`waveminer/spend-map/index.html:11`]
- **A card on `/projects/`,** in the A2 card pattern. [`projects/index.html:181`]
- **Sign notes "Patrick"** (Patrick, 2026-09-24). N1 complies: "Patrick · workbypk.com" [`waveminer/spend-map/index.html:238`]. Site pages keep their own signature, "— Patrick King, CMT" (`projects/index.html:293`). This rule applies to notes only.

**Series style — MUST** (Patrick, 2026-09-24: "same look"): later notes in the series use N1's tokens and type (`waveminer/spend-map/index.html:25-72`: Barlow Condensed display, IBM Plex Sans and Mono, self-hosted, light and dark). A new note copies N1's `@font-face` and `:root` blocks rather than re-deriving them. Nothing from the series style carries back into site pages.

**Not shared, on purpose:** N1's data blue `--accent` stays blue. It encodes meaning in the bars and edges, and the copy names it: "Blue-edged rows are the three being tested first" [`waveminer/spend-map/index.html:324`]. The published social image uses the same blue [`waveminer/spend-map/og-image.png`].

---

## Appendix — B1 reference (not binding)

`local file PKAIOS_ARCHITECTURE_MAP.html (not shipped)`. It was never shipped, and is recorded only so the divergence is on file. Nothing below applies to workbypk.com pages.

**Type**
- Loaded from Google Fonts: Space Grotesk 400–700, Inter 400–600, IBM Plex Mono 400–600 (`:9`).
- **Body:** `"Inter", system-ui, sans-serif`, `line-height: 1.5` (`:27`).
- **Display:** Space Grotesk 700, `clamp(40px,7vw,76px)`, `line-height: .96`, `-.02em` (`:37-38`).
- **Labels:** IBM Plex Mono across 18 label and caption classes (`:31,35,55,61,68,75,83,89,104,110,112,120,125,134,143,149,156`). Eyebrow is 12px, `letter-spacing: .28em`, uppercase (`:35-36`).

**Palette** (dark only; `:12-18`)

| Hex | Token | Role (from its own comments and usage) |
|---|---|---|
| `#0e1218` | `--ink` | page ground |
| `#151b24` / `#1a2230` | `--panel` / `--panel-2` | panel surfaces |
| `#243040` / `#1c2531` | `--hair` / `--hair-soft` | hairlines |
| `#e7edf4` / `#8b97a6` / `#5c6675` | `--tx` / `--tx-dim` / `--tx-faint` | text: primary / secondary / faint |
| `#d9a441` | `--z-private`, `--wall` | zone: "local / guarded" |
| `#9182c8` | `--z-sanitized` | zone: "tokenize -> cloud" |
| `#4fb8c9` | `--z-external` | zone: "cloud, free" |
| `#3fb37f` / `#e0853b` / `#e15b5b` / `#3a4656` | `--s-built` / `--s-prog` / `--s-block` / `--s-future` | build status: built / in progress / blocked / future |

**Other treatments:**
- Radial-gradient page glows (`:24-25`)
- Pill radius 999px and chip radius 4px (`:104,112`)
- Max-width 1180px (`:30`)

**Divergence from the binding system:** dark versus light; Inter/Space Grotesk/Plex versus Switzer/system mono; rounded pills versus square; gradients versus flat.
