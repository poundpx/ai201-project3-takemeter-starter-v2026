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
After the train the data come out unexpectedly not align with what i have hypothesis. For `outlook` and `reaction`drop to  zero also here is `analysis` still stay flat in zero and `experience` 
goes down to .5 which might need to revise but it was very interesting because last time we say analysis will gain a bit more and experience drop
but in this case experience drop leave analysis stay the same which unexpected but align with our hypothesis as before but not behaving as expect with out 
hypothesis while other labels dropped to zero that was so unexpected too over all gap is after train is .33 comepare to baseline at .433. So far i dont know yet happen but need more back up evidence in upcoming finding milestone


---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1. Overall accuracy | ≥ 0.50 | 0.333 | 0.333 | 0.367 | MISSED |
| 2. Every label F1 (lowest label shown) | ≥ 0.40 | 0.000 | 0.000 | 0.000 | MISSED |
| 3. No label over 50% of predictions (biggest share shown) | ≤ 50% | 100% | 100% | 86.7% | MISSED |
| 4. Agreement with staff set | ≥ 18 of 30 (0.60) | 15 / 30 | 15 / 30 | 15 / 30 | MISSED |
| 5. `experience` F1 | ≥ 0.45 | 0.500 | 0.500 | 0.556 | MET |

### Confusion matrix

| true \ predicted | experience | analysis | outlook | reaction |
|---|---|---|---|---|
| **experience** | 10 | 0 | 0 | 0 |
| **analysis** | 6 | 0 | 0 | 0 |
| **outlook** | 8 | 0 | 0 | 0 |
| **reaction** | 6 | 0 | 0 | 0 |


This matrix is for seed 42 (the first seed in section 6). Run on CPU, torch 2.14.1. Before running section 6, I changed `LABELS` in notebook cell 7 from the starter's three example labels to my four real labels, since the notebook still had the starter list. Accuracy across the three seeds was 0.333, 0.333 and 0.367, a spread of 0.033, so the result is stable. `analysis` and `reaction` have only 6 test posts each, so their scores can jump a lot between seeds.

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

**Agreement rate:** 15 / 30 = 50%

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
> *The post:* "I tracked sleep against session quality for eleven weeks. Under seven hours the next day's intervals were 6-8 seconds per mile slower..."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* Staff is right. The eleven weeks of sleep-vs-interval data is what the conclusion about scheduling hard days rests on, so the fact carries the argument (Rule 1). I labeled it from "a runner talking about themselves" instead of asking whether the fact carries the argument.
>
> *Which pile:* (a)

**2.**
> *The post:* "The club championship scoring changed in 2019 from top-6 to top-10. Since then our B team has finished above the A team twice..."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* Staff is right. The 2019 scoring change and the B team finishing above the A team twice are the evidence for "it's the scoring rewarding turnout." Remove them and the claim has nothing behind it (Rule 1).
>
> *Which pile:* (a)

**3.**
> *The post:* "Carbon plates aren't the whole story. My times dropped 2% in the shoes and another 2% the following year in the same pair..."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* Staff is right. The 2% drop in the shoes and another 2% the next year in the same pair, with only the mileage changing, is what rules out shoes as the whole story. That comparison does the work (Rule 1).
>
> *Which pile:* (a)

**4.**
> *The post:* "Checked the entry lists. 41% of this year's field have never run the distance before, against 26% five years ago..."
>
> *Staff said / I said:* `analysis` / `reaction`
>
> *My call, and why:* Staff is right. "Checked the entry lists" sounded like something that had just happened to the writer, so I treated it as a reaction. But the 41% vs 26% comparison is the argument against "standards dropped," and Rule 3 says recency does not outrank a load-bearing fact.
>
> *Which pile:* (a)

**5.**
> *The post:* "Ran the same loop in 4C and in 24C within a fortnight, same effort by heart rate. 90 seconds slower in the heat over six miles..."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* Staff is right. The same loop at 4C and 24C at the same heart-rate effort, 90 seconds slower in the heat, is the evidence for "it's more than a bit" (Rule 1). I focused on "people keep saying..." which sounds like an opinion, and missed that the number carries it.
>
> *Which pile:* (a)

**6.**
> *The post:* "Went back through the club results going back to 2012. Every single year the number of people who enter the spring marathon and don't start it sits between 18 and 23 percent. It's not a bad-luck year, it's the base rate."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* Staff is right. The 18 to 23 percent range across every year since 2012 is the evidence for "it's the base rate, not a bad-luck year," so the fact carries the argument (Rule 1). I read the confident last sentence as the point and missed that the data supports it.
>
> *Which pile:* (a)

**7.**
> *The post:* "Three of us ran the same session on the same day, different shoes, within 10 seconds of each other over 5 miles. I'm not saying shoes do nothing, but whatever they do was smaller than the noise between three people."
>
> *Staff said / I said:* `analysis` / `hot_take`
>
> *My call, and why:* I still lean `hot_take`. The writer is careful about how the claim lands ("I'm not saying shoes do nothing") and the sample is three people, so to me it reads as a personal opinion dressed up with a number. Staff's reading is also fair, because "within 10 seconds" is a checkable fact and the conclusion rests on it (Rule 1), and Rule 1 doesn't say how a hedged tone or a tiny sample should count. So I think this one is arguable on both sides, though the rule leans toward staff.
>
> *Which pile:* (c)

**8.**
> *The post:* "Heart rate zones are astrology for runners."
>
> *Staff said / I said:* `hot_take` / `analysis`
>
> *My call, and why:* Staff is right. It has no stat, date, time, quote or named comparison, only a confident one-liner with nothing argued, so it fits the `hot_take` definition. I should not have called it `analysis`.
>
> *Which pile:* (a)

**9.**
> *The post:* "The club needs to stop pretending the Tuesday session is for everyone. It isn't and it never has been."
>
> *Staff said / I said:* `hot_take` / `reaction`
>
> *My call, and why:* I still read the strong tone as a reaction. But Rule 2 says a heated post is still a `hot_take` if it makes a general claim, and this one is about the club and "never has been," not about something that just happened to the writer. I can defend my reading only because the tone sounds immediate. The rule is on staff's side.
>
> *Which pile:* (c)

**10.**
> *The post:* "Track sessions are wasted on anyone running slower than 8 minute miles. You'd get more out of just running more."
>
> *Staff said / I said:* `hot_take` / `analysis`
>
> *My call, and why:* Staff is right. "8 minute miles" is a line the writer draws inside the claim, not evidence offered for it, and nothing is checkable behind "wasted" (Rule 1).
>
> *Which pile:* (a)

**11.**
> *The post:* "Nobody actually enjoys the long run. They enjoy having done it, which is a completely different thing, and the sport would be more honest if it said so."
>
> *Staff said / I said:* `hot_take` / `reaction`
>
> *My call, and why:* Staff is right. It is a general claim about everyone ("nobody actually enjoys") with no data behind it, not a report of something that just happened to the writer (Rule 2). It sounds reflective, which is why I read it as a reaction.
>
> *Which pile:* (a)

**12.**
> *The post:* "Every injury thread on this forum is the same injury and the same three replies."
>
> *Staff said / I said:* `hot_take` / `reaction`
>
> *My call, and why:* Staff is right. It is a general claim about every thread on the forum, with no count or example offered, so it is a `hot_take` (Rule 2). I responded to the annoyed tone instead of asking whether it was about the writer's own moment.
>
> *Which pile:* (a)

**13.**
> *The post:* "First run back after eight weeks out. Two miles, slower than my warm-up used to be, and I don't care even slightly."
>
> *Staff said / I said:* `reaction` / `hot_take`
>
> *My call, and why:* Staff is right. It reports the writer's own run and feeling, just done, and makes no general claim about the world (Rule 2). I took "I don't care even slightly" as a confident claim, but it is about the writer's own state.
>
> *Which pile:* (a)

**14.**
> *The post:* "Wind was so bad on the out section I was leaning at about 20 degrees. Coming back felt like cheating."
>
> *Staff said / I said:* `reaction` / `hot_take`
>
> *My call, and why:* Staff is right. It is a report of the run the writer just did and how it felt. The "20 degrees" is a figure of speech, not evidence for an argument (Rule 2, and Rule 3 does not apply because no fact carries a claim).
>
> *Which pile:* (a)

**15.**
> *The post:* "Just realised the shoes I set every PB in this year are the ones I bought by accident in the wrong size."
>
> *Staff said / I said:* `reaction` / `hot_take`
>
> *My call, and why:* Staff is right. "Just realised" marks a recent, personal moment about the writer's own shoes. It could be read as a wry comment about shoe talk, but it asserts nothing general (Rule 2).
>
> *Which pile:* (a)


**What the pattern in my disagreements tells me:**
Of my 15 disagreements, 13 are pile (a), meaning the rule already covered the post and I applied it loosely, and only 2 (posts 7 and 9) are pile (c). The biggest cluster is 7 posts that staff called `analysis` and I did not (6 as `hot_take`, 1 as `reaction`): I reacted to the first-person voice, the hedging or the confident ending, and missed that a checkable number carried the argument (Rule 1). The rest went the other way: in 5 posts staff called a general claim `hot_take` and I called it `reaction` (3 posts) or `analysis` (2 posts), and in 3 first-person moment posts (13 to 15) staff said `reaction` and I said `hot_take`. So I applied the rules by tone and voice instead of asking whether a fact is load-bearing or whether the post is about the writer's own moment. That is evidence that my own 200 labels may be inconsistent in the same way, though the staff set is only 30 posts and under different definitions than mine. It also means my 50% agreement rate (criterion 4 target was 18 of 30, so it is MISSED) points at my labeling, and I will weigh that against the model's under-training when I diagnose the other misses.



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
