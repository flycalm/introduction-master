# Annotated Paper Introductions

Each example shows the complete introduction from a real top-venue paper, with annotations explaining why each paragraph works.

---

## Example 1: FlashAttention (NeurIPS 2022, now widely cited)

### Paragraph 1 — Problem Hook

> Transformer models have emerged as the most widely used architecture in applications such as natural language processing and image classification. Transformers have grown larger and deeper, but equipping them with longer context remains difficult, since the self-attention module at their heart has time and memory complexity quadratic in sequence length. An important question is whether making attention faster and more memory-efficient can help Transformer models address their runtime and memory challenges for long sequences.

**Why it works:**
- Opens with the architecture everyone knows (Transformer) — establishes relevance immediately
- States the specific pain point (quadratic complexity on long sequences) in sentence 2
- Frames the paper as answering a clear question — the reader now wants to know the answer

### Paragraph 2 — The Gap

> Many approximate attention methods have aimed to reduce the compute and memory requirements of attention. These methods range from sparse-approximation to low-rank approximation, and their combinations. Although these methods reduce the compute requirements to linear or near-linear in sequence length, many of them do not display wall-clock speedup against standard attention and have not gained wide adoption. One main reason is that they focus on FLOP reduction (which may not correlate with wall-clock speed) and tend to ignore overheads from memory access (IO).

**Why it works:**
- Acknowledges existing efforts (shows you know the literature)
- Sharp, specific gap: FLOP reduction doesn't translate to actual speedup because of IO overhead
- The gap is falsifiable and technical — not "methods could be better"
- Explains WHY the gap exists (focus on FLOPs, ignore memory access), which sets up their solution perfectly

### Paragraph 3 — The Approach

> In this paper, we argue that a missing principle is making attention algorithms IO-aware — that is, carefully accounting for reads and writes to different levels of fast and slow memory (e.g., between fast GPU on-chip SRAM and relatively slow GPU high bandwidth memory, or HBM). We propose FlashAttention, an IO-aware exact attention algorithm that uses tiling to reduce the number of memory reads/writes between GPU HBM and GPU on-chip SRAM.

**Why it works:**
- Names the key insight clearly (IO-awareness) — this becomes the paper's intellectual contribution
- Explains what IO-aware means in one parenthetical
- States the method name and the core technique (tiling) without diving into implementation

### Paragraph 4 — Contributions/Results

> FlashAttention trains Transformers faster than existing baselines: 15% end-to-end wall-clock speedup on BERT-large, 3x speedup on GPT-2, and 2.4x speedup on long-range arena. FlashAttention and block-sparse FlashAttention enable longer context in Transformers, yielding higher quality models (0.7 better perplexity on GPT-2 and 6.4 points of lift on long-document classification) and entirely new capabilities: the first Transformers to achieve better-than-chance performance on Path-X (seq. length 16K, 61.4% accuracy) and Path-256 (seq. length 64K, 63.1% accuracy).

**Why it works:**
- Numbers, numbers, numbers — every claim is backed by a specific metric
- Shows both efficiency gains (speedup) AND capability gains (longer context, new tasks)
- Ends with the strongest result (first-ever on Path-X/Path-256)

---

## Example 2: YOLOv10 (NeurIPS 2024)

### Paragraph 1 — Problem Context

> Real-time object detection has always been a focal point of research in the area of computer vision, which aims to accurately predict the categories and positions of objects in an image under low latency. It is widely adopted in various practical applications, including autonomous driving, robot navigation, and object tracking, etc. In recent years, researchers have concentrated on devising CNN-based object detectors to achieve real-time detection. Among them, YOLOs have gained increasing popularity due to their adept balance between performance and efficiency.

**Why it works:**
- Immediately defines the task AND the constraint (accuracy under low latency)
- Grounds the problem in real applications (autonomous driving, robot navigation)
- Narrows naturally to YOLOs as the focus

### Paragraph 2 — Gap 1 (Post-processing)

> The detection pipeline of YOLOs consists of two parts: the model forward process and the NMS post-processing. However, both of them still have deficiencies, resulting in suboptimal accuracy-latency boundaries. Specifically, YOLOs usually employ one-to-many label assignment strategy during training... Despite yielding superior performance, this approach necessitates NMS to select the best positive prediction during inference. This slows down the inference speed and renders the performance sensitive to the hyperparameters of NMS, thereby preventing YOLOs from achieving optimal end-to-end deployment.

**Why it works:**
- Two clearly separated gaps (NMS + architecture) — each gets its own paragraph
- Explains the technical reason for the gap (one-to-many assignment → NMS dependency)
- Explains why the gap matters (slows inference, sensitive to hyperparameters, prevents end-to-end deployment)

### Paragraph 3 — Gap 2 (Architecture)

> Furthermore, the model architecture design remains a fundamental challenge for YOLOs... While these efforts have achieved notable advancements, a comprehensive inspection for various components in YOLOs from both the efficiency and accuracy perspectives is still lacking. As a result, there still exists considerable computational redundancy within YOLOs, leading to inefficient parameter utilization and suboptimal efficiency.

**Why it works:**
- Second gap is distinct from the first — architecture vs. post-processing
- Points to a specific root cause (no comprehensive inspection, redundancy)

### Paragraph 4 — The Approach (merged with contributions)

> In this work, we aim to address these issues and further advance the accuracy-speed boundaries of YOLOs. We target both the post-processing and the model architecture throughout the detection pipeline. To this end, we first tackle the problem of redundant predictions in the post-processing by presenting a consistent dual assignments strategy for NMS-free YOLOs... Secondly, we propose the holistic efficiency-accuracy driven model design strategy for the model architecture...

**Why it works:**
- Clear mapping: each part of the approach addresses a specific gap mentioned earlier
- The approach section directly connects back to the two gaps identified in paragraphs 2-3

---

## Example 3: VAR (NeurIPS 2024)

### Paragraph 1 — The Big Picture

> The advent of GPT series and more autoregressive (AR) large language models (LLMs) has heralded a new epoch in the field of artificial intelligence. These models exhibit promising intelligence in generality and versatility... At the core of these models is a self-supervised learning strategy — predicting the next token in a sequence, a simple yet profound approach. Studies into the success of these large AR models have highlighted their scalability and generalizability...

### Paragraph 2 — The Gap in Vision

> In parallel, the field of computer vision has been striving to develop large autoregressive or world models, aiming to emulate their impressive scalability and generalizability. Trailblazing efforts like VQGAN and DALL-E along with their successors have showcased the potential of AR models in image generation... However, the scaling laws of these models remain underexplored, and more frustratingly, their performance significantly lags behind diffusion models... In contrast to the remarkable achievements of LLMs, the power of autoregressive models in computer vision appears to be somewhat locked.

**Why it works:**
- Sets up a contrast: AR works great for language, but is "locked" for vision
- The gap is provocative: "significantly lags behind diffusion models" — this is a strong, specific claim
- Creates dramatic tension: LLMs succeed brilliantly, but visual AR models fail — why? (The reader wants to know)

---

## Common Patterns Across All Examples

1. **Every introduction has a clear "before/after" pivot point** — usually signaled by "However", "In this paper", or "We propose"
2. **Gaps are always specific and technical**, never "existing methods could be improved"
3. **The approach paragraph always maps back to the gap** — if the gap is about IO overhead, the approach is IO-awareness; if the gap is about NMS, the approach eliminates NMS
4. **Results use concrete numbers** — percentages, speedup ratios, absolute metric values
5. **No introduction exceeds ~2 pages** in the original format
