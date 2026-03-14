# Left Hip Rehab Tracker

A personal mobile-first web app for tracking a rehabilitation program targeting left glute medius weakness, built following a left ACL reconstruction (hamstring graft) 10 years ago.

---

## Background & Clinical Context

**The person:** Male, 40. Active — soccer 1x/week, lifting 1-2x/week, cycling 1-2x/week, running 1x/week, occasional swim. Ironman background.

**The history:**
- Left ACL reconstruction ~10 years ago with hamstring graft (semitendinosus/gracilis)
- Right inguinal hernia repair (mesh)
- High training volume maintained throughout — no significant time off

**The core problem:**
Left glute medius chronically inhibited following ACL surgery. Right side has been compensating for ~10 years. This is a neuromuscular repatterning problem as much as a strength problem — the nervous system has built an efficient compensatory motor program that routes around the left glute med.

**The full compensation chain (documented through conversation):**

| Area | Left side | Right side |
|---|---|---|
| Foot | Pronated, inner-edge weighted (-4mm pedal offset) | Supinated, outer-edge weighted (+7mm pedal offset) |
| Femur | Dynamic internal rotation under load | Relative external rotation, braced |
| Knee | Valgus tendency on cuts | Relative varus, lateral compression |
| Glute med | Inhibited, neurologically quiet | Overworking, chronically shortened/gripping |
| Pelvis | Drops (Trendelenburg), rotates forward | Hikes, rotates back |
| SI joint | Hypermobile | Restricted |
| QL | Tight, overworking | Tight, overworking (dominant side) |
| Thoracic | Compensatory rotation | Right shoulder higher and more forward |
| Adductor | Longus overloaded (soccer soreness) | — |

**Objective measures of asymmetry:**
- Power pedal offset: Left -4mm, Right +7mm (11mm total spread)
- Cycling power phase start: Left 19.69°, Right 22.5° (left starts earlier, compensating for reduced peak capacity)
- Power phase end: Both 215.16° (nervous system has calibrated a symmetric endpoint)
- Peak power window: Nearly identical (left 78.75–127.97°, right 80.16–126.56°)

**Additional notes:**
- Left adductor longus and gracilis chronically overloaded as secondary stabilizers
- Right hip flexor tight from overstriding (compensating for weaker left push-off)
- Right QL and lumbar erectors significantly overworked
- Hernia repair site creates fascial restriction layered on top of compensation pattern
- Foam rolling: right side beneficial (overworkers need release), left glute med should NOT be rolled (inhibited, rolling reduces neural drive further)
- Person has ADHD — program must be simple, low cognitive load, embedded into existing training rather than replacing it

---

## The Program

### Philosophy
Keep all existing training (deadlifts, cycling, soccer, running). Add targeted work around it. A program you actually do for 12 months beats a perfect program abandoned at week 6.

### Phase Structure

**Phase 1 — Activation (Weeks 1–10)**
Build mind-muscle connection on the left side. Conscious activation before it becomes automatic. Pre-session warm-up every session.

**Phase 2 — Loaded Strength (Weeks 6–20, overlaps Phase 1)**
Single-leg RDL, Copenhagen holds, step-downs with real load. Step-down test is the weekly quality benchmark.

**Phase 3 — Sport Integration (Months 5–12)**
Transfer to fatigue state. Activation work at end of long runs/rides. Late-game soccer awareness. Gait analysis recommended.

### Key Milestones
- Weeks 6–10: Left side activation clearly felt (not TFL)
- Months 3–4: Step-down test visibly more symmetric
- Month 5–6: Left lateral hip tightness reduced
- Month 8–12: Pattern holds under fatigue in sport

### Minimum Effective Dose (pre-session, every session)
1. Banded side steps — 20 each direction, band above knees
2. Single-leg stance hold — left leg, 3 × 20 sec, keep right hip level
3. Single-leg glute bridge — left leg only, 2 × 15, squeeze hard at top

### Lift day additions
4. Single-leg RDL — left leg, 3 × 10, dumbbell in right hand
5. Step-down — left leg, 2 × 10 slow (weekly quality check)
6. Copenhagen adductor hold — left side, 3 × 20–30 sec

### Desk breaks (office has private office, band available)
- **Reset** (every ~60 min, 90 sec): kneeling hip flexor stretch left with glute squeeze + standing left glute med activation + thoracic rotation left
- **Posture** (any time, 30 sec, seated): tripod foot check + rib reset + shoulder level check + seated left glute squeeze
- **Movement** (1-2x/day, 3-4 min): wall sit with knee-out cue + banded side steps + kneeling hip flexor stretch + single-leg stance

### Morning routine
- **5 min (office days):** pushup progression + band pull-apart + pike pushup
- **15 min (WFH days):** above + single-arm dumbbell row (left first) + shoulder press + dead hang + thoracic rotation stretch left

### Progression rule
When rep target is hit cleanly for 3 sessions in a row: add a set, slow the tempo (3 sec eccentric), or advance the variation. Never grind ugly reps.

### Pushup progression order
Standard → Close grip → Archer → Deficit

---

## Files

| File | Purpose |
|---|---|
| `index.html` | Main tracker app — Today, Morning, Breaks, Progress, Guide tabs |
| `hamstring_dumbbell.html` | Single dumbbell exercise guide with session builder and timer |
| `README.md` | This file |

---

## Hosting

Hosted on **GitHub Pages**.

- Repo: upload both HTML files and README to the root of a public GitHub repo
- Enable Pages: Settings → Pages → Deploy from branch → main → / (root)
- Live URL: `https://yourusername.github.io/your-repo-name`
- Bookmark this URL on phone, use browser "Add to Home Screen" to make it feel native

**To update:** replace `index.html` or `hamstring_dumbbell.html` in the repo and commit. GitHub Pages redeploys automatically within ~60 seconds.

**Future improvement:** set up a GitHub Action to auto-deploy on commit, eliminating manual upload.

---

## Google Sheets Integration

All session logging saves to a personal Google Sheet via Google Apps Script.

**Sheet URL:**
```
https://script.google.com/macros/s/AKfycbybQj2L7Y01HSrgOuPJG_1CwGDBuZdjk062FMnzXji1D2sUojQv912cIksj3zE_fJMnOg/exec
```

**Sheet columns (in order):**

| Column | Field | Notes |
|---|---|---|
| A | Date | Timestamp string |
| B | Type | Lift / Ride / Run / Soccer / Swim / Rest / Morning · 5min / Morning · 15min / Break · Reset / Break · Posture / Break · Movement |
| C | Sym Score | 1/2/3 for training sessions, blank for morning/breaks |
| D | Sym Label | Very asymmetric / Improving / Feeling close — blank for morning/breaks |
| E | Pushup Variation | Standard / Close grip / Archer / Deficit — morning sessions only |
| F | Exercises Done | Count of checkboxes ticked |
| G | Energy | Low / Normal / High — training sessions only |
| H | Right Tension | Low / Moderate / High — key leading indicator |
| I | Day | Monday / Tuesday etc |
| J | Time of Day | Morning / Afternoon / Evening |
| K | Notes | Free text, optional |

**Right Tension is the leading indicator:** high right tension = compensation pattern active = left glute med underperforming. Goal over 12 months: right tension trending down, symmetry score trending up.

**To update Apps Script:** Extensions → Apps Script → replace code → Deploy → Manage deployments → edit → New version → Deploy → reauthorize.

### Full Apps Script code

```javascript
function doPost(e) {
  try {
    const sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
    const data = JSON.parse(e.postData.contents);

    if (sheet.getLastRow() === 0) {
      sheet.appendRow([
        'Date', 'Type', 'Sym Score', 'Sym Label', 'Pushup Variation',
        'Exercises Done', 'Energy', 'Right Tension', 'Day', 'Time of Day', 'Notes'
      ]);
    }

    sheet.appendRow([
      data.date,
      data.type,
      data.sym,
      data.symLabel || '',
      data.pushupVariation || '',
      data.checks || 0,
      data.energy || '',
      data.rightTension || '',
      data.dayOfWeek || '',
      data.timeOfDay || '',
      data.notes || ''
    ]);

    return ContentService
      .createTextOutput(JSON.stringify({ result: 'success' }))
      .setMimeType(ContentService.MimeType.JSON);
  } catch(err) {
    return ContentService
      .createTextOutput(JSON.stringify({ result: 'error', error: err.toString() }))
      .setMimeType(ContentService.MimeType.JSON);
  }
}

function doGet(e) {
  const sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  const rows = sheet.getDataRange().getValues();
  return ContentService
    .createTextOutput(JSON.stringify({ rows: rows }))
    .setMimeType(ContentService.MimeType.JSON);
}
```

---

## AI Analysis

The Progress tab has an **Analyse** button that sends the last 2 weeks of logged data to the Claude API and returns a plain-English 4-6 sentence analysis covering:
- Symmetry trend direction
- Whether right tension is improving or stuck
- Patterns between session types and outcomes
- One specific actionable observation

Uses model: `claude-sonnet-4-20250514`

---

## Key Clinical Decisions Logged

**Why single-leg over bilateral:** bilateral work allows the right side to dominate silently. Single-leg work forces the left side to own its load.

**Why not foam roll left glute med:** it's inhibited, not overworked. Rolling reduces neural drive temporarily — the opposite of what's needed.

**Why right tension is tracked instead of left hip feel:** the left side feels like "nothing" (neurologically quiet from inhibition). The right side's tightness is the leading indicator — it reflects how hard the compensation pattern has been running.

**Why bilateral deadlifts are kept:** removing them creates strength loss, psychological friction, and caloric issues. The corrective work adds around existing training, not replaces it.

**Why kneeling hip flexor stretch beats standing:** the rear knee locks the pelvis, forcing the hip flexor to actually lengthen rather than the pelvis cheating the range.

**Cycling notes:** power pedal data shows 11mm total foot offset spread and 2.8° earlier left power phase engagement (left starts sooner to compensate for reduced peak capacity). Retest in fatigued state in August/September as objective marker of program progress.

**Foot note:** left foot pronates and outer foot unloads. Right foot supinates and carries excess lateral load. Tripod foot cue (heel + little toe base + big toe base equally weighted) added to all single-leg stance work.

---

## To Resume Development in a New Conversation

Paste this README and say: *"Here is the documentation for my rehab tracker app. I want to continue developing it."* The README contains enough context to pick up without re-explaining the clinical background, technical decisions, or file structure.
