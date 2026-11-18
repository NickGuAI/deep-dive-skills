# Deliverables and a complete example

This file fixes what each deliverable and record must contain. How you produce them is decided during the run. The release checks and the rules for fixing a failed check are in [SKILL.md](../SKILL.md); they are not repeated here.

## Run folder

```text
<run>/
├── contract.md         the agreed result
├── leads.md            one row per lead
├── sources/<id>/       one folder per source
├── diagrams/           overview diagrams          ┐
├── report.md           content report by topic    │ shipped files:
├── outlines.md         outlines side by side      │ the release checks
├── table.md            topic × source table       │ run on these
├── delivery-note.md    what the requester reads   ┘
└── checks.md           hashes, check results, findings, workers
```

One page (for example an HTML file with tabs) may hold the four deliverables instead of four files; the page itself is then a shipped file.

## One folder per source

| File | Content |
|---|---|
| Saved originals | The page, PDF or file as captured, never edited. A text version of each PDF, with page markers. |
| Receipt | For each saved file: URL, capture time (UTC), HTTP status, bytes, SHA-256, and the tool that captured it. |
| Record | What the checks need: title, publisher, date and where the date comes from, URL, and what was read and what was not. The fuller record is under "Resources" in SKILL.md. |
| Outline | The source's own headings, word for word, in its own order, each with a locator (page, line or heading). A label you add, for a source without headings, is marked as yours. |
| Topic tags | One tag per topic the source covers: `section` (its own section or, in a source without headings, its own paragraphs) or `mention`, with the locator. |

The receipt, record and topic tags may share one file, and a source's outline may live only in `outlines.md`.

## The four deliverables

**Overview diagrams.** Each diagram gives the date of the sources it draws on, and its legend says what every mark means.

**Content report.** One section per topic, in the contract's order. Each statement names its source ID and locator. Keep what a source says apart from your own inference, and label the inference. Open with a short overview in which every line is a source statement or a count. End with disagreements between sources, and a gaps section: kinds of sources or topics without a source, parts not read, and logged leads that a reader would miss. A recommendation, if the stance allows it, goes in its own last section.

**Outlines side by side.** One column per source, holding its outline. Never reorder a source to fit the topics.

**Topic × source table.** One row per topic and one column per source, or the reverse. Each cell is `section`, `mention` or `—` (not found in what was read), with a locator. Totals by kind of source come from the topic tags.

## Records

- **`leads.md`**: ID; the lead; who raised it and where; state; folder or reason.
- **`checks.md`**: the shipped files, with their full SHA-256 and writer; one row per check, with who ran it, what they did not write, and the result on those hashes; the queries for what was missed, each with its date and finds; one content row per statement, outline item, table cell and diagram label; the findings, each with file and place, the problem, the evidence and its locator, the fix, the decision and who made it, and the re-check; the search for each old wording; the note's claims compared with the records; the workers and helpers, each with ID, role and final state; usage and process problems; when and how the note was delivered.
- **Delivery note**: the files and where to start; the contract version; each check's result in the numbers that `checks.md` shows; the gaps; and what the Closure check asks the note to report.

## Complete example

A small run on one narrow subject. Every authored deliverable and run record is shown in full; the saved source pages are identified by URL and hash, not reproduced here. The sources, quotations, numbers and line numbers are real: the two pages were captured on 2026-11-17, and every quotation was found in those captures. The request, the people, the searches and the other run records are illustrative. Each SHA-256 in `checks.md` is the hash of the file text shown in that file's block, final newline included; each receipt's SHA-256 is the hash of the saved capture. `S1 L36` means line 36 of the saved capture of source S1. In `checks.md`, "lead" in the "Written by" and "Decision, by whom" columns is the person or agent in charge of the run; it is not a row of `leads.md`. In a source record, `selected-sections` means that only the listed lines were read.

### contract.md

```markdown
# Contract v1: how AI model providers retire old API models

Request: "Deep dive: how do Anthropic and OpenAI retire old API models? Tell me what their API documentation says."
Stance: describe only.
Kinds of sources: each provider's API documentation on retiring models.
Topics: T1 notice before retirement · T2 what API users are told to do ·
T3 what happens to a retired model.
Deliverables: the default set.
Limits: public pages only, and the boundaries in SKILL.md.
Budget: 1 hour, no money, two pages, 1 helper, 2 checkers, repairs included.
Approved: "Yes, go ahead." (requester, 2026-11-17)
```

### leads.md

```markdown
| ID | Lead | Raised by, where | State | Folder or reason |
|---|---|---|---|---|
| L1 | OpenAI API documentation page, Deprecations | helper H1, search for OpenAI's retirement policy | captured | sources/s2/ |
| L2 | Anthropic post linked as Commitments on Model Deprecation and Preservation | helper H1, S1 L63 | logged | a news post, not API documentation: outside the contract's kind |
| L3 | Anthropic migration guides | helper H1, S1 L32 | logged | budget (two pages) |
| L4 | Anthropic API documentation page, Model deprecations | checker C1, search for what was missed | already held | sources/s1/ |
| L5 | OpenAI post on retiring GPT-4o and older models in ChatGPT | checker C1, search for what was missed | logged | about ChatGPT, not the API, as its title says: outside the contract's kind |
```

### sources/s1/record.md

```markdown
S1 · Model deprecations (S1 L2) · Anthropic, Claude API documentation; no author named.
URL: https://platform.claude.com/docs/en/about-claude/model-deprecations
Date and version: no publication date or version found for the page; its facts hold
as of the capture.
Receipt: page.md, saved from the page's Markdown version
(https://platform.claude.com/docs/en/about-claude/model-deprecations.md)
on 2026-11-17 at 02:44:16 UTC; HTTP 200; 14,846 bytes; curl, direct download;
SHA-256 cf4dc6596cae93bc850eb93f6f6d4d1f4df43162bffb6dde54623966dba6c2e4.
Access problems: none.
Read: selected-sections. Lines 1–64 in full, from the opening through Deprecation
downsides and mitigations. Not read: lines 65–235 (model status table, deprecation
history, API parameter deprecations).
Outline: the S1 column of outlines.md.
Tags: T1 section L34–36 (also mention L7, L24) · T2 section L26–32, L38–53 ·
T3 section L55–63 (also mention L18).
```

### sources/s2/record.md

```markdown
S2 · Deprecations · OpenAI, API documentation; no author named. The capture has no
page heading; the receipt notes the page title Deprecations | OpenAI API, and the
documentation's own menu names this address Deprecations (L63).
URL: https://developers.openai.com/api/docs/deprecations
Date and version: no publication date or version found for the page; its facts hold
as of the capture.
Receipt: page.md, saved from that URL on 2026-11-17 at 02:36:40 UTC; HTTP 200;
32,942 bytes; Firecrawl scrape (Markdown, main content only);
SHA-256 96780fe5284ae80e6baa58bac00e9f8e6d6feaf94365319d4ae18c1e6080dbe8.
Access problems: none.
Read: selected-sections. Line 63 (the menu entry that names this page), lines
103–115 (Overview) and 170–191 (Model deprecation notice periods, Best practices,
Migration guidance). Not read: the rest of lines 1–102 (the site's search box and
menus), lines 117–169 and 193–335 (the lists of upcoming, feature and endpoint,
fine-tuning and past deprecations), and lines 336–339 (the site's chat button).
Lines 116 and 192 are blank.
Outline: the S2 column of outlines.md.
Tags: T1 section L170–180 (also mention L105) · T2 section L182–191 ·
T3 mention L111, L180.
```

### diagrams/1-notice.md

```text
Diagram 1 · Minimum notice before an API model is retired, as each page states it
Pages captured 2026-11-17. One block is about one week (our conversion).

OpenAI · generally available models            ██████████████████████████  "At least 6 months" (S2 L176)
OpenAI · specialized variants of generally     █████████████               "At least 3 months" (S2 L177)
         available models, and image
         generation models
Anthropic · publicly released models ¹         █████████                   "at least 60 days’ notice" (S1 L36)
OpenAI · preview models ²                      ░░                          "such as 2 weeks" (S2 L178)

OpenAI emails customers who are actively using the model (S2 L172); its minimums hold "Unless safety or compliance concerns require a faster timeline" (S2 L174).
¹ Notice goes to customers with active deployments (S1 L36). The page's dates apply to Anthropic-operated platforms; partner-operated platforms "set their own retirement schedules" (S1 L24).
² Hatched: an example the page gives, not a minimum.
```

### report.md

```markdown
# How Anthropic and OpenAI retire old API models

Describe only (contract.md, v1).
S1: Anthropic, Model deprecations, API documentation; no publication date found for the page (S1 L1–5; S1 record).
S2: OpenAI, Deprecations, API documentation; no publication date found for the page (S2 L63; S2 record).
Both pages were captured on 2026-11-17; the parts read are listed in each record (S1 and S2 receipts and records).

## Overview
- Both pages say that affected customers are told by email and in the documentation (S1 L7, S2 L105).
- The minimum notice differs by provider and by kind of model (S1 L36; S2 L176–178; diagram 1).

## T1 Notice before retirement
Anthropic notifies customers with active deployments, "providing at least 60 days’ notice before model retirement for publicly released models" (S1 L36). The page's dates apply to Anthropic-operated platforms; partner-operated platforms "set their own retirement schedules" (S1 L24).

OpenAI emails customers who are actively using the model (S2 L172) and gives minimum notice periods "Unless safety or compliance concerns require a faster timeline" (S2 L174): "At least 6 months" for generally available models, and "At least 3 months" for specialized variants of generally available models and for image generation models (S2 L176–177). Preview models "may be retired with much shorter notice, such as 2 weeks" (S2 L178).

## T2 What API users are told to do
Anthropic: "migrate all usage to a suitable replacement before the retirement date" (S1 L28), test with the new models "well before the retirement date" (S1 L30, L51), and find any remaining use in a usage export "broken down by API key and model" (S1 L44).

OpenAI: "Run representative requests against both models. Compare outputs, latency, and cost before switching production traffic to the replacement." (S2 L191). A program can read each model's optional `shutdown_date` field from the List models endpoint (S2 L185).

## T3 What happens to a retired model
Anthropic: "Requests to retired models fail." (S1 L18). The page says Anthropic has committed to long-term preservation of model weights, and links a separate post on that commitment (S1 L63; leads L2).

OpenAI: a shut-down model "no longer accepts requests through the standard API" (S2 L111). In some cases, OpenAI says, developers may be able to get dedicated capacity for continued access after the shutdown date; the page says to contact its sales team to explore this (S2 L180).

## Disagreements
None found on the same point in the parts read (S1 L1–64; S2 L103–115, L170–191); the notice minimums differ (S1 L36; S2 L176–178), which we read as a difference, not a conflict.

## Gaps
- Kinds of sources or topics without a source: none (table.md; contract.md).
- Not read: S1 lines 65–235 (model status table, deprecation history, API parameter deprecations); S2 lines 117–169 and 193–335 (lists of upcoming, feature and endpoint, fine-tuning and past deprecations); and S2's search box, menus and chat button other than the menu entry at L63 (lines 1–62, 64–102 and 336–339) (S1 and S2 records).
- Logged and not read: Anthropic's post on its deprecation commitments and its migration guides (leads L2, L3), and an OpenAI post about ChatGPT (leads L5).
```

### outlines.md

```markdown
| # | S1 Anthropic, Model deprecations (read: lines 1–64) | S2 OpenAI, Deprecations (read: lines 63, 103–115, 170–191) |
|---|---|---|
| 1 | (opening, no heading; our label) L7 | Overview L103 |
| 2 | Overview L11 | Model deprecation notice periods L170 |
| 3 | Migrating to replacements L26 | Best practices L182 |
| 4 | Notifications L34 | Migration guidance L187 |
| 5 | Auditing model usage L38 | |
| 6 | Best practices L48 | |
| 7 | Deprecation downsides and mitigations L55 | |
```

### table.md

```markdown
| Topic | S1 Anthropic docs | S2 OpenAI docs |
|---|---|---|
| T1 Notice before retirement | section L34–36 (also mention L7, L24) | section L170–180 (also mention L105) |
| T2 What API users are told to do | section L26–32, L38–53 | section L182–191 |
| T3 What happens to a retired model | section L55–63 (also mention L18) | mention L111, L180 |

Sources by kind (each source counted once, under the kind the contract gives it):
API documentation: 2 (S1, S2).
```

### delivery-note.md

```markdown
# Delivery note: how Anthropic and OpenAI retire old API models

Files (contract v1): diagrams/1-notice.md (read it first), report.md, outlines.md, table.md.
Coverage passed: 5 leads, none open; 2 searches for what was missed.
Quotes passed: 18 quotations in the shipped files, 18 found in the saved originals.
Content passed: 52 of 52 content rows supported; of 4 findings, 3 were fixed and
re-checked, and 1 was wrong and withdrawn by its checker.
Closure passed: the 8 claims of this note match checks.md and leads.md.
Gaps: parts of both pages were not read, and three leads were logged without being read
(report, Gaps; leads L2, L3, L5).
Process problems: none.
Usage: 1 hour; 1 helper and 2 checkers; 2 pages captured; no money spent (no paid tools).
```

### checks.md

```markdown
# Checks, contract v1

| Shipped file | SHA-256 | Written by |
|---|---|---|
| diagrams/1-notice.md | 018b164aa32ab236b89c7020c4a2fe69beb8f77046c9f484c1b0e462071afb50 | lead |
| report.md | 3cc14eb14673795896d2867c2f4df9ffe70f628d2ce3d2dfd785a220c8cb44d7 | lead |
| outlines.md | edee92797dcc14c9724ed0f40db9ad8e42dc378d3124828c24b3c46e43bb52a1 | helper H1 |
| table.md | 633fc7d217c52da2e54c0bb3f44d90a56a46eac36d7dacb79bcd91ec84791a28 | lead |
| delivery-note.md | eb7cef5317f304b9f760c699d5243b79799b61e0d489f4c3c63cb28cc7f24c57 | lead |

| Check | Ran by (did not write) | Result on the hashes above |
|---|---|---|
| Coverage | C1 (did not search) | Pass. API documentation: S1, S2. T1–T3 each have a source. Leads: 5, none open. Search for what was missed: 2 queries (below). |
| Quotes | a run script, then C1 for the misses | Pass. 18 quotations in the shipped files, 18 found in the saved originals. No translation inside quotation marks. |
| Content | C1 (wrote no shipped file) | Pass after one repair round: all 52 content rows below are supported. 4 findings: 3 applied and re-checked, 1 withdrawn by C1. |
| Closure | C2 (did not write the note) | Pass. Searched the run folder and worker notes for open lists: 0 open. H1, C1 and C2 finished. The note's 8 claims match the records (N1–N8). |

Queries for what was missed (C1, 2026-11-17):
- Anthropic API model deprecation: S1 again (lead L4).
- OpenAI model retirement: the ChatGPT retirement post (lead L5).

Content rows, one per diagram label (D), report statement (R), outline item (O) and table cell (T):
| Row | Shipped text | Locator | Verdict |
|---|---|---|---|
| D1 | diagram title: minimum notice, as each page states it | S1 L36; S2 L174–178 | supported |
| D2 | capture date; one block is about one week, our conversion | S1 and S2 receipts; 26, 13, 9 and 2 blocks for 6 months, 3 months, 60 days and 2 weeks | supported; marked as ours |
| D3 | OpenAI, generally available models: 26 blocks, At least 6 months | S2 L176 | supported |
| D4 | OpenAI, specialized variants of generally available models, and image generation models: 13 blocks, At least 3 months | S2 L177 | supported after F3 |
| D5 | Anthropic, publicly released models: 9 blocks, at least 60 days' notice, to customers with active deployments (note 1) | S1 L36 | supported |
| D6 | OpenAI, preview models: 2 hatched blocks, such as 2 weeks | S2 L178 | supported after F2 |
| D7 | OpenAI emails customers actively using the model; its minimums hold unless safety or compliance needs a faster timeline | S2 L172, L174 | supported |
| D8 | note 1: notice goes to customers with active deployments; dates apply to Anthropic-operated platforms; partners set their own | S1 L36, L24 | supported |
| D9 | note 2: hatched means an example, not a minimum | S2 L178 | supported |
| R1 | describe only, contract v1 | contract.md | supported |
| R2 | S1 is Anthropic's Model deprecations, API documentation; no publication date found for the page | S1 L1–5; S1 record | supported |
| R3 | S2 is OpenAI's Deprecations, API documentation; no publication date found for the page | S2 L63; S2 record | supported |
| R4 | both pages captured on 2026-11-17; the parts read are listed in each record | S1 and S2 receipts and records | supported |
| R5 | both pages: affected customers told by email and in the documentation | S1 L7; S2 L105 | supported |
| R6 | minimum notice differs by provider and by kind of model | S1 L36; S2 L176–178 | supported |
| R7 | Anthropic: at least 60 days, publicly released models, to customers with active deployments | S1 L36 | supported |
| R8 | dates apply to Anthropic-operated platforms; partners set their own | S1 L24 | supported |
| R9 | OpenAI: emails customers actively using the model; unless safety or compliance; 6 months for generally available models; 3 months for specialized variants of generally available models and for image generation models | S2 L172, L174, L176, L177 | supported after F1 and F3 |
| R10 | OpenAI preview models: much shorter notice, such as 2 weeks | S2 L178 | supported |
| R11 | Anthropic: migrate before retirement; test well before; usage export by API key and model | S1 L28, L30, L51, L40–44 | supported |
| R12 | OpenAI: run representative requests; compare outputs, latency and cost | S2 L191 | supported |
| R13 | OpenAI: optional shutdown_date field from the List models endpoint | S2 L185 | supported |
| R14 | Anthropic: requests to retired models fail | S1 L18 | supported; F4 withdrawn |
| R15 | Anthropic has committed to long-term preservation of model weights; links a post | S1 L63; leads L2 | supported |
| R16 | OpenAI: a shut-down model no longer accepts requests through the standard API | S2 L111 | supported |
| R17 | OpenAI: dedicated capacity in some cases; contact sales to explore | S2 L180 | supported |
| R18 | no disagreement on the same point in the parts read; the different minimums read as a difference, labelled as our reading | S1 L1–64; S2 L103–115, L170–191; S1 L36; S2 L176–178 | supported; the reading is labelled |
| R19 | gaps: no kind of source or topic without a source | table.md; contract.md | supported |
| R20 | gaps: lines not read in S1 and S2, S2's menus and chat button included | S1 and S2 records | supported |
| R21 | gaps: leads logged and not read | leads L2, L3, L5 | supported |
| O1 | S1 column head and lines read | S1 L2; S1 record | supported |
| O2 | S2 column head and lines read | S2 L63; S2 record | supported |
| O3 | S1 (opening, no heading; our label) L7 | S1 L7 | supported; the label is marked as ours |
| O4 | S1 Overview L11 | S1 L11 | supported |
| O5 | S1 Migrating to replacements L26 | S1 L26 | supported |
| O6 | S1 Notifications L34 | S1 L34 | supported |
| O7 | S1 Auditing model usage L38 | S1 L38 | supported |
| O8 | S1 Best practices L48 | S1 L48 | supported |
| O9 | S1 Deprecation downsides and mitigations L55 | S1 L55 | supported |
| O10 | S2 Overview L103 | S2 L103 | supported |
| O11 | S2 Model deprecation notice periods L170 | S2 L170 | supported |
| O12 | S2 Best practices L182 | S2 L182 | supported |
| O13 | S2 Migration guidance L187 | S2 L187 | supported |
| O14 | completeness: the lines read hold these headings and no others, in this order | S1 L1–64: L11, L26, L34, L38, L48, L55; S2 L103–115, L170–191: L103, L170, L182, L187 | supported |
| T1 | column heads S1 Anthropic docs, S2 OpenAI docs; row heads are the contract's topics | S1 and S2 records; contract.md | supported |
| T2 | T1 × S1: section L34–36 (also mention L7, L24) | S1 L34–36; L7, the opening; L24, a line in the Overview section | supported |
| T3 | T1 × S2: section L170–180 (also mention L105) | S2 L170–180; L105, a line in the Overview section | supported |
| T4 | T2 × S1: section L26–32, L38–53 | S1 L26–32, L38–53 | supported |
| T5 | T2 × S2: section L182–191 | S2 L182–191 | supported |
| T6 | T3 × S1: section L55–63 (also mention L18) | S1 L55–63; L18, a line in the Overview section | supported |
| T7 | T3 × S2: mention L111, L180 | S2 L111, L180 | supported |
| T8 | API documentation: 2 (S1, S2), grouped by the contract's kind | contract.md; S1 and S2 records | supported |

Findings:
| ID | File, place | Problem | Evidence | Fix | Decision, by whom | Re-check |
|---|---|---|---|---|---|---|
| F1 | report.md T1 | Draft: OpenAI gives at least 6 months' notice. Missing condition. | S2 L174, L176: only generally available models, and not when safety or compliance needs a faster timeline | the T1 paragraph as shipped; the old wording, gives at least 6 months' notice, searched in the five shipped files: 0 left | applied by the lead | C1 on report.md as hashed above: pass |
| F2 | diagram 1, preview bar | Drawn solid, like a minimum. The mark does not match the legend, and it says more than the source. | S2 L178: 2 weeks is an example | hatched bar and note 2; a mark changed, not words, so there was no old wording to search; row D6 checks the new mark | applied by the lead | C1 on diagrams/1-notice.md as hashed above: pass |
| F3 | diagram 1, second bar; report.md T1 | Draft: specialized variants, image models, at least 3 months. Missing condition. | S2 L177: specialized variants of generally available models | the label and the T1 sentence as shipped; the old wording, specialized variants, image models, searched in the five shipped files: 0 left | applied by the lead | C1 on both files as hashed above: pass |
| F4 | report.md T3 | C1: locator S1 L18 is wrong; the sentence is at L28. | S1 L18 holds the quoted sentence word for word; L28 is a different sentence about requests after the retirement date | none | withdrawn by C1, its checker, after reading S1 L18 and L28 | — |

The note's claims, compared with the records (Closure, C2):
| Row | Claim in delivery-note.md | Record | Verdict |
|---|---|---|---|
| N1 | the four files, contract v1, diagram first | shipped-file table above; contract.md | matches |
| N2 | Coverage passed: 5 leads, none open; 2 searches for what was missed | Coverage row; leads.md; the two queries | matches |
| N3 | Quotes passed: 18 quotations, 18 found | Quotes row | matches |
| N4 | Content passed: 52 of 52 rows supported; 4 findings, 3 fixed and re-checked, 1 withdrawn by its checker | Content row; content rows; F1–F4 | matches |
| N5 | Closure passed: the note's 8 claims match the records | this table, N1–N8 | matches |
| N6 | parts of both pages not read; three leads logged without being read | S1 and S2 records; leads L2, L3, L5 | matches |
| N7 | process problems: none | the usage line below | matches |
| N8 | 1 hour; 1 helper and 2 checkers; 2 pages captured; no money spent | the worker table and the usage line below | matches |

| Worker | Role | Final state |
|---|---|---|
| H1 | captured S1 and S2, wrote outlines.md | finished; no finding touched its file |
| C1 | coverage, quotes and content checks | finished after the re-checks |
| C2 | closure check | finished |

Usage: 1 hour; 2 pages captured (S1, S2); no money spent (no paid tools). Process problems: none.
Delivered: 2026-11-17, a message to the requester with the paths of the five files;
sha256sum of the five files at delivery gave the values in the first table.
```
