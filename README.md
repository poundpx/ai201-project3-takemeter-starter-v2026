# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->

**The community i choose is on csc job post in reddit and a fews youtube talk regarding ai perception on job market after it have been mainstream for couple of years since 2023-2026. The classifier i sort my post into 2 group either benefit society or still need work to make improvement. The data i collect still have some weakness but overall the tech market is the most get impact by ai advancement for example it need to be in wider range of field and industry that got effecting by ai, what future will heading toward.



---

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### `label_one` Experience

**Definition:**
The writer describes something that actually happened to them, or to their own team or workplace, since AI was adopted.

**Example 1:**
`I just got fired from my software engineer ii role at a bank. I suspect AI had something to do with it. I was definitely not the only developer. But, I imagine their decision to cut the team size by multiple people likely was due to AI`

**Example 2:**
`I'm from Poland, got a dev job that I started this month, we're working using LLMs to an extent but operate on "all of your LLM code is your personal responsibility" principle, the company is expanding into a whole extra floor in the building they're in. "If something gets more cheap/efficient people will just use more of it to offset the savings" applies to companies hiring people too`

### `label_two` Analysis

**Definition:**
Makes a claim about AI's impact on the job market and backs it with specific, checkable evidence (a number, a study, a named historical event or comparison).

**Example 1:**
`This happened in the 1990's in the legal profession. Instead of firing junior attorneys, they moved from document processing and redaction into higher-level, higher-bill-rate work. Turns out that the set of billable work isn't a fixed size, and that adding value (and reducing overhead costs) can actually make customer buy more. We might not need the set of developers we have now, but there are plenty of historical counter-examples to show that automation can add value that actually expands a market, instead of just driving a race to the bottom. Whether our late-stage-capitalist overlords are capable of seeing this is another matter entirely.`

**Example 2:**
`Absolutely. Studies have come out that broadly speaking colleagues respect you less for openly using AI to complete tasks. This obviously depends on how you use it, but I know I feel a pang of disgust when I'm given something of lower quality and told "I used AI to make it." Yeah, we can tell. I still do not find a real use for AI generally, given even email drafting requires so much revision work that I would rather just write it myself, but when I do I am very coy about using it. There are also studies coming out that suggest workslop (AI produced artifacts—not product specific, mind you) is resulting in a net loss of productivity across the board. Be careful how you use these things, there's always someone downstream who will suffer from you cutting corners.`


### `label_three` outlook
**Definition:**
A claim about where AI and the job market are heading, or what the reader should do about it, resting on the writer's own opinion or confidence rather than evidence.

**Example 1:**
`AI finance bubble does not mean AI bubble. Even if the AI finance bubble bursts, the world would not be the same again. Not working (now known as unemployment) would be the norm. Therefore, the term unemployment wold then lose its meaning. Unfortunately, we have passed the point of no return. Nobody would slow down because of untrusting competition among countries and business. Some view it as a matter of life and death. Nobody wants to be left behind. All the walks of security, moral codes would be lip services at the best. Worse than nuclear arm race.`

**Example 2:**
`Yeah, that gap is real, and in AI it's wider than most fields since half the tooling people use daily was never in anyone's syllabus. Concrete thing that helped me and others: pick the one tool your team actually touches every day and get properly good at that, instead of trying to keep up with all of it.`

### `label_four` reaction
**Definition:**
Expresses the writer's feeling about AI and jobs (anger, fear, sarcasm, relief) without a personal account or supporting evidence.

**Example 1:**
`"adapt to AI" is such BS. they're designed to replace us, not to help us, there's nothing to adapt to.`

**Example 2:**
`Rich countries like US have the resources to end poverty. They have for decades. The billionaires at the top would rather let thousands of Americans die of exposure every winter than give a single dollar to prevent it. The tards that think we're going to get UBI when these billionaires are the same ones that own AI are laughably stupid. AI will take your job while the billionaires laugh at your plight. That's why they're building bunkers in New Zealand and data centers in space. To protect them from you`

### The hardest boundary


**Which two labels:**
experience vs outlook

**The decision rule I used every time:**
If the post describes the writer's own situation or work, it is experience, even if it also includes feelings, predictions, or advice. It is outlook only when the post is about the future or tells the reader what to do without a first-hand account.

**Second boundary: analysis vs outlook**
If the post supports its claim with a specific, checkable fact (a number, a date, a named event or comparison, a study), it is analysis, even if it talks about the future. If the claim rests only on the writer's opinion or confidence, it is outlook
---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->

**Where the posts came from:**
reddit, youtube talk comment on post, quora
**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->
i labeled them by reading through the comment one by one 

**Counts per label:**
| Label | Count | Share |
|---|---|---|
| experience | 63 | 31.5% |
| outlook | 49 | 24.5% |
| reaction | 44 | 22.0% |
| analysis | 44 | 22.0% |
| **Total** | **200** | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*
> `If AI never improves beyond where it is today, it would still materially change a lot over the next 5 to 10 years. People forget the internet looked overhyped and chaotic in the late 90's too. The bubble popped, but the capability stuck around and entrepreneurs slowly figured out what it was actually good for… how to make money off it. I feel we're in a similar phase. Right now, Claude can already handle a huge portion of real software engineering work. Not perfectly, but enough that an experienced engineer can be 5x-10x if they know what they're doing. That is not theory, that is happening in production workflows today at the top tech shops. And software is just the first domain that has been heavily optimized around AI. If model progress froze tomorrow, founders would spend the next decade operationalizing the same level of augmentation across law, accounting, marketing, research, ops, everything white collar. You do not need superintelligence to reshape industries. You just need tools that are good enough to compress cognitive labor by 30 to 70 percent. That creates economic pressure, and companies that use it well outcompete those that do not. It will not look like mass replacement overnight. It will look like fewer people doing more work, and over a decade that changes everything.`
>
> *Could have been:*
> `outlook`
>
> *I chose, because:*
> `analysis`. The whole post is about the future, which pulls toward outlook. But it backs its claim with a checkable comparison (the dot-com bubble and what happened to the internet afterward), so under my decision rule it is analysis.

**2.**
> *The post:*
> `The thing is, We've only seen the growth of 4 years. LLMs are so good that theyre now a threat to developers. You say it like its a walk in the park for a joe shmoe junior dev to upskill and compete with claude code. How many junior devs will follow your advice? And in that comparison how many junior devs will succeed after being good enough? Don't you think this model isn't for everyone. You yourself potrayed junior devs as a volatile position saying "AI can do that""...Being a very new CS student, I'm having nightmares seeing people calling what would by my first future position A "AI can do junior dev's job" Well then which cuckass ceo would hire me if AI can do my job? Don't you think people rushing for 'compete with claude code' will outweigh the job market for junior devs. that means all their hardwork and effort will go down the drain + we don't even see any improvement or good gesture from the community. Everyone on here thinks fixing clogged toilet will be their next job rather than being in tech. Everyone is trying to switch, What would CS student think seeing these people run away from tech. and Mind you, these mfs are 10 YOE+, Like they have been around the block, and they're thinking about switching. At this point my day to day is just reading through reddit > getting depressed > not growing and sleeping > repeat`
>
> *Could have been:*
> `reaction`
>
> *I chose, because:*
> `experience`. The post is full of strong feeling, which pulls toward reaction. But the writer grounds it in their own situation as a new CS student and describes what their daily life looks like now ("reading through reddit > getting depressed > not growing"). Because the post describes their own lived situation and not just a feeling about the topic, I chose experience.

**3.**
> *The post:*
> `I've been programming for 15 years as a hobby and an electrical engineer by trade. Although AI is not perfect, the latest models are actually quite insane. I rarely write code myself anymore and just spot inefficiencies and mistakes and point them out to guide the AI's thought. It's more like driving a car to get places than walking. But idk, if it gets any better than this (able to correct its own mistakes without a involving any guidance from someone with specialized knowledge, possibly by connecting networks of different models), it is very possible that apps can just be made end to end by vibe coding alone. Good programming practices like readability and architecture become irrelevant if no human ever needs to touch the code. We might end up being visual designers and nothing else 😂 though it's still too early to see if that will happen. As a hobbyist I'm very happy that I can write programs 20x faster than before, but if I am looking for work I would still be worried.`
>
> *Could have been:*
> `outlook`
>
> *I chose, because:*
> `experience`. The middle of the post guesses where AI is heading ("We might end up being visual designers"), which is outlook. But most of the post describes how the writer works with AI today, after 15 years of programming, and the writer hedges the guess ("too early to see if that will happen"). Since the first-hand account is the main point, I chose experience. experience overule outlook since it does including some truth in the story
---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:**

**Settings:** <!-- epochs, learning rate, batch size, seed -->

**Anything I changed from the defaults, and why:**

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->



---

## How I Used AI
i used ai to collect and guide me which data set is reach my criteria 
during the trainning i tend to over shoot or undershoot for data not related or not reach some criteria i set for so i use ai to help me.

**Moment 1**

- *What I asked for:* checker for criteria of source to be use data
- *What came back:* suggestion then using that suggestion it guide me through how to pick good data
- *What I changed:* method on how i do one by one instead gather everything at one place and then use ai to research some after my first round of human filtering hand off to ai

**Moment 2**

- *What I asked for:* as reminder what criteria did i missed during the milestone 
- *What came back:* your milestone 2 is solid but your criteria 2 seem like it contradict with what you wrote.
- *What I changed:* my workflow instead rely solely on ai i read first for requirement then later lets ai help guide me so i can detect if they make error during the work.

**Pre-labelling disclosure:**

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->


| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy | 0.433 | 0.333 | -0.100 |
| Macro F1 | 0.346 | 0.125 | -0.221 |
| F1 — `analysis` | 0.000 | 0.000 | +0.000 |
| F1 — `experience` | 0.762 | 0.500 | -0.262 |
| F1 — `outlook` | 0.316 | 0.000 | -0.316 |
| F1 — `reaction` | 0.308 | 0.000 | -0.308 |

**What I predicted before I looked:**
Before the train i do basemodel run and i got result very skew on both end and not distribute evenly 
for example `analysis` is at 0 end while `experience` is at .762 end with other 2 like`outlook` and `reaction` in range of .3-.31 rounded
from my finding am guessing that there something wrong with the way i wrote analysis labels 
so my prediction for the next one before train i guessing that model will shift from experience to analysis distributed a little more

**What the gap actually means:**
After the train the data come out unexpectedly not align with what i have hypothesis for. `outlook` and `reaction`
drop to zero also here is `analysis` still stay flat in zero and `experience` 
goes down to .5 which might need to revise but it was very interesting because last time we say analysis will gain a bit more and experience drop
but in this case experience drop leave analysis stay the same which unexpected but align with our hypothesis as before but not behaving as expect with out 
hypothesis while other labels drop death to zero that was so unexpected too over all gap is after train is .33 comepare to baseline at .433. So far i dont know yet happen but need more back up evidence in upcoming finding milestone


---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

### Confusion matrix

| true \ predicted | experience | analysis | outlook | reaction |
|---|---|---|---|---|
| **experience** | 10 | 0 | 0 | 0 |
| **analysis** | 6 | 0 | 0 | 0 |
| **outlook** | 8 | 0 | 0 | 0 |
| **reaction** | 6 | 0 | 0 | 0 |


This matrix is for seed 42 (the first seed in section 6). Run on CPU, torch 2.14.1. Accuracy across the three seeds was 0.333, 0.333 and 0.367, a spread of 0.033, so the result is stable. `analysis` and `reaction` have only 6 test posts each, so their scores can jump a lot between seeds.

**My biggest off-diagonal number, and what it means:**
The model put all 30 test posts in the `experience` column, so the matrix is one vertical line. Its 20 wrong answers are all off-diagonal in that column, and the biggest cell is 8 real `outlook` posts called `experience`. The training loss only went from about 1.36 to about 1.33 (guessing among 4 labels is about 1.39), so the model barely learned and mostly guessed its biggest label. I don't know yet whether this comes from my labels or from too little training; the agreement check in Milestone 3 should help me tell.


---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->



---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** ___ / 30 = ___%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**2.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**What the pattern in my disagreements tells me:**



---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->



**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->



<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
