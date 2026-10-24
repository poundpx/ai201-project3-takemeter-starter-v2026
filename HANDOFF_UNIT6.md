# Unit 6 handoff: where I am (TakeMeter Part 2, AI201)

Student: Minh Nguyen (Member ID 66321). Due: Monday 2026-10-26, 2:59 AM EDT.
Last updated: 2026-10-24. Delete this file before the final submission if you like; it is only a status note.

## How I want to be helped (important)
- I am new to this. Explain in plain, simple words, one small step at a time.
- Guide me and let me make the decisions. I get tired, so short steps and drafts I can check are fine,
  but I should read and approve anything written into the README, and the README should say AI helped
  (see "How I Used AI").
- Do not open or reveal `data/staff_labels.csv` answers for me to copy; Milestone 3 is already finished.
- Windows + PowerShell + VS Code. Project folder: `ai201-project3-takemeter-starter-v2026`.

## The project in one paragraph
TakeMeter fine-tunes `distilbert-base-uncased` on my 200 labeled posts (sources: CS job posts on Reddit and
YouTube talks about how AI is affecting the tech job market; 4 labels: `experience`, `analysis`, `outlook`,
`reaction`; see README "What This Does" and "Label Taxonomy" for the definitions). Unit 6 tests it: baseline vs trained, three seeds, a
confusion matrix, an agreement check against a staff set, verdicts and diagnoses, then ONE improvement.
Rule: my labels, taxonomy and criteria stay frozen. The one improvement is the only allowed change.

## Status by milestone
| Milestone | State | Commit |
|---|---|---|
| 1. Baseline | DONE. Baseline accuracy 0.433; trained (unit 5) 0.333. Table is in README. | c4b2c8f |
| 2. Three seeds + confusion matrix | DONE. Seeds 42, 7, 2024. Matrix (seed 42), device, spread, run log in README. | abc6869 |
| 3. Staff agreement | DONE. 15/30 = 50%. All 15 disagreements adjudicated in README. | 10ade0d, 787a0be |
| 4. Verdicts and diagnoses | DONE in README (drafted with AI help; I should still read it). | e5166e6 |
| 5. One improvement | NOT STARTED. I have to choose one change (see below). | |
| 6. What's still broken + submit | NOT STARTED | |

## Key results so far
Three seeds (`results_three_seeds_before.json`):

| Seed | Accuracy | Macro F1 |
|---|---|---|
| 42 | 0.333 | 0.125 |
| 7 | 0.333 | 0.125 |
| 2024 | 0.367 | 0.181 |

- The model predicted `experience` for all 30 test posts in seed 42 (one vertical column in the matrix).
- Training loss barely moved (about 1.36 to 1.33; guessing among 4 labels is about 1.39), and only about 27 updates
  happened (139 train posts, batch 16, 3 epochs).
- Criteria verdicts (targets are in `criteria.md`): 1 accuracy MISSED, 2 every-label F1 MISSED, 3 no label over
  50% of predictions MISSED, 4 staff agreement MISSED (15/30 vs 18), 5 `experience` F1 MET (weak: only via recall 1.0).
- Agreement: 13 of 15 disagreements were "rule covered it, I applied it loosely" (pile a); 2 were pile (c) (posts 7 and 9).
  Biggest cluster: 7 posts staff called `analysis` that I labeled by tone.

## NEXT STEP: Milestone 5 (pick ONE change, then retrain the same three seeds)
Options from the assignment:
1. Relabel one boundary (only if the agreement check showed I applied one rule two ways; say how many rows changed).
2. Add 30 more posts to the thinnest label (the worst-F1 label), labeled with the same care.
3. Change one training setting (more epochs or a different learning rate). Only pick this if the diagnosis points at training.

My diagnosis points at both training (loss barely moved) and labeling (agreement). Decide which one, then:
- In notebook section 6, change `RUN_LABEL = "before"` to `"after"` BEFORE running. Otherwise it overwrites
  `results_three_seeds_before.json`.
- Run the same seeds `[42, 7, 2024]`. Writes `results_three_seeds_after.json`.
- Add a "Run Log - After" (same five-row format) in README under "The Improvement", beside the before log.
- Say honestly whether it helped, even if it did not.

## Then Milestone 6
- Fill "What's Still Broken" (for each missed criterion: what I'd do, why I stopped).
- Two sentences on the gap between what my labels meant and what the model learned (the matrix is the evidence).
- Update "How I Used AI". Submit the SAME GitHub repo URL as unit 5. At least 4 new commits this unit (already met).

## Setup facts for a new computer
- Do NOT recreate the repo. Pull the latest from GitHub.
- Create/activate the venv and install: `python -m venv .venv`, `.venv\Scripts\Activate.ps1`, `pip install -r requirements.txt`.
- `python test.py` should show all passes. The baseline model (~1.6 GB) and `distilbert-base-uncased` download on first use.
- The notebook trains on CPU: about 50 seconds per seed. Run notebook sections 1 to 4 and the cell defining `evaluate`
  (section 5) before section 6, or you get `NameError` for `split_dataset`, `LABELS`, etc.
- **Notebook fix I made:** in `takemeter.ipynb` cell 7, `LABELS` was the starter's three example labels. I changed it to
  my four labels: `experience`, `analysis`, `outlook`, `reaction`. If the notebook still shows the starter list, fix it first.
- `.env` and API keys are not needed for this unit and must never be committed.
- `data/staff_labels.csv` (the TF's answer key) is intentionally NOT committed.

## Files to know
- `README.md`: the graded write-up (sections for baseline, run log, verdicts, agreement, improvement, still broken).
- `criteria.md`: my five criteria (never delete or edit the originals; revisions go underneath).
- `results.json`, `test_split.csv`: from unit 5. `baseline_results.json`, `results_three_seeds_before.json`,
  `agreement_results.json`, `my_staff_labels.csv`: from this unit, committed.
- `label_definitions.txt`: baseline prompt, my four label definitions.
