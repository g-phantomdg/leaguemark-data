# Leaguemark data

Public schema, IDs and weekly change-log hashes for **Leaguemark**, the dated record of who owns, pays for and runs new sports leagues. First edition: NBA Europe.

Website: https://leaguemark.io (launching 23 November 2026)

## What will be here

- **Schema:** the fields and the status scale (Confirmed, Reported, Rumoured) used in the Leaguemark database.
- **IDs and crosswalk:** Leaguemark IDs (for example `NBE-LON`) mapped to Companies House numbers, LEI codes, Wikidata IDs and EuroLeague club codes.
- **Weekly proofs:** each week, in `proofs/<date>/`, the SHA-256 hash of that week's manifest (`manifest.sha256`) and an independent OpenTimestamps proof of it (`manifest.txt.ots`). The manifest lists the hash of every private snapshot file, so anyone can later check the history was not edited after the fact (Rulebook section 9).

## Status

Pre-launch. The Rulebook ([RULEBOOK.md](RULEBOOK.md)) was published on 30 October 2026; v1.0.1 (1 November 2026) clarifies rule 9.2. The schema ([SCHEMA.md](SCHEMA.md), v1.0) was published on 1 November 2026. Weekly proofs start on 1 November 2026. The IDs and crosswalk will follow.

## Use and citation

The Rulebook may be reused under CC BY 4.0 (see Licence). For everything else here, a data use and citation policy will be published with the first release; until then, please contact hello@leaguemark.io before reusing it.

## Licence

The Rulebook (RULEBOOK.md) is licensed CC BY 4.0. All other files are © Leaguemark, all rights reserved, and covered by the data use and citation policy. Until it is published, please contact hello@leaguemark.io before reusing anything here.
