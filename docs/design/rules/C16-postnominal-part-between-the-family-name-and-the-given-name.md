# C16 — a postnominal part between the family name and the given name

**When:** a family comma's part is read as postnominal (C1) and a later comma part holds a name word, as in "LEE, JR, ERNEST L" or "Smith, Jr., John".

**Then:** the last later part that is not titles and suffixes is the given part, read as the part after a family comma is read, and the postnominal part keeps its reading.

- **The other later parts** stay what C2 reads them as, a part that is not titles and suffixes among them flagged, as a credential no list holds is.
- **An empty part** stops the search: doubled commas keep their structural place, and the parts past them stay C2's.

**Because:** records written in the listing form put the generation or credential in a field of its own between the surname and the given name, and filers' software writes it there in that order. The postnominal part fixes nothing about the given name, so the name word after it is the given name the listing form names, and reading it as a suffix would lose the given name entirely.

```
"LEE, JR, ERNEST L"         →  given="ERNEST"
"LEE, JR, ERNEST L"         →  middle="L"
"LEE, JR, ERNEST L"         →  suffix="JR"
"HALL, JR, JAMES EDWARD"    →  given="JAMES"
"Smith, Jr., John"          →  given="John"
"Smith, MD, John"           →  suffix="MD"
"Smith, Dr., John"          →  title="Dr."
"Smith, Jr., Dr. John"      →  given="John"
"Smith, MD, Jr., John"      →  suffix="MD, Jr."
"Smith, Jr., John Q., PhD"  →  suffix="Jr., PhD"
", Jr., John"               →  given="John"
"Fincher, MD, MACP, Jacqueline"  →  given="Jacqueline"
"Fincher, MD, MACP, Jacqueline"  →  suffix="MD, MACP"
"Fincher, MD, MACP, Jacqueline"  →  ambiguities=("comma-structure",)
"Smith, Jr., PhD"           →  given=""  · boundary
"Smith, Jr., Prof."         →  title="Prof."  · boundary
```

**Except:**

- **An empty part** before the name word keeps C2's reading of every part past it.
  ```
  "Smith, Jr.,, John"         →  suffix="Jr., John"  · boundary
  ```

**Precedence:**

- **Behind a whole name** ("John Smith, Jr., Bart"): the comma is a suffix comma, the given name is already read before it, and C2 keeps the part past the second comma; C16 reads only behind a family comma.
  ```
  "John Smith, Jr., Bart"     →  suffix="Jr., Bart"
  ```
- **A word C4's count reads as a name** ("Smith, Ma, John"): behind one name word the ambiguous credential class is the given name (C4), so C1 binds no postnominal part, the part after the first comma is the given part, and C16 does not apply.
  ```
  "Smith, Ma, John"           →  given="Ma"
  ```

---
**Signal:** comma: a name word in a comma part behind a postnominal one
**history:** decisions/C16 · **implemented:** nameparser/_pipeline/_comma.py
