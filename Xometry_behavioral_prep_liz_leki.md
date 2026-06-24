# Xometry — Behavioral / Culture Round Prep (Liz Leki)

**Role:** Staff Machine Learning Engineer, Generative AI ([JD](https://job-boards.greenhouse.io/xometry/jobs/4871650007)) · Waltham, hybrid, ITAR.
**Round:** Cultural & behavioral, 30–45 min.
**Interviewer:** **Elizabeth (Liz) Leki, Ph.D. — Director, ML Engineering** (ex-Under Armour: Data Scientist → Sr. Manager, Data Science; focus on **ML platform / MLOps / scalable high-throughput platforms**; AWS-certified).

> Adapted from your Capital One master story bank (S1–S11). Same stories, **reframed for Liz's platform/MLOps lens** and Xometry's GenAI-in-a-marketplace context. Bracketed `[numbers]` are yours to confirm.

---

## 0. Read the room — who Liz is, what she rewards

Liz is **not HR doing a soft culture chat** — she's a technical ML-platform leader. She'll read your stories for: **productionizing research, reliability/MLOps discipline, cross-team collaboration (DS ↔ engineering), and pragmatism over flash.** Lead with the stories that show research becoming durable production systems. She can tell a real story from a rehearsed one, so keep your *specific* actions and *quantified* results at the center.

Likely vibe: "How do you operate as a senior technical leader, what's it like to work with you, and will you thrive in a smaller, faster, hands-on org than Meta?"

---

## 1. Answer structure (every answer)

**S** (context + scale/stakes numbers) → **T** (your charge) → **A** (what **you** did — decisions, tradeoffs, influence) → **R** (quantified result) → **L** (lesson).

Rules: **lead with numbers**, **"I" > "we"**, make **influence/XFN explicit**, **close with quantified impact + a lesson**, ~2 min, then pause for follow-ups. Xometry (like any senior bar) rewards **repeatable systems/playbooks**, not one-offs.

**Three coach fixes (carry these in):**
1. **State role & scope UP FRONT.** One sentence before each story: *"I owned [X]; it spanned [N teams]; my span was [what I drove]."*
2. **Disagreements → lead with strategic upside (future/scaling), NOT sunk cost.** (See S10.)
3. **Incidents → Detection → Mitigation → Root cause → Prevention**, lead with mitigation. (See S4.)

---

## 2. Story → question map (Liz's lens)

| Question | Lead story |
|---|---|
| Project you led / drove results | **S6** (Sequential Recs) or **S1** (Shop the Look) |
| Productionizing research (★ most role-relevant) | **S1**, **S10** (HSTU generative) |
| Setting technical direction / influence w/o authority | **S2** (parallel multimodal), **S3** (inference partner) |
| Reliability / technical quality / MLOps (Liz's wheelhouse) | **S7** (IG Feed reliability), **S4** (incident) |
| Conflict / disagreement | **S3** (partner), **S10** (HSTU vs Slimer) |
| High-pressure / ownership | **S4** (label-drift incident) |
| Failure / learning | **S5** (eval upskilling miss) |
| Mentorship / growing people | **S8**, **S9** (peer/tech-lead mentorship) |
| Customer focus / doing the right thing | **S11** (CSAT gate) |
| Communicating complex ML to execs/non-technical | **S4**, **S6** |

**Lead with the flagships:** S1/S6 (project leadership), S10 (productionizing GenAI + hardest disagreement), S7 (reliability/MLOps — speaks Liz's language), S4 (incident), S5 (failure).

---

## 3. Master story bank (S1–S11)

### S1 · Shop the Look (STL) — flagship "project I led" / productionizing a new modality
**Opener:** *"I was the concept owner + technical lead — wrote the PRFAQ, owned the multimodal modeling, drove it concept→production over ~1 year. Span: my multimodal-science work + coordinating ~4 AS + 4 SWE and XFN partners (Amazon Fashion, BD, Alexa runtime/inference eng, context-carryover science, PMs). First-author on 2 papers + a granted patent."*
- **S:** Alexa was text-only; we made it multimodal. On-screen influencer images; user refers by visual attribute ("select the red dress"), drills in, adds to cart. Became the **first multimodal SLM in production** (pre Google/OpenAI multimodal).
- **A (spine = handling pushback):** PRFAQ drew leadership pushback on **tech maturity** and **real user need**.
  - *Tech maturity:* chose **multimodal embeddings** (CLIP-style: pre-encode images, encode utterance at runtime, dot-product match) over segmentation; proved **<300 ms** latency; built a prototype on a prototype Alexa device and demoed to leadership.
  - *User need:* stood up **focus groups** + a **multimodal-CSAT gate** (ship only at **≥4/5** on "would you use daily / does it feel natural"); iterated many rounds.
- **Production complexity:** latency <300 ms via caching image embeddings on device + cloud utterance encoding. *(Be ready: cleaner design is utterance-ID + image-ID all in cloud — acknowledge it.)* Context-carryover service moved from storing **text tokens → multimodal vectors** (bigger payload, same latency budget; ~500M-param transformers + contrastive loss).
- **R:** PRFAQ est. ~4–5% engagement; actual ≈ **2–3% at launch, ~1–2% sustained**; **+3–4% on-device purchases** for daily users; built Alexa multimodal train/inference from scratch; **2 papers + patent**. *(Confirm figures.)*
- **L:** led via **technical vision + influence, not authority**; for a net-new modality, expect actuals under the PRFAQ estimate.
- **Xometry bridge:** *"This is exactly the productionize-GenAI problem you're hiring for — taking a new multimodal capability from research to a latency- and reliability-bound product."*

### S2 · Parallel text + multimodal — influence / prioritization / disagreeing with leadership
- **S:** Pre-ChatGPT you'd shipped a multimodal SLM; leadership wanted **text-only** to chase ChatGPT.
- **A:** pushed back at **director/strategy level**; acknowledged execution risk; proposed a **de-risked parallel 12-mo roadmap** sharing infra + learnings; reframed "two competing bets" → "text first, multimodal layered on top." **Classify → Allocate → De-risk → Rebalance.**
- **R:** at text launch the **multimodal pipeline was ready** → seamless extension; faster multimodal in AGI; spun up the multimodal-eval team. *"Without it, 6–12 months behind."*
- **L:** influencing leadership = **conviction + pragmatism** (de-risk, tie to existing priorities).

### S3 · Inference partner conflict / adoption delay — conflict + DS↔Eng collaboration
- **S:** Tech Lead Applied Scientist on contextual + multimodal embeddings; partner inference-eng team agreed, then delivered sub-par latency/quality and resisted further investment (stretched, research risk).
- **A:** understood their **constraints**; reframed with **hard data**; aligned on shared goal; **phased** (session first, multimodal second); **reduced their friction** (lent AS effort); joint standups + roadmap + patent; **jointly escalated** for added investment. **Diagnose → Prove Value → Reduce Friction → Align Incentives → Drive Accountability → Scale.**
- **R:** shipped both in **1 yr**; **+4% engagement, +2% goal-success, no major defect regression**; created a reusable **Science↔Eng collaboration model**.
- **L:** *"Most conflicts aren't disagreement on goals — they're misaligned constraints."*

### S4 · Label-drift incident (Christmas freeze) — high-pressure / incident / MLOps ★ Liz-relevant
**Structure: Detection → Mitigation → Root cause → Prevention.**
- **Opener:** *"I own reliability for all late-stage recommendation/ranking models (~50% of my scope). A label-drift hit days before the Christmas freeze; on-calls couldn't triage it, so I led the response."*
- **Why it matters:** ranking → engagement → ads → revenue; models train **online (~hourly)**; freshness must be in hours (we compete with TikTok). Bad model = irrelevant feed = lost revenue, magnified at holiday peak.
- **① Detection:** normalized entropy (NE) for some task labels (P(comment)/P(like)/P(follow)) was **decaying**; online training started **following the decaying label**. Diagnosed by splitting labels by app → Android → specific Android version. (SEV2.)
- **② Mitigation (stop bleeding first):** options — fix our side / **hold model stable + pause online training** (stale vs. poison pill) / get **Google to patch upstream**. Had **DS quantify blast radius (~$millions)** → escalated to IG leadership + Google → **Android patch**. Then cleared corrupted data, rolled back the model, monitored label recovery, restarted training. *(Rejected dropping all Android traffic — ~250M/500M DAU, too much skew.)*
- **③ Root cause:** the Android version's UI change **broke the join between click events and training data** → labels dropped.
- **④ Prevention:** on-call + DS runbooks; a **revenue-based cross-org/company escalation path**; a **mitigation playbook** (hold-stale vs fix vs retrain-without-labels); easy **checkpoint rollback**; label-distribution-by-device dashboard; **config kill-switch** for a bad feed.
- **R:** contained over the freeze, avoided ~$millions; turned an undocumented annual fire-drill into a repeatable, faster response.
- **L:** *"In any incident I run Detection → Mitigation → Root cause → Prevention, leading with mitigation, and I make the next response faster."*

### S5 · Eval-framework upskilling miss — failure / learning ⭐ honest failure
- **S:** As tech lead, built a **multimodal LLM eval framework in 3 weeks** with science + eng; science delivered + pivoted; **eng wasn't upskilled** to maintain it. Delivery was explicit; **upskilling implicit** — director flagged the miss.
- **A:** owned it cleanly ("optimized short-term delivery over long-term capability"); gathered perspectives; instituted **pairing, design reviews, knowledge-sharing**; made future projects carry **explicit delivery + capability goals**.
- **R:** next cycle, engineers independently owned similar LLM-eval workflows.
- **L:** leadership = **building sustainable capability**; surface **implicit expectations** early.

### S6 · Sequential Recs into IG Feed — flagship technical project leadership ⭐
- **S:** Tech lead (IC), IG Feed Core ML ranking. Led **pointwise → sequential ranking** paradigm shift — technical *and* org challenge. XFN: modeling, data, training, infra/serving.
- **A:** set goals (**~2% lift** in time-spent/sessions; match train/serve latency); built a **joint Model/Data/Training/Serving roadmap** (killed silos); assigned POCs; drove **accuracy-vs-latency** tradeoff explicitly.
- **R:** hit targets; paradigm shift in feed ranking; **standardized the data format → reused by other teams**; foundation for future sequence-based ranking.
- **L:** *"Leading large ML initiatives is less about the model and more about orchestrating systems and teams."*

### S7 · IG Feed Reliability — technical quality + sustained XFN ★ Liz's wheelhouse
- **S:** Reliability priority for IG Feed ranking; as tech lead drove the **reliability roadmap** across data/features/training/serving; balanced PM (UX/velocity), Eng (stability), ML (quality).
- **A:** defined quality in **horizons** (immediate SEV / medium monitoring+tooling / long model+system fixes); **mechanisms not heroics** (metric tracking, reliability criteria in design/code/experiment reviews, **weekly reliability + monthly director reviews**, blameless postmortems); made tradeoffs explicit.
- **R:** **SEVs −40%, downtime −20%**; reliability embedded in design reviews; reactive firefighting → proactive discipline.
- **L:** *"Technical quality at scale comes from systems and culture, not heroics."*

### S8 · Channeled a strong engineer → org-wide agentic workstream — mentorship
- A strong engineer had lost motivation on reliability work; as tech lead I found the **intersection of their strengths (modeling+systems), interest (AI), and an org priority** → co-created a **model-debugging agent**; connected them to agentic-AI teams; **championed the work**.
- **R:** the debugging agent was **used across Feeds/Reels/Explore**; they grew into **leading a new agentic workstream**.
- **Framing:** *"I multiply impact by channeling strong engineers toward the highest-leverage emerging problems."*

### S9 · Raised the production bar with a strong researcher — mentorship / standards
- A strong researcher kept shipping elegant models that hurt prod latency. As tech lead I gave **direct, data-backed feedback**, paired them with systems engineers, **scoped-then-expanded** their work until they became the **org authority on feature reliability**. (Mentorship + raising the technical bar.)

### S10 · HSTU (generative) vs. Slimer (non-gen) — hardest technical disagreement ⭐ productionizing GenAI
- **S:** At Meta I **led bringing sequential *generative* recommendation (HSTU)** to IG Feed, replacing feature-based late-stage ranking. Scoped a **~1-yr** revamp. Late in the program, a parallel Reels team's **non-generative model (Slimer)** — built partly on *our* data — scored **numerically better**. Disagreement (with the systems lead): ship the generative model I'd led, or ship Slimer.
- **A:**
  1. **Challenged the comparison:** ours had **3 quarters** of online A/B; Slimer's was **~3 weeks + partly offline** — not apples-to-apples. Designed a quarter-long A/B; quantified the gap (both beat prod ~**50–60%**; the two differed only ~**5%** — plausibly noise).
  2. **Led with strategic upside (NOT sunk cost):** the generative model **launches at its lowest point** and improves via **scaling laws** (add layers, extend sequence 2k→8k→30k for ~linear gains). The non-gen model is **best-in-class with no headroom** → shipping it backs us into classical ML. HSTU is **future-resilient**.
  3. **Removed the either/or:** secured **two launch windows** — ship HSTU first, then Slimer on top if its results held.
  4. **Systematized:** parallel efforts **share work + get cross-team feedback before building**.
- **R:** shipped **HSTU first** (**~2–3% time-spent / teen-session lift**), then Slimer's incremental gains half a quarter later; relationship intact.
- **L:** *"I resolve technical disagreements with data and the long-term trajectory — scaling-law headroom — not by defending sunk effort."*
- ⚠️ **Delivery:** lead with the **scaling-laws / future-resilience** point; never "we worked 9 months so we should ship it" (sunk-cost trap).

### S11 · STL customer-satisfaction gate — "do the right thing" / customer focus
- **S:** Concept owner + tech lead for STL; competitive pressure to ship fast. Risk: a new modality gets a **novelty bump** then dies.
- **A:** refused to optimize for the launch date; partnered with product + BD on **focus groups**; defined a **CSAT gate (≥4/5 on "use daily / feels natural")**; accepted delay; communicated to leadership *why* a novelty would cost customer trust.
- **R:** shipped something customers valued — engagement + on-device purchases **moved and held** (not a spike); the gate became a **reusable bar**.
- **L:** doing right by the customer sometimes means **slowing down and holding a bar under pressure**, and bringing leadership along.

---

## 4. "Why Xometry / why leave Meta" (be honest + positive)

- **Pull, not push:** own a **0→1 GenAI charter end-to-end** with fast, visible customer/business impact — harder to get at Meta's scale.
- **Domain fit:** the manufacturing-marketplace problem (multimodal document understanding, extraction from drawings) echoes your **Celect** retail-marketplace work — which you enjoyed and thrived in (founding team, 10→60, Nike acquisition).
- **Build, not just lead:** you want to stay **hands-on** with frontier multimodal models, not drift into pure management.
- **Practical:** local to Waltham (Arlington); hybrid is a plus.

*(Note: Xometry's stated culture leans pragmatic/customer-and-quality-focused — emphasize ownership, low ego, bias to ship, and curiosity about the manufacturing domain.)*

---

## 5. "What's it like to work with you" (self-awareness)

- **Strengths:** calm under pressure, makes tradeoffs explicit, reduces collaborators' burden, communicates across technical/non-technical, brings clarity to ambiguity.
- **Growth edge (be real):** *"I've optimized for delivery speed at the expense of bringing people along — I learned that the hard way (S5), and now I plan explicitly for capability-building and stakeholder alignment up front."*

---

## 6. Questions to ask Liz (tailored to her platform/MLOps lens)

- How mature is the **ML platform and MLOps tooling** today, and where do you want it in 12 months?
- How do **ML engineering and data science divide ownership** here?
- What does the **path from research prototype to production** look like at Xometry?
- What's the **biggest gap** you're hoping this Staff hire closes?
- What does the team culture feel like on a good day — and on a hard one?
- How does leadership balance **moving fast on GenAI** with quality/reliability for customers?

---

## 7. Day-of reminders

- **Open every story with role & scope** (what you owned · who else · your span).
- **Disagreements → lead with strategic upside (scaling/future), not sunk cost** (S10).
- **Incidents → Detection → Mitigation → Root cause → Prevention**, lead with mitigation (S4).
- **Lead with flagships:** S1/S6 (leadership), **S10 (productionizing GenAI — most role-relevant)**, S7 (reliability — Liz's language), S4 (incident), S5 (failure).
- Speak her language: **research→production, MLOps, reliability, DS↔Eng collaboration.**
- Bridge to Xometry: every flagship ties to *"productionizing GenAI for a marketplace where correctness matters."*
- **"I," scale numbers up front, quantified impact + lesson to close;** pause for follow-ups; have questions ready.
- Be **warm, candid, self-aware** — culture rounds weight EQ and culture-add heavily.
