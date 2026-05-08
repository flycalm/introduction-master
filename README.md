# Introduction-Master

> AI-powered introduction writing skill for top-tier conferences and journals — built from the DNA of Nature, Science, NeurIPS, ICML, and CVPR papers.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**English** | [中文](#中文)

---

## Why Introduction Matters More Than Method

Here's a truth most researchers learn too late: **reviewers spend 15 minutes on your paper, and most of that is on the Introduction.**

Think about it. NeurIPS gets ~40,000 submissions. Each reviewer handles 5-10 papers. They're unpaid volunteers. They scan your Abstract, read the first three paragraphs of your Introduction, glance at Figure 1 — and **that's when they decide whether your paper is a 5 (weak reject) or a 7 (weak accept).**

Your Method section could be brilliant. Your experiments could be flawless. But if your Introduction doesn't hook the reviewer in those first paragraphs, **they'll never read them carefully enough to find out.**

The Introduction is your paper's story. And at top venues, **storytelling wins.**

---

## The Pain Points You Know Too Well

Every researcher who's written a paper has felt this:

| Pain Point | You've Been There |
|-----------|-------------------|
| **The Blank Page** | "How do I even start? 'With the rapid development of deep learning...' — no, that's what EVERYONE writes." |
| **The Vague Gap** | "Existing methods have limitations... but what SPECIFICALLY is wrong? I know there's a gap, but I can't articulate it sharply." |
| **The Dense Reviewer** | "I wrote 2 pages explaining my approach, and Reviewer #2 still said 'novelty is unclear.' What did I do wrong?" |
| **The Structure Struggle** | "Do I start with background? Do I list related work? Do I save contributions for the end? I've rearranged the same paragraphs 5 times." |
| **The Contribution Cliché** | "We propose a novel method... significant improvements... state-of-the-art performance." — Every. Single. Paper. |
| **The Figure 1 Problem** | "I have results figures, but I don't know how to design that overview figure that tells the whole story at a glance." |

These aren't writing problems. They're **structural problems** — and they're solvable.

---

## What Introduction-Master Does

**Introduction-Master** is a Claude Code skill that teaches you to write introductions the way top papers actually write them. Not theory. Not generic advice. **Patterns extracted from reading 15+ Nature/Science/NeurIPS papers line by line.**

It turns this vague feeling of "I need a better intro" into a **concrete, repeatable process:**

1. **Diagnoses** what's wrong with your current draft (vague gap? weak hook? contributions that don't match the story?)
2. **Suggests** specific opening strategies (5 proven templates) and gap patterns (8 templates) that match your paper's actual contribution
3. **Drafts** paragraphs that follow the exact 4-part structure used by FlashAttention, YOLOv10, LLaVA, AlphaFold3, BLIP-2, and more
4. **Checks** that your introduction passes the "three-question test" every reviewer unconsciously applies

---

## Quick Start

```bash
# Clone the skill into your Claude Code skills directory
git clone https://github.com/flycalm/introduction-master.git

# Use it in Claude Code
/introduction-master
```

Then describe your paper to Claude — what problem you solve, what gap exists, what method you built, what results you got. The skill will guide you from there.

---

## What Makes This Different

Most introduction advice tells you: "be clear", "state your contributions", "motivate your work."

**This skill shows you HOW**, with real patterns from real papers:

- **5 opening hook strategies** — from "The Concrete Example" (used in safety/robustness papers) to "The Striking Contradiction" (used in paradigm-shift papers)
- **8 gap templates** — scenario gaps, assumption gaps, trade-off gaps, scale gaps, domain transfer gaps, and more
- **Annotated real introductions** from FlashAttention, YOLOv10, VAR, LLaVA-1.5, and others — showing why each sentence works, not just what it says
- **The self-check framework**: "What problem? Why can't others solve it? How do you solve it?" — if any answer is unclear, the introduction needs work

---

## Repository Structure

```
introduction-master/
├── SKILL.md                          # Main skill — the writing process & 4-paragraph framework
└── references/
    ├── paper-examples.md             # Line-by-line annotated introductions from top papers
    ├── opening-hooks.md              # 5 opening strategies with templates & real examples
    └── gap-patterns.md               # 8 proven gap patterns + red flags checklist
```

---

## License

MIT © [flycalm](https://github.com/flycalm)

---

# 中文

## 为什么 Introduction 比 Method 重要

说一个大多数研究者都踩过的坑：**审稿人在你的论文上只花 15 分钟，而其中大部分时间都用在读 Introduction 上。**

想想这个场景。NeurIPS 每年收到 ~4 万篇投稿。每个审稿人手里 5-10 篇。他们是义务劳动。他们扫一眼 Abstract，读完 Introduction 的前三段，瞟一眼 Figure 1——**就在这几分钟里，他们已经决定了你的论文是 5 分（弱拒）还是 7 分（弱收）。**

你的 Method 写得再漂亮，你的实验做得再扎实——但如果 Introduction 前三段没把人勾住，**审稿人根本不会认真看后面的内容。**

Introduction 是你论文的故事。在顶会上，**故事讲得好的人赢。**

---

## 写 Introduction 的那些痛点，你一定懂

每个写过论文的研究者都有过这些体验：

| 痛点 | 你肯定经历过 |
|------|-------------|
| **无从下手** | "第一句话怎么写？'随着深度学习的飞速发展……' ——不行，所有人都这么写。" |
| **Gap 说不清楚** | "现有方法确实有不足……但到底是哪里不足？我知道有 Gap，但就是没法一句话讲透。" |
| **审稿人不买账** | "我写了两页纸解释我的方法，Reviewer #2 还是说 'novelty is unclear'。到底哪里出了问题？" |
| **结构来回改** | "第一段写背景？第二段写 Related Work？Contribution 放最后？同一堆素材，来回排了五遍了。" |
| **贡献写成了套话** | "我们提出了一个新颖的方法……显著的性能提升……达到了 state-of-the-art……"——每篇论文都这么写。 |
| **Figure 1 不会画** | "我有实验结果图，但我不知道那张一张图讲清楚整篇论文的 Overview Figure 该怎么设计。" |

这些不是写作水平的问题。这些是**结构性问题**——而结构性问题是有办法解决的。

---

## Introduction-Master 做什么

**Introduction-Master** 是一个 Claude Code skill，教你怎么用顶会论文真正的写法来写 Introduction。不讲虚的，不给泛泛的建议。**从 15+ 篇 Nature/Science/NeurIPS 顶会论文里逐行拆解出来的模式。**

它把你脑子里那个"我觉得 Introduction 写得不好"的模糊感觉，变成一个**具体可操作的流程：**

1. **诊断**你的草稿哪里有问题（Gap 太虚？Hook 不够抓人？Contribution 和前面的故事对不上？）
2. **推荐**适合你论文的开场策略（5 种模板）和 Gap 写法（8 种模板）
3. **草拟**遵循顶会论文四段式结构的段落——FlashAttention、YOLOv10、LLaVA、AlphaFold3、BLIP-2 都是这个结构
4. **自检**你的 Introduction 能不能通过每个审稿人潜意识里都在做的"三问测试"

---

## 快速开始

```bash
# 克隆 skill 到你的 Claude Code 目录
git clone https://github.com/flycalm/introduction-master.git

# 在 Claude Code 中使用
/introduction-master
```

然后告诉 Claude 你的论文——解决了什么问题、有什么 Gap、你的方法是什么、实验结果如何。Skill 会引导你一步步完成 Introduction。

---

## 和普通写作建议的区别

大多数 Introduction 写作建议会告诉你："要清晰"、"要突出贡献"、"要讲好动机"。

**这个 skill 告诉你具体怎么做**，用的全是真实论文里的真实模式：

- **5 种开场策略**——从"具体案例式"（适合可信AI/安全类论文）到"反差冲击式"（适合范式革新类论文）
- **8 种 Gap 模板**——场景缺口、假设缺口、权衡缺口、规模缺口、领域迁移缺口……每种都有真实论文的原文案例
- **逐句批注的真实 Introduction**——FlashAttention、YOLOv10、VAR、LLaVA-1.5 等顶会论文的 Introduction，不止告诉你写了什么，还解释为什么这么写有效
- **三问自检框架**："你做什么问题？为什么现有方法做不了？你怎么做的？"——有任何一个答不清楚，Introduction 就还需要改

---

## 仓库结构

```
introduction-master/
├── SKILL.md                          # 主 skill — 写作流程 & 四段式框架
└── references/
    ├── paper-examples.md             # 顶会论文 Introduction 逐句批注
    ├── opening-hooks.md              # 5 种开场策略 + 模板 + 真实案例
    └── gap-patterns.md               # 8 种 Gap 模板 + 避坑清单
```

---

## License

MIT © [flycalm](https://github.com/flycalm)
