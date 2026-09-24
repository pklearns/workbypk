# Work by PK — Design System (derived)

Derived from pages already built for workbypk.com. Nothing here is invented: every rule cites the file and line it came from. Where the sources disagreed, Patrick resolved each conflict (2026-09-21). The winning value is stated as a MUST, and the losing option is kept as a *Superseded (for reference)* line with its trace. Where the sources are silent, the rule is marked **UNSPECIFIED**.

---

## 0. Provenance and pinning

**Repo HEAD at extraction:** `d4cdebf6334cb51dd1e70cbf1b159e46862a5444`
**Working tree:** A1, A2 and A3 were read from the working tree as it stood, not from HEAD. At extraction, `index.html` and `projects/index.html` had uncommitted edits, and `build-log/` is untracked.

**Traces are valid only against these hashes.** If a hash no longer matches, re-verify the traces that point into that file.

| ID | File (repo-relative unless absolute) | sha256 |
|---|---|---|
| A1 | `index.html` | `d9126d2905734ad65b48df32091b547b5376e29ffdf649b4cfe8b8b73f158d82` |
| A1 | `styles.css` | `7a5872522bc7f5399812eddfe680d6a2bcdf0ae36df4fc1b106d574f764d9490` |
| A2 | `projects/index.html` | `10c436a88740a93c3ceb17833627aa30078b87730b9ee522071573c847f6e08e` |
| A3 | `build-log/index.html` | `1888168d3ebb46cf39ef160fcd226d11a32c6ed69febf9c82d372ebae12d425d` |
| A3 | `build-log/log.css` | `572a91ff35c302811b7afdba3b08cede35c8225a6073eb36e9d64211c50367d4` |
| A4 | `exhibits/index.html` | `160816b7cd96961d9bb2043d2b55397d17f62ba34cc40c82451fc4fb362c6bbf` |
| A5 | `exhibits/shape-of-time/index.html` | `8d8fc91edd3d89a6d0af1cf313228d15a7dd5f2692fb42417f9332a01304a4dc` |
| B1 | `/Users/knuggs/Downloads/PKAIOS_ARCHITECTURE_MAP.html` | `2ed881317a5f2509ed750fbe9d6af0fcf5b1946379b7e7d5d6376546a829018a` |
| N1 | `waveminer/spend-map/index.html` | `c714297b5d2446b2581e010798e08cd999b3bbc219149e10f768fe57ff641667` |

**Drift (2026-09-24):** A2 no longer matches its pin. Commit `e479186` inserted the N1 card at `projects/index.html:169-187` (19 lines). A2 traces at or below line 168 still hold. Traces past it in §1–§10 (`:193`, `:230-249`, `:255`) now sit 19 lines lower: for example, `[running / confirm]` has moved from `:193` to `:212`. The §11 traces (`:181`, `:274`) cite the current file. Re-pin A2 at the next full re-verification.

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

- **Hub system (A1, superseded for new pages):** `styles.css` tokens `--bg / --ink / --ink-strong / --ink-muted / --line / --accent` (`styles.css:1-8`). Fixed px sizes, weight 500 headings.
- **Section system (A2, A3, A4):** tokens `--garnet / --garnet-deep / --paper / --gold / --ink / --ink-soft / --rule / --mono / --s-*`. These are identical in `projects/index.html:11-25`, `build-log/log.css:8-21` and `exhibits/index.html:11-24`. Fluid `clamp()` sizes, weight 700 headings.

**What both systems share** (these are firm rules):

- **MUST** use `#E4E5E2` as the page background. [`styles.css:2`, `projects/index.html:14`, `build-log/log.css:11`, `exhibits/index.html:14`]
- **MUST** use `#6E1E28` as the single accent: links, and the brand color. [`styles.css:7`, `styles.css:32`, `projects/index.html:12`, `projects/index.html:52`, `build-log/log.css:9`, `build-log/log.css:48`, `exhibits/index.html:12`]. A4 calls garnet and paper "the house garnet and paper" (`exhibits/index.html:127`). It also describes a page that "abandons the house palette" as a departure (`exhibits/index.html:113`).
- **MUST** set all text in Switzer, loaded from Fontshare, with the fallback `ui-sans-serif, system-ui, sans-serif`. [`styles.css:18`, `index.html:9`, `projects/index.html:9,28`, `build-log/index.html:19`, `build-log/log.css:24`, `exhibits/index.html:9,27`]
- **MUST** be light-only (research notes: see §11). No A-file has `prefers-color-scheme`, `data-theme` or `color-scheme` (checked with `rg`, no hits).
- **MUST** use 1px solid hairlines as the only structural border. [`styles.css:77-78,140`, `projects/index.html:69,75`, `build-log/log.css:52,55`, `exhibits/index.html:64,68`]
- **MUST NOT** use `box-shadow`, gradients or rounded corners on containers. There are zero `box-shadow`, `gradient` or container `border-radius` declarations in A1–A4 (`rg`). The only radius is `50%` on 8px status dots (`projects/index.html:61,64`).
- **MUST** be a single centered column with a reading-width cap. [`styles.css:26-29`, `projects/index.html:37`, `build-log/log.css:33`, `exhibits/index.html:36`] The cap is `66ch` (P7).

**P0 — resolved.**
- **MUST** build every new page on the section system (A2–A4 tokens, scale and chrome), with one exception: links follow A1 (P9). Research notes are out of scope for this rule; they follow §11.
- The existing hub (A1) is not changed by this decision. Its values are recorded below as *Superseded (for reference)*.
- *Superseded (for reference):* the hub system, built from `styles.css` tokens (`styles.css:1-8`).

---

## 2. Color

Each color's role is inferred from the selector it styles.

### 2a. Shared

| Hex | Token(s) | Role | Trace |
|---|---|---|---|
| `#E4E5E2` | `--bg` / `--paper` | Page background. Also the far end of every section-system `color-mix()`. | `styles.css:2,16`; `projects/index.html:14,29`; `build-log/log.css:11,25`; `exhibits/index.html:14,28` |
| `#6E1E28` | `--accent` / `--garnet` | **Interactive and brand.** Link text, focus ring, wordmark tile, selection background, uppercase label text inside panels, SVG primary strokes. | `styles.css:7,32,43`; `projects/index.html:12,35,43,52,79`; `build-log/log.css:9,31,39,48`; `exhibits/index.html:12,34,42,62,83` |

### 2b. Section system (A2–A4)

| Hex / value | Token | Role | Trace |
|---|---|---|---|
| `#41111A` | `--garnet-deep` | **Heading ink.** h1 and h2 text, and h2 link text. | `projects/index.html:13,49,84`; `build-log/log.css:10,45,59`; `exhibits/index.html:13,48,73` |
| `#221317` | `--ink` | **Body text.** Also the bold emphasis inside muted paragraphs. | `projects/index.html:17,30,87`; `build-log/log.css:13,26`; `exhibits/index.html:16,29` |
| `#CDA96A` | `--gold` | **Ordinal and directional marks:** wordmark letters, `ISSUE NO.` / `EXHIBIT` index labels, the `→` arrow in link rows, SVG secondary strokes, the left rule on the quoted brief, the "specced" status. It is never used for body text. | `projects/index.html:15,43,66,80,117`; `build-log/log.css:12,39,57,70`; `exhibits/index.html:15,42,55,72,75` |
| `#E2C48C` | (literal) | **Selection text** on a garnet selection background. | `projects/index.html:35`; `build-log/log.css:31`; `exhibits/index.html:34` |
| `color-mix(in oklch, var(--ink) 70%, var(--paper))` | `--ink-soft` | **Secondary text:** deks, descriptions, dates, legend, footnote paragraphs, the "parked" status. | `projects/index.html:18,58,85,86,93`; `build-log/log.css:14,47,67,77`; `exhibits/index.html:17,50,77,85` |
| `color-mix(in oklch, var(--ink) 55%, var(--paper))` | (inline) | **Metadata line:** the dates and the tech fingerprint under list items. Lighter than `--ink-soft`. | `build-log/log.css:65`; `exhibits/index.html:81` (A3 + A4 only, and A3 copies A4) |
| `color-mix(in oklch, var(--garnet) 22%, var(--paper))` | `--rule` | **Hairline dividers** between list items, and the image border. | `projects/index.html:19,69,75,92`; `build-log/log.css:15,52,55`; `exhibits/index.html:18,64,68` |
| `#3F6B3A` | (literal) | **Status "running" (in use now).** Text and dot. | `projects/index.html:65,116`. Single file with 3 uses, so it meets the threshold, but only A2 has status. |
| `#B4402F` | `--ember` | **No role.** Declared but never referenced. See Known page defects, D3. | `projects/index.html:16` |

**Tints (single-source, A4):**
- `color-mix(garnet 5%, paper)`: panel background for the quoted brief (`exhibits/index.html:56`).
- `color-mix(garnet 4%, paper)`: row hover background (`exhibits/index.html:71`).
- `color-mix(ink 85%, paper)`: italic brief text (`exhibits/index.html:59`).

### 2c. Color rules (resolved)

- **P1 — MUST** use `#221317` (`--ink`) for body text. [`projects/index.html:17`, `build-log/log.css:13`, `exhibits/index.html:16`]
  *Superseded (for reference):* `#33353A`, hub body ink [`styles.css:3,17`].
- **P2 — MUST** use `#41111A` (`--garnet-deep`) for h1 and h2. [`projects/index.html:49,84`, `build-log/log.css:45`, `exhibits/index.html:48,73`]
  *Superseded (for reference):* `#1A1B1E`, hub `--ink-strong` [`styles.css:4,59,92,100,124`].
- **P3 — MUST** use `--ink-soft` (`color-mix(in oklch, var(--ink) 70%, var(--paper))`) for secondary text. [`projects/index.html:18`, `build-log/log.css:14`, `exhibits/index.html:17`]
  *Superseded (for reference):* `#61636A`, hub `--ink-muted` [`styles.css:5,65,106,127,142`].
- **P4 — MUST** use `--rule` (`color-mix(in oklch, var(--garnet) 22%, var(--paper))`) for hairlines. [`projects/index.html:19`, `build-log/log.css:15`, `exhibits/index.html:18`]
  *Superseded (for reference):* `#D2D3D0`, hub `--line` [`styles.css:6,78,140`].
- **P5 — MUST** color the "parked" status with `--ink-soft`, both the legend dot and the status text/dot. [`projects/index.html:67`]
  *Known inconsistency:* the A2 legend dot is a literal `#8a8a86` (`projects/index.html:118`). This is logged as D4 and has not been edited.
- **Related observation (not a rule):** "specced" uses a plain gold dot in the legend (`projects/index.html:117`) but gold at `filter: brightness(0.75)` for the status text (`projects/index.html:66`). The darkening is presumably for legibility on paper. That reason is inferred, not stated in the source.

---

## 3. Typography

### 3a. Family and loading
- **MUST** use Switzer for all text, loaded from `api.fontshare.com` with `display=swap` (the sources are in §1).
- **MUST** use the system mono stack for labels and metadata in the section system: `ui-monospace, 'SF Mono', SFMono-Regular, Menlo, Consolas, monospace` via `--mono`. [`projects/index.html:20`, `build-log/log.css:16`, `exhibits/index.html:19`] A1 has no monospace at all.
- **MUST NOT** use IBM Plex Mono, Space Grotesk or Inter. None of them appear in A1–A4. They appear only in B1 and in the excluded pages.
- **MUST** load Switzer weights 400–700. [`projects/index.html:9`, `build-log/index.html:19`, `exhibits/index.html:9`]
  *Superseded (for reference):* 400, 500 and 600 on the hub [`index.html:9`].
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
- **h2:** weight 700, `letter-spacing: -0.01em`. [`projects/index.html:84`, `build-log/log.css:58`, `exhibits/index.html:73`]
- **Body:** `line-height: 1.62`, and `text-wrap: pretty` on paragraphs. [`projects/index.html:32,50`, `build-log/log.css:28,46`, `exhibits/index.html:31,49`]

- **P6 — MUST** use the four fluid `--s-*` steps above, with 700-weight h1 and h2. [`projects/index.html:21-24,49,84`, `build-log/log.css:17-20,45,58`, `exhibits/index.html:20-23,48,73`]
  *Superseded (for reference):* the hub's fixed px scale with one 600px breakpoint and 500-weight headings [`styles.css:20-21,56-58,90-91,97-99,64,73,105,141,145-149`]:
  - body 18px / 17px
  - name 26px / 23px
  - lead 20px / 19px
  - h2 20px/500
  - role and nav 17px
  - stamp and footer 15px
- **P7 — MUST** use a body `line-height` of `1.62`. [`projects/index.html:32`, `build-log/log.css:28`, `exhibits/index.html:31`]
  *Superseded (for reference):* `1.68` [`styles.css:21`].
- **P7 — MUST** cap the page column at `max-width: 66ch` and secondary paragraphs at `58ch`. [`projects/index.html:37,86`, `build-log/log.css:33,67`, `exhibits/index.html:36,77`]
  *Superseded (for reference):* `max-width: 660px` [`styles.css:27`].

---

## 4. Labels, captions and metadata (section system unless noted)

**Rules:**
- **MUST** set index labels (`ISSUE NO. 4`, `EXHIBIT 01`) in mono, 600, `--s--1`, `line-height: 1`, `letter-spacing: 0.12em`, gold. The uppercase is in the copy itself, not produced by CSS. [`build-log/log.css:57` + `build-log/index.html:36`; `exhibits/index.html:72` + `exhibits/index.html:111`] (A3 + A4 only; A3 copies A4.)
- **MUST** set metadata lines in mono, 500, `--s--1`, `line-height: 1.7`, `letter-spacing: 0.03em`, colored ink 55% into paper. This covers dates and tech fingerprints. [`build-log/log.css:61-66`, `exhibits/index.html:78-82`]
- **MUST** separate metadata fields with ` · ` (middle dot). [`projects/index.html:132`, `exhibits/index.html:114`, `index.html:99`]
- **MUST** end link rows with `→`. In A3 and A4 the arrow is gold and nudges 4px on hover. [`build-log/log.css:70-71`, `exhibits/index.html:75-76`; A2 uses the plain `→` character in link text, `projects/index.html:135`]
- **MUST** sign section pages with a `.sig` line reading `— Patrick King, CMT`, set 2.2–2.4rem below the content. [`projects/index.html:101,255`; `build-log/log.css:78`, `build-log/index.html:71`; `exhibits/index.html:87,142`]
- **Section page titles end with a period** in all three section pages: "Projects." "Build log." "Exhibits." [`projects/index.html:112`, `build-log/index.html:30`, `exhibits/index.html:98`]. This is a copy pattern. Under the §10 contract a builder never writes titles anyway.

**Single-source patterns:**
- **Status chip:** mono 600, `letter-spacing: 0.1em`, uppercased by CSS, preceded by an 8px round dot in the status color. [`projects/index.html:63-67`]
- **Legend and dates:** mono 500, not uppercased. [`projects/index.html:57,85`]
- **Panel label:** Switzer (not mono), 600, `--s--1`, `letter-spacing: 0.12em`, uppercase, garnet. [`exhibits/index.html:62`]
- *Superseded (for reference):*
  - the hub's ` — state` suffix [`index.html:45`, `styles.css:127`]
  - the hub's 15px "Updated" stamp [`index.html:73`, `styles.css:104-108`]

**Figure captions:** CSS exists (`projects/index.html:91-93`), but the only `<figure>` is inside a commented-out template (`projects/index.html:230-249`). No rendered caption existed at extraction, so captions are **UNSPECIFIED** in practice. *Update 2026-09-24:* the N1 card now renders the template figure (`projects/index.html:182-185`). That is a single use, and it sets no rule.

---

## 5. Borders, corners, shadows, marks

- **MUST** separate list items with a hairline: a top border on the list container and a bottom border on each item. [`projects/index.html:69,75`; `build-log/log.css:52,55`; `exhibits/index.html:64,68`]
- **MUST** keep corners square. There is no `border-radius` on any box. The wordmark is a square tile: 40px, `aspect-ratio: 1`, garnet ground, gold "PK". [`projects/index.html:40-45`, `build-log/log.css:36-41`, `exhibits/index.html:39-44`]
- **MUST NOT** add shadows (see §1).
- **Accent rule (single-source):** a 3px gold left border on a tinted panel, used for the quoted brief. [`exhibits/index.html:55-56`]
- **Focus — MUST** on every page (research notes: see §11): `:focus-visible` gets `outline: 2px solid #6E1E28` with `outline-offset: 3px`. [`styles.css:42-45`] This is promoted from A1 (2026-09-21). A2–A4 currently define no focus style; see D6.
- **Project marks (single-source, 7 uses):** 52px inline SVGs (40px ≤560px). Garnet primary stroke and gold secondary stroke, both `stroke-width: 2` with round caps. Garnet fills for nodes. [`projects/index.html:78-81,97`]

---

## 6. Spacing and layout

**Base unit:** none can be derived. Values don't cluster on a single unit in either system, so reuse the literal values below rather than a computed scale.

**Section system (rem):**
- Page padding: `clamp(3rem, 8vh, 5.5rem)` top and bottom, `clamp(1.25rem, 5vw, 2rem)` at the sides. [`projects/index.html:37`, `build-log/log.css:33`, `exhibits/index.html:36`]
- Header row to title: `margin-bottom: 2.6rem`; title to intro: `1.2rem`. [same three files, lines 39/49, 35/45, 38/48]
- List block: `margin-top: 2.6rem`. [`projects/index.html:69`, `build-log/log.css:52`, `exhibits/index.html:64`]
- List item padding is `1.6rem 0 1.7rem` in `build-log/log.css:54` and `exhibits/index.html:67`, but `1.8rem 0 2rem` in `projects/index.html:74`. That difference is minor and the A2 rows are taller because they carry an icon column. It is not raised as a PICK.
- h2 margins: `0.45rem 0 0.2rem`. [`build-log/log.css:58`, `exhibits/index.html:73`]
- Paragraph rhythm: `margin-block: 1em`. [`projects/index.html:50`, `build-log/log.css:46`, `exhibits/index.html:49`]
- Row layout (A2 only): a grid of `64px 1fr`, gap `clamp(1rem, 3vw, 1.8rem)`, collapsing to one column at ≤560px. [`projects/index.html:70-76,95-99`]

*Superseded (for reference):* the hub's px spacing.
- body padding `clamp(36px, 7vh, 60px) 22px clamp(72px, 12vh, 120px)` [`styles.css:23`]
- paragraph gap 20px [`styles.css:85`]
- nav gap 22px [`styles.css:71`]
- divider margin 34px [`styles.css:79`]
- h2 top margin 44px [`styles.css:96`]
- footer: 56px margin, 22px padding [`styles.css:138-139`]
- breakpoint 600px [`styles.css:145`]

- **P8 — MUST** frame every page the same way (research notes: see §11):
  - **Top:** the PK wordmark and a `← workbypk.com` back-link.
  - **Bottom:** the `— Patrick King, CMT` signature.
  - **Traces:** [`projects/index.html:107-110,255`, `build-log/index.html:25-28,71`, `exhibits/index.html:93-96,142`]
- *Superseded (for reference):* the hub masthead (name, role, nav), divider and footer line "Patrick King · Bay Miles Group LLC · 2026" [`index.html:16-27,98-100`].

---

## 7. Links, motion, theme

**Links:**
- **P9 — MUST** use A1's tuned underline on every page (research notes: see §11). That means:
  - `#6E1E28` text
  - `text-decoration: underline`, with `text-decoration-thickness: 1px` and `text-underline-offset: 3px`
  - `text-decoration-color: rgba(110, 30, 40, 0.35)` at rest, going to full `#6E1E28` on hover
  - a `160ms ease` transition
  - Trace: [`styles.css:31-40`]
- *Superseded (for reference):* the section pages' `a { color: garnet }` with the browser-default underline [`projects/index.html:52`, `build-log/log.css:48`]. The section-specific exceptions stay as observed: the back-link and h2 title links show no underline until hover, and the h2 hover offset is 4px [`projects/index.html:46-47`, `build-log/log.css:42-43,59-60`, `exhibits/index.html:45-46`].

**Motion:**
- **MUST** keep motion to short transitions (0.15–0.16s): hover color, the arrow nudge, the row tint. [`styles.css:37`, `build-log/log.css:70`, `exhibits/index.html:69,75`]
- **MUST** honor `prefers-reduced-motion`. [`styles.css:47-50`, `build-log/log.css:73-75`] A4 has a gap here; see D2.

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
| D1 | The wordmark requests `font-weight: 800`, but pages load Switzer only up to 700. The browser falls back to or synthesizes the weight. | `projects/index.html:9,44`; `build-log/index.html:19` + `build-log/log.css:40`; `exhibits/index.html:9,43` |
| D2 | `exhibits/index.html` has transitions (`:69,75`) with no `prefers-reduced-motion` block. `rg` finds 0 matches in the file. | `exhibits/index.html:69,75` |
| D3 | `--ember: #B4402F` is declared but never used (0 `var(--ember)` references). | `projects/index.html:16` |
| D4 | The "parked" legend dot uses a literal `#8a8a86` instead of `--ink-soft` (the P5 rule). | `projects/index.html:118` vs `:67` |
| D5 | A1 (hub) uses superseded values (P1-P4, P6-P8). Out of spec; migrate or ratify later. Not compliant. | `styles.css:1-8,20-27,56-58,90-99,145-149`; `index.html:16-27,98-100` |
| D6 | A2–A4 have no `:focus-visible` style, which the focus MUST in §5 requires. | `projects/index.html:10-102`, `build-log/log.css`, `exhibits/index.html:10-88` (no `focus` match) |

---

## 10. BUILD CONTRACT

Any page built from this system is bound by the following.

1. **Approved copy is preserved verbatim.** Every word, punctuation mark, capitalization and line of copy Patrick has approved goes onto the page exactly as supplied. No rewording, trimming, reordering, "tightening" or typographic substitution.
2. **Nothing is added.** The builder must not add headlines, labels, claims, stats, testimonials or explanatory captions. That includes eyebrows, kickers, section intros, tooltip text, alt-text that makes claims, and "fingerprint" or metadata lines not in the supplied copy.
3. **Self-written text is listed before publishing.** Any text the builder wrote itself, of any length and for any reason (including placeholder, alt, `aria-label`, `<title>` and meta description), is listed for Patrick's approval **before** the page is published. Nothing ships until that list is approved.
4. Bracketed placeholders present in the corpus stay as placeholders until Patrick supplies the copy. Examples: `[DEK — issue no. 4, 2–3 sentences, pending final copy]` at `build-log/index.html:39`, and `[running / confirm]` at `projects/index.html:193`. A builder must never fill them.

---

## 11. Research notes (own design)

**Decision (Patrick, 2026-09-24):** research notes keep their own design. The map, filters, bar charts, graded sources and dark mode are data-document needs that §1–§7 were never derived from (§8 lists tables, charts and dark theme as UNSPECIFIED). Rebuilding N1 on the section system was considered and rejected (Patrick's "draft it", 2026-09-24).

**Scope:** pages published as a numbered research note in a series. First instance: N1, `waveminer/spend-map/index.html` (WaveMiner · Research note 01), published 2026-09-24.

**Shared with the site** (every note MUST; these are the shared basics Patrick agreed to):
- **Link color is house garnet** `#6E1E28` in light mode, matching the §1 accent. [`waveminer/spend-map/index.html:36,79`]
  - *Builder-chosen, pending Patrick (not a rule):* N1's dark-mode link color is `#E8A0A8` [`:52,65`], picked for 8.8:1 contrast on N1's dark ground `#0F1514`. The site has no dark theme to derive it from (§7, §8).
  - *Builder-chosen, pending Patrick (not a rule):* only the color is shared. N1 keeps its own underline, not P9's.
- **A visible `:focus-visible` outline** in the link color. [`waveminer/spend-map/index.html:80`] N1's outline is 2px with a 2px offset, not §5's 3px offset. That offset is N1's own and is not a defect.
- **Honor `prefers-reduced-motion`.** [`waveminer/spend-map/index.html:221`]
- **A `← workbypk.com` back-link to `/`.** [`waveminer/spend-map/index.html:228`]
- **A byline and date line with ` · ` separators** (§4). [`waveminer/spend-map/index.html:232`]
- **`og:site_name` set to `Work by PK`.** [`waveminer/spend-map/index.html:11`]
- **A card on `/projects/`,** in the A2 card pattern. [`projects/index.html:181`]

**Series style — Proposed (not decided):** N1's own tokens and type (`waveminer/spend-map/index.html:25-72`: Barlow Condensed display, IBM Plex Sans and Mono, self-hosted) are the style for later notes in the same series. The proposal is that a new note copies N1's `:root` blocks rather than re-deriving them. Nothing from the series style carries back into site pages.

**Not shared, on purpose:** N1's data blue `--accent` stays blue. It encodes meaning in the bars and edges, and the copy names it: "Blue-edged rows are the three being tested first" [`waveminer/spend-map/index.html:318`]. The published social image uses the same blue [`waveminer/spend-map/og-image.png`].

**Open (not a rule):** the byline name. N1 signs "Patrick · workbypk.com" [`:232`], while A2 signs "— Patrick King, CMT" (`projects/index.html:274`). Patrick has not decided this.

---

## Appendix — B1 reference (not binding)

`/Users/knuggs/Downloads/PKAIOS_ARCHITECTURE_MAP.html`. It was never shipped, and is recorded only so the divergence is on file. Nothing below applies to workbypk.com pages.

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
