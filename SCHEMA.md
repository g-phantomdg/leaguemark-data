# Leaguemark Schema

**Version 1.0** · Published 1 November 2026 · Read with the Leaguemark Rulebook v1.0.1
Licence: © Leaguemark, all rights reserved; covered by the data use and citation policy (until it is published, contact hello@leaguemark.io before reusing anything here) · Repository: github.com/leaguemark/leaguemark-data

This schema lists the records Leaguemark keeps about the business of NBA Europe, the fields on each, and the exact field names we use. The change log records every change under one of these field names, so the same kind of fact is always filed the same way. The IDs, statuses and sourcing rules are set by the Rulebook; this document doesn't repeat them.

Fields marked **v1** are collected now. Fields we plan to add later are listed in section 6 and are not part of this version.

---

## 1. How a value is stored

Every published value carries the same envelope:

| Part | Meaning | Format |
|---|---|---|
| Value | The fact itself | As set out for the field below |
| Status | Confirmed, Reported, Not yet announced, Unknown or Not applicable (Rulebook section 1) | Text |
| Source URL | The original source | URL |
| Source type | Official, Press, Filing, Social or Job posting | Text |
| Originating outlet | Who first reported it | Outlet ID (OUT-001…) |
| First seen | When we first logged the value | Date (Lisbon) |
| Last verified | When we last checked it against a source | Date (Lisbon) |
| Log ID | The change-log row that set it | CL-00001… |

**Formats used throughout:**
- IDs: as in Rulebook section 7. A field that points to another record holds that record's ID.
- Dates: ISO 8601 (2026-11-01). Timestamps: ISO 8601 in UTC.
- Money: an amount, its currency (ISO 4217, such as EUR or USD) and the date it applies to. We never convert or estimate a figure on public pages; a figure is always the one the source gives.
- Edition: the season a per-season record belongs to. The 2027 edition covers the build phase and the 2027–28 season.
- One value per row: a field that can hold several values (bidders, other tenants) is logged one value per change-log row.

**Field type** in the tables below is the verification field type from Rulebook 4.6, which decides who may verify a value.

## 2. Record types

| Record type | ID | One record per | Lasts |
|---|---|---|---|
| League | NBE-LEAGUE | The league | Permanent |
| Market slot | NBE-<CITY> | Permanent city place in the league | Permanent |
| Team | TM-0001 | Team, permanent or rotating | Permanent |
| Company | CO-<NAME> | Company, club, investor vehicle, brand or agency | Permanent |
| Person | PE-0001 | Person | Permanent |
| Arena | AR-<NAME> | Arena | Permanent |
| Team season | (team ID + edition) | Team per edition | Per edition |
| Ownership stake | (team ID + investor ID + edition) | Investor in a team per edition | Per edition |
| Role | (person ID + organisation ID + title) | Person in a role | Start to end date |
| Partnership | (organisation ID + partner ID + category + edition) | Commercial deal per edition | Per edition |

A **market slot** is the permanent place for a city (NBE-LON for London). It exists before any team does, and carries the bidding and award process. A **team** gets its own ID once it exists, and keeps it if its name, owner or arena changes. Rotating teams have no market slot; their place in the league is recorded season by season in Team season.

## 3. Permanent records

### 3.1 League (NBE-LEAGUE)

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| Launch date | When the first season starts | Date | Date |
| Number of teams | Total, permanent and rotating places | Number, per kind | League structure / rules |
| Qualification route | How rotating places are won | Text | League structure / rules |
| Market slots | The permanent city places | Market slot IDs | League structure / rules |
| Ownership split | Shares held by NBA team owners and by the permanent team owners | Percent, per holder | League structure / rules |
| Loss funding | Who funds start-up losses, and for how long | Text | League structure / rules |
| Franchise fee sharing | How franchise fees are distributed | Text | League structure / rules |
| Sale process | How franchises are sold (order, method) | Text | League structure / rules |
| Sale adviser | Bank or firm running the sale; one per row | Company ID | Other |
| Award timing | When franchise awards are expected or due | Date or text | Date |
| Media rights partner | Broadcaster or platform; one per row | Company ID | Sponsor / partner |
| Negotiation | A negotiation with another organisation, and its current state | Organisation ID + text | League structure / rules |
| Offer | Terms of an offer made or received | Organisation ID + text, money where stated | Valuation / deal terms |
| Projection | A figure or outcome the league has projected | Text, money where stated; always an attributed statement | Statement |

### 3.2 Market slot (NBE-<CITY>)

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| City | | Text | Other |
| Country | | ISO 3166 country code | Other |
| Time zone | | IANA time zone (Europe/London) | Other |
| Franchise status | Where the city's franchise stands | Bidding, Front-runner identified, Awarded, Ratified, Active | League structure / rules |
| Bidder | A person, company or group bidding for the franchise; one per row | Person or company ID | Bidder / consortium |
| Front-runner | The bidder reported or announced as preferred | Person or company ID | Bidder / consortium |
| Franchise fee | Price paid or offered for the franchise | Money | Valuation / deal terms |
| Award date | When the franchise was awarded | Date | Date |
| Ratification date | When the owner was approved by the league | Date | Date |
| Team | The team that holds the slot | Team ID | League structure / rules |
| Same-country rival | The other slot in the same country | Market slot ID | Other |
| Metro population | | Number, with year | Figure |
| Other pro teams | Professional teams in the city, all sports; one per row | Company ID | Other |

### 3.3 Team (TM-0001)

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| Market slot | The slot a permanent team holds | Market slot ID | League structure / rules |
| Team name | Full name, kept by edition | Text | Other |
| Short name | | Text | Other |
| Abbreviation | | Text | Other |
| Colours | Primary and secondary | Hex codes | Other |
| Logo link | Link to the official logo (we don't host logo files) | URL | Link health / archive |
| Website | | URL | Link health / archive |
| Social account | One per row | URL | Link health / archive |
| Predecessor club | A club the team grew out of; one per row | Company ID + relationship (relocated, rebranded, merged, new) | Other |
| EuroLeague licence status | The predecessor club's EuroLeague position | Text | League structure / rules |
| Domestic league | Domestic league the club also plays in | Text | League structure / rules |
| Crosswalk codes | See section 5 | | Registry fact |

### 3.4 Company (CO-<NAME>)

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| Name | Registered or trading name | Text | Registry fact |
| Country | | ISO 3166 country code | Registry fact |
| Company kind | Club, private equity, family office, investment vehicle, brand, agency, broadcaster, league body, other | Text | Other |
| Agency services | For agencies and suppliers: services offered; one per row | Text | Sponsor / partner |
| Other sports assets | Other teams or leagues it owns stakes in; one per row | Company ID or text | Owner |
| Negotiation | As for League | Organisation ID + text | League structure / rules |
| Offer | As for League | Organisation ID + text, money where stated | Valuation / deal terms |
| Projection | As for League | Text; always an attributed statement | Statement |
| Plan | For a league body or club: an announced plan, format or expansion | Text, date where stated | League structure / rules |
| Member terms | For a league body: terms that bind its member clubs (licences, franchise agreements, exit terms) | Text, money where stated | Valuation / deal terms |
| Crosswalk codes | See section 5 | | Registry fact |

### 3.5 Person (PE-0001)

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| Name | | Text | Person / role |
| Public profile link | Official or professional profile; one per row | URL | Link health / archive |
| Other sports assets | For investors; one per row | Company ID or text | Owner |

We hold public professional information only: name, role, employer, dates and public profile links. No personal contact details, home addresses or dates of birth.

### 3.6 Arena (AR-<NAME>)

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| Name | | Text | Other |
| Naming-rights partner | | Company ID | Sponsor / partner |
| Basketball capacity | | Number | Figure |
| Owner | | Company ID | Owner |
| Operator | | Company ID | Other |
| Other tenant | One per row | Company ID | Other |
| Arena kind | Existing, temporary or new build | Text | Other |
| Opening year | | Year | Date |
| Address and location | | Text, latitude and longitude | Other |
| Training facility | | Text | Other |

## 4. Per-edition records

### 4.1 Team season

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| League status | Permanent, Rotating or Not in league this edition | Text | League structure / rules |
| Qualification route | For rotating teams: how the place was won | Text | League structure / rules |
| Home arena | | Arena ID | Other |
| Franchise fee paid | | Money | Valuation / deal terms |
| Reported value | A published estimate of the team's value, with its publisher and date; never our own | Money + outlet ID + date | Valuation / deal terms |
| Payroll position | Once salary rules are published | Money or text | Figure |

### 4.2 Ownership stake

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| Investor | | Person or company ID | Owner |
| Investor role | Controlling, lead, minority, or celebrity / athlete investor | Text | Owner |
| Stake | Share held | Percent | Owner |
| Investor kind | Football club, private equity, family office, individual, athlete, former NBA owner | Text | Owner |
| Entry date | | Date | Date |
| Ratification date | | Date | Date |

### 4.3 Role

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| Organisation | Where the role is held | Team, company or league ID | Person / role |
| Title | As the organisation states it | Text | Person / role |
| Role group | Owner, leadership, basketball operations, commercial | Text | Person / role |
| Start date | | Date | Date |
| End date | | Date | Date |
| Previous employer | | Company ID or text | Person / role |

### 4.4 Partnership

| Field name | Meaning | Format | Field type |
|---|---|---|---|
| Organisation | Who the deal is with | Team or league ID | Sponsor / partner |
| Partner | | Company ID | Sponsor / partner |
| Category | Bank, airline, auto, beverage, betting, tech and so on | Text | Sponsor / partner |
| Deal tier | Naming rights, jersey front, patch, official partner, supplier | Text | Sponsor / partner |
| Start date | | Date | Date |

## 5. Identifier crosswalk

Where they exist, these codes are linked to our IDs and published in the crosswalk file:

| Code | For | Example source |
|---|---|---|
| Companies House number | UK companies | Companies House |
| LEI | Companies with a Legal Entity Identifier | GLEIF |
| Wikidata ID | Any record with a Wikidata item | Wikidata |
| EuroLeague club code | Clubs in EuroLeague competitions | EuroLeague |

A crosswalk code is a registry fact with its own source. It never replaces our ID.

## 6. Not in this version

Added in a later version when subscribers or pilot agencies ask for them: deal values and end dates of partnerships; agencies that brokered deals; suppliers per service; hiring signals; follower history; revenue estimates; hospitality inventory; full staff charts and career histories; player records; a comparables table of franchise sales in other leagues.

Adding fields or record types is a clarification under Rulebook 8.2, because it can't change any existing row's status or score. Renaming or removing a field is a rule change.
