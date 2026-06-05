---
name: write-academic-paper
description: Draft, revise, outline, or evaluate Chinese academic and graduate research papers by section, including abstracts, introductions, related work, methods, experiments/results, discussion, conclusions, references, acknowledgements, and declarations. Use when the user asks how to write a thesis or paper, wants section structure, paragraph drafts, logic checks, reviewer-style revisions, or wants research materials turned into polished Chinese academic prose.
---

# Write Academic Paper

## Core Use

Use this skill to help write, revise, diagnose, or outline Chinese academic papers. Ground every output in the user's actual research problem, method, data, experiments, and results. If key facts are missing, ask only for the minimum needed information or draft with explicit placeholders such as `[数据集名称]`, `[核心指标]`, and `[提升幅度]`.

Do not invent experimental results, datasets, references, funding, ethics approval, code availability, or author contributions. When the user asks for a polished section without enough evidence, provide a fill-in draft and mark unsupported claims clearly.

## Workflow

1. Identify the target task: full-paper outline, single-section draft, section revision, logic diagnosis, or style polishing.
2. Identify the target section: abstract, introduction, related work, methods, experiments/results, discussion, conclusion, or post-text declarations.
3. Collect the minimum research context: research problem, existing-method limitations, proposed method, main modules, datasets, metrics, comparison results, ablation findings, application value, and limitations.
4. Load `references/section-guides.md` when detailed section logic, common structures, or cautions are needed.
5. Draft or revise with a clear chain: research problem -> existing gap -> proposed work -> evidence -> meaning.
6. Check whether each claim is supported by methods, experiments, citations, or user-provided facts.
7. Return the result in the form the user asked for: outline, paragraph draft, rewritten section, checklist, or reviewer-style comments.

## Section Strategy

- Abstract: compress the paper into background, problem, method, results, and conclusion. Include metrics only when provided.
- Introduction: build necessity. Move from importance, to existing work, to limitations, to this paper's contribution.
- Related work: organize literature by technical route or research focus, then show unresolved gaps and this paper's position.
- Methods: explain what the paper does, not general textbook background. Define input/output, framework, modules, key improvements, and output process.
- Experiments/results: prove effectiveness through settings, comparison, ablation, parameter or robustness analysis, visualization, complexity, and summary.
- Discussion: interpret results. Explain why results occur, compare with prior work, state significance, and admit limitations.
- Conclusion: summarize the research problem, work, main findings, significance, and concise future work without adding new facts.
- References/declarations: follow the target journal, conference, or school format; keep transparency items factual.

## Revision Rules

For diagnosis or editing, first identify the main weakness before rewriting:

- Logic gap: missing transition between problem, gap, method, and evidence.
- Evidence gap: claims are stronger than the reported experiment or citation support.
- Structure gap: content belongs in another section, or the section is missing a standard role.
- Academic tone issue: wording is too absolute, promotional, colloquial, or vague.
- Repetition issue: abstract, conclusion, and discussion repeat the same sentences instead of serving distinct roles.

When rewriting, preserve the user's technical meaning. Improve order, precision, transitions, and academic tone. Avoid overstating with phrases equivalent to "彻底解决"; prefer measured claims such as "提供了一种有效思路" or "在一定程度上改善".

## Output Patterns

For "帮我写": produce a section draft with placeholders for missing facts, followed by a short list of information needed to finalize it.

For "怎么写": provide the section purpose, recommended paragraph structure, what to include, and common mistakes.

For "帮我改": give a brief diagnosis, then a revised version, then note any claims that still need data or citation support.

For "列提纲": provide a paper-level or section-level outline using the standard order: abstract, introduction, related work, methods, experiments/results, discussion, conclusion, references/declarations.

For "审稿人视角": focus on necessity, novelty, method clarity, experimental fairness, ablation completeness, limitation honesty, and whether conclusions follow from results.
