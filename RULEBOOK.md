# Leaguemark Rulebook

**Version 1.0.1** · Published 1 November 2026 · Applies to every record judged under Rules version v1.0.1. Version 1.0 differs only in the wording of rule 9.2 step 6 (see Changes)
Licence: this Rulebook text is CC BY 4.0. Data and other files in the repository are covered by our data use and citation policy. · Repository: github.com/leaguemark/leaguemark-data

This Rulebook sets out how Leaguemark decides what is true about the business of NBA Europe, how sure we are, and how anyone can check that we kept to these rules. It is fixed before the data it governs. Rules change only forward, under a new version number (section 8), and never after we have seen the results they would affect.

Every row in our change log and verification log records the Rules version it was judged under. A row judged under this version is judged by this text, even after later versions are published.

This Rulebook describes how we work. It is not a promise that any value is complete or correct, and nothing we publish is investment, legal or financial advice.

---

## 1. Statuses

Every value we hold has a status, a source and a last-verified date.

| Status | Meaning | Where it appears |
|---|---|---|
| **Confirmed** | Announced by the league, FIBA, the club or the company itself; or said on the record by a named official speaking for the organisation (rule 1.2); or, for the filing fact only, shown in a company registry filing | Site, downloads, data feed, brief |
| **Reported** | Reported by a credible outlet under the source rules in section 3 | Site, downloads, data feed, brief |
| **Rumoured** | A single or weak source that doesn't meet the bar for Reported | Email brief only, labelled "Rumoured, unconfirmed", with the source. Never on pages, in downloads or in the feed |
| **Not yet announced** | The value will exist (an owner for a city, a launch date) but has not been announced or reported | Site |
| **Unknown** | The value may exist, but no source we accept gives it | Site |
| **Not applicable** | The field doesn't apply to this record | Site |

Separately from its status, every claim we assess has a **review state**: *Draft* (not yet decided), *Approved* (decided and eligible to publish) or *Rejected* (assessed and not accepted, kept on file). Nothing is public until it is Approved and has a status, and Rumoured items are never public on the site even when Approved.

**1.1 When in doubt.** If a claim sits between Reported and Rumoured, it is Rumoured.

**1.2 On-record statements.** A statement by a named official, on the record and speaking for the organisation, is Confirmed when a journalist quotes or closely paraphrases it, provided the outlet is Tier 1 or Tier 2 (section 3). Unnamed officials, "sources say" and "people familiar with" are at most Reported.

**1.3 Paywalls.** Nothing rises above Rumoured on a headline or snippet alone. Reported needs the full article to have been read, or an open source carrying the same claim with attribution.

**1.4 Registry filings.** A filing confirms what it records (a company exists, an officer was appointed). Any link between that company and a franchise bid is a separate claim, judged on its own sources.

**Illustrations** (invented, to show how the rules apply):

| What we saw | Status | Rule |
|---|---|---|
| The league's press release names the owner for a city | Confirmed | Official announcement |
| A Tier 1 wire quotes a named league executive: "We will announce in mid-November" | Confirmed, as a statement | 1.2; and section 2 (attributed statement) |
| A Tier 1 newspaper says, citing unnamed people, that a consortium has bid for a city | Reported | 3.3 |
| A Tier 2 basketball site says the same, citing no source, and nobody else reports it independently | Rumoured | 3.3 |
| A club fan site says the same | Rumoured | 3.3 |
| Only a paywalled headline is available | Rumoured | 1.3 |

## 2. Claims

**2.1 One claim per row.** A claim is one checkable fact about one entity: one bidder for one city, one figure, one date. An article naming three bidders gives three rows. A row found to carry several claims is split before approval: the new rows are created and the original is Rejected with "split into CL-…" in its notes. It is never deleted.

**2.2 Facts and attributed statements.** Every row is one of two classes:
- **Fact:** the event or value itself (the owner is X; the fee is Y).
- **Attributed statement:** someone said or projected something ("the league projects X", "the chief executive said Y will happen"). The status applies to the attribution, not to X. A statement can be Confirmed as a statement while X remains unproven.

Attributed statements are not scored in the calibration bands (section 5), because they are true the moment they are said. Where the underlying event matters, it goes in our private, dated forecast log, or gets its own Fact row when it happens.

## 3. Sources

**3.1 Originating source.** For each claim we record the outlet that first reported it (the originating source) separately from outlets that only repeated it. Re-reports of one story count as one source, however many outlets carry it. Sister brands are separate outlets (credit goes to whoever broke the story). An event host is not an outlet: a statement made at a conference is credited to the outlet that reported it.

**3.2 Outlet tiers.** Every outlet we use has an ID (OUT-001…) and a tier:

| Tier | Who | What one report from it can support |
|---|---|---|
| **Tier 1** | Wires and major national news or sports organisations | Reported, once the article has been read |
| **Tier 2** | Basketball specialists, sports-business trade press, national sports sites | Reported only if the story names its source, or a second Tier 1 or Tier 2 outlet confirms the claim with its own reporting. Otherwise Rumoured |
| **Tier 3** | Fan sites, aggregators, partisan sites | Never above Rumoured on its own; a lead to follow up |
| **Not credible** | Reserved | Never above Rumoured |

An outlet we haven't placed yet is treated as Tier 3 until it is placed. Tiers are set by the editor and recorded with the Rules version they were set under. Placing a new outlet can happen at any time; moving an outlet that already has a tier is a rule change (section 8).

**3.3 Applying the tiers.** Reported needs either one Tier 1 originating report that we have read, or one Tier 2 originating report that names its source, or one Tier 2 report plus independent reporting from a second Tier 1 or Tier 2 outlet. A re-report of the same story is not independent reporting.

**3.4 Paywalled sources.** We cite the original first, with a one-line summary in our own words, credit and link, labelled "(paywall)", and add a free corroborating link when one exists. We never reproduce paywalled text. Paywalled article text stays out of our AI tools unless the subscription terms allow it. For archiving, a paywalled source is kept as metadata: URL, headline, byline, date, an attempted public archive capture and our own one-line note.

**3.5 Archiving.** Every open source is captured on the Internet Archive's Wayback Machine before its row is approved, and the archive link is stored on the row. Where we also keep a private evidence copy of a source, its SHA-256 fingerprint is stored on the row (section 9); the copy itself is never published.

## 4. Verification

**4.1 Who verifies.** Nothing goes live without verification, whoever or whatever drafted it. By default the editor verifies. AI agents draft, check and propose a status for every item and record their reasoning, the rule they applied and exactly what they saw. Judgement fields get a second, adversarial check by an agent before they reach the editor.

**4.2 Blind by design.** The agent's proposed status and probability are kept in a private verification log. The editor sets their status without seeing the proposal. The change log's status stays empty until the editor decides.

**4.3 Earned autonomy.** Agents may verify a field type (4.6) on their own only after they have matched the editor on at least 50 items of that type with no misses. Only these items count:
- blind decisions (the editor's status was set before the proposal was seen);
- live captures (items logged when they happened, not backfilled);
- items not on the always-the-editor's list (4.4).

Fifty matches with no misses still allows a true miss rate of up to about 6%, so the editor spot-checks agent-verified items every week. A miss found in a spot check returns that field type to the editor until it earns the threshold again.

When the AI model or the agent's instructions change, a field type that has earned autonomy re-qualifies on 20 blind items before it verifies alone again.

**4.4 Always the editor's.** These stay with the editor whatever the agents' record:
- owner, bidder and consortium membership;
- any call between Reported and Rumoured;
- valuations and deal terms;
- Day 0 alerts and weekly brief items;
- items whose only source is paywalled.

This list is reviewed at the month-3 scorecard review (section 5.8) and on 31 March 2027.

**4.5 The outcome route.** Judgement fields can also earn autonomy on outcomes rather than agreement: if the agents' calls for a field type meet every calibration band in section 5, with at least 20 resolved items in each band, that counts. The first review is at month 3; until a review grants it, judgement fields stay with the editor.

**4.6 Field types.** Autonomy is earned, and the scorecard is split, by field type:

| Field type | Covers | Example |
|---|---|---|
| Owner | Who owns or controls a team, and in what share | "Company X holds the majority stake in the London team" |
| Bidder / consortium | Who bid for a franchise, and who is in a bidding group | "Investor Y is part of the consortium bidding for Paris" |
| Registry fact | What a company registry filing records | "Company Z was incorporated on [date]" |
| Sponsor / partner | Commercial partners and their categories | "Brand A is the team's shirt sponsor" |
| Valuation / deal terms | Prices, fees, valuations and terms of a deal | "The entry fee is reported at [amount]" |
| Date | When something happened or is scheduled | "The league will announce teams on [date]" |
| Figure | Any other number (attendance, revenue, count) | "The arena seats [number]" |
| League structure / rules | Format, number of teams, qualification, governance | "Four places rotate by sporting merit" |
| Statement | An attributed statement (2.2) | "The commissioner said talks are close" |
| Link health / archive | Whether a source link works and its archive is captured | "The source URL resolves; Wayback capture taken" |
| Person / role | Who holds a role | "Person B is the team's chief commercial officer" |
| Other | Anything not covered above | — |

**4.7 Disagreements.** Whenever the editor's status differs from the agent's proposal, the editor records why, choosing one cause: *source misread, rule misapplied, rule unclear, missing context, paywall / access, claim not split, AI was right* or *other*. The causes feed a monthly review of the agents' instructions, tested on held-out past decisions before any change goes live.

## 5. Scorecard

The scorecard measures the system, not the person. It answers one question per status: does it mean what it says?

**5.1 Outcomes.** Every scored claim ends in one outcome, recorded with the source and date that settled it:
- **Confirmed later:** a source at Confirmed level supports the claim. For a claim that was already Confirmed, this means nothing at Confirmed level has contradicted it by its check-by date.
- **Contradicted:** a source at Confirmed level contradicts it.
- **Faded:** neither has happened by the check-by date.
- **Open:** the check-by date hasn't arrived.
- **Not scored:** an attributed statement (2.2), a duplicate, or a row Rejected because it was split.

**5.2 Check-by dates.** Each claim has its own check-by date:
- bid and ownership claims: the city's franchise award plus 30 days;
- everything else: 90 days after the event.

**5.3 Calibration bands.** For each status, the share of resolved claims that were Confirmed later must fall inside its band:

| Status | Share Confirmed later | If it falls outside |
|---|---|---|
| Confirmed | 95% or more | The on-record rule (1.2) is too loose |
| Reported | 75% or more | Claims are being promoted to Reported too easily |
| Rumoured | 25–65% | Above: claims that should be Reported are held back. Below: noise is being logged |
| Rejected | 20% or less | Rejections are too harsh |

Share Confirmed later = Confirmed later ÷ (Confirmed later + Contradicted + Faded). Open and Not scored claims are left out. Only Fact rows are scored.

**5.4 Small samples.** A band is judged only once 20 or more of its claims have resolved. Before that we show counts only ("6 of 7"), never a rate. Rates are always shown next to their counts.

**5.5 Splits.** Results are shown:
- by who verified (the editor, or an agent);
- by source access (open, paywalled read in full, paywalled headline only);
- by originating outlet (kept private until a decision at the month-3 review).

**5.6 Agents are scored too.** Every agent proposal is scored against the outcome, including proposals the editor overruled. Agents give a probability that the claim will prove true. To compare agents with the editor at status level, an agent's probability counts as:

| Probability | Counts as |
|---|---|
| 95% or more | Confirmed |
| 75–94% | Reported |
| 25–74% | Rumoured |
| under 25% | Rejected |

An agent has to reach a status's minimum to earn it, the same bar the band sets for that status.

**5.7 Speed.** Speed is measured from Event at (when the event was announced or first reported) to Published at (when we published it). Backfilled rows and rows whose event time is only known to the day or month are left out of speed figures.

**5.8 Fixed in advance.** These bands, windows and cut points are fixed in this version before any results exist. The first review is three months after public launch. Any change is a rule change under section 8, applies forward only, and starts a new scorecard period.

## 6. Corrections and updates

**6.1 The log is append-only.** Once a row is Approved it is never edited, except under 6.5. Every change, including a fix, is a new row that links to the row it affects.

**6.2 Kinds of change.**
- **Update / status change:** the world changed or new reporting arrived (an owner was named; a Reported claim was Confirmed). Not an error.
- **Correction:** we got it wrong: the value, status or source we published didn't match what the source said. The new row supersedes the old one and the correction appears in the public correction log.
- **Retraction:** we withdraw a published claim entirely. It appears in the public correction log with the reason.

**6.3 Changed after approval.** Before every weekly proof (section 9), we check that no Approved row's content has changed since approval and that every published status matches the editor's decision in the verification log. Any exception is listed in that week's manifest.

**6.4 What pages show.** Public pages show the current value, its status, source and last-verified date. The full history is kept in the change log and proven by the weekly hash.

**6.5 Legal removals.** These rules give way to the law. If we must remove or change personal data or other content, for example after a valid data protection request or a court order, we do so in the logs and in our private snapshots, including earlier ones. The weekly manifest records that a row was removed or changed for legal reasons, without repeating what it said.

## 7. IDs

**7.1 Our own IDs.** Every record has our own ID. IDs from our database software are never used in exports, URLs or files.

| ID | Used for | Example |
|---|---|---|
| NBE-LEAGUE | The league itself | NBE-LEAGUE |
| NBE-&lt;CITY&gt; | A market slot: the permanent place for a city, not the team that fills it | NBE-LON, NBE-MAN, NBE-PAR, NBE-LYO, NBE-BER, NBE-MUN, NBE-ROM, NBE-MIL, NBE-MAD, NBE-BAR, NBE-ATH, NBE-IST |
| TM-0001 | A team, permanent or rotating, numbered in the order we first record it | TM-0001 |
| CO-&lt;NAME&gt; | A company | CO-EUROLEAGUE |
| PE-0001 | A person, numbered in the order we first record them | PE-0001 |
| AR-&lt;NAME&gt; | An arena | AR-O2 |
| OUT-001 | An outlet | OUT-012 |
| CL-00001, VL-00001, FL-00001 | Change log, verification log and forecast log rows | CL-00024 |

Team and person IDs never come from a name, city or club code, so a club that renames or moves keeps its ID. A rotating team's league status is recorded season by season, not in its ID. Club codes (such as the EuroLeague code), company registry numbers, LEI codes and Wikidata IDs are linked to our IDs in the published identifier crosswalk. If a name-based ID is already taken, the new one gets a numeric suffix (CO-ATLAS-2).

**7.2 Stability.**
- An ID is never reused and never retired, except under 6.5.
- When two IDs turn out to be the same entity, the duplicate points to the survivor ("merged into"); the duplicate ID stays on file.
- An ID is **provisional** until the first change-log row about that entity is Approved. From then on it is **permanent**: anything we have published or hashed never changes ID. A provisional ID can be merged into another, but is never reused.

## 8. Versions and record keeping

**8.1 Rules versions.** Each change-log row records the Rules version in force when it was approved. Each verification-log row records the version in force when the editor decided. The agent's own instructions are versioned separately and recorded on every row the agent writes. Rows judged before this Rulebook was published are marked v0.

**8.2 How rules change.** Every change is recorded in our decision log before it applies, and applies forward only. Old rows are never rewritten; a re-judgement is a new row.

After public launch, changes are released at two speeds:
- **Clarifications** (wording, examples, export steps, field descriptions) are released monthly at most, as v1.0.1, v1.0.2 and so on. They cannot change any row's status or score, so they don't split the scorecard.
- **Rule changes** (status definitions, outlet tiers, bands, autonomy thresholds, scorecard method) are released quarterly at most, as v1.1, v1.2 and so on, starting at the month-3 review. Each starts a new scorecard period.
- **Urgent fixes** can be released at any time, labelled with the reason: a rule producing wrong public statuses, or a change our legal advice requires.

The test for which is which: could the change alter any row's status or score? If yes, it is a rule change.

Before public launch, changes are released as needed, each recorded in the decision log.

**8.3 Capture.** Every row records whether it was captured live (logged when it happened) or backfilled (logged after the fact). Our record starts on 19 October 2026; earlier events were logged after the fact and are marked as backfill. Backfilled rows never count toward speed figures or agent autonomy.

**8.4 Time.** Timestamps are recorded and exported in UTC (ISO 8601). Date-only fields are Lisbon dates. Where only the date or month of an event is known, that is recorded alongside the placeholder time.

**8.5 Rejected claims.** Every claim we assess gets a row, including the ones we reject. Rejected rows are never deleted, except under 6.5: they are what makes the Rejected band (5.3) measurable.

## 9. Proof of history

Each week we publish a proof that our private records existed in their exact form on that date, so anyone can check later that the history wasn't rewritten.

**9.1 What is covered.** The change log, verification log, forecast log, verification-hours log and decision log, plus this Rulebook.

**9.2 Steps.**
1. Export each table from its fixed export view: all fields, sorted by row number, no filters. The same data always gives the same file.
2. Compute the SHA-256 hash of each file.
3. Write a manifest listing each file and its hash, the previous week's manifest hash and the Rulebook version in force.
4. List in the manifest any row approved before last week's proof whose content has changed since (6.3), and any removal or change made under 6.5.
5. Hash the manifest and take an independent OpenTimestamps proof of it.
6. Commit the exact files to our private repository, and the manifest hash and timestamp proof to this public repository. This public repository is protected against history rewrites. Access to the private repository is restricted, and if any file in it were changed, it would no longer match the hashes in the manifest, whose own hash and timestamp proof are published here. Commits are signed. The only exception is a removal under 6.5, which is recorded in the next manifest.

Because each manifest includes the previous week's hash, a missing or redone week is visible.

**9.3 Evidence copies.** Where we keep a private evidence copy of an open source, or of a paywalled source whose licence allows it, its SHA-256 fingerprint is stored on the row and so is covered by the weekly proof. The copy itself stays private.

## 10. Record start

No change-log row was approved and no weekly proof was published until this Rulebook and our record-keeping setup were in place. The first manifest says so and names the Rulebook version it starts under.

One exception was allowed: if a franchise award, owner ratification or EuroLeague defection had happened before that point, its row could be approved under v0, and the first manifest would name it.

## Changes

- **v1.0.1 (1 November 2026), clarification (rule 8.2):** rule 9.2 step 6 now says how each repository is protected. No status, score or ID changes.
- **v1.0 (30 October 2026):** first published version.
