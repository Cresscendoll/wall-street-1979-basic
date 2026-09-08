# NASDAQ/NMS 1984 MARKET VALUE LEADERS
## Canonical verified historical dataset pack for the BASIC project

**Purpose:** replace the current Fortune 1979 dataset with a stronger historical stock-market dataset that actually contains market value for all 100 ranked securities.

**Recommended application identity:**  
`NASDAQ/NMS TOP 100 — 1984 MARKET VALUE LEADERS`

**Dataset size:** 100 companies  
**Ranking basis:** market value  
**Historical year shown by source:** 1984  
**Source market-value coverage:** 100 / 100  
**Source shares-outstanding coverage:** 100 / 100  
**Derived implied-price coverage:** 100 / 100  

---

# 1. WHY THIS DATASET IS BETTER FOR THIS PROJECT

The earlier Fortune 1979 dataset was historically useful, but it ranked companies by revenue. It did not provide a complete historical stock-price or market-cap dataset, so the application had to display zero verified price and market-cap records.

During a new research pass, a substantially better historical source was found:

> **“100 NASDAQ/NMS MARKET VALUE LEADERS — 1984”**

The table is preserved inside the official archival record of the **Montana State Senate, Business & Industry Committee, February 14, 1985**. The preserved table contains 100 ranked NASDAQ/NMS companies and provides, for each row:

- company;
- market value;
- shares outstanding;
- rank by market value.

This means the BASIC application can now be built around **real historical stock-market valuation data for all 100 rows** rather than around corporate revenue.

This is a better thematic fit for a “Wall Street / stock monitor” application.

---

# 2. CRITICAL HISTORICAL LABELING RULE

This dataset must **NOT** be called the “NASDAQ-100 Index 1984.”

The Nasdaq-100 Index did not launch until **January 31, 1985**.

The historically correct label for this dataset is the wording used by the source:

> **100 NASDAQ/NMS MARKET VALUE LEADERS — 1984**

Recommended application wording:

`NASDAQ/NMS TOP 100`  
`1984 MARKET VALUE LEADERS`

or:

`NASDAQ/NMS MARKET MONITOR — 1984`

Do not present this as the official Nasdaq-100 index roster.

---

# 3. SOURCE PROVENANCE

## Primary archival source

Official Montana government archive:

`https://courts.mt.gov/external/leg/1985/senate/02-14-sbus.pdf`

Document:

`MINUTES OF THE MEETING — BUSINESS & INDUSTRY COMMITTEE — MONTANA STATE SENATE — February 14, 1985`

The historical table appears in the committee exhibits around PDF scan pages 44–45 and is headed:

`100 NASDAQ/NMS MARKET VALUE LEADERS`  
`1984`

The table has columns for:

- Symbol
- Company Name
- Market Value
- Shares Outstanding

The surrounding 1985 committee materials concern NASDAQ/NMS and include correspondence/material from securities-industry participants including the National Association of Securities Dealers.

## Supporting historical context

Contemporary material in the same archival record describes NASDAQ/NMS as a national computerized securities market and states that the NASDAQ National Market System was a segment of NASDAQ subject to SEC/NASD criteria.

For modern confirmation that the *Nasdaq-100 Index* itself only launched on January 31, 1985:

`https://www.nasdaq.com/newsroom/what-is-the-nasdaq-100-guide-to-one-of-worlds-most-watched-indexes`

---

# 4. DATE SEMANTICS

The preserved source table is labeled **1984**, but the table itself does not state a precise trading-day snapshot such as `1984-12-31`.

Therefore:

### Allowed
- `1984 MARKET VALUE`
- `1984 NASDAQ/NMS MARKET VALUE LEADERS`
- `SOURCE YEAR: 1984`

### Not allowed without another primary source
- `DECEMBER 31, 1984 CLOSE`
- `12/31/1984 MARKET CAP`
- any other exact quote date

The application should preserve the source's actual level of precision.

---

# 5. WHAT “VERIFIED” SHOULD MEAN IN THE APP

The boot screen should no longer say:

`PRICE TABLE ..... 0 VERIFIED / 100 UNAVAILABLE`  
`MCAP TABLE ...... 0 VERIFIED / 100 UNAVAILABLE`

For this new dataset, use counters that reflect what the source actually supplies:

```text
NASDAQ/NMS TABLE .... 100 VERIFIED / 100 TOTAL
MARKET VALUE ........ 100 VERIFIED / 100 TOTAL
SHARES OUTSTANDING .. 100 VERIFIED / 100 TOTAL
IMPLIED PRICE ....... 100 DERIVED  / 100 TOTAL
INDEX ............... READY
```

The distinction between **VERIFIED** and **DERIVED** is important.

- Market Value = historical source field.
- Shares Outstanding = historical source field.
- Implied Price = arithmetic calculation from the two source fields.

Formula:

`IMPLIED PRICE = MARKET VALUE / SHARES OUTSTANDING`

The implied price must **not** be labeled as an independently verified historical closing quote.

Recommended label:

`IMPLIED $/SHARE`

or:

`DERIVED $/SHARE`

---

# 6. DATASET QA SUMMARY

Canonical row count: **100**

Market-value ordering is strictly non-increasing from rank 1 through rank 100.

Key sentinels:

- Rank 1: Intel Corporation
- Rank 2: MCI Communications Corporation
- Rank 3: Apple Computer, Inc.
- Rank 50: Betz Laboratories, Inc.
- Rank 51: Network Systems Corporation
- Rank 100: Ogilvy & Mather International Inc.

Derived statistics for the 100-row table:

- Combined market value: **$61,179,563,000**
- Combined market value: **$61.180 billion**
- Average company market value: **$611.796 million**
- Median company market value: **$498.680 million**
- Top 10 combined market value: **$15.372 billion**
- Top 10 share of this 100-company market-value pool: **25.13%**

These aggregate values are derived from the 100 transcribed source rows.

---

# 7. CANONICAL 100-ROW DATASET

`Source market value` and `Shares outstanding` are historical source fields.

Columns marked `*` are derived arithmetic fields added for application usefulness.

| Rank | Company | Source market value | Shares outstanding | Implied $/share* | Share of Top-100 pool* |
|---:|---|---:|---:|---:|---:|
| 1 | Intel Corporation | $3,178,140,000 | 112,501,000 | $28.25 | 5.195% |
| 2 | MCI Communications Corporation | $1,806,057,000 | 240,808,000 | $7.50 | 2.952% |
| 3 | Apple Computer, Inc. | $1,763,081,000 | 61,325,000 | $28.75 | 2.882% |
| 4 | Farmers Group, Inc. | $1,680,624,000 | 33,866,000 | $49.63 | 2.747% |
| 5 | Intergraph Corporation | $1,413,555,000 | 25,937,000 | $54.50 | 2.311% |
| 6 | Safeco Corporation | $1,226,814,000 | 37,037,000 | $33.12 | 2.005% |
| 7 | Roadway Services, Inc. (The) | $1,211,155,000 | 40,372,000 | $30.00 | 1.980% |
| 8 | St. Paul Companies, Inc. (The) | $1,074,859,000 | 20,044,000 | $53.62 | 1.757% |
| 9 | Pioneer Hi-Bred International, Inc. | $1,013,650,000 | 31,926,000 | $31.75 | 1.657% |
| 10 | PNC Financial Corp. | $1,004,279,000 | 22,072,000 | $45.50 | 1.642% |
| 11 | Price Company (The) | $934,538,000 | 22,724,000 | $41.13 | 1.528% |
| 12 | American Greetings Corporation | $880,956,000 | 27,856,000 | $31.63 | 1.440% |
| 13 | Allied Bancshares, Inc. | $874,543,000 | 40,914,000 | $21.38 | 1.429% |
| 14 | Digital Switch Corporation | $871,987,000 | 39,862,000 | $21.88 | 1.425% |
| 15 | American National Insurance Company | $869,220,000 | 28,854,000 | $30.12 | 1.421% |
| 16 | PACCAR Inc. | $807,111,000 | 18,138,000 | $44.50 | 1.319% |
| 17 | Tandem Computers Incorporated | $793,794,000 | 40,192,000 | $19.75 | 1.297% |
| 18 | Consolidated Papers, Inc. | $767,181,000 | 21,919,000 | $35.00 | 1.254% |
| 19 | Tele-Communications, Inc. | $767,087,000 | 32,993,000 | $23.25 | 1.254% |
| 20 | Trust Company of Georgia | $762,731,000 | 23,835,000 | $32.00 | 1.247% |
| 21 | Subaru of America, Inc. | $693,712,000 | 6,085,000 | $114.00 | 1.134% |
| 22 | Shoney's, Inc. | $674,751,000 | 21,336,000 | $31.62 | 1.103% |
| 23 | Gulf Broadcast Company | $673,271,000 | 113,437,000 | $5.94 | 1.100% |
| 24 | CoreStates Financial Corporation | $668,670,000 | 15,069,000 | $44.37 | 1.093% |
| 25 | Alexander & Baldwin, Inc. | $662,519,000 | 18,403,000 | $36.00 | 1.083% |
| 26 | Philips (NV) Gloeilampen | $658,719,000 | 42,498,000 | $15.50 | 1.077% |
| 27 | Shared Medical Systems Corporation | $658,638,000 | 24,170,000 | $27.25 | 1.077% |
| 28 | Sovran Financial Corporation | $656,161,000 | 16,988,000 | $38.62 | 1.073% |
| 29 | First Union Corporation | $646,489,000 | 18,876,000 | $34.25 | 1.057% |
| 30 | Apollo Computer Inc. | $622,277,000 | 31,114,000 | $20.00 | 1.017% |
| 31 | Citizens and Southern Georgia Corporation | $621,444,000 | 32,073,000 | $19.38 | 1.016% |
| 32 | Kemper Corporation | $621,118,000 | 14,238,000 | $43.62 | 1.015% |
| 33 | Multimedia, Inc. | $612,291,000 | 16,661,000 | $36.75 | 1.001% |
| 34 | ServiceMaster Industries Inc. | $585,954,000 | 21,307,000 | $27.50 | 0.958% |
| 35 | Molex Incorporated | $579,304,000 | 19,976,000 | $29.00 | 0.947% |
| 36 | Nordstrom, Inc. | $576,135,000 | 18,436,000 | $31.25 | 0.942% |
| 37 | Herman Miller, Inc. | $566,121,000 | 16,529,000 | $34.25 | 0.925% |
| 38 | First Executive Corporation | $557,767,000 | 47,980,000 | $11.62 | 0.912% |
| 39 | Adolph Coors Company | $544,251,000 | 34,284,000 | $15.87 | 0.890% |
| 40 | Ameritrust Corporation | $537,050,000 | 9,300,000 | $57.75 | 0.878% |
| 41 | Liz Claiborne, Inc. | $535,805,000 | 21,220,000 | $25.25 | 0.876% |
| 42 | Willamette Industries, Inc. | $533,505,000 | 15,135,000 | $35.25 | 0.872% |
| 43 | Southland Financial Corporation | $526,081,000 | 17,391,000 | $30.25 | 0.860% |
| 44 | Pacific Telecom, Inc. | $524,188,000 | 40,322,000 | $13.00 | 0.857% |
| 45 | Pic 'N' Save Corporation | $522,970,000 | 26,148,000 | $20.00 | 0.855% |
| 46 | Ohio Casualty Corporation | $521,637,000 | 11,158,000 | $46.75 | 0.853% |
| 47 | Rouse Company (The) | $518,636,000 | 15,033,000 | $34.50 | 0.848% |
| 48 | LIN Broadcasting Corporation | $518,052,000 | 21,117,000 | $24.53 | 0.847% |
| 49 | Genentech, Inc. | $514,352,000 | 15,240,000 | $33.75 | 0.841% |
| 50 | Betz Laboratories, Inc. | $506,389,000 | 14,894,000 | $34.00 | 0.828% |
| 51 | Network Systems Corporation | $490,972,000 | 21,821,000 | $22.50 | 0.803% |
| 52 | Millipore Corporation | $485,076,000 | 11,215,000 | $43.25 | 0.793% |
| 53 | Valley National Corporation | $483,280,000 | 16,737,000 | $28.87 | 0.790% |
| 54 | Micron Technology, Inc. | $476,125,000 | 17,314,000 | $27.50 | 0.778% |
| 55 | Rainier Bancorporation | $469,525,000 | 9,807,000 | $47.88 | 0.767% |
| 56 | Citizens Utilities Company | $466,548,000 | 16,370,000 | $28.50 | 0.763% |
| 57 | Wyman-Gordon Company | $466,176,000 | 18,835,000 | $24.75 | 0.762% |
| 58 | Midlantic Banks, Inc. | $464,660,000 | 15,818,000 | $29.38 | 0.760% |
| 59 | United States Health Care Systems, Inc. | $461,373,000 | 14,142,000 | $32.62 | 0.754% |
| 60 | Yellow Freight System, Inc. of Delaware | $453,517,000 | 14,284,000 | $31.75 | 0.741% |
| 61 | U.S. Bancorp | $448,700,000 | 18,314,000 | $24.50 | 0.733% |
| 62 | Micom Systems, Inc. | $446,281,000 | 15,798,000 | $28.25 | 0.729% |
| 63 | Policy Management Systems Corporation | $445,940,000 | 16,216,000 | $27.50 | 0.729% |
| 64 | National City Corporation | $431,794,000 | 11,363,000 | $38.00 | 0.706% |
| 65 | Sonoco Products Company | $428,453,000 | 10,916,000 | $39.25 | 0.700% |
| 66 | Mack Trucks, Inc. | $425,236,000 | 30,648,000 | $13.87 | 0.695% |
| 67 | Worthington Industries, Inc. | $422,970,000 | 18,490,000 | $22.88 | 0.691% |
| 68 | United Virginia Bankshares, Incorporated | $412,068,000 | 11,944,000 | $34.50 | 0.674% |
| 69 | Maxicare Health Plans, Inc. | $404,825,000 | 16,357,000 | $24.75 | 0.662% |
| 70 | El Paso Electric Company | $404,558,000 | 30,823,000 | $13.13 | 0.661% |
| 71 | Kinder-Care Learning Centers, Inc. | $404,190,000 | 27,403,000 | $14.75 | 0.661% |
| 72 | Life Investors Inc. | $395,163,000 | 9,409,000 | $42.00 | 0.646% |
| 73 | HealthAmerica Corporation | $388,654,000 | 22,862,000 | $17.00 | 0.635% |
| 74 | Avantek, Inc. | $387,267,000 | 18,891,000 | $20.50 | 0.633% |
| 75 | Monarch Capital Corporation | $386,270,000 | 8,680,000 | $44.50 | 0.631% |
| 76 | Hartford National Corporation | $385,098,000 | 14,464,000 | $26.62 | 0.629% |
| 77 | Lotus Development Corporation | $378,888,000 | 15,953,000 | $23.75 | 0.619% |
| 78 | State Street Boston Corporation | $378,350,000 | 8,225,000 | $46.00 | 0.618% |
| 79 | Service Merchandise Company, Inc. | $375,342,000 | 31,944,000 | $11.75 | 0.614% |
| 80 | Daisy Systems Corporation | $373,698,000 | 14,513,000 | $25.75 | 0.611% |
| 81 | Charming Shoppes, Inc. | $368,184,000 | 21,500,000 | $17.12 | 0.602% |
| 82 | Food Lion, Inc. (Class B) | $367,920,000 | 26,280,000 | $14.00 | 0.601% |
| 83 | Economics Laboratory, Inc. | $365,016,000 | 13,582,000 | $26.87 | 0.597% |
| 84 | Bruno's, Inc. | $362,858,000 | 17,809,000 | $20.37 | 0.593% |
| 85 | Food Lion, Inc. (Class A) | $361,350,000 | 26,767,000 | $13.50 | 0.591% |
| 86 | Noxell Corporation | $359,420,000 | 8,054,000 | $44.63 | 0.587% |
| 87 | Hoover Company (The) | $357,357,000 | 12,376,000 | $28.88 | 0.584% |
| 88 | Andrew Corporation | $354,822,000 | 10,138,000 | $35.00 | 0.580% |
| 89 | Hamilton Oil Corporation | $354,130,000 | 25,295,000 | $14.00 | 0.579% |
| 90 | Comerica, Inc. | $351,560,000 | 10,302,000 | $34.13 | 0.575% |
| 91 | I.M.S. International, Inc. | $348,398,000 | 9,578,000 | $36.37 | 0.569% |
| 92 | First Florida Banks, Inc. | $345,172,000 | 15,601,000 | $22.12 | 0.564% |
| 93 | Florida National Banks of Florida, Inc. | $343,882,000 | 11,858,000 | $29.00 | 0.562% |
| 94 | Pay'n Save Corporation | $342,765,000 | 15,234,000 | $22.50 | 0.560% |
| 95 | Maryland National Corporation | $342,584,000 | 7,786,000 | $44.00 | 0.560% |
| 96 | McCormick & Company, Incorporated | $342,208,000 | 10,736,000 | $31.87 | 0.559% |
| 97 | United Stationers Inc. | $340,040,000 | 13,467,000 | $25.25 | 0.556% |
| 98 | First Alabama Bancshares, Inc. | $331,874,000 | 15,259,000 | $21.75 | 0.542% |
| 99 | Chi-Chi's, Inc. | $329,757,000 | 26,119,000 | $12.63 | 0.539% |
| 100 | Ogilvy & Mather International Inc. | $329,650,000 | 9,157,000 | $36.00 | 0.539% |

---

# 8. IMPORTANT NOTE ON TRANSCRIPTION

The archival PDF is a scanned 1985 committee record. The canonical dataset above was normalized from the historical table and obvious scan/OCR punctuation artifacts were cleaned.

The application should use the **company names, rank order, market values and shares-outstanding values in this MD as its canonical migration dataset**.

Do not replace values by scraping modern finance sites.

Do not “modernize” company names to current successor corporations. The historical name is part of the value of the project.

---

# 9. RECOMMENDED BASIC DATA MODEL

The new runtime dataset can remain embedded directly in BASIC.

Conceptual fields:

```text
RANK
COMPANY_NAME$
MARKET_VALUE
SHARES_OUTSTANDING
IMPLIED_PRICE
POOL_WEIGHT
```

Recommended calculations at startup:

```text
IMPLIED_PRICE = MARKET_VALUE / SHARES_OUTSTANDING
POOL_WEIGHT = MARKET_VALUE / TOTAL_TOP100_MARKET_VALUE * 100
```

The raw source fields should be embedded as `DATA` statements.

Example style:

```basic
10000 DATA 1,"Intel Corporation",3178140000,112501000
10010 DATA 2,"MCI Communications Corporation",1806057000,240808000
10020 DATA 3,"Apple Computer, Inc.",1763081000,61325000
```

Use a numeric type capable of safely holding values above 3 billion.

Do not accidentally use a 32-bit signed integer for raw dollar market values.

If the chosen BASIC compiler's classic integer types are unsafe, use a floating-point numeric type for market values while keeping presentation as whole dollars.

---

# 10. REQUIRED APPLICATION MIGRATION

The old application is Fortune-focused.

The new version should conceptually migrate from:

`WALL STREET 1979 / FORTUNE 100 CORPORATE MONITOR`

to something closer to:

`NASDAQ/NMS 1984`  
`TOP 100 MARKET VALUE MONITOR`

The central ranking is now genuinely a market-value ranking.

### Replace old primary metrics

Remove or demote:

- Fortune revenue rank
- Fortune revenue
- Fortune profit
- profit margin

Primary list-view fields should become:

- Rank
- Company
- Market Value
- Shares Outstanding
- Implied $/Share

Optional compact view:

```text
RK  COMPANY                    MARKET VALUE    SHARES      $/SHARE*
01  INTEL CORPORATION          $3.178B         112.501M     $28.25
02  MCI COMMUNICATIONS         $1.806B         240.808M      $7.50
03  APPLE COMPUTER             $1.763B          61.325M     $28.75
```

`* IMPLIED FROM SOURCE MARKET VALUE / SOURCE SHARES`

---

# 11. SORTING / RANKING MODES

Required:

1. Source rank
2. Market value descending
3. Market value ascending
4. Shares outstanding descending
5. Implied $/share descending
6. Company alphabetical
7. Share of Top-100 pool

Because market value is complete for all 100 records, sorting should always rank 100/100 records.

---

# 12. COMPANY DETAIL SCREEN

Recommended content:

```text
==============================================================
APPLE COMPUTER, INC.
NASDAQ/NMS MARKET VALUE LEADER — 1984
==============================================================

SOURCE RANK ............ 3
MARKET VALUE ........... $1.763B
SHARES OUTSTANDING ..... 61.325M
IMPLIED $/SHARE* ....... $28.75
TOP-100 POOL WEIGHT .... x.xxx%

* DERIVED: MARKET VALUE / SHARES OUTSTANDING
  NOT PRESENTED AS AN INDEPENDENT HISTORICAL CLOSING QUOTE

[COMPARE]  [BACK]
==============================================================
```

No revenue/profit fields are needed unless they are retained as a clearly separate legacy dataset, which is not recommended for the main UI.

---

# 13. VISUAL REDESIGN DIRECTION

The current green-terminal identity is good and should be preserved, but the migration is an opportunity for a stronger polished 1980s financial-terminal presentation.

The result should still look like BASIC-era software, not like a modern web dashboard.

Recommended palette:

- black background;
- phosphor green primary text;
- amber/yellow highlight;
- white/light-gray sparingly for emphasis.

Recommended character:

- financial data terminal;
- keyboard-first;
- clean ASCII separators;
- dense but readable;
- no gradients;
- no modern cards;
- no mouse-first design.

---

# 14. ASCII U.S. FLAG / TOP 100 MARK

Add a restrained ASCII American flag to the boot screen or main screen.

Suggested concept:

```text
* * * * * * * * * * |========================
 * * * * * * * * *  |========================
* * * * * * * * * * |========================
 * * * * * * * * *  |========================
==============================================
==============================================
==============================================

          NASDAQ/NMS  //  TOP 100
            MARKET VALUE 1984
```

It should look like a terminal graphic, not a modern illustration.

The main identity should read approximately:

```text
NASDAQ/NMS DATA SYSTEM
UNITED STATES // MARKET VALUE MONITOR

              TOP 100
        MARKET VALUE LEADERS
               1984
```

Keep the flag compact enough that it does not make navigation worse.

---

# 15. BOOT SCREEN TARGET

A much stronger boot screen would be:

```text
NASDAQ/NMS DATA SYSTEM
COPYRIGHT 1984 // HISTORICAL RECONSTRUCTION

MEMORY TEST ............ OK
NASDAQ/NMS TABLE ....... 100 VERIFIED / 100 TOTAL
MARKET VALUE ........... 100 VERIFIED / 100 TOTAL
SHARES OUTSTANDING ..... 100 VERIFIED / 100 TOTAL
IMPLIED PRICE .......... 100 DERIVED  / 100 TOTAL
INDEX .................. READY

         [ ASCII U.S. FLAG ]
              TOP 100
         MARKET VALUE 1984

PRESS ANY KEY TO ENTER
```

This directly fixes the psychologically ugly `0 VERIFIED / 100 UNAVAILABLE` startup state without fabricating data.

---

# 16. MAIN MENU TARGET

Suggested menu:

```text
[1] MARKET VALUE DIRECTORY
[2] TOP 10 BOARD
[3] SEARCH COMPANY
[4] SORT / RANKINGS
[5] COMPANY COMPARISON
[6] MARKET OVERVIEW
[7] DATA / METHODOLOGY
[8] ABOUT / SOURCES
[Q] QUIT
```

`MARKET OVERVIEW` can show:

- total value of this Top-100 pool;
- average;
- median;
- Top-10 combined value;
- Top-10 share of pool;
- ASCII bar chart of largest firms.

---

# 17. HISTORICAL HONESTY RULES

Do not:

- call this the `NASDAQ-100 Index 1984`;
- invent an exact 1984 snapshot date;
- label derived implied price as an actual verified closing quote;
- silently replace old company names with current names;
- use current market caps;
- mix current and historical share counts;
- use modern tickers as if they were historical tickers.

Do:

- call market value `VERIFIED` because it is supplied by the historical table;
- call shares outstanding `VERIFIED` because it is supplied by the table;
- call implied price `DERIVED`;
- show the source and methodology inside the application;
- preserve 100/100 coverage honestly.

---

# 18. MIGRATION ACCEPTANCE CHECKS

After Codex migrates the app, check:

- [ ] exactly 100 records;
- [ ] Intel is rank 1;
- [ ] MCI is rank 2;
- [ ] Apple is rank 3;
- [ ] Betz Laboratories is rank 50;
- [ ] Network Systems is rank 51;
- [ ] Ogilvy & Mather International is rank 100;
- [ ] all 100 market values loaded;
- [ ] all 100 shares-outstanding values loaded;
- [ ] all 100 implied prices calculate without divide-by-zero;
- [ ] source rank and market-value descending produce the same order;
- [ ] boot screen shows 100/100 verified market value;
- [ ] boot screen shows 100/100 verified shares;
- [ ] boot screen calls implied price DERIVED, not VERIFIED quote;
- [ ] old Fortune-specific labels are removed from primary UI;
- [ ] no exact trading date is invented;
- [ ] application still compiles as BASIC;
- [ ] GitHub language goal remains BASIC 100.0%;
- [ ] final standalone Windows executable still works.

---

# 19. RECOMMENDED FILE ROLE

Place this file in:

`D:\Basic`

Suggested filename:

`NASDAQ_NMS_1984_VERIFIED_DATASET.md`

When this file is present, it should supersede the old Fortune 1979 dataset sections for the application's primary data model.

The original project MD remains useful for BASIC/GitHub/build requirements, but **this file becomes canonical for the historical company dataset and the 1984 market-value redesign**.

---

# 20. SHORT DECISION SUMMARY

For the next project revision:

**OLD**
`Fortune 100 / 1979 / revenue-ranked / market-cap unavailable`

**NEW**
`NASDAQ/NMS Top 100 / 1984 / market-value-ranked / market value 100/100 / shares 100/100`

This is a materially better match for the original idea of a historical stock-market monitor.

