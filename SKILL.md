---
name: introduction-master
description: Write polished introductions for top-tier CS conferences (NeurIPS, ICML, CVPR, ACL, etc.) and journals (Nature, Science). Use this skill whenever the user asks to write, draft, revise, or improve a paper introduction, "intro section", "introduction for my paper", or mentions they are preparing a submission for a top venue. Also trigger when the user provides a method/contribution and asks to turn it into a story or framework for a paper introduction.
---

# Introduction Writer for Top Venues

Write introductions that follow the proven structure of top conference and journal papers. Every introduction should tell a clear story: **a problem matters → existing methods can't solve it → you solved it → the results are strong**.

## Core Philosophy

Before writing a single word, internalize these principles:

1. **The reviewer has 15 minutes.** They will read your introduction first — and if the first three paragraphs don't hook them, they won't read the rest carefully. The introduction is the most important section of your paper.

2. **Don't start with grand backgrounds.** Reviewers have read "With the rapid development of deep learning..." thousands of times. It says nothing about YOUR work. Start with the specific problem you're solving.

3. **Your introduction tells a story, not a literature review.** Every paragraph should pull the reader forward. A reviewer should be able to answer three questions after reading: What problem do you solve? Why can't existing methods solve it? How do you solve it?

4. **Write the introduction LAST.** You'll know your real contribution, your actual results, and how you differ from prior work only after experiments are done. If you draft the intro first, you'll likely rewrite it anyway.

## The Four-Paragraph Structure

Nearly every top paper follows this structure. Deviate only when you have a specific reason.

### Paragraph 1: Problem and Motivation (The Hook)

**Goal:** Make the reviewer understand what you're working on within 30 seconds.

**What to do:**
- Open with the specific problem, task, or phenomenon — not the general field
- Use a concrete example, a striking fact, or a specific pain point if possible
- Establish why this problem matters in practical terms

**What NOT to do:**
- Start with "Recently, [field] has achieved remarkable progress..."
- Use more than 2-3 sentences of background before getting to the point
- List a long chain of prior work in the first paragraph

**Patterns from top papers:**

| Paper | Opening Sentence | Why It Works |
|-------|-----------------|--------------|
| FlashAttention (NeurIPS 2022) | "Transformer models have emerged as the most widely used architecture... but equipping them with longer context remains difficult, since self-attention has time and memory complexity quadratic in sequence length." | Names the problem immediately (slow on long sequences) |
| YOLOv10 (NeurIPS 2024) | "Real-time object detection has always been a focal point of research... which aims to accurately predict the categories and positions of objects in an image under low latency." | Defines the task crisply, hints at the constraint (low latency) |
| BLIP-2 (ICML 2023) | "Vision-language pre-training research has witnessed rapid advancement... However, most state-of-the-art models incur a high computation cost during pre-training, due to end-to-end training using large-scale models and datasets." | States the trend, then immediately points to the pain |
| LLaVA-1.5 (NeurIPS 2024) | "Large multimodal models (LMMs) have become increasingly popular... Recent studies are converging on visual instruction tuning. The results are promising... However, despite many benchmarks and developments, it still remains unclear what the best recipe is to train LMMs." | Narrows from general field to specific unsolved question |

### Paragraph 2: The Gap (Why Existing Work Falls Short)

**Goal:** Convince the reviewer that there is a real, unsolved problem that deserves attention.

This is the most critical paragraph. A weak gap means a weak paper.

**What to do:**
- Identify a SPECIFIC, VERIFIABLE shortcoming of existing approaches
- The gap should be sharp enough that the reviewer nods and thinks "yes, that is a problem"
- Support with evidence or concrete examples when possible

**What NOT to do:**
- Vague statements like "existing methods still have room for improvement"
- A laundry list of prior methods followed by "however, these methods have limitations"
- Gaps that your method doesn't actually address

**Proven gap patterns (pick the one that fits your work):**

- **Scenario gap:** "Existing methods only consider scenario X, but scenario Y is fundamentally different because..."
- **Assumption gap:** "Prior work assumes condition A holds, but in real deployments, A is routinely violated..."
- **Evaluation gap:** "Current benchmarks cover dimensions D1-D3, but lack coverage of critical dimension D4..."
- **Trade-off gap:** "Previous approaches solve problem X but introduce new problem Y; no method addresses both simultaneously..."
- **Scale gap:** "Existing work validates on small-scale data (hundreds of examples); performance degrades severely at real-world scale (millions)..."
- **Domain transfer gap:** "Method M performs well in English/Western contexts, but completely fails when applied to [other language/culture] because..."
- **Cost gap:** "Current approaches require extensive human annotation/expert intervention, making deployment at scale prohibitively expensive..."
- **Architecture gap:** "The standard pipeline relies on component C which creates bottleneck B, yet removing C has been considered infeasible because..."

**Examples from real papers:**

> FlashAttention: "Many approximate attention methods have aimed to reduce compute... Although these methods reduce FLOPs to linear or near-linear, **many of them do not display wall-clock speedup against standard attention** and have not gained wide adoption. One main reason is that they focus on FLOP reduction (which may not correlate with wall-clock speed) and **tend to ignore overheads from memory access (IO).**"

> YOLOv10: "YOLOs usually employ one-to-many label assignment... Despite yielding superior performance, **this approach necessitates NMS to select the best positive prediction during inference. This slows down inference speed** and renders performance sensitive to NMS hyperparameters..."

> VAR: "the scaling laws of these [visual AR] models remain underexplored, and more frustratingly, **their performance significantly lags behind diffusion models... the power of autoregressive models in computer vision appears to be somewhat locked.**"

### Paragraph 3: Your Approach (How You Fill the Gap)

**Goal:** Explain at a high level what you did and WHY you did it that way.

**What to do:**
- State your key insight or approach in 2-4 sentences
- Explain **why** your approach solves the gap identified in Paragraph 2
- Connect each design choice back to a specific limitation you mentioned
- Include a forward reference to Figure 1 if you have an overview figure

**What NOT to do:**
- Dump technical details — save those for the Method section
- Just list what you used without explaining why
- Present your method as an obvious combination of existing techniques

**Key principle: Method simplicity is not a weakness IF you explain why.** If your method is A+B, you must explain why this particular combination is non-obvious and why it solves the gap.

**Template pattern:**
> "In this work, we aim to [address the gap]. To this end, we first [key insight 1] by [approach]. This allows us to [benefit]. Secondly, we [key insight 2] to [benefit]. Unlike [prior approach] which [limitation], our method [advantage]."

### Paragraph 4: Contributions and Results

**Goal:** Summarize what the reader should take away — specific contributions and key results.

**What to do:**
- List 3-4 specific, verifiable contributions
- Include concrete numbers when possible (datasets built, performance improvements, etc.)
- State results that support your claims
- Keep contributions factual, not aspirational

**What NOT to do:**
- Vague contributions: "We propose a novel method for X"
- Overclaimed adjectives: "groundbreaking", "revolutionary", "significant" (let facts speak)
- Contributions that are actually just things you did ("We ran experiments on dataset X")

**Good contribution format:**
> "Our contributions are three-fold: (1) We construct [name], a benchmark of X samples covering Y scenarios... (2) We propose [method], which addresses [gap] by [key mechanism]... (3) Extensive experiments on Z benchmarks demonstrate that [method] outperforms [baseline] by A% on [metric] while requiring B× less [resource]..."

## Figure 1 Design Guidance

Modern top-conference papers almost always include a Figure 1 on page 1 that visually tells the entire story. When discussing the introduction, proactively ask about or suggest a Figure 1 concept.

**What makes a good Figure 1:**
- Shows the problem, the limitation of existing approaches, and your solution — all in one visual
- Uses a consistent visual language (color coding, icons)
- Is self-contained: a reviewer can understand the core idea by looking at Figure 1 + caption alone
- Does NOT dump all method details — keep it high-level

**Practical tip from experienced authors:** Draw Figure 1 BEFORE writing the introduction. If you can't draw it, you haven't thought clearly enough about your contribution.

## Self-Check After Writing

After drafting the introduction, verify you can answer these three questions in one sentence each:

1. **What problem do you solve?** (One sentence, understandable to a non-expert)
2. **Why can't existing methods solve it?** (One specific, falsifiable gap)
3. **How do you solve it?** (One sentence on your key insight)

If any answer is unclear to you, it will be unclear to the reviewer. Revise until each answer is crisp.

## Length Guidelines

- **Conference papers (NeurIPS, ICML, CVPR, etc.):** ~1.5 to 2 pages in the conference template. If you exceed 2 pages, cut aggressively — reviewer patience has limits.
- **Journal papers (Nature, Science, TPAMI, etc.):** Can be shorter or longer depending on the journal format. Nature/Science introductions are typically very condensed.

## Common Mistakes to Avoid

1. **Overusing adjectives.** Words like "novel", "significant", "state-of-the-art", and "groundbreaking" signal insecurity, not strength. Let your results speak.

2. **Writing a Related Work section in disguise.** Paragraph 2 should NOT be a list: "Method A did X [1], Method B did Y [2], Method C did Z [3]... however these methods have limitations." This tells the reviewer nothing about WHY existing work is insufficient for YOUR specific problem.

3. **Too many citations in the introduction.** Use citations to support specific claims, not to show you've read the literature. 5-15 well-chosen citations is better than 40 scattered ones.

4. **Delaying the hook.** If your first 3-4 sentences don't communicate what problem you're solving, rewrite them.

5. **Contributions that don't match the story.** If your gap paragraph talks about efficiency, but your first contribution is about accuracy, there's a mismatch. The contributions should flow naturally from the gap.

## Interactive Writing Process

When the user asks you to write or revise an introduction:

1. **Gather information first.** Ask for: the research problem, the specific gap, the key method/insight, and the main results. If the user hasn't done experiments yet, suggest they wait before finalizing the introduction.

2. **Draft each paragraph with clear intent.** Label the role of each paragraph (hook, gap, approach, contributions) so the user can assess whether the structure works.

3. **Point out weak spots.** If a gap is vague, say so and ask for more specifics. If contributions are soft, suggest making them more concrete.

4. **Offer alternatives.** For the opening hook, offer 2-3 different styles (concrete example vs. striking fact vs. specific problem statement) and let the user choose.

5. **Iterate.** Introduction writing is rewriting. The first draft is rarely the final one.
