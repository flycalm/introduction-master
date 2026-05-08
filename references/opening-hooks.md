# Opening Hook Strategies

The first 2-3 sentences of your introduction determine whether the reviewer keeps reading. Here are proven strategies for crafting effective openings, with examples from top papers.

---

## Strategy 1: The Specific Problem Statement

Open by naming exactly what task or problem you address. This is the most common and reliable strategy.

**Template:** "[Task] aims to [goal], but [specific difficulty]. This paper addresses [your angle]."

**Real examples:**
- FlashAttention: "Transformer models have emerged as the most widely used architecture... but equipping them with longer context remains difficult, since the self-attention module at their heart has time and memory complexity quadratic in sequence length."
- YOLOv10: "Real-time object detection has always been a focal point of research in the area of computer vision, which aims to accurately predict the categories and positions of objects in an image under low latency."

**Best for:** Systems papers, method papers, any paper where the problem is already well-known in the community.

---

## Strategy 2: The Concrete Example

Open with a specific, vivid example that illustrates why the problem matters in practice.

**Template:** "[Specific scenario with details]. This illustrates [broader problem your paper addresses]."

**Adapted examples (from the guidance):**
- For a hallucination/safety paper: "In 2024, a lawyer cited ChatGPT-generated case law in court — the judge discovered all six cases were fabricated, complete with fake citations and docket numbers. When LLMs enter medical diagnosis, legal counsel, and financial decision-making, a single hallucination can mean a lost lawsuit, a catastrophic investment, or a life-threatening misdiagnosis."
- For a multilingual paper: "A mental health chatbot that works flawlessly in English tells a Spanish-speaking teenager 'no entiendo tu pregunta' when she describes suicidal thoughts. This is not a hypothetical — most deployed NLP systems fail catastrophically on non-English inputs, and no existing benchmark systematically measures this gap."

**Best for:** Papers addressing safety, fairness, robustness, or real-world deployment. Also works well for papers introducing a new problem or benchmark.

---

## Strategy 3: The Striking Contradiction

Open by pointing out a paradox or contradiction in the current state of the field.

**Template:** "While [field] has made enormous progress on [metric A], it has surprisingly neglected / failed at [aspect B]."

**Real example:**
- VAR: "The advent of GPT series... has heralded a new epoch... At the core of these models is... predicting the next token. [Paragraph of LLM success]. In parallel, the field of computer vision has been striving to develop large autoregressive models... However... their performance significantly lags behind diffusion models. In contrast to the remarkable achievements of LLMs, the power of autoregressive models in computer vision appears to be somewhat locked."

**Best for:** Papers that challenge a prevailing assumption, reveal a surprising finding, or apply a technique from one domain to another where it hasn't been tried.

---

## Strategy 4: The Gap in Understanding

Open by identifying a fundamental question that the field hasn't answered.

**Template:** "Despite the success of [technique/approach], it remains unclear [specific unanswered question]."

**Real example:**
- LLaVA-1.5: "Large multimodal models (LMMs) have become increasingly popular... Recent studies on LMMs are converging on a central concept known as visual instruction tuning. The results are promising... However, despite many benchmarks and developments, it still remains unclear what the best recipe is to train LMMs towards the goal of general-purpose assistants."

**Best for:** Systematic studies, ablation papers, papers that unify or compare existing approaches.

---

## Strategy 5: The Cost/Pain Point

Open by quantifying a practical barrier that prevents wider adoption.

**Template:** "While [approach] achieves [good result], it requires [prohibitive cost], which prevents [important application]."

**Real example:**
- BLIP-2: "Vision-language pre-training research has witnessed rapid advancement... where pre-trained models with increasingly larger scale have been developed to continuously push the state-of-the-art... However, most state-of-the-art vision-language models incur a high computation cost during pre-training, due to end-to-end training using large-scale models and datasets."

**Best for:** Efficiency papers, democratization papers, papers that make a technique more accessible.

---

## Choosing Your Strategy

Ask yourself:
1. Is my problem well-known in the community? → Strategy 1 (Problem Statement) or Strategy 4 (Gap in Understanding)
2. Does my problem have real-world impact that might not be obvious? → Strategy 2 (Concrete Example)
3. Am I challenging a community assumption? → Strategy 3 (Striking Contradiction)
4. Is my main contribution making something practical/cheaper? → Strategy 5 (Cost/Pain Point)

---

## What to Avoid

- **"With the rapid development of deep learning..."** — This has been written thousands of times. The reviewer's eyes will glaze over.
- **"In recent years, [field] has attracted significant attention..."** — Every field attracts significant attention. What makes YOUR work matter?
- **Starting with a citation dump.** "Large language models have shown remarkable capabilities [1,2,3,4,5,6,7,8]..." — The first sentence should be YOUR idea, not a list of references.
- **Too broad.** If your first sentence could apply to 500 other papers, narrow it down.
