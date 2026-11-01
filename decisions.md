---
status: active
last_updated:
---

# Decisions

Append-only, newest at the top. Never edit a past entry; add a new one that corrects it. The one exception: the `Outcome:` line is filled in when the decision is reviewed. Use the `log-decision` skill to add entries, and `context-refresh` to review them when their **Review on** date passes.

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
- Outcome:
```

---

<!-- New entries go below this line, newest first. -->
