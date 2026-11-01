---
file: decisions
status: active
last_updated: 2026-10-06
review_every: 30d
---

# Decisions

Append-only. Newest at the top. Never edit a past entry; add a new one that corrects or reviews it. Use the `log-decision` skill to add entries, and `context-refresh` to fill in outcomes when a review date passes.

## Entry format

```
### YYYY-MM-DD — <the decision in one line>
- Area: <area slug or "general">
- Options I considered:
- Why this one:
- Rule check: <which of my rules this follows or breaks, and why>
- I'll know it worked if:
- Review on: YYYY-MM-DD
- Confidence (1–5) and mood:
- Outcome (filled at review):
```

---

<!-- New entries go below this line, newest first. -->

### 2026-10-06 — Hoian Teslat praegu 11% juures, mitte ei vähenda 6%-ni
- Area: investing
- Options I considered: vähendada kohe 6%-ni; vähendada 8%-ni; hoida ja otsustada hiljem
- Why this one: see tõuseb ikka veel ja ma ei taha liiga vara müüa
- Rule check: **rikub** reeglit „ükski aktsia üle 8%“ ja Tesla teesi müügitingimust
- I'll know it worked if: ausalt, ma ei tea, mis mulle seda ütleks
- Review on: 2026-12-01
- Confidence (1–5) and mood: 2 — elevil, natuke süüdlaslik
- Outcome (filled at review):

### 2026-01-12 — Jätan iga-aastase tasakaalustamise vahele
- Area: investing
- Options I considered: tasakaalustada 70/30 peale ja vähendada Teslat; jätta see aasta vahele
- Why this one: tundus vale müüa seda, mis töötas
- Rule check: **rikub** reeglit „tasakaalustan igal jaanuaril“
- I'll know it worked if: suveks pole portfell riskantsem
- Review on: 2026-07-01
- Confidence (1–5) and mood: 3 — rahulik, natuke laisk
- Outcome (filled at review): 2026-07-02 — Tesla osakaal portfellis kasvas edasi. Üksikaktsiad on nüüd üle mu 35% vahemiku. Sama otsust ma enam ei teeks.
