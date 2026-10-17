# Acceptance criteria — TakeMeter

Five criteria that say what "working" means for this classifier, written in
unit 5 **before** anything was trained.

**All five are yours this time.** None are given. You've had two projects of
practice.

An acceptance criterion names a number. *"The model is accurate"* is an
opinion. *"Every label has an F1 of at least 0.60 on the held-out set"* is a
criterion.

Under each, write a sentence or two on **why that number**. A reason that says
something about your data or your taxonomy earns credit — *"I picked 0.60 F1
for `reaction` because it's my smallest label and I only have about 50
examples of it"*. A reason that could be attached to any project does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## Pick numbers you can defend

Not numbers that sound impressive. Three labels means a coin-flip guesser gets
about 33%, so a target of 0.40 is barely a target. Your number should sit
somewhere you'd honestly call useful.

**Cover at least three of these five areas.** They're here as prompts, not as a
form to fill in — a criterion that fits none of them is fine if it names a
number.

| Area | A question it could answer |
|---|---|
| Overall accuracy | How often does it need to be right to be worth using? |
| Per-label performance | Is one label allowed to be much worse than the others? |
| Balance | How lopsided can your label counts get before it's a problem? |
| Consistency | If someone else labelled the same posts, how often should you agree? |
| Confidence | Should a confident prediction be right more often than an unsure one? |

Two things worth knowing before you pick numbers, because both will affect
whether you hit them:

- **Your smallest label will have the jumpiest score.** If a label has 50
  examples, about 8 land in the test split. An F1 computed on 8 examples moves
  a lot between seeds. A target for that label should be looser than one for
  your biggest label, and saying so is a good reason.
- **Unit 6 tests across three seeds, and the target has to hold across all
  three.** A target of 0.65 against results of 0.71, 0.62, 0.68 is a **miss**.
  Pick with that in mind — it is stricter than it first sounds.

---

## 1. Overall accuracy on the held-out test set is at least 0.50.
**Why this target:**
With 4 labels, random guessing gets about 25%, and always guessing
   `experience` (my biggest label) gets about 32.5%, so 0.50 is well above
   both. When I labeled 20 posts cold, my labels matched the AI's pre-labels
   only 10 out of 20 times (50%), mostly disagreeing on `experience`. Since
   the model learns from those same labels, I expect its accuracy to land
   near that level, so 0.50 is the point where it is at least as consistent
   as my own labeling.



---

## 2.Every label has an F1 of at least 0.40 on the held-out test set.
**Why this target:**
My labels overlap. `experience` posts often include the writer's
   predictions or other people's takes on the market, so they cross over
   into `outlook`, and that is the boundary I expect the model to confuse
   most. `analysis` and `reaction` also have only about 6 posts each in the
   test set, so one or two mistakes can drop their score a lot. I set the
   floor at 0.40 so that no label is ignored, even if the overlap pulls
   some scores down.


---

## 3.On the held-out test set, no single label makes up more than 50% of
   the model's predictions.

**Why this target:**
I want every label to have a fair chance. `experience` is my biggest
   label (32.5% of the data) and overlaps with the others, so the model may
   lean toward guessing it. A skew above 50% would make the results
   imbalanced and biased, and I want a fair perspective across all four labels.


---

## 4.On the 30-post staff set, my labels agree with the staff labels on at least 18 of 30 posts (0.60).


**Why this target:**
When I labeled 20 of my own posts cold, my labels matched the AI's
   pre-labels only 50% of the time. Staff rules are written by experienced
   people and should be clearer than an AI's guesses, so I expect to do
   better than that, at about 60–70%. I set the bar at the bottom of that
   range, 0.60.



---

## 5. The `experience` label has an F1 of at least 0.45 on the held-out test set.



**Why this target:**
`experience` is my biggest and most important label, but it overlaps
   with `outlook` and `reaction`, so on the first run I expect the model to
   both miss some real experience posts and wrongly guess experience for
   others. Because it has the most test posts (about 10), I expect it to
   score a bit above my 0.40 floor for every label, so I set 0.45 as my bar
   for this first run. If it falls short, my plan is to add posts from other
   industries and write a sharper experience rule, then check whether the
   score holds or improves.



---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->
