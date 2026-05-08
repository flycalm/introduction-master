# Gap Patterns: How to Write a Sharp, Compelling Gap

The gap paragraph is the most critical part of your introduction. A weak gap makes the reviewer question whether your paper needs to exist. A sharp gap makes them nod and think "yes, someone should solve that."

---

## The Anatomy of an Effective Gap

A good gap paragraph has three components:

1. **Acknowledge what exists** (1-2 sentences): Show you know the landscape. This builds credibility.
2. **Identify what's missing or broken** (the core gap): Be specific, technical, and falsifiable.
3. **Explain the consequence** (1 sentence): Why does this gap matter? What breaks because of it?

---

## Eight Proven Gap Templates

### 1. Scenario Gap
**Pattern:** "Existing methods focus on X, but real-world deployment involves Y, which is different because [reason]."

**When to use:** Your work addresses a setting, domain, or scenario that prior work ignored.

**Example (real, adapted):**
> "Existing VQA benchmarks exclusively use images sourced from English-speaking countries and evaluated on English questions. However, visual question answering in non-English cultural contexts involves fundamentally different visual concepts, scene compositions, and linguistic structures. A model that achieves 80% on VQAv2 may fail to recognize common objects in a Southeast Asian market or a Middle Eastern household, because these visual concepts are simply absent from training data."

---

### 2. Assumption Gap
**Pattern:** "Prior work assumes [condition A], but [condition A] does not hold in practice because [reason]."

**When to use:** Your work removes or relaxes a limiting assumption.

**Example (real, adapted from top papers):**
> "Most object detection methods assume that NMS post-processing is an acceptable cost for removing duplicate predictions. However, in real-time deployment scenarios such as autonomous driving and robot navigation, the non-deterministic runtime of NMS creates unpredictable latency spikes that can cause control loops to miss deadlines. No existing work has demonstrated competitive detection accuracy without relying on NMS or introducing equivalent post-processing overhead."

---

### 3. Trade-off Gap
**Pattern:** "Method A addresses problem X but worsens problem Y. Method B addresses Y but worsens X. No method addresses both simultaneously."

**When to use:** Your work achieves a Pareto improvement over existing methods.

**Example (real, adapted):**
> "Existing approaches to instruction tuning present a trade-off: models like LLaVA excel at conversational visual reasoning but underperform on academic VQA benchmarks requiring short-form answers, while models like InstructBLIP achieve strong VQA performance but produce overly brief, unhelpful responses for conversational queries. The root cause of this trade-off remains unknown, and no single model achieves strong performance on both axes simultaneously."

---

### 4. Evaluation Gap
**Pattern:** "Existing benchmarks cover dimensions D1-D3 but lack D4, which is critical because [reason]."

**When to use:** Your main contribution is a new benchmark, dataset, or evaluation methodology.

**Example (adapted):**
> "Current LLM evaluation suites comprehensively measure factual accuracy (MMLU), reasoning (GSM8K), and coding ability (HumanEval). However, no benchmark systematically evaluates an LLM's ability to recognize and communicate its own uncertainty — a capability that is critical for high-stakes deployment in medical and legal domains, where overconfidence can lead to catastrophic errors."

---

### 5. Scale Gap
**Pattern:** "Method M works on N examples, but real-world deployment involves M examples (M >> N), and performance degrades by [X%] at scale."

**When to use:** Your work demonstrates scalability that prior methods lack.

**Example (real, adapted):**
> "Recent advances in protein structure prediction have shown impressive accuracy on curated benchmark sets of a few hundred proteins. However, when these methods are applied to the full set of known protein sequences (hundreds of millions), the computational cost becomes prohibitive, and accuracy degrades for sequences with few evolutionary homologs. The gap between benchmark performance and real-world applicability remains unquantified."

---

### 6. Domain/Bias Gap
**Pattern:** "Method M works well in context C1 (typically English/Western/majority), but fails in context C2 because [specific reason]."

**When to use:** Your work addresses fairness, bias, or cross-domain transfer.

**Example (adapted):**
> "Toxicity detection models trained on English social media data achieve >95% AUC on in-domain test sets. However, when applied to content in African American Vernacular English (AAVE), these same models flag innocuous in-group expressions as toxic at 2-3x the rate of Standard American English, because the training data systematically under-represents AAVE speakers and over-represents toxic labels on AAVE text."

---

### 7. Architecture/Pipeline Gap
**Pattern:** "The standard pipeline requires component C, which introduces bottleneck B. Removing C would solve B, but has been considered infeasible because [reason]."

**When to use:** Your work restructures an established pipeline or architecture.

**Example (real, adapted from FlashAttention):**
> "The standard Transformer self-attention implementation reads and writes the full attention matrix to GPU HBM at every layer. This creates a memory bandwidth bottleneck: the compute capabilities of modern GPUs far outstrip HBM bandwidth, meaning attention is IO-bound rather than compute-bound for all but the longest sequences. Previous attempts to reduce this bottleneck through approximation sacrifice accuracy without achieving wall-clock speedup."

---

### 8. Supervision/Data Gap
**Pattern:** "State-of-the-art methods require [expensive resource], which limits [important application]."

**When to use:** Your work reduces data/label/supervision requirements.

**Example (adapted):**
> "Current state-of-the-art medical image segmentation models require pixel-level annotations from board-certified radiologists, costing approximately $200 per image and requiring months of effort. This annotation bottleneck means that these models can only be developed for the most common conditions at well-funded institutions, while rare diseases and resource-constrained settings are systematically excluded from benefiting."

---

## Red Flags: Signs Your Gap is Too Weak

If your gap paragraph sounds like any of these, revise it:

| Weak Statement | Problem | Stronger Alternative |
|---------------|---------|---------------------|
| "Existing methods still have room for improvement." | Every method always has room for improvement. Not a gap. | "Existing methods fail on X because of Y." |
| "Previous work has not explored [your method]." | Absence of evidence is not evidence of a gap. Why SHOULD it be explored? | "Previous work cannot handle X, which is necessary for Y." |
| "Despite recent progress, challenges remain." | Which challenges? Why do they remain? | Name the specific challenge and its root cause. |
| "Method A achieves SOTA but has not been applied to domain B." | Domain transfer is a contribution only if domain B is genuinely different in a way that matters. | Explain what specifically breaks when applying A to B. |

---

## The "However" Test

After writing your gap paragraph, find the word "However" (or equivalent pivot). Everything before it should establish what's known. Everything after it should establish what's unknown and why it matters. If the "after" part could apply to any paper in your subfield, it's not specific enough.
